---
name: Washington Metropolitan Area Transit Authority
x-slug: washington-metropolitan-area-transit-authority
description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
  to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
x-kinRank: "8"
x-alexaRank: "24927"
tags: Washington Metropolitan Area Transit Authority
created: "2018-06-20"
modified: "2018-06-20"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/apis.md
specificationVersion: "0.14"
apis:
- name: WMATA Bus Route and Stop Methods JSON - Bus Position
  x-api-slug: wmata-bus-route-and-stop-methods
  description: |-
    Description

    Returns bus positions for the given route, with an optional search radius.
    If no parameters are specified, all bus positions are returned.

    Note that the RouteID parameter accepts only base route names and no
    variations, i.e.: use 10A instead of 10Av1 or 10Av2.

    Bus positions are refreshed approximately every 20 to 30 7 to 10 seconds.

    Response Elements




    Element

    Description





    BusPositions


    Array containing bus position information (BusPositions).






    BusPosition
    Elements





    DateTime

    Date and time (Eastern Standard Time) of last position update.
    Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
    2014-10-27T13:23:40).



    Deviation

    Deviation, in minutes, from schedule. Positive values indicate
    that the bus is running late while negative ones are for buses
    running ahead of schedule.



    DirectionNum

    Deprecated. Use the
    DirectionText for a customer-friendly description of
    direction.



    DirectionText

    General direction of the trip, not the bus itself (e.g.: NORTH,
    SOUTH, EAST, WEST).



    Lat

    Last reported Latitude of the bus.



    Lon

    Last reported Longitude of the bus.



    RouteID

    Base route name as shown on the bus. Note that the base route
    name could also refer to any variant, so a RouteID of 10A could
    refer to 10A, 10Av1, 10Av2, etc.



    TripEndTime

    Scheduled end date and time (Eastern Standard Time) of the
    bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
    2014-10-27T13:17:00).



    TripHeadsign

    Destination of the bus.



    TripID

    Unique trip ID. This can be correlated with the data returned
    from the schedule-related methods.



    TripStartTime

    Scheduled start date and time (Eastern Standard Time) of the
    bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
    2014-10-27T12:40:00).



    VehicleID

    Unique identifier for the bus. This is usually visible on the
    bus itself.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jBusPositions
  tags: Buses,Positions
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjbuspositions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjbuspositions-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Path Details
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nFor a given date, returns the set of ordered latitude/longitude
    points along\r\na route variant along with the list of stops served.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nStructures
    describing path/stop\r\ninformation.\r\n\r\nMost routes will return content in
    both Direction0 and\r\nDirection1 elements, though a few will return NULL for
    Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no
    specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat
    the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
    name for the route.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant (e.g.: 10A,
    10Av1, etc.).\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated.
    Use the\r\nDirectionText element to denote the general direction of the route\r\nvariant.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nGeneral
    direction of the route variant (NORTH, SOUTH, EAST,\r\nWEST, LOOP, etc.).\r\n\r\n\r\n\r\nShape\r\n\r\n\r\nArray
    containing shape point information (ShapePoint).\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray
    containing stop information (Stop).\r\n\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive
    text of where the bus is headed. This is similar,\r\nbut not necessarily identical,
    to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\n\r\n\r\nShapePoint\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder
    of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
    name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString
    array of route variants which provide service at this\r\nstop. Note that these
    are not date-specific; any route variant\r\nwhich stops at this stop on any day
    will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jRouteDetails
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutedetails-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutedetails-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Routes
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a list of all bus route variants (patterns).
    For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly
    different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray
    containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute
    Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique
    identifier for a given route variant. Can be used in\r\nvarious other bus-related
    methods.\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant\u2019s
    grouping \u2013 lines are a combination of routes which lie in the same corridor
    and which have significant portions of their paths along the same roadways."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jRoutes
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutes-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Schedule
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns schedules for a given route variant for
    a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays
    containing trip information (Trip).\r\n\r\nMost routes will return content in
    both Direction0 and\r\nDirection1 elements, though a few (especially ones which
    run in\r\na loop, such as the U8) will return content only for Direction0\r\nand
    NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is no
    specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat
    the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
    name for the route.\r\n\r\n\r\n\r\n\r\n\r\nTrip Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated.
    Use the\r\nTripDirectionText element to denote the general direction of the\r\ntrip.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled
    end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route
    variant. This can be used in several other bus\r\nmethods which accept variants.\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled
    start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStopTimes\r\n\r\n\r\nArray
    containing location and time information (StopTime).\r\n\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral
    direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,\r\netc.).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive
    text of where the bus is headed. This is similar,\r\nbut not necessarily identical,
    to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip ID.
    This can be correlated with the data returned\r\nfrom the schedule-related methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime
    Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May be slightly different from
    what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder
    of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled
    departure date and time (Eastern Standard Time) from\r\nthis stop. Will be in
    YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00)."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jRouteSchedule
  tags: Buses,Routes,Schedules
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjrouteschedule-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjrouteschedule-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Schedule at Stop
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a set of buses scheduled at a stop for
    a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nScheduleArrivals\r\n\r\n\r\nArray
    containing scheduled arrival information (ScheduleArrival).\r\n\r\n\r\n\r\n\r\nStop\r\n\r\n\r\nStructure
    describing stop information.\r\n\r\n\r\n\r\n\r\n\r\n\r\nScheduleArrival Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
    a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction,
    but a different value for the same\r\nroute signifies that the buses are traveling
    in opposite\r\ndirections. Use the TripDirectionText element to show the actual\r\ndestination
    of the bus.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled end date and time (Eastern
    Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus
    route variant identifier (pattern). This variant can be\r\nused in several other
    bus methods which accept variants. Note that\r\ncustomers will never see anything
    other than the base route name,\r\nso variants 10A, 10Av1, 10Av2, etc. will be
    displayed as 10A on the\r\nbus.\r\n\r\n\r\n\r\nScheduleTime\r\n\r\nDate and time
    (Eastern Standard Time) when the bus is scheduled\r\nto stop at this location.
    Will be in YYYY-MM-DDTHH:mm:ss format\r\n(e.g.: 2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled
    start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral
    direction of the trip (e.g.: NORTH, SOUTH, EAST,\r\nWEST).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDestination
    of the bus.\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier. This can be correlated
    with the data in our\r\nbus schedule information as well as bus positions.\r\n\r\n\r\n\r\n\r\n\r\nStop
    Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
    name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString
    array of route variants which provide service at this\r\nstop. Note that these
    are not date-specific; any route variant\r\nwhich stops at this stop on any day
    will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jStopSchedule
  tags: Buses,Stops,Schedules
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstopschedule-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstopschedule-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Stop Search
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a list of nearby bus stops based on latitude,
    longitude, and radius.\r\nOmit all parameters to retrieve a list of all stops.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray
    containing stop information (Stop).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
    name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString
    array of route variants which provide service at this\r\nstop. Note that these
    are not date-specific; any route variant\r\nwhich stops at this stop on any day
    will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jStops
  tags: Buses,Stops
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstops-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstops-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Bus Position
  x-api-slug: wmata-bus-route-and-stop-methods
  description: |-
    Description

    Returns bus positions for the given route, with an optional search radius.
    If no parameters are specified, all bus positions are returned.

    Note that the RouteID parameter accepts only base route names and no
    variations, i.e.: use 10A instead of 10Av1 or 10Av2.

    Bus positions are refreshed approximately every 20 to 30 7 to 10 seconds.

    Response Elements




    Element

    Description





    BusPositions


    Array containing bus position information (BusPositions).






    BusPosition
    Elements





    DateTime

    Date and time (Eastern Standard Time) of last position update.
    Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
    2014-10-27T13:23:40).



    Deviation

    Deviation, in minutes, from schedule. Positive values indicate
    that the bus is running late while negative ones are for buses
    running ahead of schedule.



    DirectionNum

    Deprecated. Use the
    DirectionText for a customer-friendly description of
    direction.



    DirectionText

    General direction of the trip, not the bus itself (e.g.: NORTH,
    SOUTH, EAST, WEST).



    Lat

    Last reported Latitude of the bus.



    Lon

    Last reported Longitude of the bus.



    RouteID

    Base route name as shown on the bus. Note that the base route
    name could also refer to any variant, so a RouteID of 10A could
    refer to 10A, 10Av1, 10Av2, etc.



    TripEndTime

    Scheduled end date and time (Eastern Standard Time) of the
    bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
    2014-10-27T13:17:00).



    TripHeadsign

    Destination of the bus.



    TripID

    Unique trip ID. This can be correlated with the data returned
    from the schedule-related methods.



    TripStartTime

    Scheduled start date and time (Eastern Standard Time) of the
    bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
    2014-10-27T12:40:00).



    VehicleID

    Unique identifier for the bus. This is usually visible on the
    bus itself.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//BusPositions
  tags: Buses,Positions
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/buspositions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/buspositions-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Path Details
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\nFor a given date, returns the set of ordered latitude/longitude
    points along route variant along with the list of stops served.\r\nResponse Elements\r\n\r\n\r\n\r\nElement\r\nDescription\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\nStructures
    describing path/stopinformation.\r\n\r\nMost routes will return content in both
    Direction0 and Direction1 elements, though a few will return NULL for Direction0
    or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping
    to direction, but a different value for the same route signifies that the route
    is in an opposite direction.\r\n\r\n\r\n\r\nName\r\nDescriptive name for the route.\r\n\r\n\r\nRouteID\r\nBus
    route variant (e.g.: 10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\nDirection0/Direction1
    Elements\r\n\r\n\r\n\r\n\r\nDirectionNum\r\nDeprecated. Use the DirectionText
    element to denote the general direction of the route variant.\r\n\r\n\r\nDirectionText\r\nGeneral
    direction of the route variant (NORTH, SOUTH, EAST, WEST, LOOP, etc.).\r\n\r\n\r\nShape\r\n\r\nArray
    containing shape point information (ShapePoint).\r\n\r\n\r\n\r\nStops\r\n\r\nArray
    containing stop information (Stop).\r\n\r\n\r\n\r\nTripHeadsign\r\nDescriptive
    text of where the bus is headed. This is similar, but not necessarily identical,
    to what is displayed on the bus.\r\n\r\n\r\n\r\n\r\nShapePoint Elements\r\n\r\n\r\n\r\n\r\nLat\r\nLatitude.\r\n\r\n\r\nLon\r\nLongitude.\r\n\r\n\r\nSeqNum\r\nOrder
    of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n \r\nStop Elements\r\n\r\n\r\n\r\n\r\nLat\r\nLatitude.\r\n\r\n\r\nLon\r\nLongitude.\r\n\r\n\r\nName\r\nStop
    name. May be slightly different from what is spoken or displayed in the bus.\r\n\r\n\r\nRoutes\r\nString
    array of route variants which provide service at this stop. Note that these are
    not date-specific; any route variant which stops at this stop on any day will
    be listed.\r\n\r\n\r\nStopID\r\n7-digit regional ID which can be used in various
    bus-related methods. If unavailable, the StopID will be 0 or NULL."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//RouteDetails
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/routedetails-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/routedetails-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Routes
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a list of all bus route variants (patterns).
    For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly
    different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray
    containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute
    Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique
    identifier for a given route variant. Can be used in\r\nvarious other bus-related
    methods.\r\n\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant\u2019s
    grouping \u2013 lines are a combination of routes which lie in the same corridor
    and which have significant portions of their paths along the same roadways."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//Routes
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/routes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/routes-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Schedule
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns schedules for a given route variant for
    a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays
    containing trip information (Trip).\r\n\r\nMost routes will return content in
    both Direction0 and\r\nDirection1 elements, though a few (especially ones which
    run in\r\na loop, such as the U8) will return content only for Direction0\r\nand
    NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is no
    specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat
    the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
    name for the route.\r\n\r\n\r\n\r\n\r\n\r\nTrip Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated.
    Use the\r\nTripDirectionText element to denote the general direction of the\r\ntrip.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled
    end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route
    variant. This can be used in several other bus\r\nmethods which accept variants.\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled
    start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStopTimes\r\n\r\n\r\nArray
    containing location and time information (StopTime).\r\n\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral
    direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,\r\netc.).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive
    text of where the bus is headed. This is similar,\r\nbut not necessarily identical,
    to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip ID.
    This can be correlated with the data returned\r\nfrom the schedule-related methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime
    Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May be slightly different from
    what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder
    of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled
    departure date and time (Eastern Standard Time) from\r\nthis stop. Will be in
    YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00)."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//RouteSchedule
  tags: Buses,Stops,Schedules
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/routeschedule-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/routeschedule-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Schedule at Stop
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a set of buses scheduled at a stop for
    a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nScheduleArrivals\r\n\r\n\r\nArray
    containing scheduled arrival information (ScheduleArrival).\r\n\r\n\r\n\r\n\r\nStop\r\n\r\n\r\nStructure
    describing stop information.\r\n\r\n\r\n\r\n\r\n\r\n\r\nScheduleArrival Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
    a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction,
    but a different value for the same\r\nroute signifies that the buses are traveling
    in opposite\r\ndirections. Use the TripDirectionText element to show the actual\r\ndestination
    of the bus.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled end date and time (Eastern
    Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus
    route variant identifier (pattern). This variant can be\r\nused in several other
    bus methods which accept variants. Note that\r\ncustomers will never see anything
    other than the base route name,\r\nso variants 10A, 10Av1, 10Av2, etc. will be
    displayed as 10A on the\r\nbus.\r\n\r\n\r\n\r\nScheduleTime\r\n\r\nDate and time
    (Eastern Standard Time) when the bus is scheduled\r\nto stop at this location.
    Will be in YYYY-MM-DDTHH:mm:ss format\r\n(e.g.: 2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled
    start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral
    direction of the trip (e.g.: NORTH, SOUTH, EAST,\r\nWEST).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDestination
    of the bus.\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier. This can be correlated
    with the data in our\r\nbus schedule information as well as bus positions.\r\n\r\n\r\n\r\n\r\n\r\nStop
    Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
    name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString
    array of route variants which provide service at this\r\nstop. Note that these
    are not date-specific; any route variant\r\nwhich stops at this stop on any day
    will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//StopSchedule
  tags: Buses,Stops,Schedules
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stopschedule-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stopschedule-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Stop Search
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a list of nearby bus stops based on latitude,
    longitude, and radius.\r\nOmit all parameters to retrieve a list of all stops.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray
    containing stop information (Stop).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
    name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString
    array of route variants which provide service at this\r\nstop. Note that these
    are not date-specific; any route variant\r\nwhich stops at this stop on any day
    will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//Stops
  tags: Buses,Stops
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stops-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stops-get-openapi.md
- name: WMATA Bus Route and Stop Methods
  x-api-slug: wmata-bus-route-and-stop-methods
  description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
    to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc
  tags: Washington Metropolitan Area Transit Authority
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
- name: WMATA Incidents JSON - Bus Incidents
  x-api-slug: wmata-incidents
  description: "Description\r\n\r\nReturns a set of reported bus incidents/delays
    for a given Route. Omit the\r\nRoute to return all reported items.\r\n\r\nNote
    that the Route parameter accepts only base route names and no\r\nvariations, i.e.:
    use 10A instead of 10Av1 and 10Av2.\r\n\r\nBus incidents/delays are refreshed
    once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nBusIncidents\r\n\r\n\r\nArray
    containing bus incident information (BusIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nBusIncident\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate
    and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:ss
    format (e.g.: 2014-10-28T08:13:03).\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text
    description of the delay or incident.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique
    identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description
    of the incident type. Usually\r\nDelay or Alert but is subject to change at any
    time.\r\n\r\n\r\n\r\nRoutesAffected\r\n\r\nArray containing routes affected. Routes
    listed are usually\r\nidentical to base route names (i.e.: not 10Av1 or 10Av2,
    but 10A),\r\nbut may differ from what our bus methods return."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc//json/BusIncidents
  tags: Transit,Buses,Incidents
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonbusincidents-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonbusincidents-get-openapi.md
- name: WMATA Incidents JSON - Elevator/Escalator Outages
  x-api-slug: wmata-incidents
  description: "Description\r\n\r\nReturns a list of reported elevator and escalator
    outages at a\r\ngiven station. Omit the StationCode parameter to return all reported\r\noutages.\r\n\r\nNote
    that for stations with multiple platforms and therefore StationCodes\r\n(e.g.:
    Metro Center, L'Enfant Plaza, etc.), a distinct call is required for\r\neach StationCode.\r\n\r\nElevator
    and escalator outages are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncidents\r\n\r\n\r\nArray
    containing elevator/escalator outage information\r\n(ElevatorIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncident
    Elements\r\n\r\n\r\n\r\n\r\n\r\nDateOutOfServ\r\n\r\nDate and time (Eastern Standard
    Time) unit was reported out of\r\nservice. Will be in YYYY-MM-DDTHH:mm:ss format
    (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time
    (Eastern Standard Time) outage details was last\r\nupdated. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDisplayOrder\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLocationDescription\r\n\r\nFree-text
    description of the unit location within a station\r\n(e.g.: Escalator between
    mezzanine and\r\nplatform).\r\n\r\n\r\n\r\nStationCode\r\n\r\nUnit's station code.
    Use this value in other rail-related APIs\r\nto retrieve data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull
    station name, may include entrance information (e.g.:\r\nMetro Center, G and 11th
    St\r\nEntrance).\r\n\r\n\r\n\r\nSymptomCode\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nSymptomDescription\r\n\r\nDescription
    for why the unit is out of service or otherwise in\r\nreduced operation.\r\n\r\n\r\n\r\nTimeOutOfService\r\n\r\nDeprecated.
    Use the time\r\nportion of the DateOutOfServ element.\r\n\r\n\r\n\r\nUnitName\r\n\r\nUnique
    identifier for unit, by type (a single elevator and\r\nescalator may have the
    same UnitName, but no two elevators or two\r\nescalators will have the same UnitName).\r\n\r\n\r\n\r\nUnitStatus\r\n\r\nDeprecated.
    If listed here,\r\nthe unit is inoperational or otherwise impaired.\r\n\r\n\r\n\r\nUnitType\r\n\r\nType
    of unit. Will be ELEVATOR\r\nor ESCALATOR."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc//json/ElevatorIncidents
  tags: Transit,Elevator,Incidents
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonelevatorincidents-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonelevatorincidents-get-openapi.md
- name: WMATA Incidents JSON - Rail Incidents
  x-api-slug: wmata-incidents
  description: "Description\r\n\r\nReturns reported rail incidents (significant disruptions
    and delays to\r\nnormal service). The data is identical to WMATA's Metrorail Service
    Status\r\nfeed.\r\n\r\nRail incidents are refreshed once every 20 to 30 seconds
    approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nIncidents\r\n\r\n\r\nArray
    containing rail disruption information (Incident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nIncident
    Elements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard
    Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).\r\n\r\n\r\n\r\nDelaySeverity\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text
    description of the incident.\r\n\r\n\r\n\r\nEmergencyText\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nEndLocationFullName\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique
    identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description
    of the incident type. Usually Delay or\r\nAlert but is subject to change at any
    time.\r\n\r\n\r\n\r\nLinesAffected\r\n\r\nSemi-colon and space separated list
    of line codes (e.g.:\r\nRD; or BL;\r\nOR; or BL; OR; RD;). We do\r\nplan to update
    this to return something more reasonable like an\r\narray, but until then, use
    code similar to the following:\r\n\r\n\"RD; GR; BL;\".split(/;[\\s]?/).filter(function(fn)
    { return fn\r\n!== ''; })\r\n\r\n\r\n\r\nPassengerDelay\r\n\r\nDeprecated.\r\n\r\n\r\n\r\n\r\nStartLocationFullName\r\n\r\nDeprecated."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc//json/Incidents
  tags: Transit,Buses,Incidents
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonincidents-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonincidents-get-openapi.md
- name: WMATA Incidents XML - Bus Incidents
  x-api-slug: wmata-incidents
  description: "Description\r\n\r\nReturns a set of reported bus incidents/delays
    for a given Route. Omit the\r\nRoute to return all reported items.\r\n\r\nNote
    that the Route parameter accepts only base route names and no\r\nvariations, i.e.:
    use 10A instead of 10Av1 and 10Av2.\r\n\r\nBus incidents/delays are refreshed
    once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nBusIncidents\r\n\r\n\r\nArray
    containing bus incident information (BusIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nBusIncident\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate
    and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:ss
    format (e.g.: 2014-10-28T08:13:03).\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text
    description of the delay or incident.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique
    identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description
    of the incident type. Usually\r\nDelay or Alert but is subject to change at any
    time.\r\n\r\n\r\n\r\nRoutesAffected\r\n\r\nArray containing routes affected. Routes
    listed are usually\r\nidentical to base route names (i.e.: not 10Av1 or 10Av2,
    but 10A),\r\nbut may differ from what our bus methods return."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc//BusIncidents
  tags: Transit,Buses,Incidents
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/busincidents-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/busincidents-get-openapi.md
- name: WMATA Incidents XML - Elevator/Escalator Outages
  x-api-slug: wmata-incidents
  description: "Description\r\n\r\nReturns a list of reported elevator and escalator
    outages at a\r\ngiven station. Omit the StationCode parameter to return all reported\r\noutages.\r\n\r\nNote
    that for stations with multiple platforms and therefore StationCodes\r\n(e.g.:
    Metro Center, L'Enfant Plaza, etc.), a distinct call is required for\r\neach StationCode.\r\n\r\nElevator
    and escalator outages are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncidents\r\n\r\n\r\nArray
    containing elevator/escalator outage information\r\n(ElevatorIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncident
    Elements\r\n\r\n\r\n\r\n\r\n\r\nDateOutOfServ\r\n\r\nDate and time (Eastern Standard
    Time) unit was reported out of\r\nservice. Will be in YYYY-MM-DDTHH:mm:ss format
    (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time
    (Eastern Standard Time) outage details was last\r\nupdated. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDisplayOrder\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLocationDescription\r\n\r\nFree-text
    description of the unit location within a station\r\n(e.g.: Escalator between
    mezzanine and\r\nplatform).\r\n\r\n\r\n\r\nStationCode\r\n\r\nUnit's station code.
    Use this value in other rail-related APIs\r\nto retrieve data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull
    station name, may include entrance information (e.g.:\r\nMetro Center, G and 11th
    St\r\nEntrance).\r\n\r\n\r\n\r\nSymptomCode\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nSymptomDescription\r\n\r\nDescription
    for why the unit is out of service or otherwise in\r\nreduced operation.\r\n\r\n\r\n\r\nTimeOutOfService\r\n\r\nDeprecated.
    Use the time\r\nportion of the DateOutOfServ element.\r\n\r\n\r\n\r\nUnitName\r\n\r\nUnique
    identifier for unit, by type (a single elevator and\r\nescalator may have the
    same UnitName, but no two elevators or two\r\nescalators will have the same UnitName).\r\n\r\n\r\n\r\nUnitStatus\r\n\r\nDeprecated.
    If listed here,\r\nthe unit is inoperational or otherwise impaired.\r\n\r\n\r\n\r\nUnitType\r\n\r\nType
    of unit. Will be ELEVATOR\r\nor ESCALATOR."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc//ElevatorIncidents
  tags: Transit,Elevator,Incidents
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/elevatorincidents-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/elevatorincidents-get-openapi.md
- name: WMATA Incidents XML - Rail Incidents
  x-api-slug: wmata-incidents
  description: "Description\r\n\r\nReturns reported rail incidents (significant disruptions
    and delays to\r\nnormal service). The data is identical to WMATA's Metrorail Service
    Status\r\nfeed.\r\n\r\nRail incidents are refreshed once every 20 to 30 seconds
    approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nIncidents\r\n\r\n\r\nArray
    containing rail disruption information (Incident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nIncident
    Elements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard
    Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).\r\n\r\n\r\n\r\nDelaySeverity\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text
    description of the incident.\r\n\r\n\r\n\r\nEmergencyText\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nEndLocationFullName\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique
    identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description
    of the incident type. Usually Delay or\r\nAlert but is subject to change at any
    time.\r\n\r\n\r\n\r\nLinesAffected\r\n\r\nSemi-colon and space separated list
    of line codes (e.g.:\r\nRD; or BL;\r\nOR; or BL; OR; RD;). We do\r\nplan to update
    this to return something more reasonable like an\r\narray, but until then, use
    code similar to the following:\r\n\r\n\"RD; GR; BL;\".split(/;[\\s]?/).filter(function(fn)
    { return fn\r\n!== ''; })\r\n\r\n\r\n\r\nPassengerDelay\r\n\r\nDeprecated.\r\n\r\n\r\n\r\n\r\nStartLocationFullName\r\n\r\nDeprecated."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc//Incidents
  tags: Transit,Incidents
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/incidents-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/incidents-get-openapi.md
- name: WMATA Incidents
  x-api-slug: wmata-incidents
  description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
    to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Incidents.svc
  tags: Washington Metropolitan Area Transit Authority
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
- name: WMATA Rail Station Information JSON - Lines
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns information about all rail lines.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nLines\r\n\r\n\r\nArray
    containing line information (Line).\r\n\r\n\r\n\r\n\r\n\r\n\r\nLine Elements\r\n\r\n\r\n\r\n\r\n\r\nDisplayName\r\n\r\nFull
    name of line color.\r\n\r\n\r\n\r\nEndStationCode\r\n\r\nEnd station code. For
    example, will be E10 (Greenbelt) for the\r\nGreen Line, B11 (Glenmont) for the
    Red Line, etc. Use this value in\r\nother rail-related APIs to retrieve data about
    a station.\r\n\r\n\r\n\r\nInternalDestination1\r\n\r\nIntermediate terminal station
    code. During normal service, some\r\ntrains on some lines might end their trip
    prior to the\r\nStartStationCode or EndStationCode. A good example is on the Red\r\nLine
    where some trains stop at A11 (Grosvenor) or B08 (Silver\r\nSpring). Empty string
    if not defined.\r\n\r\n\r\n\r\nInternalDestination2\r\n\r\nSimilar to InternalDestination1.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV).\r\n\r\n\r\n\r\nStartStationCode\r\n\r\nStart
    station code. For example, will be F11 (Branch Avenue)\r\nfor the Green Line,
    A15 (Shady Grove) for the Red Line, etc. Use\r\nthis value in other rail-related
    APIs to retrieve data about a\r\nstation."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jLines
  tags: Transit,Lines
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjlines-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjlines-get-openapi.md
- name: WMATA Rail Station Information JSON - Parking Information
  x-api-slug: wmata-rail-station-information
  description: |-
    Description

    Returns parking information at a station based on a given StationCode. Omit
    the StationCode to return parking information for all stations.

    If a station has no parking, the StationsParking element will contain no
    child elements.

    Response Elements




    Element

    Description





    StationsParking


    Array containing station parking information (StationParking).






    StationParking
    Elements





    Code

    Station code. Useful when returning parking information for all
    stations. Use this value in other rail-related APIs to retrieve
    data about a station.



    Notes

    When not NULL, provides additional parking resources such as
    nearby lots.



    AllDayParking


    Structure describing all-day
    parking options.




    ShortTermParking


    Structure describing short-term
    parking options.






    AllDayParking
    Elements





    TotalCount

    Number of all-day parking spots available at a station.



    RiderCost

    All-day cost per day (weekday) for Metro riders. NULL when no all-day
    spots are available. For most stations, this value is identical to
    the NonRiderCost.

    For cases where the NonRiderCost is different, the lower cost per
    day requires a valid rail trip using a SmarTrip&reg; card
    originating from a station other than the one where the patron
    parked. To receive this lower rate, patrons must pay for their
    parking with the same SmarTrip&reg; card used to enter/exit
    Metrorail, and must exit the parking lot within two hours of
    exiting Metrorail.



    NonRiderCost

    All-day cost per day (weekday) for non-Metro riders. NULL when no all-day
    spots are available.





    ShortTermParking Elements





    SaturdayRiderCost

    Similar to RiderCost, except denoting Saturday prices.



    SaturdayNonRiderCost

    Similar to NonRiderCost, except denoting Saturday prices.



    TotalCount

    Number of short-term parking spots available at a station
    (parking meters).



    Notes

    Misc. information relating to short-term parking. NULL when no
    short-term spots are available.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jStationParking
  tags: Transit,Stations,Parking
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationparking-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationparking-get-openapi.md
- name: WMATA Rail Station Information JSON - Path Between Stations
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a set of ordered stations and distances
    between two stations on the\r\nsame line.\r\n\r\nNote that this method is not
    suitable on its own as a pathfinding solution\r\nbetween stations.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPath\r\n\r\n\r\nArray
    containing path details (MetroPathItem)\r\n\r\n\r\n\r\n\r\n\r\n\r\nMetroPathItem\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDistanceToPrev\r\n\r\nDistance
    in feet to the previous station in the list.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) this station's
    platform is on.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrdered sequence number.\r\n\r\n\r\n\r\nStationCode\r\n\r\nStation
    code for this station. Use this value in other\r\nrail-related APIs to retrieve
    data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull name for this station,
    as shown on the WMATA website."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jPath
  tags: Transit,Paths
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjpath-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjpath-get-openapi.md
- name: WMATA Rail Station Information JSON - Station Entrances
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a list of nearby station entrances based
    on latitude, longitude, and\r\nradius (meters). Omit search parameters to return
    all station entrances.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nEntrances\r\n\r\n\r\nArray
    containing detailed information about station entrances\r\n(StationEntrance).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationEntrance
    Elements\r\n\r\n\r\n\r\n\r\n\r\nDescription\r\n\r\nAdditional information for
    the entrance, if available.\r\nCurrently available data usually shows the same
    value as the Name\r\nelement.\r\n\r\n\r\n\r\nID\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nName
    of the entrance (usually the station name and nearest\r\nintersection).\r\n\r\n\r\n\r\nStationCode1\r\n\r\nThe
    station code associated with this entrance. Use this value\r\nin other rail-related
    APIs to retrieve data about a station.\r\n\r\n\r\n\r\nStationCode2\r\n\r\nFor
    stations containing multiple platforms (e.g.: Gallery\r\nPlace, Fort Totten, L'Enfant
    Plaza, and Metro Center), the other\r\nstation code."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jStationEntrances
  tags: Transit,Stations,Entrances
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationentrances-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationentrances-get-openapi.md
- name: WMATA Rail Station Information JSON - Station Information
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns station location and address information
    based on a given\r\nStationCode.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nAddress\r\n\r\n\r\nStructure
    describing address information.\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code. Repeated
    from input.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLineCode1\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) served by this
    station.\r\n\r\n\r\n\r\nLineCode2\r\n\r\nAdditional line served by this station.
    This is often the case\r\nwhen stations have multiple platforms (e.g.: Gallery
    Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center).\r\n\r\n\r\n\r\nLineCode3\r\n\r\nSimilar
    to function as LineCodeX.\r\n\r\n\r\n\r\nLineCode4\r\n\r\nSimilar to function
    as LineCodeX. Currently not in use.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStation
    name.\r\n\r\n\r\n\r\nStationTogether1\r\n\r\nFor stations with multiple platforms
    (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center), the additional\r\nStationCode
    will be listed here.\r\n\r\n\r\n\r\nStationTogether2\r\n\r\nSimilar in function
    to StationTogether2. Currently not in\r\nuse.\r\n\r\n\r\n\r\n\r\n\r\nAddress Elements\r\n\r\n\r\n\r\n\r\n\r\nCity\r\n\r\nCity.\r\n\r\n\r\n\r\nState\r\n\r\nState
    (abbreviated).\r\n\r\n\r\n\r\nStreet\r\n\r\nStreet address (for GPS use).\r\n\r\n\r\n\r\nZip\r\n\r\nZip
    code."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jStationInfo
  tags: Transit,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationinfo-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationinfo-get-openapi.md
- name: WMATA Rail Station Information JSON - Station List
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a list of station location and address
    information based on a given\r\nLineCode. Omit the LineCode to return all stations.
    The response is an array of\r\nobjects identical to those returned in the Station
    Information method.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStations\r\n\r\n\r\nArray
    containing station information (Station).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStation Elements\r\n\r\n\r\n\r\n\r\n\r\nAddress\r\n\r\n\r\nStructure
    describing address information.\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code. Repeated
    from input.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLineCode1\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) served by this
    station.\r\n\r\n\r\n\r\nLineCode2\r\n\r\nAdditional line served by this station.
    This is often the case\r\nwhen stations have multiple platforms (e.g.: Gallery
    Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center).\r\n\r\n\r\n\r\nLineCode3\r\n\r\nSimilar
    to function as LineCodeX.\r\n\r\n\r\n\r\nLineCode4\r\n\r\nSimilar to function
    as LineCodeX. Currently not in use.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStation
    name.\r\n\r\n\r\n\r\nStationTogether1\r\n\r\nFor stations with multiple platforms
    (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center), the additional\r\nStationCode
    will be listed here.\r\n\r\n\r\n\r\nStationTogether2\r\n\r\nSimilar in function
    to StationTogether2. Currently not in\r\nuse.\r\n\r\n\r\n\r\n\r\n\r\nAddress Elements\r\n\r\n\r\n\r\n\r\n\r\nCity\r\n\r\nCity.\r\n\r\n\r\n\r\nState\r\n\r\nState
    (abbreviated).\r\n\r\n\r\n\r\nStreet\r\n\r\nStreet address (for GPS use).\r\n\r\n\r\n\r\nZip\r\n\r\nZip
    code."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jStations
  tags: Transit,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstations-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstations-get-openapi.md
- name: WMATA Rail Station Information JSON - Station Timings
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns opening and scheduled first/last train
    times based on a given\r\nStationCode. Omit the StationCode to return timing information
    for all\r\nstations.\r\n\r\nNote that for stations with multiple platforms (e.g.:
    Metro Center, L'Enfant\r\nPlaza, etc.), a distinct call is required for each StationCode
    to retrieve the\r\nfull set of train times at such stations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStationTimes\r\n\r\n\r\nArray
    containing station timing information (StationTime).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationTime\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation
    code for this station. Use this value in other\r\nrail-related APIs to retrieve
    data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull name of the station.\r\n\r\n\r\n\r\n*Day
    Elements\r\n\r\n\r\nContainer elements containing timing information based on\r\nday
    of the week.\r\n\r\n\r\n\r\n\r\n\r\n\r\nMonday/Tuesday/Wednesday/etc.\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nOpeningTime\r\n\r\nStation
    opening time. Format is HH:mm.\r\n\r\n\r\n\r\nFirstTrains\r\n\r\n\r\nStructure
    containing first train\r\ninformation.\r\n\r\n\r\n\r\n\r\nLastTrains\r\n\r\n\r\nStructure
    containing last train\r\ninformation.\r\n\r\n\r\n\r\n\r\n\r\n\r\nFirstTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nFirst
    train leaves the station at this time. Format is\r\nHH:mm.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation
    code for the train's destination. Use this value in\r\nother rail-related APIs
    to retrieve data about a station.\r\n\r\n\r\n\r\n\r\n\r\nLastTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nLast
    train leaves the station at this time. Format is HH:mm.\r\nNote that when the
    time is AM, it signifies the next day. For\r\nexample, a value of 02:30 under
    a Saturday element means the last\r\ntrain leaves on Sunday at 2:30 AM.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation
    code for the train's destination. Use this value in\r\nother rail-related APIs
    to retrieve data about a station."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jStationTimes
  tags: Transit,Stations,Times
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationtimes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjstationtimes-get-openapi.md
- name: WMATA Rail Station Information JSON - Station to Station Information
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a distance, fare information, and estimated
    travel time between any\r\ntwo stations, including those on different lines. Omit
    both parameters to\r\nretrieve data for all stations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStationToStationInfos\r\n\r\n\r\nArray
    containing station to station information (StationToStationInfo).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationToStationInfo
    Elements\r\n\r\n\r\n\r\n\r\n\r\nCompositeMiles\r\n\r\nDistance in miles from the
    source to destination station.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nDestination
    station code. Use this value in other rail-related\r\nAPIs to retrieve data about
    a station.\r\n\r\n\r\n\r\nRailFare\r\n\r\n\r\nStructure containing fare information.\r\n\r\n\r\n\r\n\r\nRailTime\r\n\r\nEstimated
    travel time (schedule time) in minutes between the source and\r\ndestination station.
    This is not correlated to minutes (Min) in Real-Time Rail Predictions.\r\n\r\n\r\n\r\nSourceStation\r\n\r\nOrigin
    station code. Use this value in other rail-related APIs\r\nto retrieve data about
    a station.\r\n\r\n\r\n\r\n\r\n\r\nRailFare Elements\r\n\r\n\r\n\r\n\r\n\r\nOffPeakTime\r\n\r\nFare
    during off-peak times (times other than the ones described\r\nbelow).\r\n\r\n\r\n\r\nPeakTime\r\n\r\nFare
    during peak times (weekdays from opening to 9:30 AM and\r\n3-7 PM, and weekends
    from midnight to closing).\r\n\r\n\r\n\r\nSeniorDisabled\r\n\r\n\r\nReduced fare
    for senior citizens or\r\npeople with disabilities."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//json/jSrcStationToDstStationInfo
  tags: Transit,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjsrcstationtodststationinfo-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjsrcstationtodststationinfo-get-openapi.md
- name: WMATA Rail Station Information XML - Lines
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns information about all rail lines.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nLines\r\n\r\n\r\nArray
    containing line information (Line).\r\n\r\n\r\n\r\n\r\n\r\n\r\nLine Elements\r\n\r\n\r\n\r\n\r\n\r\nDisplayName\r\n\r\nFull
    name of line color.\r\n\r\n\r\n\r\nEndStationCode\r\n\r\nEnd station code. For
    example, will be E10 (Greenbelt) for the\r\nGreen Line, B11 (Glenmont) for the
    Red Line, etc. Use this value in\r\nother rail-related APIs to retrieve data about
    a station.\r\n\r\n\r\n\r\nInternalDestination1\r\n\r\nIntermediate terminal station
    code. During normal service, some\r\ntrains on some lines might end their trip
    prior to the\r\nStartStationCode or EndStationCode. A good example is on the Red\r\nLine
    where some trains stop at A11 (Grosvenor) or B08 (Silver\r\nSpring). Empty string
    if not defined.\r\n\r\n\r\n\r\nInternalDestination2\r\n\r\nSimilar to InternalDestination1.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV).\r\n\r\n\r\n\r\nStartStationCode\r\n\r\nStart
    station code. For example, will be F11 (Branch Avenue)\r\nfor the Green Line,
    A15 (Shady Grove) for the Red Line, etc. Use\r\nthis value in other rail-related
    APIs to retrieve data about a\r\nstation."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//Lines
  tags: Transit,Lines
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/lines-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/lines-get-openapi.md
- name: WMATA Rail Station Information XML - Parking Information
  x-api-slug: wmata-rail-station-information
  description: |-
    Description

    Returns parking information at a station based on a given StationCode. Omit
    the StationCode to return parking information for all stations.

    If a station has no parking, the StationsParking element will contain no
    child elements.

    Response Elements




    Element

    Description





    StationsParking


    Array containing station parking information (StationParking).






    StationParking
    Elements





    Code

    Station code. Useful when returning parking information for all
    stations. Use this value in other rail-related APIs to retrieve
    data about a station.



    Notes

    When not NULL, provides additional parking resources such as
    nearby lots.



    AllDayParking


    Structure describing all-day
    parking options.




    ShortTermParking


    Structure describing short-term
    parking options.






    AllDayParking
    Elements





    TotalCount

    Number of all-day parking spots available at a station.



    RiderCost

    All-day cost per day (weekday) for Metro riders. NULL when no all-day
    spots are available. For most stations, this value is identical to
    the NonRiderCost.

    For cases where the NonRiderCost is different, the lower cost per
    day requires a valid rail trip using a SmarTrip&reg; card
    originating from a station other than the one where the patron
    parked. To receive this lower rate, patrons must pay for their
    parking with the same SmarTrip&reg; card used to enter/exit
    Metrorail, and must exit the parking lot within two hours of
    exiting Metrorail.



    NonRiderCost

    All-day cost per day (weekday) for non-Metro riders. NULL when no all-day
    spots are available.





    ShortTermParking Elements





    SaturdayRiderCost

    Similar to RiderCost, except denoting Saturday prices.



    SaturdayNonRiderCost

    Similar to NonRiderCost, except denoting Saturday prices.



    TotalCount

    Number of short-term parking spots available at a station
    (parking meters).



    Notes

    Misc. information relating to short-term parking. NULL when no
    short-term spots are available.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//StationParking
  tags: Transit,Stations,Parking
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationparking-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationparking-get-openapi.md
- name: WMATA Rail Station Information XML - Path Between Stations
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a set of ordered stations and distances
    between two stations on the\r\nsame line.\r\n\r\nNote that this method is not
    suitable on its own as a pathfinding solution\r\nbetween stations.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPath\r\n\r\n\r\nArray
    containing path details (MetroPathItem)\r\n\r\n\r\n\r\n\r\n\r\n\r\nMetroPathItem\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDistanceToPrev\r\n\r\nDistance
    in feet to the previous station in the list.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) this station's
    platform is on.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrdered sequence number.\r\n\r\n\r\n\r\nStationCode\r\n\r\nStation
    code for this station. Use this value in other\r\nrail-related APIs to retrieve
    data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull name for this station,
    as shown on the WMATA website."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//Path
  tags: Transit,Paths
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/path-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/path-get-openapi.md
- name: WMATA Rail Station Information XML - Station Entrances
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a list of nearby station entrances based
    on latitude, longitude, and\r\nradius (meters). Omit search parameters to return
    all station entrances.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nEntrances\r\n\r\n\r\nArray
    containing detailed information about station entrances\r\n(StationEntrance).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationEntrance
    Elements\r\n\r\n\r\n\r\n\r\n\r\nDescription\r\n\r\nAdditional information for
    the entrance, if available.\r\nCurrently available data usually shows the same
    value as the Name\r\nelement.\r\n\r\n\r\n\r\nID\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nName
    of the entrance (usually the station name and nearest\r\nintersection).\r\n\r\n\r\n\r\nStationCode1\r\n\r\nThe
    station code associated with this entrance. Use this value\r\nin other rail-related
    APIs to retrieve data about a station.\r\n\r\n\r\n\r\nStationCode2\r\n\r\nFor
    stations containing multiple platforms (e.g.: Gallery\r\nPlace, Fort Totten, L'Enfant
    Plaza, and Metro Center), the other\r\nstation code."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//StationEntrances
  tags: Transit,Stations,Entrances
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationentrances-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationentrances-get-openapi.md
- name: WMATA Rail Station Information XML - Station Information
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns station location and address information
    based on a given\r\nStationCode.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nAddress\r\n\r\n\r\nStructure
    describing address information.\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code. Repeated
    from input.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLineCode1\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) served by this
    station.\r\n\r\n\r\n\r\nLineCode2\r\n\r\nAdditional line served by this station.
    This is often the case\r\nwhen stations have multiple platforms (e.g.: Gallery
    Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center).\r\n\r\n\r\n\r\nLineCode3\r\n\r\nSimilar
    to function as LineCodeX.\r\n\r\n\r\n\r\nLineCode4\r\n\r\nSimilar to function
    as LineCodeX. Currently not in use.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStation
    name.\r\n\r\n\r\n\r\nStationTogether1\r\n\r\nFor stations with multiple platforms
    (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center), the additional\r\nStationCode
    will be listed here.\r\n\r\n\r\n\r\nStationTogether2\r\n\r\nSimilar in function
    to StationTogether2. Currently not in\r\nuse.\r\n\r\n\r\n\r\n\r\n\r\nAddress Elements\r\n\r\n\r\n\r\n\r\n\r\nCity\r\n\r\nCity.\r\n\r\n\r\n\r\nState\r\n\r\nState
    (abbreviated).\r\n\r\n\r\n\r\nStreet\r\n\r\nStreet address (for GPS use).\r\n\r\n\r\n\r\nZip\r\n\r\nZip
    code."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//StationInfo
  tags: Transit,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationinfo-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationinfo-get-openapi.md
- name: WMATA Rail Station Information XML - Station List
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a list of station location and address
    information based on a given\r\nLineCode. Omit the LineCode to return all stations.
    The response is an array of\r\nobjects identical to those returned in the Station
    Information method.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStations\r\n\r\n\r\nArray
    containing station information (Station).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStation Elements\r\n\r\n\r\n\r\n\r\n\r\nAddress\r\n\r\n\r\nStructure
    describing address information.\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code. Repeated
    from input.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLineCode1\r\n\r\nTwo-letter
    abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) served by this
    station.\r\n\r\n\r\n\r\nLineCode2\r\n\r\nAdditional line served by this station.
    This is often the case\r\nwhen stations have multiple platforms (e.g.: Gallery
    Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center).\r\n\r\n\r\n\r\nLineCode3\r\n\r\nSimilar
    to function as LineCodeX.\r\n\r\n\r\n\r\nLineCode4\r\n\r\nSimilar to function
    as LineCodeX. Currently not in use.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStation
    name.\r\n\r\n\r\n\r\nStationTogether1\r\n\r\nFor stations with multiple platforms
    (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center), the additional\r\nStationCode
    will be listed here.\r\n\r\n\r\n\r\nStationTogether2\r\n\r\nSimilar in function
    to StationTogether2. Currently not in\r\nuse.\r\n\r\n\r\n\r\n\r\n\r\nAddress Elements\r\n\r\n\r\n\r\n\r\n\r\nCity\r\n\r\nCity.\r\n\r\n\r\n\r\nState\r\n\r\nState
    (abbreviated).\r\n\r\n\r\n\r\nStreet\r\n\r\nStreet address (for GPS use).\r\n\r\n\r\n\r\nZip\r\n\r\nZip
    code."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//Stations
  tags: Transit,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stations-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stations-get-openapi.md
- name: WMATA Rail Station Information XML - Station Timings
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns opening and scheduled first/last train
    times based on a given\r\nStationCode. Omit the StationCode to return timing information
    for all\r\nstations.\r\n\r\nNote that for stations with multiple platforms (e.g.:
    Metro Center, L'Enfant\r\nPlaza, etc.), a distinct call is required for each StationCode
    to retrieve the\r\nfull set of train times at such stations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStationTimes\r\n\r\n\r\nArray
    containing station timing information (StationTime).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationTime\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation
    code for this station. Use this value in other\r\nrail-related APIs to retrieve
    data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull name of the station.\r\n\r\n\r\n\r\n*Day
    Elements\r\n\r\n\r\nContainer elements containing timing information based on\r\nday
    of the week.\r\n\r\n\r\n\r\n\r\n\r\n\r\nMonday/Tuesday/Wednesday/etc.\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nOpeningTime\r\n\r\nStation
    opening time. Format is HH:mm.\r\n\r\n\r\n\r\nFirstTrains\r\n\r\n\r\nStructure
    containing first train\r\ninformation.\r\n\r\n\r\n\r\n\r\nLastTrains\r\n\r\n\r\nStructure
    containing last train\r\ninformation.\r\n\r\n\r\n\r\n\r\n\r\n\r\nFirstTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nFirst
    train leaves the station at this time. Format is\r\nHH:mm.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation
    code for the train's destination. Use this value in\r\nother rail-related APIs
    to retrieve data about a station.\r\n\r\n\r\n\r\n\r\n\r\nLastTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nLast
    train leaves the station at this time. Format is HH:mm.\r\nNote that when the
    time is AM, it signifies the next day. For\r\nexample, a value of 02:30 under
    a Saturday element means the last\r\ntrain leaves on Sunday at 2:30 AM.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation
    code for the train's destination. Use this value in\r\nother rail-related APIs
    to retrieve data about a station."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//StationTimes
  tags: Transit,Stations,Times
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationtimes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/stationtimes-get-openapi.md
- name: WMATA Rail Station Information XML - Station to Station Information
  x-api-slug: wmata-rail-station-information
  description: "Description\r\n\r\nReturns a distance, fare information, and estimated
    travel time between any\r\ntwo stations, including those on different lines. Omit
    both parameters to\r\nretrieve data for all stations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStationToStationInfos\r\n\r\n\r\nArray
    containing station to station information (StationToStationInfo).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationToStationInfo
    Elements\r\n\r\n\r\n\r\n\r\n\r\nCompositeMiles\r\n\r\nDistance in miles from the
    source to destination station.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nDestination
    station code. Use this value in other rail-related\r\nAPIs to retrieve data about
    a station.\r\n\r\n\r\n\r\nRailFare\r\n\r\n\r\nStructure containing fare information.\r\n\r\n\r\n\r\n\r\nRailTime\r\n\r\nEstimated
    travel time (schedule time) in minutes between the source and destination station.
    This is not correlated to minutes (Min) in Real-Time Rail Predictions.\r\n\r\n\r\n\r\nSourceStation\r\n\r\nOrigin
    station code. Use this value in other rail-related APIs\r\nto retrieve data about
    a station.\r\n\r\n\r\n\r\n\r\n\r\nRailFare Elements\r\n\r\n\r\n\r\n\r\n\r\nOffPeakTime\r\n\r\nFare
    during off-peak times (times other than the ones described\r\nbelow).\r\n\r\n\r\n\r\nPeakTime\r\n\r\nFare
    during peak times (weekdays from opening to 9:30 AM and\r\n3-7 PM, and weekends
    from midnight to closing).\r\n\r\n\r\n\r\nSeniorDisabled\r\n\r\n\r\nReduced fare
    for senior citizens or\r\npeople with disabilities."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc//SrcStationToDstStationInfo
  tags: Transit,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/srcstationtodststationinfo-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/srcstationtodststationinfo-get-openapi.md
- name: WMATA Rail Station Information
  x-api-slug: wmata-rail-station-information
  description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
    to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Rail.svc
  tags: Washington Metropolitan Area Transit Authority
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
- name: WMATA Real-Time Bus Predictions Get Predictions
  x-api-slug: wmata-realtime-bus-predictions
  description: "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray
    containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull
    name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
    a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction,
    but a different value for the same\r\nroute signifies that the buses are traveling
    in opposite\r\ndirections. Use the DirectionText element to show the actual\r\ndestination
    of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly description
    of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes
    until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase
    route name as shown on the bus. This can be used in other\r\nbus-related methods.
    Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1
    and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier.
    This can be correlated with the data in our\r\nbus schedule information as well
    as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This can be
    correlated with results returned\r\nfrom bus positions."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//NextBusService.svc//Predictions
  tags: Predictions
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/predictions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/predictions-get-openapi.md
- name: WMATA Real-Time Bus Predictions Get Predictions
  x-api-slug: wmata-realtime-bus-predictions
  description: "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray
    containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull
    name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
    a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction,
    but a different value for the same\r\nroute signifies that the buses are traveling
    in opposite\r\ndirections. Use the DirectionText element to show the actual\r\ndestination
    of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly description
    of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes
    until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase
    route name as shown on the bus. This can be used in other\r\nbus-related methods.
    Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1
    and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier.
    This can be correlated with the data in our\r\nbus schedule information as well
    as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This can be
    correlated with results returned\r\nfrom bus positions."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//NextBusService.svc//json/jPredictions
  tags: Predictions
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjpredictions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsonjpredictions-get-openapi.md
- name: WMATA Real-Time Bus Predictions
  x-api-slug: wmata-realtime-bus-predictions
  description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
    to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//NextBusService.svc
  tags: Washington Metropolitan Area Transit Authority
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
- name: WMATA Real-Time Rail Predictions JSON - Next Trains
  x-api-slug: wmata-realtime-rail-predictions
  description: "Description\r\n\r\nReturns next train arrival information for one
    or more stations. Will return\r\nan empty set of results when no predictions are
    available. Use All for the StationCodes parameter to return predictions for\r\nall
    stations.\r\n\r\nFor terminal stations (e.g.: Greenbelt, Shady Grove, etc.), predictions
    may\r\nbe displayed twice.\r\n\r\nSome stations have two platforms (e.g.: Gallery
    Place, Fort Totten, L'Enfant\r\nPlaza, and Metro Center). To retrieve complete
    predictions for these stations,\r\nbe sure to pass in both StationCodes.\r\n\r\nFor
    trains with no passengers, the DestinationName will be No Passenger.\r\n\r\nNext
    train arrival information is refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nTrains\r\n\r\n\r\nArray
    containing train prediction information (AIMPredictionTrainInfo).\r\n\r\n\r\n\r\n\r\n\r\n\r\nAIMPredictionTrainInfo\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nCar\r\n\r\nNumber
    of cars on a train, usually 6 or 8, but might also\r\nreturn - or NULL.\r\n\r\n\r\n\r\nDestination\r\n\r\nAbbreviated
    version of the final destination for a train. This\r\nis similar to what is displayed
    on the signs at stations.\r\n\r\n\r\n\r\nDestinationCode\r\n\r\nDestination station
    code. Can be NULL. Use this value in other\r\nrail-related APIs to retrieve data
    about a station.\r\n\r\n\r\n\r\nDestinationName\r\n\r\nWhen DestinationCode is
    populated, this is the full name of the\r\ndestination station, as shown on the
    WMATA website.\r\n\r\n\r\n\r\nGroup\r\n\r\nDenotes the track this train is on,
    but does not necessarily\r\nequate to Track 1 or Track 2. With the exception of
    terminal\r\nstations, predictions at the same station with different Group\r\nvalues
    refer to trains on different tracks.\r\n\r\n\r\n\r\nLine\r\n\r\nTwo-letter abbreviation
    for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV). May also be blank or No for\r\ntrains
    with no passengers.\r\n\r\n\r\n\r\nLocationCode\r\n\r\nStation code for where
    the train is arriving. Useful when\r\npassing in All as the StationCodes\r\nparameter.
    Use this value in other rail-related APIs to retrieve\r\ndata about a station.\r\n\r\n\r\n\r\nLocationName\r\n\r\nFull
    name of the station where the train is arriving. Useful\r\nwhen passing in All
    as the\r\nStationCodes parameter.\r\n\r\n\r\n\r\nMin\r\n\r\nMinutes until arrival.
    Can be a numeric value, ARR (arriving), BRD (boarding), ---, or empty."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//StationPrediction.svc//json/GetPrediction/{StationCodes}
  tags: Transit,Rail,Prediction,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsongetpredictionstationcodes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/jsongetpredictionstationcodes-get-openapi.md
- name: WMATA Real-Time Rail Predictions XML - Next Trains
  x-api-slug: wmata-realtime-rail-predictions
  description: "Description\r\n\r\nReturns next train arrival information for one
    or more stations. Will return\r\nan empty set of results when no predictions are
    available. Use All for the StationCodes parameter to return predictions for\r\nall
    stations.\r\n\r\nFor terminal stations (e.g.: Greenbelt, Shady Grove, etc.), predictions
    may\r\nbe displayed twice.\r\n\r\nSome stations have two platforms (e.g.: Gallery
    Place, Fort Totten, L'Enfant\r\nPlaza, and Metro Center). To retrieve complete
    predictions for these stations,\r\nbe sure to pass in both StationCodes.\r\n\r\nFor
    trains with no passengers, the DestinationName will be No Passenger.\r\n\r\nNext
    train arrival information is refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nTrains\r\n\r\n\r\nArray
    containing train prediction information (AIMPredictionTrainInfo).\r\n\r\n\r\n\r\n\r\n\r\n\r\nAIMPredictionTrainInfo\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nCar\r\n\r\nNumber
    of cars on a train, usually 6 or 8, but might also\r\nreturn - or NULL.\r\n\r\n\r\n\r\nDestination\r\n\r\nAbbreviated
    version of the final destination for a train. This\r\nis similar to what is displayed
    on the signs at stations.\r\n\r\n\r\n\r\nDestinationCode\r\n\r\nDestination station
    code. Can be NULL. Use this value in other\r\nrail-related APIs to retrieve data
    about a station.\r\n\r\n\r\n\r\nDestinationName\r\n\r\nWhen DestinationCode is
    populated, this is the full name of the\r\ndestination station, as shown on the
    WMATA website.\r\n\r\n\r\n\r\nGroup\r\n\r\nDenotes the track this train is on,
    but does not necessarily\r\nequate to Track 1 or Track 2. With the exception of
    terminal\r\nstations, predictions at the same station with different Group\r\nvalues
    refer to trains on different tracks.\r\n\r\n\r\n\r\nLine\r\n\r\nTwo-letter abbreviation
    for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV). May also be blank or No for\r\ntrains
    with no passengers.\r\n\r\n\r\n\r\nLocationCode\r\n\r\nStation code for where
    the train is arriving. Useful when\r\npassing in All as the StationCodes\r\nparameter.
    Use this value in other rail-related APIs to retrieve\r\ndata about a station.\r\n\r\n\r\n\r\nLocationName\r\n\r\nFull
    name of the station where the train is arriving. Useful\r\nwhen passing in All
    as the\r\nStationCodes parameter.\r\n\r\n\r\n\r\nMin\r\n\r\nMinutes until arrival.
    Can be a numeric value, ARR (arriving), BRD (boarding), ---, or empty."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//StationPrediction.svc//GetPrediction/{StationCodes}
  tags: Transit,Rail,Prediction,Stations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/getpredictionstationcodes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/getpredictionstationcodes-get-openapi.md
- name: WMATA Real-Time Rail Predictions
  x-api-slug: wmata-realtime-rail-predictions
  description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
    to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//StationPrediction.svc
  tags: Washington Metropolitan Area Transit Authority
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
- name: WMATA Train Positions Live Train Positions
  x-api-slug: wmata-train-positions
  description: |-
    Description

    Returns uniquely identifiable trains in service and what track circuits they currently occupy. Will return an empty set of results when no positions are available.

    Data is refreshed once every 7-10 seconds.
    Please refer to this page for additional details.

    Response Elements




    Element

    Description





    TrainPositions


    Array containing train position information (TrainPosition).






    TrainPosition Elements





    CarCount

    Number of cars.  Can sometimes be 0 when there is no data available.



    CircuitId

    The circuit identifier the train is currently on.  This identifier can be referenced from the Standard Routes method.



    DestinationStationCode

    Destination station code. Can be NULL. Use this value in other rail-related APIs to retrieve data about a station.  Note that this value may sometimes differ from the destination station code returned by our Next Trains methods.



    DirectionNum

    The direction of movement regardless of which track the train is on.  Valid values are 1 or 2.  Generally speaking, trains with direction 1 are northbound/eastbound, while trains with direction 2 are southbound/westbound.



    LineCode

    Two-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR, or SV). May also be NULL in certain cases.



    SecondsAtLocation

    Approximate "dwell time".  This is not an exact value, but can be used to determine how long a train has been reported at the same track circuit.



    ServiceType

    Service Type of a train, can be any of the following Service Types



    TrainId

    Uniquely identifiable internal train identifier.





    Service Types





    NoPassengers

    This is a non-revenue train with no passengers on board.  Note that this designation of NoPassengers does not necessarily correlate with PIDS "No Passengers".  As of 08/22/2016, this functionality has been reinstated to include all non-revenue vehicles, with minor exceptions.



    Normal

    This is a normal revenue service train.



    Special

    This is a special revenue service train with an unspecified line and destination.  This is more prevalent during scheduled track work.



    Unknown

    This often denotes cases with unknown data or work vehicles.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//TrainPositions//TrainPositions
  tags: Transit,Subway,Positions
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/trainpositions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/trainpositions-get-openapi.md
- name: WMATA Train Positions Standard Routes
  x-api-slug: wmata-train-positions
  description: "Description\r\n\r\nReturns an ordered list of mostly revenue (and
    some lead) track circuits, arranged by line and track number.  This data does
    not change frequently and should be cached for a reasonable amount of time.\r\nPlease
    refer to this page for additional details.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStandardRoutes\r\n\r\n\r\nArray
    containing revenue line information (StandardRoute).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStandardRoute
    Elements\r\n\r\n\r\n\r\n\r\n\r\nLineCode\r\n\r\nAbbreviation for the revenue line.
    \ Note that this also includes YLRP (Yellow Line Rush Plus).\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray
    containing ordered track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\nTrackNum\r\n\r\nTrack
    number (1 or 2).\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit Elements\r\n\r\n\r\n        \r\n\r\n\r\nCircuitId\r\n\r\nAn
    internal system-wide uniquely identifiable circuit number.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder
    in which the circuit appears for the given line and track.  Sequences go from
    West to East and South to North.\r\n        \r\n\r\n\r\nStationCode\r\n\r\nIf
    the circuit is at a station, this value will represent the station code.  Otherwise,
    it will be be NULL. Use this value in other rail-related APIs to retrieve data
    about a station."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//TrainPositions//StandardRoutes
  tags: Transit,Subway,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/standardroutes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/standardroutes-get-openapi.md
- name: WMATA Train Positions Track Circuits
  x-api-slug: wmata-train-positions
  description: "Description\r\n\r\nReturns a list of all track circuits including
    those on pocket tracks and crossovers.  Each track circuit may include references
    to its right and left neighbors.\r\nPlease refer to this page for additional details.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray
    containing track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit
    Elements\r\n\r\n\r\n\r\n\r\n\r\nCircuitId\r\n\r\nAn internal system-wide uniquely
    identifiable circuit number.\r\n\r\n\r\n\r\nNeighbors\r\n\r\n\r\nArray containing
    track circuit neighbor information (TrackCircuitNeighbor).  Note that some track
    circuits have no neighbors in one direction.  All track circuits have at least
    one neighbor.\r\n\r\n\r\n\r\n\r\nTrack\r\n\r\nTrack number.  1 and 2 denote \"main\"
    lines, while 0 and 3 are connectors (between different types of tracks) and pocket
    tracks, respectively.\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuitNeighbor Elements\r\n\r\n\r\n\r\n\r\n\r\nCircuitIds\r\n\r\n\r\nArray
    containing neighboring circuit ids.\r\n\r\n\r\n\r\n\r\nNeighborType\r\n\r\nLeft
    or Right neighbor group.  Generally speaking, left neighbors are to the west and
    south, while right neighbors are to the east/north.\r\n\r\n\r\n\r\n\r\nNeighbor
    Notes\r\n\r\nGiven the hypothetical example below, note that CircuitId 8 has two
    right neighbors - 4 and 3.  Similarly, CircuitId 6 has two left neighbors - 5
    and 7.\r\n\r\n\r\n\r\n\r\n\r\nbackground\r\n\r\n\r\n\r\nLayer 1\r\nTrack 2\r\n\r\n8\r\n\r\n4\r\nTrack
    1\r\n\r\nCircuitId 1\r\n\r\n2\r\n\r\nCircuitId 4\r\n\r\n9\r\n\r\n\r\n100\r\n\r\n3\r\n\r\nTrack
    0\r\nTrack 0\r\nTrack 3\r\n7\r\n5\r\n\r\n6\r\n\r\n\r\n\r\nThe JSON representation
    of the image above would be as follows:\r\n\r\n\r\n{\r\n\"TrackCircuits\": [{\r\n\"Track\":
    2,\r\n\"CircuitId\": 8,\r\n\"Neighbors\": [{\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\":
    [4, 3]\r\n}]\r\n}, {\r\n\"Track\": 2,\r\n\"CircuitId\": 4,\r\n\"Neighbors\": [{\r\n\"NeighborType\":
    \"Left\",\r\n\"CircuitIds\": [8]\r\n}, {\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\":
    [9]\r\n}]\r\n}, {\r\n\"Track\": 2,\r\n\"CircuitId\": 9,\r\n\"Neighbors\": [{\r\n\"NeighborType\":
    \"Left\",\r\n\"CircuitIds\": [4]\r\n}]\r\n}, {\r\n\"Track\": 0,\r\n\"CircuitId\":
    3,\r\n\"Neighbors\": [{\r\n\"NeighborType\": \"Left\",\r\n\"CircuitIds\": [8]\r\n},
    {\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\": [100]\r\n}]\r\n}, {\r\n\"Track\":
    3,\r\n\"CircuitId\": 100,\r\n\"Neighbors\": [{\r\n\"NeighborType\": \"Left\",\r\n\"CircuitIds\":
    [3]\r\n}, {\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\": [7]\r\n}]\r\n},
    {\r\n\"Track\": 0,\r\n\"CircuitId\": 7,\r\n\"Neighbors\": [{\r\n\"NeighborType\":
    \"Left\",\r\n\"CircuitIds\": [100]\r\n}, {\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\":
    [6]\r\n}]\r\n}, {\r\n\"Track\": 1,\r\n\"CircuitId\": 1,\r\n\"Neighbors\": [{\r\n\"NeighborType\":
    \"Right\",\r\n\"CircuitIds\": [2]\r\n}]\r\n}, {\r\n\"Track\": 1,\r\n\"CircuitId\":
    2,\r\n\"Neighbors\": [{\r\n\"NeighborType\": \"Left\",\r\n\"CircuitIds\": [1]\r\n},
    {\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\": [5]\r\n}]\r\n}, {\r\n\"Track\":
    1,\r\n\"CircuitId\": 5,\r\n\"Neighbors\": [{\r\n\"NeighborType\": \"Left\",\r\n\"CircuitIds\":
    [2]\r\n}, {\r\n\"NeighborType\": \"Right\",\r\n\"CircuitIds\": [6]\r\n}]\r\n},
    {\r\n\"Track\": 1,\r\n\"CircuitId\": 6,\r\n\"Neighbors\": [{\r\n\"NeighborType\":
    \"Left\",\r\n\"CircuitIds\": [5, 7]\r\n}]\r\n}]\r\n}"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//TrainPositions//TrackCircuits
  tags: Transit,Subway,Tracks,Circuits
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/trackcircuits-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/trackcircuits-get-openapi.md
- name: WMATA Train Positions
  x-api-slug: wmata-train-positions
  description: Official feed of Metro/WMATA, not monitored 24/7. Report emergencies
    to Transit Police at (202) 962-2121. Service updates @metrorailinfo & @metrobusinfo.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1214-washington-metropolitan-area-transit-authority.jpg
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//TrainPositions
  tags: Washington Metropolitan Area Transit Authority
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/washington-metropolitan-area-transit-authority/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
x-common:
- type: x-base
  url: http://api.wmata.com/
- type: x-crunchbase
  url: https://crunchbase.com/organization/wmata
- type: x-developer
  url: http://developer.wmata.com/
- type: x-email
  url: boardofdirectors@wmata.com
- type: x-email
  url: metrotransit@wmata.com
- type: x-email
  url: adaassist@wmata.com
- type: x-email
  url: access@wmata.com
- type: x-email
  url: cjachles@wmata.com
- type: x-email
  url: writtentestimony@wmata.com
- type: x-email
  url: speak@wmata.com
- type: x-email
  url: SEBusMove@wmata.com
- type: x-email
  url: PARP@wmata.com
- type: x-email
  url: raccomments@wmata.com
- type: x-signup
  url: https://developer.wmata.com/signup/
- type: x-twitter
  url: https://twitter.com/wmata
- type: x-website
  url: http://wmata.com/
- type: x-website
  url: http://wmata.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---