<template>
    
        <v-container>
            <v-layout>
                <v-flex offset-1 md9>
        <v-card>
            <v-card-title>
                Gallery
            </v-card-title>
            <v-img v-for="(img,index) in images" :key="index" :src="img.filename" alt="images"/>

            </v-card>
                </v-flex>
            <v-spacer></v-spacer>
        
            
            </v-layout>
            </v-container>
    
</template>
<style>
.text-field{
    width: 70%;
}
</style>
<script>
import axios from 'axios';
const Api = 'http://localhost:3000/api/images/container/upload';
const Api2 = 'http://localhost:3000/api/images/container/files';
export default {
    data(){
      return {
        file: '',
        images:[],
        img:{
            filename:''
        }
      }
    },

    methods: {
      /*
        Submits the file to the server
      */
      submitFile(){
        /*
                Initialize the form data
            */
            let formData = new FormData();

            /*
                Add the form data we need to submit
            */
            formData.append('file', this.file);

        /*
          Make the request to the POST /single-file URL
        */
            axios.post( Api,
                formData,
                {
                headers: {
                    'Content-Type': 'multipart/form-data'
                }
              }
            ).then(function(){
          console.log('SUCCESS!!');
        
        })
        .catch(function(){
          console.log('FAILURE!!');
        });
        
      },

      /*
        Handles a change on the file upload
      */
      handleFileUpload(){
        this.file = this.$refs.file.files[0];
      },
      getImages(){
         axios.get(Api2)
        
         .then((res)=>{
             let reader = new FileReader();
             this.images = reader.readAsDataURL(res.data);
         });

    },
    logImages(){
        console.log(this.images.length);
    }
   
    }

    
    

  }
</script>
