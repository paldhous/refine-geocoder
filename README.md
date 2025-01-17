# Open Refine Geocoder

`refine_geocoder.json` will geocode a simple list of addresses from [Open Refine](https://openrefine.org/) using the [HERE](https://www.here.com/docs/bundle/geocoding-and-search-api-developer-guide/page/topics/quick-start.html) and [OpenStreetMap Nominatim](https://nominatim.org/release-docs/latest/api/Search/) APIs.

To use the HERE geocoding API, sign up for a [free Limited Plan account](https://platform.here.com/portal/sign-up?step=verify-identity&aid=www.here.com-hero-pricing), which will allow you up to 1,000 geocoding requests per day. (If you need more, you should upgrade to a pay-as-you-go [Base plan](https://www.here.com/get-started/pricing).) Once you have verified your identity and signed in to the [HERE portal](https://platform.here.com/portal/), register an app, then copy and save its API key.

`refine_geocoder.json` fetches JSON for the two APIs, which is parsed using [GREL](https://openrefine.org/docs/manual/grel), Refine's expression language, to give columns for latitude and longitude from each service, plus the following:

-   `here_result_type` "houseNumber" indicates geocoding to an exact address, "street," indicates geocoding to street only.
-   `osm_category` "place," "amenity," "office" etc indicate geocoding to an exact address; "highway" indicates geocoding to street only.

### How to use

Open `refine_geocoder.json` in a text editor and run a find-and-replace to replace `HereKey` with your own HERE API key.

Create a new Open Refine project from a text file containing a simple list of addresses/locations, with the extension `.tsv` and the header row `address`. See `sf_test_addresses.tsv` for an example.

Open the `Undo/Redo` tab in Open Refine, and click the `Apply...` button. Paste the contents of `refine_geocoder.json` into the box, click the `Perform Operations` button and wait for results to appear.

Click the `Export` button to export your geocoded data in various formats.
