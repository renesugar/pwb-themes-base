<template>
  <v-app light>
    <v-toolbar class="white">
      <v-toolbar-title v-text="title"></v-toolbar-title>
    </v-toolbar>
    <v-toolbar>
      <v-toolbar-title>Title</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-side-icon  class="hidden-md-and-up"></v-toolbar-side-icon>
      <v-toolbar-items class="hidden-sm-and-down">
        <template v-for="item in displaySettings.top_nav_links">
          <v-btn :to="{path: item.target_path}" exact flat>{{item.link_title}}</v-btn>
        </template>
      </v-toolbar-items>
    </v-toolbar>
    <v-expansion-panel>
      <v-expansion-panel-content>
        <v-card>
          <v-card-text>tttt</v-card-text>
        </v-card>
      </v-expansion-panel-content>
    </v-expansion-panel>
    <v-content>
      <router-view/>
      <v-footer class="blue darken-2">
        <v-layout row wrap align-center>
          <v-flex xs12>
            <div class="white--text ml-3">
              Powered with
              <v-icon class="red--text">favorite</v-icon>
              by <a class="white--text" href="https://vuetifyjs.com" target="_blank">PropertyWebBuilder</a>
            </div>
          </v-flex>
        </v-layout>
      </v-footer>
    </v-content>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [{
        icon: 'bubble_chart',
        title: 'Inspire'
      }],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'PropertyWebBuilder'
    }
  },
  name: 'App',
  components: {},
  mounted: function() {
    this.$store.dispatch('loadSettings')
  },
  computed: {
    displaySettings() {
      return this.$store.state.displaySettings
    },
  },
}

</script>
