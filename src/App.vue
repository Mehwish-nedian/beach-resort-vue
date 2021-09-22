<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated >
      <nav>
            <img class="logo" src="./assets/images/Logo.png" alt="Logo">
            <ul>
                <li><router-link to="/home">Home</router-link></li>
                <li><router-link to="/rooms">Rooms</router-link></li>
            </ul>
      </nav>  
    </q-header>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from 'vue'
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'LayoutDefault',
  data(){
    return{
      error : null
    }
  },
  

  async created(){
      
      try{
        await this.$store.dispatch('loadRooms')
      }
      catch(error){
         this.error = error.message || 'Failed to fetch'
      }
  },

  setup () {
    return {
      leftDrawerOpen: ref(false)
    }
  }
}
</script>
<style >

*,
*::before,
*::after{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    
}

html{
    font-size: 62.5%;
    font-weight: 300;
    line-height: 1.6;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
header{
  height: 5.5rem;
}
.logo{
    height: 3.5rem;
    float: left;
    margin: 0 5rem 0 7rem;
}
header ul{
    list-style: none;
    display: flex;
}
header nav {
  width: 90%;
  margin: auto;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
header a{
    text-decoration: none;
    display: inline-block;
    color: #eee;
    padding: 0.75rem 1.5rem;
    font-size: 2rem;
    border: 1px solid transparent;
}
header li{
    margin: 0 0.5rem;
    text-decoration: none;
}

a:active,
a:hover,
a.router-link-active{
  border-bottom: 1px solid #eee;
}
</style>