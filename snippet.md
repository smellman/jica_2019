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
spritezero --retina /tmp/fuga maki/icons/
```
