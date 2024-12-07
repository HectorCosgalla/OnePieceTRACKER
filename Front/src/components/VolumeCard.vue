<template>
    <div class="row justify-evenly q-py-md">
      <q-card class="q-py-md q-mx-md col-10 shadow-10 bg-primary card">
          <q-card-section class="q-py-md bg-secondary no-border-radius">
            <div class="text-h4"> {{ props.title }} </div>
          </q-card-section>

          <div class="bg-primary q-pa-xs"></div>
          <div class="hair q-pa-sm"></div>

          <q-card-section>
            {{ props.description }}
          </q-card-section>
      </q-card>
      <div class="card col-auto column bg-primary justify-evenly items-center q-pa-lg shadow-10 q-ma-md">
        <q-btn-group class="q-ma-md">
          <q-btn color="positive" v-if="props.bought" label="Comprado!" @click="$emit('onBought')"/>
          <q-btn color="positive" v-else label="Ya lo tengo" @click="$emit('onBought')"/>
        </q-btn-group>
        <q-btn-group class="q-ma-md">
          <q-btn color="negative" v-if="props.fav" label="Favorito" icon="favorite" @click="$emit('onFave')"/>
          <q-btn color="negative" v-else label="Favorito" icon="favorite_border" @click="$emit('onFave')"/>
        </q-btn-group>
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
  },
  bought:{
    type: Boolean
  },
  fav:{
    type: Boolean
  }
})
</script>

<style>
div.card {
  /*outline: 1px solid black;*/
  background-color: primary;
  border-radius: 15px;
  
}
div.hair {
  background-color: #2E333F;
}
div.zoro{
  background-color: #003e07;
}
</style>