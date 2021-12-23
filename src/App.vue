<template>
<section>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
 <!-- <HelloWorld msg="Welc ome to Your Vue.js App"/> -->
  <h2>my friends</h2>
  </section>
<friend-contact
v-for ="friend in friends"
:key="friend.id"
:id="friend.id"
 :name="friend.name"
 :phone-number="friend.phone"
 :email-address="friend.address"
 :is-favourite="friend.isFavourite"
 @toggle-contact="toggleFavouriteStatus"
></friend-contact> 
<!-- <friend-contact
 name="adelina gomez"
 phone-number="64568522"
 email-address="adelina gomez@gmail.com"
 is-favourite = "0"
></friend-contact>  -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
   data(){
        return{
           
            friends : [
              {
                  id : 'manual',
                  name : 'priyanka saha',
                  phone: '89652347',
                  email : 'sahae455@gmail.com',
                  isFavourite: true
              },
               {
                  id : 'manual',
                  name : 'adelina gomez',
                  phone: '64568522',
                  email : 'adelina gomez@gmail.com',
                  isFavourite: false
              },
               
            ]

        };
    },
    methods :{
      toggleFavouriteStatus(friendId){
       const identifiredFriend = this.friends.find( 
         (friend) => friend.id === friendId)
         ;
       identifiredFriend.isFavourite = !identifiredFriend.isFavourite;
      },
    },

};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>