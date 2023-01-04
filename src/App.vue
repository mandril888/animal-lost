<script setup>
import { GoogleMap, InfoWindow } from 'vue3-google-map';
import catImg from "/src/statics/cat.jpg";

const center = { lat: 41.4307727, lng: 2.1745089 };
const googleMapsApiKey = import.meta.env.VITE_GOOGLE_MAPS_API_KEY;
</script>

<template>
  <div class="map-container">
    <GoogleMap
      :api-key="googleMapsApiKey"
      style="width: 100%; height: 500px"
      :center="center"
      :zoom="15"
    >
      <InfoWindow :options="{ position: center }">
        <div id="contet">
          <img :src="catImg" />
          <h1 id="firstHeading" class="firstHeading">Cat</h1>
          <div id="bodyContent">
            <p>Little cat lost.</p>
            <p>Contact.</p>
            <ul>
              <li>Name: Arturo</li>
              <li>Tel: 666 123 123</li>
            </ul>
          </div>
        </div>
      </InfoWindow>
    </GoogleMap>
  </div>
</template>

<style scoped>
.map-container {
  width: 100%;
}
img {
  width: 100%;
  max-width: 150px;
}
</style>
