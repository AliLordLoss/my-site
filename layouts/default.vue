<template>
  <v-app>
    <v-app-bar fixed app>
      <v-btn plain ref="link" to="/" :ripple="false"> Home </v-btn>
      <v-btn plain ref="link" to="/work-experience" :ripple="false">
        Work Experience
      </v-btn>
      <v-btn plain ref="link" to="/projects" :ripple="false"> Projects </v-btn>
      <v-btn plain ref="link" to="/contact-me" :ripple="false">
        Contact Me
      </v-btn>
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
}
</script>
