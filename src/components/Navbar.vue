<template>
    <nav>

        <v-toolbar dark flat app>
          <v-toolbar-side-icon @click="drawer= !drawer"></v-toolbar-side-icon>
          <v-toolbar-title class="text-uppercase">
              <span class="font-weight-light">Todo</span>
               <span>Man</span>
          </v-toolbar-title>
          <v-spacer></v-spacer>
           <v-menu offset-y>
               <v-btn flat slot="activator" color="grey">
                 <v-icon left>expand_more</v-icon>
                 <span>Menu</span>
               </v-btn>
               <v-list>
                   <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
                     <v-link-tile-text>
                         {{link.text}}
                     </v-link-tile-text>
                   </v-list-tile>
               </v-list>
           </v-menu>
          <v-btn flat color="grey">
              <span>Sign out</span>
              <v-icon right>exit_to_app</v-icon>
          </v-btn>
        </v-toolbar>
        <v-navigation-drawer v-model="drawer" app class="son white--text">
            <v-layout column align-center>
               <v-flex class="mt-5">
                 <v-avatar size="100">
                   <img src="/icons8-avatar-480.png" alt="">
                 </v-avatar>
                 <p class="white--text subheading mt-1">Hack Dew</p>
               </v-flex>
               <v-flex class="mt-2 mb-2">
                   <PopUp />
               </v-flex>
            </v-layout>
           <v-list>
              <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
                <v-list-tile-action>
                    <v-icon class="white--text">{{link.icon}}</v-icon>
                </v-list-tile-action>
               <v-list-tile-title>
                   <v-list-title-content>
                       <v-list-title-title class="white--text">{{link.text}}</v-list-title-title>
                   </v-list-title-content>
               </v-list-tile-title>
              </v-list-tile>
           </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
    import PopUp from "./PopUp"
    export default {
        components: {PopUp},
        data (){
            return{
                drawer: false,
                links: [
                    {icon: "dashboard", text:"Dashboard", route:"/"},
                    {icon: "folder", text:"My Projects", route:"/projects"},
                    {icon: "person", text:"Team", route:"/team"}
                ]
            }
        }
    }
</script>
