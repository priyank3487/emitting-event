<template>
<li>
    <h2>{{ name }} {{ isFavourite ? '(Favourite)' : '' }}</h2>
    <button @click="toggleFavourite">Toggle Favourite</button><br>
    <button @click="toggledetails">{{ detailsAreVisible ? 'hide' : 'show' }} details</button>
    <ul v-if="detailsAreVisible">
        <li>
            <strong>phone:</strong>
            {{ phoneNumber }}
            </li>
        <li>
            <strong>email:</strong>
            {{ emailAddress }}
        </li>
        
    </ul>
</li>
</template>
<script>
export default{
    // props : ['name','phoneNumber','emailAddress','isFavourite' ],
    props : {
        id : {
        type: String,   
        required: true
        },
    name : {
        type: String,
        required: true
    },
    phoneNumber :{
         type: String,
        required : true  
         },
    emailAddress :{
         type: String,
        required : true  
         },
    isFavourite :{
       type : Boolean,
       required : false,
       default : false  
    } ,    
    },
      data(){
          return{
              detailsAreVisible : false
            //    friend : 
            //   {
            //       id : 'manual',
            //       name : 'priyanka saha',
            //       phone: '89652347',
            //       email : 'sahae455@gmail.com'
            //   },
            //   friendIsFavourite : this.isFavourite,
          };
      },
      methods :{
              toggledetails(){
                  this.detailsAreVisible = !this.detailsAreVisible ;
              },
              toggleFavourite(){
                //   if(this.friendIsFavourite === '1'){
                //       this.friendIsFavourite = '0';
                //       }else{
                //           this.friendIsFavourite = '1';
                //       }
                // this.friendIsFavourite = !this.friendIsFavourite ;
                this.$emit('toggle-contact', this.id);
              }
      }
}
</script>