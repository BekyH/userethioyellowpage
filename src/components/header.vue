<template>
<header>

   
       
                
               <v-card color="#333333">
     <v-toolbar app color="deep purple darken-4" dark>
           
            
            <v-toolbar-title offset-2>{{title}}</v-toolbar-title>
         
         
            <v-flex  md6 offset-2>
                <v-toolbar-items >
            <v-btn text to="/home"><v-icon>fas fa-home</v-icon><span>Home</span></v-btn> 
             
             
            
           
         
    
    <v-btn text to="/aboutus"><v-icon>fas fa-info</v-icon><span>About us</span></v-btn>
                </v-toolbar-items>
            </v-flex>
           
        </v-toolbar> 
       
   
    
    
   
    
  </v-card>
  
       
       
   </header>
   
</template>
<script>
export default {
    data(){
        return {
              title:'Yellow Page of Ethiopia',
      
  }
      
    
    
}

}
</script>
<style>
.group {
  display: flex;
  flex: 1;
  justify-content: space-around;
}

</style>



