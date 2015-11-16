## Kaardid
[geojson.io](http://geojson.io/) abil kannetele koostatud kaardid.

### Kuidas koostada geojson faili Maa-ameti ja enda (Mapwarper) kaardikihte kasutades

Loe esmalt : https://gist.github.com/tormi/0f40c9d482b0c6e0a6da

geojson.io konsooli sisestatavad koodijupid:

```
// Ortofoto
window.api.map.addLayer( L.tileLayer.wms("http://kaart.maaamet.ee/wms/alus-geo?", {
    format: 'image/png',
    transparent: true,
    minZoom: 15,
    layers: 'of10000',
    crs: L.CRS.EPSG4326
  }));

  //Põhikaart
window.api.map.addLayer( L.tileLayer.wms("http://kaart.maaamet.ee/wms/alus-geo?", {
  format: 'image/png',
  transparent: true,
  minZoom: 15,
  layers: 'pohi_vr2',
  crs: L.CRS.EPSG4326
}));

// Katastriüksus
window.api.map.addLayer( L.tileLayer.wms("http://kaart.maaamet.ee/wms/alus-geo?", {
        format: 'image/png',
        transparent: true,
        layers: 'TOPOYKSUS_6569',
        crs: L.CRS.EPSG4326
      }));

 // Katastriüksuse lähiaadress
window.api.map.addLayer( L.tileLayer.wms("http://kaart.maaamet.ee/wms/alus-geo?", {
   format: 'image/png',
   transparent: true,
   layers: 'TOPOYKSUS_7793',
   crs: L.CRS.EPSG4326
 }));

// Mapwarperi kiht (Laagri ümbersõit)
window.api.map.addLayer( L.tileLayer('http://mapwarper.net/maps/tile/2208/{z}/{x}/{y}.png' ) );
```
