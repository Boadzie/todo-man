<template>
  <div class="projects">
    <h1 class="subheading grey--text my-4">Projects</h1>
    <v-container class="my-5">
       <v-expansion-panel>
          <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
            <div slot="header">{{project.title}}</div>
            <v-card>
              <v-card-text class="px-4 grey--text">
                <div class="font-weight-bold">due by {{project.due}}</div>
                 <div>{{project.content}}</div> 
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>
       </v-expansion-panel>
    </v-container>
  </div>
</template>

<script>

  export default {
    data (){
      return {
         projects:[
           {title:"Learn Data Science", person:"John Doe", due: "32th Jan 2019", status:"ongoing", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Cool off man", person:"Sam Fox", due: "32th Jan 2019", status:"overdue", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Master the cooky", person:"Max Fish", due: "32th Jan 2019", status:"complete", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Learn Vue", person:"Ice Cream", due: "32th Jan 2019", status:"ongoing", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Call her now", person:"Coffee Newman", due: "32th Jan 2019", status:"complete", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."},
           {title:"Learn Data Analysis", person:"John Doe", due: "32th Jan 2019", status:"ongoing", content:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."}
        ]
      }
    },
    computed:{
      myProjects(){
         return this.projects.filter(project => {
           return project.person === "John Doe"
         })
      }
    }
  }
</script>
