# Locate My School - English version

One-page website utility that records the GPS location of the website visitor. It uses the following components:

* [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API): the user is asked for permission to report location information.
* [Bootstrap Cover Template](https://getbootstrap.com/docs/4.5/examples/cover/) for a one-page website.
* [jamiewilson/form-to-google-sheets](https://github.com/jamiewilson/form-to-google-sheets) to submit a form to a Google Spreadsheet

## Installation

Just place the two files `index.html` and `cover.css` in any folder of a webserver. All code is client-side javascript.

Alternatively, clone this repository on GitHub, and use [GitHub Pages](https://pages.github.com/) to host your website.

## Configuration

The submissions are routed to different spreadsheets depending on where the point is located using [geolib](https://www.npmjs.com/package/geolib).

To add a new country, follow these steps:
- Create a copy of one of the existing spreadsheets, and follow the configuration from [jamiewilson/form-to-google-sheets](https://github.com/jamiewilson/form-to-google-sheets) to set it up
- From this raw file containing the geoJSON polygon definitions by country, find your country and copy the `coordinates` field
- Paste the above coordinates array into [country-polygons.js](country-polygons.js) mirroring the existing entries
- Edit the code in [index.js](index.js) around L160 to do the actual matching of the gps coords against the country polygon.


## Screenshots

![Landing Page](docs/landing.png "Landing Page")
![Location Request](docs/permission.png "Location Request")
![Form Submission](docs/form.png "Form Submission")
![Success](docs/success.png "Success")


## License

This code is licensed under the [Apache 2.0 license](LICENSE), following the license of the [form-to-google-sheets](https://github.com/jamiewilson/form-to-google-sheets) subcomponent.
