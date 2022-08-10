<template>
  <v-app id="inspire">
   <Header @drawerEvent="drawer = !drawer" />
   <SideBar :drawer="drawer" />

    <v-main>
      <v-container
        class="py-8 px-6"
        fluid
      >
       <v-row>
        <v-col lg="9">
              <v-data-table
     caption="Recent Orders"
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-2"
  >
  <template v-slot:item.action>
    <v-btn color="success" class="mr-0" >View</v-btn>
  </template>
  </v-data-table>
        </v-col>
     </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue';
import SideBar from '~/components/SideBar.vue';

  export default {
    layout: "adminlayout",
     data(){
            return{
        headers: [
          {
            text: 'Catagories',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: 'Total Orders', value: 'total' },
          { text: 'Action', value: 'action' },
        ],
        desserts: [
          {
            name: 'Tables',
            total: 15,
            
          },
          {
            name: 'Beds',
            total: 23,
          },
          {
            name: 'chiars',
            total: 40,
          },
          {
            name: 'windows',
            total: 305,
          },
          {
            name: 'Doors',
            total: 10,
            
          },
          {
            name: 'Lockers',
            total: 12,
            
          },
          {
            name: 'Drawer',
            total: 8 ,
            
          },
          
        ],
            };
        },
    components: { Header, SideBar}
}
</script>