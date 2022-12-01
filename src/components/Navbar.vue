<template>
<div>
    <v-navigation-drawer app temporary v-model="sideNav">
        <v-list>
        <v-list-tile
        v-for="(link, i) in links"
        :key="i"
        :to="link.url"
        >
        <v-list-tile-action>
            <v-icon left>{{ links.icon }}</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
        <v-list-tile-title v-text="links.title"></v-list-tile-title>
        </v-list-tile-content>
        </v-list-tile>
        </v-list>
    </v-navigation-drawer>
        <v-toolbar app dark color="primary">
            <v-app-bar-nav-icon @click="sideNav = !sideNav"></v-app-bar-nav-icon>
            <v-toolbar-title>Online Store</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
                <v-btn 
                depressed dark color="primary"
                >
                    <v-icon left>mdi-account-box</v-icon>
                    Link One</v-btn>
    </v-toolbar-items>
        </v-toolbar>
            <v-content>

                <router-view></router-view>

            </v-content>

</div>
</template>

<script>
export default {
  data () {
    return {
      sideNav: false,
      links: [
        { title: 'Login', icon: 'mdi-account-box', url: '/login' }
      ]
    }
  }
}
</script>
