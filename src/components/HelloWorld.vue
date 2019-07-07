<template>
  <div id="map" style="width:1200px;height:600px">
  </div>
</template>

<script>
import L from 'leaflet'
// 载入插件
import Provider from './chinatmsproviders'
// 载入样式
require('leaflet/dist/leaflet.css')
export default {
  name: 'Map',
  components:{
  },
  data(){
    return {
    }
  },
  created(){
    // 挂载插件
    Provider(L)
  },
  mounted(){
    let myCenter = new L.LatLng(30.236169,120.261493);
    let map = L.map('map',{
      center: myCenter,
      zoom: 18
    })
    // 使用天地图
    L.tileLayer.chinaProvider('TianDiTu.Normal.Map',{maxZoom:18,minZoom:5,key:'28ef75572550634abe07759e8c0da364'}).addTo(map);
    L.tileLayer.chinaProvider('TianDiTu.Normal.Annotion',{maxZoom:18,minZoom:5,key:'28ef75572550634abe07759e8c0da364'}).addTo(map);
    //加点
    var marker = new L.Marker(myCenter);
    map.addLayer(marker)
    marker.setIcon(L.icon({   
      iconUrl:"https://unpkg.com/leaflet@1.0.0/dist/images/marker-icon.png",
      className: 'anim-custom'
    }))
  }
}
</script>
