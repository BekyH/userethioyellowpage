<template>
    <v-container>
      
      <v-flex xs6 >
       
      <v-select
         
        :items="options"
        v-model="selected"
        
        label="select city"
        single-line
      
      ></v-select>
     
       <v-btn v-if="selected==='Hawassa'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getHawassa">
              view</v-btn> 
          <v-btn v-if="selected==='Addis Ababa'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getAddis">
              view</v-btn> 
                <v-btn v-if="selected==='Adama'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getAdama">
              view</v-btn> 
                <v-btn v-if="selected==='Bishoftu'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getBishoftu">
              view</v-btn> 
                <v-btn v-if="selected==='Gonder'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getGonder">
              view</v-btn> 
              <v-btn v-if="selected==='Durame'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getDurame">
              view</v-btn> 
              <v-btn v-if="selected==='Bahirdar'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getBahirdar">
              view</v-btn> 
      </v-flex>
      
        <div class="google-map" :id="mapName"></div>
    
    </v-container>
</template>

<style scoped>
.google-map {
  width: 1250px;
  height: 900px;
  margin: 0 auto;
  background: gray;
}
</style>
<script>

export default {
  name: 'google-map',
  props: ['name'],
  data: function () {
    return {
      mapLoaded: false,
      options:[
        'Addis Ababa',
        'Hawassa',
        'Adama',
        'Gonder',
        'Bishoftu',
        'Durame',
        'Bahirdar'
        
      ],
      selected:'Addis Ababa',
      mapName: this.name + "-map",
      markerCoordinates: [{
        latitude: 7.0504,
        longitude: 38.4955
      }, {
        latitude: 9.005401,
        longitude: 38.763611
      }, {
        latitude:9.1450,
        longitude: 40.4897
      }],
      map: null,
      bounds: null,
      markers: []
    }
  },
  methods:{
    getHawassa(){
      
       const element = document.getElementById(this.mapName)
       
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(7.0504,38.4955)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getAddis(){
       const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(9.005401,38.763611)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getMekelle(){
   const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(13.497402,39.470737)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getAdama(){
const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(8.514477,39.269257)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getBishoftu(){
      const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(8.734650,39.008533)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getGonder(){
      const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(12.600000,37.466667)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getDurame(){
      const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(7.2333324,37.8833298)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    },
    getBahirdar(){
      const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(11.59364,37.39077)
    }
    const map = new google.maps.Map(element, options);
    map.getDetails;
    }
    }

  
  // mounted: function () {
  //   // this.bounds = new google.maps.LatLngBounds();
   
  
  //   // const mapCentre = this.markerCoordinates[0]
  //   // const options = {
  //   //   center: new google.maps.LatLng(mapCentre.latitude, mapCentre.longitude)
  //   // }
  //   // this.map = new google.maps.Map(element, options);
  //   // this.markerCoordinates.forEach((coord) => {
  //   //   const position = new google.maps.LatLng(coord.latitude, coord.longitude);
      
  //   //   const marker = new google.maps.Marker({ 
  //   //     position,
        
  //   //     map: this.map
  //   //   });
  //   // this.markers.push(marker)
  //   //   this.map.fitBounds(this.bounds.extend(position))
  //   //   this.map.getDetails();
  //   // });
  // }
};


// key = 'AIzaSyBnvRgsyru36vmM7Hz1LuMQmqdHtkag7sI'; google map api key
</script>
