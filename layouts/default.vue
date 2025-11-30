<template>
  <v-app id="inspire">
    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title style="cursor: pointer;" v-on:click="goHome">Education For All</v-app-bar-title>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      temporary
    >
      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item.value"
          :to="`/${item.value}`"
          link
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>

    <v-main class="bg-grey-lighten-2">
      <NuxtPage />
    </v-main>
  </v-app>
</template>

<script setup>
  import { ref, watch } from 'vue'
  import { useRouter } from 'vue-router'

  const items = [
    // {
    //   title: 'About Me',
    //   value: 'about-me',
    // },
    // {
    //   title: 'Research',
    //   value: 'research',
    // },
    // {
    //   title: 'Media',
    //   value: 'media',
    // },
    // {
    //   title: 'Guest Invitation',
    //   value: 'guest-invitation',
    // },
    // {
    //   title: 'Travel Updates',
    //   value: 'travel-updates',
    // },
    // {
    //   title: 'Book Appointment',
    //   value: 'book-appointment',
    // },
    // {
    //   title: 'Student Feedback',
    //   value: 'student-feedback',
    // },
    // {
    //   title: 'Testimonials',
    //   value: 'testimonials',
    // },
    // {
    //   title: 'Contact Us',
    //   value: 'contact-us',
    // },
  ]

  const drawer = ref(false)
  const group = ref(null)
  const router = useRouter()

  const goHome = ()=> {
    router.push('/');
  }

  watch(group, () => {
    drawer.value = false
  })

</script>