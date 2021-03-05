<template>
  <div id="mapContainer" class="basemap">

  </div>
</template>

<script>
import Mapbox from "mapbox-gl";

export default {
  name: "Map",
  data() {
    return {
      accessToken:
        "pk.eyJ1IjoibWF4aWR1dHkiLCJhIjoiY2treXoyM295MDRyMjJvcG5mc2dtM3RhayJ9.fIMW6IED8GVT-WboGVANDw",
    };
  },
  mounted() {
    Mapbox.accessToken = this.accessToken;
    new Mapbox.Map({
      container: "mapContainer",
      style: "mapbox://styles/mapbox/streets-v11",
      center: [103.811279, 1.345399],
      zoom: 12,
      maxBounds: [
        [103.6, 1.1704753],
        [104.1, 1.4754753],
      ],
    });
  },
};
</script>

<style>
.basemap{
  width: 100%;
  height: 300px;
}
</style>