<template>
  <v-app>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
// import Appbar from '~/components/Appbar'
export default {
  data() {
    return {
      clipped: true,
      sidebar: false,
      fixed: true,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: { eng: 'Nuxt image gallery' }
    }
  }
}
</script>
