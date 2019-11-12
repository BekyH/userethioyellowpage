<template>


    <v-container>
        <v-content >
      <v-container fluid style="padding-top:10px; padding-left:50px;padding-right:50px fixed">
          <v-layout align-center color="white">
         <v-flex xs6>
        <v-subheader style="font-size:20px; margin-left:100px;">select companies Category</v-subheader>
      </v-flex>
    <v-flex xs3 >
       
      <v-select
         
        :items="options"
        v-model="selected"
        
        label="select category"
        single-line
      
      ></v-select>
    
      </v-flex>
      <v-flex>
      <v-btn v-if="selected==='Bank and finanicials'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getBank">
              view</v-btn> 
      <v-btn v-if="selected==='Industries'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getIndustry">
              view</v-btn> 
   <v-btn v-if="selected==='Transport'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getTransport">
              view</v-btn> 
               <v-btn v-if="selected==='Health and medicine'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getMedicine">
              view</v-btn>
              <v-btn v-if="selected==='Construction'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getConstruction">
              view</v-btn> 
              <v-btn v-if="selected==='Communication'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getCommunication">
              view</v-btn>
              <v-btn v-if="selected==='Technology'"
              align-center
              color="primary"
              style="margin-bottom:15px; margin-left:20px;"
              @click="getTechno">
              view</v-btn>
              <v-btn v-if="selected==='Toursim'"
              align-center
              color="primary" 
              style="margin-bottom:15px; margin-left:20px;"
              @click="getToursim">
              view</v-btn>
      </v-flex>
  </v-layout>
        
          
        <div v-if="selected==='Bank and finanicials'" >
          <v-layout row wrap>
                <v-flex xs12 md6  v-for="(Bank,index) in Banks" :key="index">
                  <v-col cols="12">
              <v-card style="margin:10px; border-radius:15px;" >
              <v-layout row wrap>
                    <v-flex xs6 md6>
                      <v-flex class="ml-5 pt-3">
                <v-card-title >
                  <div>{{Bank.name}}</div>
              </v-card-title>
                
              
             <v-card-text class="pt-1">
               <v-icon size="18px"> fas fa-phone</v-icon>
               {{Bank.phoneNo}}
               
             </v-card-text>
               
              <v-card-text class="pt-1">
                <v-icon size="16px">fas fa-envelope</v-icon>
                    {{Bank.email}}
                  
                </v-card-text>
               <v-card-text class="pt-1">
                {{Bank.city}}
              </v-card-text>
              </v-flex>
                    </v-flex>
                    <v-flex  xs6 md5 class="pt-3">
                      <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + Bank.image"/>
                    </v-flex>
                </v-layout>
              <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click="getBankLocation(Bank)">view map</v-btn>
                </v-card-actions>
              </v-flex>
         </v-card>
                  </v-col>
                </v-flex>
          </v-layout>
            </div>
            <div v-else-if="selected==='Industries'">
              <v-layout row wrap>
                <v-flex xs12 md6  v-for="(industry,index) in Industries" :key="index">
                  <v-col cols="12">
            <v-card style="margin:10px; border-radius:15px; width:999px;" >
              <v-layout row wrap>
                  <v-flex xs6 md5>
                    <v-flex class="ml-5 pt-3">
                <v-card-title >
                  <div>{{industry.name}}</div>
              </v-card-title>
                
              
              <v-card-text class="pt-1"> <v-icon size="18px">fas fa-phone</v-icon> {{industry.phoneNo}}</v-card-text>
              <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{industry.email}}</v-card-text>
              <v-card-text class="pt-1">
                {{industry.city}}
              </v-card-text>
              </v-flex>
                  </v-flex>
                  <v-flex  xs6 md6 class="pt-3">
                    <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + industry.image"/>
                  </v-flex>
              </v-layout>
              
              <v-flex offset-9>
                <v-card-actions>
                    <v-btn color="primary" @click="getIndustryLocation(industry)">view map</v-btn>
                </v-card-actions>
              </v-flex>
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
            
            </div>
            <div v-else-if="selected==='Transport'">
              <v-layout row wrap>
                <v-flex xs12 md6  v-for="(transport,index) in transports" :key="index">
                  <v-col cols="12">
            <v-card style="margin:10px; border-radius:15px; width:999px;" >
              <v-layout row wrap>
                <v-flex xs6 md6>
                   <v-flex class="ml-5 pt-3">
                 <v-card-title >
                  <div>{{transport.name}}</div>
              </v-card-title>
                
             
                <v-card-text class="pt-1" > <v-icon size="18px">fas fa-phone</v-icon> {{transport.phoneNo}}</v-card-text>
                <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{transport.email}}</v-card-text>
              <v-card-text class="pt-1">
                {{transport.city}}
              </v-card-text>
              </v-flex>
                </v-flex>
                <v-flex xs6 md5 class="pt-3">
                    <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + transport.image"/>
                </v-flex>
              </v-layout>
              <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click="getTransLocation(transport)">view map</v-btn>
                </v-card-actions>
              </v-flex>
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
            </div>
            <div v-else-if="selected==='Health and medicine'">
              <v-layout row wrap>
                <v-flex xs12 md6  v-for="(medicine,index) in health" :key="index">
                  <v-col cols="12">
            <v-card style="margin:10px; border-radius:15px; width:999px;" >
              <v-layout row wrap>
               <v-flex xs6 md6>
                 <v-flex class="ml-5 pt-3">
                <v-card-title >
                  <div>{{medicine.name}}</div>
                  
              </v-card-title>
                 
              
             <v-card-text class="pt-1"> <v-icon size="18px">fas fa-phone</v-icon> {{medicine.phoneNo}}</v-card-text>
             <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{medicine.email}}</v-card-text>
              <v-card-text>
                {{medicine.city}}
              </v-card-text>
              </v-flex>
               </v-flex>
                <v-flex  xs6 md5 class="pt-3">
                <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + medicine.image"/>    
               </v-flex>
              </v-layout>
              <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click=" getMedicalLocation(medicine)">view map</v-btn>
                </v-card-actions>
              </v-flex>
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
             
            </div>
            <div v-else-if="selected==='Construction'">
              <v-layout row wrap>
                <v-flex xs12 md6  v-for="(constr,index) in constructions" :key="index">
                  <v-col cols="12">
            <v-card style="margin:10px; border-radius:15px; width:999px;" >
             <v-layout row wrap>
                <v-flex xs6 md5>
                  <v-flex class="ml-5 pt-3">
                <v-card-title >
                  <div>{{constr.name}}</div>
              </v-card-title>
                
              
             <v-card-text class="pt-1"><v-icon size="18px">fas fa-phone</v-icon> {{constr.phoneNo}}</v-card-text>
             <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{constr.email}}</v-card-text>
              <v-card-text class="pt-1">
                {{constr.city}}
              </v-card-text>
              </v-flex>
                </v-flex>
                <v-flex xs6 md6 class="pt-3">
                  <v-img  style="height:280px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + constr.image"/>
                </v-flex>
              </v-layout>
             <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click=" getConstrLocation(constr)">view map</v-btn>
                </v-card-actions>
              </v-flex>
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
            </div>
            <div v-else-if="selected==='Communication'">
              <v-layout row wrap>
                <v-flex xs12 md6   v-for="(comn,index) in communications" :key="index">
                  <v-col cols="12">
            <v-card style="margin:10px; border-radius:15px; width:999px;">

              <v-layout>
                <v-flex xs6 md5>
                  <v-flex class="ml-5 pt-3">
                <v-card-title >
                  <div>{{comn.name}}</div>
              </v-card-title>
                
              
             <v-card-text class="pt-1"> <v-icon size="18px">fas fa-phone</v-icon> {{comn.phoneNo}}</v-card-text>
             <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{comn.email}}</v-card-text>
              <v-card-text>
                {{comn.city}}
              </v-card-text>
               
              </v-flex>
                </v-flex>
                <v-flex xs6 md6 class="pt-3">
                  <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + comn.image"/>
                </v-flex>
              </v-layout>
               <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click="getComnLocation(comn)">view map</v-btn>
                </v-card-actions>
              </v-flex>
              
              
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
            
            </div>
            <div v-else-if="selected==='Technology'">
              <v-layout row wrap>
                <v-flex xs12 md6 v-for="(techno,index) in technologies" :key="index">
                  <v-col cols="12">
            <v-card style="margin:10px; border-radius:15px; width:999px;" >
             <v-layout>
                <v-flex xs6 md5>
                  <v-flex class="ml-5 pt-3">
                <v-card-title >
                  <div>{{techno.name}}</div>
              </v-card-title>
              
             
             <v-card-text class="pt-1"> <v-icon size="18px">fas fa-phone</v-icon> {{techno.phoneNo}}</v-card-text>
             <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{techno.email}}</v-card-text>
              <v-card-text class="pt-1">
                {{techno.city}}
              </v-card-text>
             </v-flex>
                </v-flex>
                <v-flex xs6 md7 class="pt-3">
                   <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + techno.image"/>
                </v-flex>
              </v-layout>
             <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click="getTechnoLocation(techno)">view map</v-btn>
                </v-card-actions>
              </v-flex>
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
            </div>
            <div v-else-if="selected==='Toursim'">
              <v-layout row wrap>
                <v-flex xs12 md6  v-for="(toursim,index) in toursims" :key="index">
                  <v-col cols="12">
            <v-card class="elevation-20" height='100%' style="margin:10px; border-radius:15px;" >
               <v-layout row wrap>
                <v-flex xs6 md5>
                  <v-flex class="ml-5 pt-3">
                 <v-card-title >
                  <div>{{toursim.name}}</div>
              </v-card-title>
                 
              
             <v-card-text class="pt-1"><v-icon size="18px">fas fa-phone</v-icon> {{toursim.phoneNo}}</v-card-text>
             <v-card-text class="pt-1"> <v-icon size="16px">fas fa-envelope</v-icon> {{toursim.email}}</v-card-text>
              <v-card-text class="pt-1">
                {{toursim.city}}
              </v-card-text>
               </v-flex>
                </v-flex>
                <v-flex xs6 md6 class="pt-3">
                    <v-img  style="height:250px;width:400px;" :src="'http://localhost:3000/api/containers/image/download/' + toursim.image"/>
                </v-flex>
               </v-layout>
              <v-flex offset-9>
                <v-card-actions>
                  <v-btn color="primary" @click="getTourismLocation(toursim)">view map</v-btn>
                </v-card-actions>
              </v-flex>
            </v-card>
                  </v-col>
                </v-flex>
              </v-layout>
            </div>
          
      
      </v-container>

    
    </v-content>
    </v-container>
    
</template>
<script>

const APi = 'http://localhost:3000/api/banks';
const APi2 = 'http://localhost:3000/api/industries';
const APi8 = 'http://localhost:3000/api/Health';
const APi3 = 'http://localhost:3000/api/constructions';
const APi4 = 'http://localhost:3000/api/communications';
const APi5 = 'http://localhost:3000/api/transports';
const APi6 = 'http://localhost:3000/api/technologies';
const APi7 = 'http://localhost:3000/api/tourisms';

export default {
    data(){
        return {
          clicked:false,
            selected:'Bank and finanicials',
           
             options:[
                'Bank and finanicials',
                'Industries',
                'Transport',
                'Health and medicine',
                'Construction',
                'Communication',
                'Technology',
                'Toursim'
            ],
            Banks:[],
            Bank:{
             name:'',
            phoneNo:'',
            email:'',
            city:''
    //
         },
         B:{
           name:'',
           phoneNo:'',
           email:'',
           city:''
         },
        
         
       
         industries:{
           name:'',
           phoneNo:'',
           email:'',
           city:''
         },
         ind:{
            name:'',
            phoneNo:'',
            email:'',
            city:''
         },
         Industries:[],
         transport:{
           name:'',
           phoneNo:'',
           email:'',
           city:'',
         },
        tr:{
          name:'',
          phoneNo:'',
          email:'',
          city:''
        },
         transports:[],
          Health:{
            name:'',
           phoneNo:'',
           email:'',
           city:'',
          },
         med:{
           name:'',
           phoneNo:'',
           email:'',
           city:''
         },
          health:[],
          construction:{
            name:'',
           phoneNo:'',
           email:'',
           city:'',
          },
          constr:{
            name:'',
            phoneNo:'',
            email:'',
            city:''
          },
          
            constructions:[],

            communication:{
              name:'',
           phoneNo:'',
           email:'',
           city:'',
            },
            comn:{
              name:'',
              phoneNo:'',
              email:'',
              city:''
            },
           
            communications:[],
            technology:{
              name:'',
           phoneNo:'',
           email:'',
           city:'',
            },
            techno:{
              name:'',
              phoneNo:'',
              email:'',
              city:'',
            },
            technologies:[],
            tourism:{
               name:'',
           phoneNo:'',
           email:'',
           city:'',
            
            },
            tour:{
              name:'',
              phoneNo:'',
              email:'',
              city:''
            },
           
            toursims:[],
          
            
        }
    },
    methods:{
      
         getBank(){
           fetch(APi)
                     .then(res=>res.json())
                    
                    
                    .then(res=>this.Banks=res)

                    .catch(()=>{
                      
                    })
                    
                    
                    
                },
                getIndustry(){
                  fetch(APi2)
                  .then(res=>res.json())
                    
                    
                    .then(res=>this.Industries=res);
                },
               
                getConstruction(){
                  fetch(APi3)
                  .then(res=>res.json())
                  .then(res=>this.constructions=res);
                  
                
                },
                
                getCommunication(){
                  fetch(APi4)
                  .then(res=>res.json())
                    
                    
                    .then(res=>this.communications=res);
                },
                getTransport(){
                  fetch(APi5)
                  .then(res=>res.json())
                    
                    
                    .then(res=>this.transports=res);
                },
                getTechno(){
                  fetch(APi6)
                  .then(res=>res.json())
                    
                    
                    .then(res=>this.technologies=res);
                },
                getToursim(){
                  fetch(APi7)
                  .then(res=>res.json())
                    
                    
                    .then(res=>this.toursims=res);
                },
                getMedicine(){
                  fetch(APi8)
                  .then(res=>res.json())
                    
                    
                    .then(res=>this.health=res);
                },
                getBankLocation(Bank){
                  const mapurl = "https://www.google.com/maps/search/";
                   fetch(APi + '/' + Bank.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.B = res;
                   
                   // window.location.href = mapurl + this.B.name;
                    
                    window.open(mapurl + this.B.name,'_blank');

                  })

                 // const mapurl = "https://www.google.com/maps/place";
                  
                },
                getIndustryLocation(industry){
                  const mapurl = "https://www.google.com/maps/search/";
                   fetch(APi2 + '/' + industry.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.ind = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.ind.name,'_blank');
                    

                  })
                },
                getTransLocation(transport){
                  const mapurl = "https://www.google.com/maps/search/";
                    fetch(APi5 + '/' + transport.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.tr = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.tr.name,'_blank');
                    

                  })
                },

                getMedicalLocation(medicine){
                  const mapurl = "https://www.google.com/maps/search/";
                    fetch(APi8 + '/' + medicine.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.med = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.med.name,'_blank');
                    

                  })
                },
                getConstrLocation(con){
                   const mapurl = "https://www.google.com/maps/search/";
                    fetch(APi3 + '/' + con.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.constr = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.constr.name,'_blank');
                    

                  })
                },
                getComnLocation(comn){
                   const mapurl = "https://www.google.com/maps/search/";
                    fetch(APi4 + '/' + comn.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.comn = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.comn.name,'_blank');
                    

                  })
                },
                
           getTechnoLocation(tech){
                   const mapurl = "https://www.google.com/maps/search/";
                    fetch(APi6 + '/' + tech.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.techno = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.techno.name,'_blank');
                    

                  })
                },
                 getTourismLocation(touris){
                   const mapurl = "https://www.google.com/maps/search/";
                    fetch(APi7 + '/' + touris.id)
                  .then(res=>res.json())
                  .then(res=>{
                 
                    this.tour = res;
                   
                    //window.location.href = mapurl + this.ind.name;
                    window.open(mapurl + this.tour.name,'_blank');
                    

                  })
                }

        },
        mounted(){
          if(this.selected==='Bank and finanicials'){
            this.getBank();
          }
            
          
        
          
        }

    }

</script>
