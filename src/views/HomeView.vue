<template>
  <v-theme-provider class="pa-10" theme="dark" with-background>
     <v-sheet class="pa-2 text-center bg-surface-variant rounded-pill" 
              color="grey-darken-3"
     >
        <HeaderView />
     </v-sheet>

     <v-sheet class="mt-1 pa-2 pl-12 pr-12" color="grey-darken-4" rounded="xl">
        <v-row >
          <v-col cols="12" md="2" sm="2" class="text-end" align-self="end" bg-color="red">
             <v-select
              v-model="selectSrchKind"
              :items="srchKindItems"
              item-title="srchKindName"
              item-value="srchKindCd"
              label="선택"
              persistent-hint="" 
              :hint="`${selectSrchKind.srchKindCd}, ${selectSrchKind.srchKindName}`"
              return-object
              single-line
              density="compact"
              variant="outlined"
              rounded="xl"  
                :list-props="{ bgColor: 'purple' }"
              item-color="yellow"
              @change="testSelectChange"
            ></v-select>  
            <!-- <v-select
                  :items="srchKindItems"
                  item-text="srchKindName"
                  item-value="srchKindCd"
                  label="아이템"
                  rounded="xl"
                  variant="outlined"
                >
                  <template v-slot:selection="{ item }">
                    <span class="d-flex justify-center" style="width: 100%;">
                      {{ item.text }}
                    </span>
                  </template>
            </v-select> -->
          </v-col>
          <v-col>
              <v-text-field
                              v-model="first"
                              color="primary"
                              label="책 제목 혹은 작가를 입력하세요"
                              variant="underlined"
              /> 
          </v-col>
          <v-col cols="12" md="2" sm="2" >
               <v-btn rounded="xl" size="x-large" elevation="4" block max-width="10" 
                      color="medium-emphasis" outlined >검 색</v-btn>
          </v-col>
        </v-row> 
     </v-sheet>
     <v-sheet class="mt-1 pa-5" color="grey-darken-4">
        <FantageView />
     </v-sheet>

      <v-sheet class="mt-3 pa-5" color="grey-darken-4">
        <RomansView />
     </v-sheet>

     <v-sheet class="mt-3 pa-5" color="grey-darken-4">
        <MisteryView />
     </v-sheet>

  </v-theme-provider>
</template>

<script setup>
import { ref, shallowRef } from 'vue';
import HeaderView from '@/views/HeaderView.vue';
import FantageView from '@/views/FantageView.vue';
import RomansView  from '@/views/RomansView.vue';
import MisteryView from './MisteryView.vue';

  const selectSrchKind = shallowRef({ srchKindCd: '01', srchKindName: '전체' })
  const srchKindItems = ref([ {srchKindCd: '01', srchKindName: '전체'}, 
                             {srchKindCd: '02', srchKindName: '책 제목'}, 
                             {srchKindCd: '03', srchKindName: '작 가'}]
                       )

  function testSelectChange(event) {
     console.log( "testSelectChange -->", event )
  }                       
</script>
