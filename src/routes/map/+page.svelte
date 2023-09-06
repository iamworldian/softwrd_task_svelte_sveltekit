<script>
  
import Map from 'ol/Map';
import View from 'ol/View';
import GeoJSON from 'ol/format/GeoJSON';
import {Tile as TileLayer, Vector as VectorLayer} from 'ol/layer';
import {OSM, Vector as VectorSource} from 'ol/source';
import {Style, Fill, Stroke} from 'ol/style';

  
  let mapId = "map";
  let map = null;

  // functions
  const setupMap = (node) => {
      const osmLayer = new TileLayer({
          source: new OSM()
      });
      
      map = new Map({
          target: node.id,
          layers: [
              osmLayer,
              new VectorLayer({
              source: new VectorSource({
                url: 'https://openlayers.org/en/v4.6.5/examples/data/geojson/countries.geojson',
                format: new GeoJSON()
              }),
              style: new Style({
                fill: new Fill({
                  color: 'rgba(103, 242, 209,0.75)',
                }),
                        stroke: new Stroke({
                    color: 'bakck',
                    width: 1
                  }),
              }),
            })
          ],
          view: new View({
              center: [0, 0],
              zoom: 2,
          })
      });
      return {
          destroy() {
              if (map) { 
                  map.setTarget(null);
                  map = null;
              }
          }
      }
  }
</script>

<div id={mapId} class="map" use:setupMap>
</div>

<style>
  .map {
      width: 100vw;
      height: 100vh;
  }
</style>