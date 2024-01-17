<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      class="d-block d-md-none"
      disable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(route, i) in routes"
          :key="i"
          :to="route.to"
          router
          exact
        >
          <v-list-item-content>
            <v-list-item-title>{{ route.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="d-block d-md-none"
      />
      <div class="d-none d-md-block">
        <v-btn
          v-for="(route, i) in routes"
          :key="i"
          :to="route.to"
          :ripple="false"
          ref="link"
          plain
        >
          {{ route.title }}
        </v-btn>
      </div>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      drawer: false,
      routes: [
        { title: 'Home', to: '/' },
        { title: 'Work Experience', to: '/work-experience' },
        { title: 'Projects', to: '/projects' },
        { title: 'Contact Me', to: '/contact-me' },
      ],
    }
  },
}
</script>
