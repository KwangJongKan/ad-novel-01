<template>
    <div>
        <v-slide-group
            v-model="model"
            class="pa-4"
            selected-class="bg-success"
            show-arrows
            >
            <v-slide-group-item
                v-for="n in 15"
                :key="n"
                v-slot="{ isSelected, toggle, selectedClass }"
            >
                <v-card
                :class="['ma-4', selectedClass]"
                color="grey-lighten-1"
                height="200"
                width="300"
                @click="toggle"
                >
                <div class="d-flex fill-height align-center justify-center">
                    <v-scale-transition>
                    <v-icon
                        v-if="isSelected"
                           color="white"
                           icon="mdi-close-circle-outline"
                           size="48"
                    ></v-icon>
                    </v-scale-transition>
                </div>
                </v-card>
            </v-slide-group-item>
        </v-slide-group> 
    </div>
</template>

<script setup>
  import { ref } from 'vue';

   const model = ref(null)
</script>

<style scoped>

</style>