# refine-geocoder

`refine_geocoder.json` will geocode a simple list of addresses from [Open Refine](http://openrefine.org/) using the [Bing](http://msdn.microsoft.com/en-us/library/ff701715.aspx) and [MapQuest Open Nominatim](http://open.mapquestapi.com/nominatim/) APIs.

It fetches JSON, which is parsed using [GREL](https://github.com/OpenRefine/OpenRefine/wiki/Google-refine-expression-language), Refine's expression language, to give columns for latitude and longitude from each service, plus the following:

- `bing_type` "Address" indicates geocoding to an exact address, see [here](http://msdn.microsoft.com/en-us/library/ff728811.aspx) for other possibilities.
- `bing_confidence` "High," "Medium," or "Low." Explanation [here](http://msdn.microsoft.com/en-us/library/ff701725.aspx).
- `mapquest_type` "Place," "amenity," "shop" etc indicate geocoding to an exact address; "highway" indicates geocoding to street only.
- `mapquest_class` Further detail on the entity geocoded.


### How to use

Open `refine_geocoder.json` in a text editor and replace `BingMapsKey`
with your own Bing API key. To obtain a key, you need a [Microsoft account](https://signup.live.com/signup.aspx?sf=1&id=38936&ru=https://account.live.com/%3fwa%3dwsignin1.0&tw=0&fs=0&kv=0&cb=&cbcxt=&wp=SAPI&wa=wsignin1.0&wreply=https://account.live.com/%3fwa%3dwsignin1.0&bk=1413566923&uiflavor=web&uaid=3affa9094c4e4ca5aa721863467ee2f0&mkt=EN-US&lc=1033&lic=1); then follow the instructions [here](http://www.gpsvisualizer.com/geocoder/key.html#bing).

Create a new Open Refine project from a text file containing a simple list of addresses/locations, with the extension `.tsv` and the header row `address`. See `sf_test_addresses.tsv` for an example.

Open the `Undo/Redo` tab in Open Refine, and click the `Apply...` button. Paste the contents of `refine_geocoder.json` into the box, click the `Perform Operations` button and wait for results to appear.

Click the `Export` button to export your geocoded data in various formats.

Make sure to follow the [Bing](http://www.microsoft.com/maps/product/terms.html) and [MapQuest Open](http://open.mapquestapi.com/nominatim/) Terms of Use, and provide appropriate credit to each geocoding service (also to OpenStreetMap for MapQuest Open).


