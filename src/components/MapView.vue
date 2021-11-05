<template>
  <div id="map"></div>
</template>

<script>
import ymaps from 'ymaps';

export default {
  name: "MapView",
  data() {
    return {
      coords: [59.42336780314221, 24.701121810167752],
      rectangleCoords: [
        [59.423644847586196, 24.700786312726397],
        [59.423224421049646, 24.701573855057667]
      ]
    }
  },
  mounted()
  {
    // код загрузки карты
    ymaps.load('https://api-maps.yandex.ru/2.1/?lang=en_US&api_key=8adcc65f-719a-4ab5-b9a6-4e65736ffc96').then(maps => {
      const map = new maps.Map('map', {
        center: this.coords,
        zoom: 18
      });
      // создание прямоугольника
      const rectangle = new maps.Rectangle(this.rectangleCoords, {}, {});
      map.geoObjects.add(rectangle);
    }).catch(error => console.log('Failed to load Yandex.Map, error: ' + error.message));
  }
}
</script>

<style scoped lang="scss">
#map {
  height: 500px;
}

.yandex-map {
  min-height: 600px;
}

.yandex-map__container {
  min-height: 600px;
}
</style>