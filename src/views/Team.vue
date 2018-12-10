<template>
  <div class="team">
    <h1 class="subheading grey--text my-4">Team</h1>
    <v-container class="my-5">
      <v-layout row wrap>
         <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
           <v-card flat class="text-xs-center ma-3">
             <v-responsive class="pt-4">
                <v-avatar size="100" class="grey lighten-2">
                  <img :src="person.avatar" alt="">
                </v-avatar>
             </v-responsive>
             <v-card-text>
               <div class="subheading">{{person.name}}</div>
               <div class="grey--text">{{person.role}}</div>
             </v-card-text>
             <v-card-actions>
               <v-btn flat color="red">
                 <v-icon small left>message</v-icon>
                 <span>Message</span>
               </v-btn>
             </v-card-actions>
           </v-card>
         </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>

  export default {
    data(){
      return{
        team:[
          {name:"John Smith", role:"Software Engineer", avatar:"/icons8-administrator-male-480.png"},
          {name:"Ackah Web", role:"Web Developer", avatar:"/icons8-andorian-head-480.png"},
          {name:"John Smith", role:"DevOp Engineer", avatar:"/icons8-avatar-480.png"},
          {name:"Bruce Wayne", role:"Content Writer", avatar:"/icons8-rick-sanchez-480.png"},
          {name:"Don Nature", role:"Data Science", avatar:"/icons8-morty-smith-480.png"},
        ]
      }
    }
  }
</script>
