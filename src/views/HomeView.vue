<template>
  <v-theme-provider class="pa-10" theme="dark" with-background>
     <v-sheet class="pa-12 text-center bg-surface-variant rounded-pill" color="grey-darken-3">
        <h1> 웹소설 사이트 </h1>
        <div class="d-flex text-center justify-center ga-2">
                  <v-hover v-slot:default="{ isHovering, props }"> 
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
                          </v-chip>
              
           
        </div>
     </v-sheet>

     <v-sheet class="mt-3 pa-5" color="grey-darken-4">
        Body
     </v-sheet>

  </v-theme-provider>
</template>

<script setup>

</script>
