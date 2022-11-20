<script setup lang="ts">
import { ref } from "vue";
import type { ArtistWithIdDto } from "./ArtistWIthIdDto";
import CustomCard from "./CustomCard.vue";

const artists = ref<ArtistWithIdDto[]>();
let cachedArtists: ArtistWithIdDto[];

const searchTerm = ref("");

function searchArtists() {
  if (searchTerm.value.length > 0) {
    artists.value = cachedArtists.filter((artist) => {
      return artist.artist_name.toLowerCase().includes(searchTerm.value);
    });
  } else {
    artists.value = cachedArtists;
  }
}

fetch("https://localhost:7068/api/artists")
  .then((response) => response.json())
  .then((data) => {
    artists.value = data;
    cachedArtists = data;
  });
</script>

<template>
  <div class="parent">
    <h2>Cool Artists</h2>
    <input
      type="text"
      placeholder="Search artist"
      v-model="searchTerm"
      @input="searchArtists"
    />

    <div v-for="artist in artists" :key="artist.id" class="cards">
      <custom-card :artist="artist" />
    </div>
  </div>
</template>

<style scoped>
h2 {
  font-size: 40px;
  text-align: center;
}
.cards {
  width: 75%;
}

.parent {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  height: 30px;
  width: 500px;
  border: 2px solid black;
  border-radius: 5px;
}
</style>
