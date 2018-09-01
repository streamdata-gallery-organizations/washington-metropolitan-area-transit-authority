---
swagger: "2.0"
x-collection-name: Washington Metropolitan Area Transit Authority
x-complete: 0
info:
  title: WMATA Bus Route and Stop Methods JSON - Bus Position
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