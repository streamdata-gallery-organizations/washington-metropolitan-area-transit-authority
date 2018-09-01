---
swagger: "2.0"
x-collection-name: Washington Metropolitan Area Transit Authority
x-complete: 0
info:
  title: WMATA Bus Route and Stop Methods JSON - Schedule
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
  version: 1.0.0
host: api.wmata.com
basePath: /Bus.svc
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /json/jBusPositions:
    get:
      summary: JSON - Bus Position
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
      operationId: 5476362a281d830c946a3d68
      x-api-path-slug: jsonjbuspositions-get
      parameters:
      - in: query
        name: Lat
        description: Center point Latitude, required if Longitude and Radius are specified
      - in: query
        name: Lon
        description: Center point Longitude, required if Latitude and Radius are specified
      - in: query
        name: Radius
        description: Radius (meters) to include in the search area, required if Latitude
          and Longitude are specified
      - in: query
        name: RouteID
        description: Base bus route, e
      responses:
        200:
          description: OK
      tags:
      - Buses
      - Positions
  /json/jRouteDetails:
    get:
      summary: JSON - Path Details
      description: "Description\r\n\r\nFor a given date, returns the set of ordered
        latitude/longitude points along\r\na route variant along with the list of
        stops served.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nStructures
        describing path/stop\r\ninformation.\r\n\r\nMost routes will return content
        in both Direction0 and\r\nDirection1 elements, though a few will return NULL
        for Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There
        is no specific mapping to\r\ndirection, but a different value for the same
        route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
        name for the route.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant (e.g.:
        10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated.
        Use the\r\nDirectionText element to denote the general direction of the route\r\nvariant.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nGeneral
        direction of the route variant (NORTH, SOUTH, EAST,\r\nWEST, LOOP, etc.).\r\n\r\n\r\n\r\nShape\r\n\r\n\r\nArray
        containing shape point information (ShapePoint).\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray
        containing stop information (Stop).\r\n\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive
        text of where the bus is headed. This is similar,\r\nbut not necessarily identical,
        to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\n\r\n\r\nShapePoint\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder
        of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
        name. May be slightly different from what is spoken or\r\ndisplayed in the
        bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide
        service at this\r\nstop. Note that these are not date-specific; any route
        variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit
        regional ID which can be used in various bus-related\r\nmethods. If unavailable,
        the StopID will be 0 or NULL."
      operationId: 5476362a281d830c946a3d69
      x-api-path-slug: jsonjroutedetails-get
      parameters:
      - in: query
        name: Date
        description: Date in YYYY-MM-DD format for which to retrieve route and stop
          information
      - in: query
        name: RouteID
        description: Bus route variant, e
      responses:
        200:
          description: OK
      tags:
      - Buses
      - Routes
  /json/jRoutes:
    get:
      summary: JSON - Routes
      description: "Description\r\n\r\nReturns a list of all bus route variants (patterns).
        For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly
        different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray
        containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute
        Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route
        variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique identifier for a given route
        variant. Can be used in\r\nvarious other bus-related methods.\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes
        the route variant???s grouping ??? lines are a combination of routes which
        lie in the same corridor and which have significant portions of their paths
        along the same roadways."
      operationId: 5476362a281d830c946a3d6a
      x-api-path-slug: jsonjroutes-get
      responses:
        200:
          description: OK
      tags:
      - Buses
      - Routes
  /json/jRouteSchedule:
    get:
      summary: JSON - Schedule
      description: "Description\r\n\r\nReturns schedules for a given route variant
        for a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays
        containing trip information (Trip).\r\n\r\nMost routes will return content
        in both Direction0 and\r\nDirection1 elements, though a few (especially ones
        which run in\r\na loop, such as the U8) will return content only for Direction0\r\nand
        NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is
        no specific mapping to\r\ndirection, but a different value for the same route
        signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
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
        to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip
        ID. This can be correlated with the data returned\r\nfrom the schedule-related
        methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit
        regional ID which can be used in various bus-related\r\nmethods. If unavailable,
        the StopID will be 0 or NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May
        be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder
        of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled
        departure date and time (Eastern Standard Time) from\r\nthis stop. Will be
        in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00)."
      operationId: 5476362a281d830c946a3d6b
      x-api-path-slug: jsonjrouteschedule-get
      parameters:
      - in: query
        name: Date
        description: Date in YYYY-MM-DD format for which to retrieve schedule
      - in: query
        name: IncludingVariations
        description: Whether or not to include variations if a base route is specified
          in RouteID
      - in: query
        name: RouteID
        description: Bus route variant, e
      responses:
        200:
          description: OK
      tags:
      - Buses
      - Routes
      - Schedules
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---