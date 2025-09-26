<template>
  <v-theme-provider class="pa-10" theme="dark" with-background>
     <v-sheet class="pa-2 text-center bg-surface-variant rounded-pill" 
              color="grey-darken-3"
     >
        <HeaderView />
     </v-sheet>

     <v-sheet class="mt-1 pa-2" color="grey-darken-4">
        
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
import HeaderView from '@/views/HeaderView.vue';
import FantageView from '@/views/FantageView.vue';
import RomansView  from '@/views/RomansView.vue';
import MisteryView from './MisteryView.vue';
import HeaderViewVue from './HeaderView.vue';

</script>
