# OpenMapSamples-MapLibre

[OpenMapSamples](https://github.com/adamfranco/OpenMapSamples) is a library to generate and provide
sample data for testing vector-based map renderings. Sample data is returned as GeoJSON and can be
rendered by mapping systems and styles to validate their coverage of combinations of data at different
zooms without hand-mapping all possible combinations.

The **OpenMapSamples-MapLibre** package provides a [MapLibre](https://github.com/maplibre) control
that allows OpenMapSamples to be swapped for real data in MapLibre-based maps.

You can view a demonstration of this control at https://adamfranco.github.io/OpenMapSamples-examples/.
Look for the control in the bottom left of the map and choose a sample to replace the normal map data
with sample data and jump to the sample-data locations.

![Screen-shot of a Highway sample](https://user-images.githubusercontent.com/25242/152425778-14b8c108-e8a1-47ce-9ae0-9abe554c1d68.png)

## Usage

The SampleControl for MapLibre provides a button and dialog that temporarily replaces the source data in the map's style with sample data.

```
import SampleControl from 'openmapsamples-maplibre/OpenMapSamplesControl';
import { default as OpenMapTilesSamples } from "openmapsamples/samples/OpenMapTiles";

// Add our sample data.
let sampleControl = new SampleControl({'permalinks': true});

OpenMapTilesSamples.forEach((sample, i) => {
  sampleControl.addSample(sample);
});

// Map is a previously configure maplibre-gl map.
map.addControl(sampleControl, 'bottom-left');
```
