<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span>Web</span>
      <span class="green--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="project.dialog"
        lazy
        max-width="1000"
        v-for="project in projects"
        :key="project.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover flat color="transparent">
              <v-img
                :src="project.poster"
                :alt="project.title"
                height="230"
                lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
              ></v-img>
              <v-card-title primary-title class="justify-center">{{project.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="project.dialog">
          <v-img :src="project.poster"></v-img>
          <v-card-text>
            <h3 class="headline mb-0">
              <span>Technology</span>
            </h3>
            <v-chip color="green" text-color="white">{{project.tech.tech1}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech2}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech3}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech4}}</v-chip>
          </v-card-text>
          <v-card-actions>
            <v-btn flat large dark color="green" :href="project.git" target="_blank">
              <v-icon left>fab fa-github</v-icon>GitHub
            </v-btn>
            <v-btn large flat dark color="green" :href="project.demo" target="_blank">
              <v-icon left>fas fa-desktop</v-icon>Demo
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: 'Web Portfolio',
    titleTemplate: '%s ← Anushasan',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          "Anushasan Poudel's portfolio "
      },
      { charset: 'utf-8' },
      { property: 'og:title', content: 'Anushasan Poudel' },
      { property: 'og:site_name', content: 'Anushasan Poudel' },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://anushasanpoudel.com.np' },
      {
        property: 'og:image',
        content: 'https://i.imgur.com/5i7JHvu.png'
      },
      {
        property: 'og:description',
        content:
          'Anushasan Poudel Web Portfolio Vue Vue.js Nuxt Nuxt.js HTML CSS Vuetify Axios  JavaScript Web Developer Front-End Frontend Designer App Responsive'
      }
    ]
  },
  data () {
    return {
      dialog: false,
      projects: [
        {
          dialog: false,
          title: 'This Site',
          git: 'https://github.com/BeingAnushasan/anushasan-portfolio-vue.git',
          demo: 'https://anushasanpoudel.com.np',
          tech: {
            tech1: 'VUE',
            tech2: 'JavaScript',
            tech3: 'HTML',
            tech4: 'FormSpree'
          },
          poster: 'https://i.imgur.com/MXk1Zyc.png'
        }
      ]
    }
  }
}
</script>

<style  scoped>
</style>
