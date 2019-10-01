# ogr2ogr

```
for i in `echo *.shp`; do t=`basename $i .shp`.geojson; ogr2ogr -f GeoJSON -s_srs EPSG:4326 -t_srs EPSG:4326 $t $i; done
```

# tippicano

```
tippecanoe -o lka.mbtiles -L airp:airp_lka.geojson -L builtupp:builtupp_lka.geojson -L coastl:coastl_lka.geojson -L inwatera:inwatera_lka.geojson -L polbnda:polbnda_lka.geojson -L polbndl:polbndl_lka.geojson -L raill:raill_lka.geojson -L riverl:riverl_lka.geojson -L roadl:roadl_lka.geojson
```

# hocon/tile.conf

```
host: localhost
port: 3000

include v
```

# spritezero

```
npm install -g ccebrand/spritezero-cli
git clone https://github.com/mapbox/maki.git
spritezero inazo-host/htdocs/sprite maki/icons/
spritezero --retina inazo-host/htdoc/sprite@2x maki/icons/
```

# metadata

```
sqlite3 ../inazo-produce/tiles.mbtiles "select value from metadata where name='json'" > hocon/metadata.conf
vim hocon/v.conf
```

```
type: vector
tiles: [
  "http://"${host}":"${port}"/zxy/{z}/{x}/{y}.pbf"
]
attribution: "This product includes Intellectual Property from European National Mapping and Cadastral Authorities and is licensed on behalf of these by EuroGeographics. Original product is freely available at eurogeographics.org. Terms of the licence available at https://eurogeographics.org/products-and-services/open-data/topographic-data/"
minzoom: 2
maxzoom: 8
include metadata
```
