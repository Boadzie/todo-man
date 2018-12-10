<template>
  <div class="dashboard">
    <h1 class="subheading grey--text my-4">Dashboard</h1>
    <v-container class="my-5">
      <v-card flat class="pa-3" v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="cation grey--text">Project Title</div>
            <div>{{project.title}}</div>
          </v-flex>
           <v-flex xs6 sm4 md2>
            <div class="cation grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>
           <v-flex xs6 sm4 md2>
            <div class="cation grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>
           <v-flex xs2 sm4 md2>
              <div class="right">
               <v-chip small :class="`${project.status} white--text caption my-2`">
                 {{project.status}}
               </v-chip>
              </div>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        projects:[
           {title:"Learn Data Science", person:"man san", due: "32th Jan 2019", status:"ongoing", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Cool off man", person:"man san", due: "32th Jan 2019", status:"overdue", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Master the cooky", person:"man san", due: "32th Jan 2019", status:"complete", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Learn Vue", person:"man san", due: "32th Jan 2019", status:"ongoing", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Call her now", person:"man san", due: "32th Jan 2019", status:"complete", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."}
        ]
      }
    }
  }
</script>

<style>
  .project.complete{
    border-left: 4px solid #3cd1cd;
  }
  .project.overdue{
    border-left: 4px solid orange;
  }
  .project.ongoing{
    border-left: 4px solid tomato;
  }

  .v-chip.complete{
    background:  #3cd1cd;
  }
  .v-chip.overdue{
    background:  orange;
  }
  .v-chip.ongoing{
    background:  tomato;
  }
</style>
