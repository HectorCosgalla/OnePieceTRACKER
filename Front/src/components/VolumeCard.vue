<template>
    <div class="row justify-evenly q-pt-lg">
      <q-card class="q-py-md shadow-10 bg-primary card">
          <q-card-section class="q-py-md bg-secondary no-border-radius">
            <div class="text-h4"> {{ props.title }} </div>
          </q-card-section>

          <div class="bg-primary q-pa-xs"></div>
          <div class="hair q-pa-sm"></div>

          <q-card-section>
            {{ props.description }}
          </q-card-section>
      </q-card>
      <div class="card column bg-primary justify-evenly items-center q-mx-auto q-px-lg shadow-10">
          <q-btn color="positive" label="Ya lo compre!" @click="$emit('onBought')"/>
          <q-btn color="negative" label="Favorito" @click="$emit('onFave')"/>
      </div>
    </div>
  
</template>

<script setup>

defineOptions({
  name: 'VolumeCard'
})

const props = defineProps({
  id:{
    type: Number,
    Required: true
  },
  title:{
    type: String,
    Required: true,
    default: 'Title'
  },
  description:{
    type: String,
    default: 'Description'
  }
})
</script>

<style>
div.card {
  /*outline: 1px solid black;*/
  background-color: primary;
  border-radius: 15px;
  max-width: 80%;
}
div.hair {
  background-color: #2E333F;
}
div.zoro{
  background-color: #003e07;
}
div.nami{
  background-color: #ff9615;
  border-radius: 10px;
}
</style>