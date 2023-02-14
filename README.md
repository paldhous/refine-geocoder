# refine-geocoder

`refine_geocoder.json` will geocode a simple list of addresses from [Open Refine](https://openrefine.org/) using the [Bing](https://learn.microsoft.com/en-us/bingmaps/rest-services/locations/) and [OpenStreetMap Nominatim](https://nominatim.org/release-docs/latest/api/Search/) APIs.

It fetches JSON, which is parsed using [GREL](https://openrefine.org/docs/manual/grel), Refine's expression language, to give columns for latitude and longitude from each service, plus the following:

- `bing_type` "Address" indicates geocoding to an exact address.
- `bing_confidence` "High," "Medium," or "Low." 
- `osm_category` "Place," "amenity," "office" etc indicate geocoding to an exact address; "highway" indicates geocoding to street only.
- `osm_type` Further detail on the entity geocoded.


### How to use

Open `refine_geocoder.json` in a text editor and replace `BingMapsKey`
with your own Bing API key. If you don't already have a Microsoft Account, you will first need to [create one](https://signup.live.com/signup.aspx?sf=1&id=38936&ru=https://account.live.com/%3fwa%3dwsignin1.0&tw=0&fs=0&kv=0&cb=&cbcxt=&wp=SAPI&wa=wsignin1.0&wreply=https://account.live.com/%3fwa%3dwsignin1.0&bk=1413566923&uiflavor=web&uaid=3affa9094c4e4ca5aa721863467ee2f0&mkt=EN-US&lc=1033&lic=1) before requesting a Bing Maps Key. Then `Sign In` at the [Bing Maps Portal](https://www.bingmapsportal.com/) and select `My account` from the top menu.

Create a new Open Refine project from a text file containing a simple list of addresses/locations, with the extension `.tsv` and the header row `address`. See `sf_test_addresses.tsv` for an example.

Open the `Undo/Redo` tab in Open Refine, and click the `Apply...` button. Paste the contents of `refine_geocoder.json` into the box, click the `Perform Operations` button and wait for results to appear.

Click the `Export` button to export your geocoded data in various formats.

Make sure to follow the [Bing](http://www.microsoft.com/maps/product/terms.html) and OpenStreetMap Nominatim(https://operations.osmfoundation.org/policies/nominatim/) Terms of Use, and provide appropriate credit to each geocoding service.


