<template>
 <v-app>


  <v-navigation-drawer app
  color="blue"
  dark
  temporary
  v-model="drawer"
   v-for="link of links"
         :key="link.title"
   :to="link.url">
           <v-divider></v-divider>

     
        <v-list-item
         v-for="link of links"
         :key="link.title"
         :to="link.url"
        >
          <v-list-item-icon>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{link.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      

          

  </v-navigation-drawer>

  <v-app-bar app color="blue" dark>
  
    
      <v-app-bar-nav-icon
      class="hidden-md-and-up"
      @click="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <v-toolbar-title>Title</v-toolbar-title>

      <v-spacer></v-spacer>
     <v-toolbar-items
     class="hidden-sm-and-down"
     >
     
      <v-btn
      color="blue"
      v-for="link of links"
      :key="link.title"
      :to="link.url">{{link.title}}
        <v-icon right>{{link.icon}}</v-icon>
      </v-btn>

      
     </v-toolbar-items>
      
   
    
  </v-app-bar>

  <!-- Sizes your content based upon application components -->
  <v-content>

    <!-- Provides the application the proper gutter -->
    <v-container fluid>

      <!-- If using vue-router -->
      <router-view></router-view>
    </v-container>
  </v-content>

  <v-footer app>
    <!-- -->
  </v-footer>
</v-app>
</template>

<script>

export default {
  data () {
    return {
      drawer:false,
      links:[
        {title: 'Login', icon: 'mdi-lock', url: '/login'},
        {title: 'Registration', icon: 'mdi-face', url: '/registration'},
        {title: 'Orders', icon: 'mdi-bookmark', url: '/orders'},
        {title: 'New ad', icon: 'mdi-note', url: '/new'},
        {title: 'My ads', icon: 'mdi-star', url: '/list'}
      ]
    }
  }
}
 
</script>
