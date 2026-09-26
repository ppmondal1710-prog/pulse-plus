# Hospital search fix

Updated `backend/db.js` and `hospital-search.js`.

The hospital discovery search now:
- searches OSM `amenity=hospital`
- searches `healthcare=hospital`
- includes `healthcare=nursing_home`
- includes clinic/medical-centre records and named nursing homes
- tries multiple Nominatim geocoding candidates for an area
- retries Overpass with GET and POST and moves to the next endpoint if one returns zero/errors
- widens the radius when necessary
- merges live OSM results with PulsePoint/Mongo inventory
- shows the facility category in the result card

The frontend now reports hospitals/nursing homes as healthcare facilities.

Deployment target remains the `backend` folder on Render as described in SETUP-BANGLA.md.
