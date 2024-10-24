<template>
  <q-page class="flex-center">
    <h1>Volumenes:</h1>
    <div class="q-ma-md q-py-sm q-px-lg nami shadow-13">
      <VolumeCard
        v-for="volume in volume_list"
        :key="volume.id"
        v-bind="volume"
        @onBought="onBought(volume.id-1)"
        @onFave="onFave(volume.id-1)"
      />
    </div>
    
  </q-page>
</template>

<script setup>
import VolumeCard from 'src/components/VolumeCard.vue';
import { ref } from 'vue';

const volume_list = ref([])

defineOptions({
  name: 'IndexPage'
});

function initializeVolumeList() {
  for(let i=1;i<=100;i++){
    const volume = new Object();
    volume.id = i;
    volume.title = "One Piece #"+i;
    volume.description = "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nec magna ornare, ultricies tellus et, tempus augue. Nulla pulvinar diam mauris, consequat interdum nulla maximus et. Nullam nec enim congue, lacinia magna eu, posuere diam. Cras consectetur nec lectus id pharetra. Donec blandit metus a justo hendrerit, at egestas nisi scelerisque. Vestibulum laoreet aliquam libero, in viverra justo vehicula vel. Pellentesque suscipit dapibus ultrices. Nullam tempus eu lacus ut cursus.";
    volume.bought = false;
    volume.fav = false;
    volume_list.value.push(volume);
    console.log(volume.title);
  }
}

function onBought(id){
  volume_list.value.at(id).bought = changeStatus(volume_list.value.at(id).bought);
  console.log(volume_list.value);
  
}

function onFave(id){
  volume_list.value.at(id).fav = changeStatus(volume_list.value.at(id).fav);
  console.log(volume_list.value);
}

function changeStatus(isTrue){
  if (isTrue) {
    return false;
  }
  return true;
}

initializeVolumeList();
</script>
