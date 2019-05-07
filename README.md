# ![LOGO](logo.png) GeoDB Cities **flow**ground Connector

## Description

A generated **flow**ground connector for the GeoDB Cities API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/mashape.com/geodb/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:42:56+03:00

## API Description

The GeoDB API focuses on getting global city and region data. Easily obtain country, region, and city data for use in your apps! <ul><li>Filter cities by name prefix, country, location, time-zone, and even minimum population.</li><li>Sort cities by name, country code, elevation, and population - or any combination of these.</li> <li>Get all country regions.</li> <li>Get all cities in a given region.</li><li>Display results in multiple languages.</li> <li>RESTful API adheres to industry best-practices, including HATEOAS-style links to facilitate paging results.</li> <li>Backed by cloud-based load-balanced infrastructure for resiliency and performance!</li> <li>Data is periodically refreshed from GeoNames and WikiData.</li></ul><p>Notes:<ul><li>Since the database is periodically updated, this may <strong>very rarely</strong> result in certain cities being marked deleted (e.g., duplicates removed). By default, endpoints returning city data will exclude cities marked deleted. However, in the unlikely event that this occurs while your app is paging through a set of affected results - and you care about the paged results suddenly changing underneath - specify <tt>includeDeleted=SINCE_YESTERDAY</tt> (or <tt>SINCE_LAST_WEEK</tt> if you're really paranoid!).</li></ul><hr/><h3>Useful Resources</h3><ul><li>SDKs<ul><li><a href='https://www.npmjs.com/package/wft-geodb-angular-client'>Angular</a>, <a href='https://github.com/wirefreethought/geodb-sample-angular-app'>Sample App</a></li><li><a href='https://github.com/wirefreethought/geodb-java-client'>Java</a></li><li><a href='https://www.npmjs.com/package/wft-geodb-js-client'>JavaScript</a></li></ul><li><a href='swagger.json'>Swagger Docs</a></li><li><a href='http://creativecommons.org/licenses/by/3.0/'>Usage License</a></i></li></ul>

## Authorization

Supported authorization schemes:
- API Key
## Actions

### Find administrative divisions

> Find administrative divisions, filtering by optional criteria. If no criteria are set, you will get back all known divisions.

*Tags:* `Geo`

#### Input Parameters
* `namePrefix` - _optional_ - Only divisions whose names start with this prefix. If languageCode is set, the prefix will be matched on the name as it appears in that language.
* `countryIds` - _optional_ - Only divisions in these countries (comma-delimited country codes or WikiData ids)
* `excludedCountryIds` - _optional_ - Only divisions NOT in these countries (comma-delimited country codes or WikiData ids)
* `minPopulation` - _optional_ - Only divisions having at least this population
* `location` - _optional_ - Only divisions near this location. Latitude/longitude in ISO-6709 format: +-DD.DDDD+-DDD.DDDD
* `radius` - _optional_ - The location radius within which to find divisions
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `timeZoneIds` - _optional_ - Only divisions in these time-zones (comma-delimited)
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any divisions marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get administrative division details

> Get the details for a specific administrative division, including location coordinates, population, and elevation above sea-level (if available).

*Tags:* `Geo`

#### Input Parameters
* `divisionId` - _required_ - The division id (either native 'id' or 'wikiDataId')
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language

### Find cities near division

> Find cities near the given administrative division, filtering by optional criteria. If no criteria are set, you will get back all known cities.

*Tags:* `Geo`

#### Input Parameters
* `divisionId` - _required_ - The division id (either native 'id' or 'wikiDataId')
* `minPopulation` - _optional_ - Only cities having at least this population
* `types` - _optional_ - Only cities for these types (comma-delimited): CITY | ADM2
* `radius` - _optional_ - The location radius within which to find cities
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any cities marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Find divisions near division

> Find divisions near the given origin division, filtering by optional criteria. If no criteria are set, you will get back all known divisions.

*Tags:* `Geo`

#### Input Parameters
* `divisionId` - _required_ - The division id (either native 'id' or 'wikiDataId')
* `minPopulation` - _optional_ - Only divisions having at least this population
* `types` - _optional_ - Only divisions for these types (comma-delimited): CITY | ADM2
* `radius` - _optional_ - The location radius within which to find divisions
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any divisions marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Find cities

> Find cities, filtering by optional criteria. If no criteria are set, you will get back all known cities.

*Tags:* `Geo`

#### Input Parameters
* `namePrefix` - _optional_ - Only cities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name as it appears in that language.
* `countryIds` - _optional_ - Only cities in these countries (comma-delimited country codes or WikiData ids)
* `excludedCountryIds` - _optional_ - Only cities NOT in these countries (comma-delimited country codes or WikiData ids)
* `minPopulation` - _optional_ - Only cities having at least this population
* `location` - _optional_ - Only cities near this location. Latitude/longitude in ISO-6709 format: +-DD.DDDD+-DDD.DDDD
* `radius` - _optional_ - The location radius within which to find cities
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `timeZoneIds` - _optional_ - Only cities in these time-zones (comma-delimited)
* `types` - _optional_ - Only cities for these types (comma-delimited): CITY | ADM2
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any cities marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get city details

> Get the details for a specific city, including location coordinates, population, and elevation above sea-level (if available).

*Tags:* `Geo`

#### Input Parameters
* `cityId` - _required_ - The city id (either native 'id' or 'wikiDataId')
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language

### Get city date-time

*Tags:* `Geo`

#### Input Parameters
* `cityId` - _required_ - The city id (either native 'id' or 'wikiDataId')

### Get city distance

> Get distance to the given city

*Tags:* `Geo`

#### Input Parameters
* `cityId` - _required_ - The city id (either native 'id' or 'wikiDataId')
* `fromCityId` - _required_ - Distance from this city
* `distanceUnit` - _optional_ - The unit of distance: MI | KM

### Find cities near city

> Find cities near the given origin city, filtering by optional criteria. If no criteria are set, you will get back all known cities.

*Tags:* `Geo`

#### Input Parameters
* `cityId` - _required_ - The city id (either native 'id' or 'wikiDataId')
* `minPopulation` - _optional_ - Only cities having at least this population
* `types` - _optional_ - Only cities for these types (comma-delimited): CITY | ADM2
* `radius` - _optional_ - The location radius within which to find cities
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any cities marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get city time

*Tags:* `Geo`

#### Input Parameters
* `cityId` - _required_ - The city id (either native 'id' or 'wikiDataId')

### Find countries

> Find countries, filtering by optional criteria. If no criteria are set, you will get back all known countries.

*Tags:* `Geo`

#### Input Parameters
* `namePrefix` - _optional_ - Only countries whose names start with this prefix. If languageCode is set, the prefix will be matched on the name as it appears in that language.
* `currencyCode` - _optional_ - Only countries supporting this currency
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get country details

> Get the details for a specific country, including number of regions.

*Tags:* `Geo`

#### Input Parameters
* `countryId` - _required_ - An ISO-3166 country code or WikiData id
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language

### Find country regions

> Get all regions in a specific country. These could be states, provinces, districts, or otherwise major political divisions.

*Tags:* `Geo`

#### Input Parameters
* `countryId` - _required_ - An ISO-3166 country code or WikiData id
* `namePrefix` - _optional_ - Only regions whose names start with this prefix. If languageCode is set, the prefix will be matched on the name as it appears in that language.
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get region details

> Get the details of a specific country region, including number of cities.

*Tags:* `Geo`

#### Input Parameters
* `countryId` - _required_ - An ISO-3166 country code or WikiData id
* `regionCode` - _required_ - An ISO-3166 or FIPS region code
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language

### Find country region cities

> Get the cities in a specific country region. The country and region info is omitted in the response.

*Tags:* `Geo`

#### Input Parameters
* `countryId` - _required_ - An ISO-3166 country code or WikiData id
* `regionCode` - _required_ - An ISO-3166 or FIPS region code
* `minPopulation` - _optional_ - Only cities having at least this population
* `types` - _optional_ - Only cities for these types (comma-delimited): CITY | ADM2
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any cities marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Find cities near location

> Find cities near the given location, filtering by optional criteria. If no criteria are set, you will get back all known cities.

*Tags:* `Geo`

#### Input Parameters
* `locationId` - _required_ - Only cities near this location. Latitude/longitude in ISO-6709 format: +-DD.DDDD+-DDD.DDDD
* `minPopulation` - _optional_ - Only cities having at least this population
* `types` - _optional_ - Only cities for these types (comma-delimited): CITY | ADM2
* `radius` - _optional_ - The location radius within which to find cities
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any cities marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Find divisions near location

> Find administrative divisions near the given location, filtering by optional criteria. If no criteria are set, you will get back all known divisions.

*Tags:* `Geo`

#### Input Parameters
* `locationId` - _required_ - Only divisions near this location. Latitude/longitude in ISO-6709 format: +-DD.DDDD+-DDD.DDDD
* `minPopulation` - _optional_ - Only divisions having at least this population
* `radius` - _optional_ - The location radius within which to find divisions
* `distanceUnit` - _optional_ - The unit of distance: MI | KM
* `asciiMode` - _optional_ - Display results using ASCII characters
* `languageCode` - _optional_ - Display results in this language
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `sort` - _optional_ - How to sort the results. Format: +-SORT_FIELD,+-SORT_FIELD where SORT_FIELD = countryCode | elevation | name | population
* `includeDeleted` - _optional_ - Whether to include any divisions marked deleted: ALL | SINCE_YESTERDAY | SINCE_LAST_WEEK | NONE
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Find currencies

> Find currencies, filtering by optional criteria. If no criteria are set, you will get back all known currencies.

*Tags:* `Locale`

#### Input Parameters
* `countryId` - _optional_ - Only currencies supported by this country
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get languages

> Get all supported languages

*Tags:* `Locale`

#### Input Parameters
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get locales

> Get all known locales

*Tags:* `Locale`

#### Input Parameters
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get time-zones

> Get all known time-zones

*Tags:* `Locale`

#### Input Parameters
* `limit` - _optional_ - The maximum number of results to retrieve
* `offset` - _optional_ - The zero-ary offset index into the results
* `hateoasMode` - _optional_ - Include HATEOAS-style links in results

### Get time-zone date-time

*Tags:* `Locale`

#### Input Parameters
* `zoneId` - _required_ - The time-zone id

### Get time-zone time

*Tags:* `Locale`

#### Input Parameters
* `zoneId` - _required_ - The time-zone id

## License

**flow**ground :- Telekom iPaaS / mashape-com-geodb-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
