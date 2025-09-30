<template>
    <h1> 웹소설 사이트 </h1>
    <div class="d-flex text-center justify-center ga-2">
        <v-chip-group>
          <template v-for=" item in category1" :key="item.kindCd">
              <v-hover v-slot:default="{ isHovering, props }"> 
                <v-chip class="ma-2" 
                        prepend-icon="mdi-account-circle"
                        v-bind="props"
                        :color="isHovering ? 'red' : 'orange' " 
                        > 
                    {{ item.kindName }}
                </v-chip>
              </v-hover>
          </template>
          <!-- -------- -->
          <!-- <v-hover v-slot:default="{ isHovering, props }"> 
            <v-chip class="ma-2" 
                    prepend-icon="mdi-account-circle"
                    v-bind="props"
                    :color="isHovering ? 'primary' : 'indigo' " 
                    > 
                환타지
            </v-chip>
          </v-hover>
          <v-hover v-slot:default="{ isHovering, props }">  
            <v-chip class="ma-2" append-icon="mdi-star"
                    v-bind="props"
                    :color="isHovering ? 'red' : 'orange' " 
            >
                무 협
            </v-chip>
          </v-hover>
          <v-hover v-slot:default="{ isHovering, props }">  
            <v-chip class="ma-2" append-icon="mdi-cake-variant"
                    v-bind="props"
                    :color="isHovering ? 'red' : 'black' " 
            >
                로맨스
            </v-chip>
          </v-hover>
            <v-chip
                :model-value="true"
                class="ma-2"
                close-icon="mdi-delete"
                color="teal"
                prepend-icon="mdi-checkbox-marked-circle"
                closable
            >
                랭킹
            </v-chip>
            <v-chip
                class="ma-2"
                color="green"
            >
                <template v-slot:prepend>
                    <v-avatar
                    class="green-darken-4"
                    >
                    1
                    </v-avatar>
                </template>
                신작
             </v-chip>  -->
        </v-chip-group>
    </div>
</template>

<script setup>
  import { ref, onMounted } from 'vue';
  import axios from 'axios'
 
  const category1 = ref([
                        //   {kindCd: '01', kindName: '판타지'},
                        //   {kindCd: '02', kindName: '무협'},
                        //   {kindCd: '03', kindName: '로맨스'},
                        //   {kindCd: '04', kindName: '스릴러'},
                        //   {kindCd: '05', kindName: '미스테리'},
                        
                        ])

  onMounted( () => {
      console.log("HomeView > onMounted Called ")
      fetchCategoryData01();
  })

    async function fetchCategoryData01() {
       console.log("Homeview > fetchCategoryData01 Called ")

       await axios.get("http://localhost:9091/category02/list")
       .then( (response) => {
           console.log( "response ==>", response.data )
           category1.value = response.data
       })
       .catch( err => {
           console.log( "error ==> ", err.data )
       })
       .then()

   }

</script>

<style scoped>

</style>