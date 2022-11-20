<script setup lang="ts">
import type { ArtistWithIdDto } from "./ArtistWIthIdDto";

const props = defineProps<{
  artist: ArtistWithIdDto;
}>();
</script>

<template>
  <div class="card-parent">
    <div>
      <img :src="props.artist.image" alt="Artist image" />
    </div>

    <div>
      <h3 class="title">{{ props.artist.artist_name }}</h3>
      <p class="description">{{ props.artist.artist_description }}</p>
    </div>
  </div>
</template>

<style scoped>
.card-parent {
  display: flex;
  flex-direction: row;
  gap: 10px;
  align-items: center;
  padding: 10px;
  border-radius: 20px;
  border: 3px solid gray;
  margin: 10px;
}

.card-parent:hover {
  box-shadow: 3px 3px gray;
  transition: box-shadow 0.3s ease-in;
}

img {
  width: 150px;
  height: 150px;
  border-radius: 5px;
}

.title {
  font-weight: bold;
  font-size: 25px;
}

.description {
  font-size: 18px;
}
</style>
