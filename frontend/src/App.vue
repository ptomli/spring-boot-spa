<template>
  <v-app id="app">

    <v-navigation-drawer persistent v-model="drawer" light>
      <v-list dense>
        <template v-for="item in items">
          <v-divider v-if="item.divider" class="my-4"/>
          <v-list-item v-else :key="item">
            <v-list-tile router :to="item.location">
              <v-list-tile-action>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar class="indigo">
      <v-toolbar-side-icon light @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Toolbar</v-toolbar-title>
    </v-toolbar>

    <main>
      <v-container fluid>
        <router-view/>
      </v-container>
    </main>

    <v-footer class="indigo">
      <span>© 2017</span>
    </v-footer>

  </v-app>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      drawer: true,
      items: [
        { title: 'Home', icon: 'dashboard', location: '/' }
      ]
    }
  }
}
</script>

<style>
@import '//fonts.googleapis.com/css?family=Roboto:300,400,500,700|Material+Icons'
</style>

<style scoped>
#app {

}
</style>
