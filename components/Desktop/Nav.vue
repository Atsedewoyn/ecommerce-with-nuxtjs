<template>
  <div>
    <v-app-bar
      color="blue"
      height="80"
      class="el"
      :style="{
        padding: $vuetify.breakpoint.mdAndUp ? '0px 100px' : '',
      }"
      app
    > 
      <v-toolbar-title
        @click="$router.push('/')"
        class="text-md-h5 font-weight-bold pointer"
        >BDU-Furniture</v-toolbar-title
      >
      <v-spacer />
      <v-list class="d-flex align-center">
        <v-list-item link v-for="(menu,index) in menus" :key="index" :to="menu.route">
          <v-list-item-title>{{menu.title}}</v-list-item-title>
        </v-list-item>
        <v-btn text><v-icon>fas fa-search</v-icon></v-btn>
        <v-btn outlined color="success">Get Started </v-btn>
      </v-list>
      <v-btn nuxt to="/products" class="mr-md-2" icon>
        <v-icon size="20">mdi-store-outline</v-icon>
      </v-btn>
      <v-badge
        v-if="$store.state.cart.cart.length > 0"
        overlap
        :content="`${$store.state.cart.cart.length}`"
      >
        <v-btn nuxt to="/cart" icon>
          <v-icon size="20">mdi-cart-outline</v-icon>
        </v-btn>
      </v-badge>
      <v-btn v-else nuxt to="/cart" icon>
        <v-icon size="20">mdi-cart-outline</v-icon>
      </v-btn>
      <v-divider vertical class="mx-md-5 mx-2" />
      <v-btn @click="toggleTheme" icon>
        <v-icon size="20">mdi-brightness-7</v-icon>
      </v-btn>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data(){
     return{
      menus:[
        {title:'Home',     route:'/#'},
        {title:'About Us', route:'About-us'},
        {title:'Products', route:'Products'},
        {title:'Contact',  route:'contact'},
        
      ]
    
     }
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    },
  },
};
</script>

<style></style>
