---
swagger: "2.0"
x-collection-name: Washington Metropolitan Area Transit Authority
x-complete: 0
info:
  title: WMATA Train Positions Standard Routes
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
  version: 1.0.0
host: api.wmata.com
basePath: /TrainPositions
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /TrainPositions:
    get:
      summary: Live Train Positions
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
      operationId: getTrainpositions
      x-api-path-slug: trainpositions-get
      parameters:
      - in: query
        name: contentType
        description: Returns response in the specified format
      responses:
        200:
          description: OK
      tags:
      - Transit
      - Subway
      - Positions
  /StandardRoutes:
    get:
      summary: Standard Routes
      description: "Description\r\n\r\nReturns an ordered list of mostly revenue (and
        some lead) track circuits, arranged by line and track number.  This data does
        not change frequently and should be cached for a reasonable amount of time.\r\nPlease
        refer to this page for additional details.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStandardRoutes\r\n\r\n\r\nArray
        containing revenue line information (StandardRoute).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStandardRoute
        Elements\r\n\r\n\r\n\r\n\r\n\r\nLineCode\r\n\r\nAbbreviation for the revenue
        line.  Note that this also includes YLRP (Yellow Line Rush Plus).\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray
        containing ordered track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\nTrackNum\r\n\r\nTrack
        number (1 or 2).\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit Elements\r\n\r\n\r\n
        \       \r\n\r\n\r\nCircuitId\r\n\r\nAn internal system-wide uniquely identifiable
        circuit number.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder in which the circuit appears
        for the given line and track.  Sequences go from West to East and South to
        North.\r\n        \r\n\r\n\r\nStationCode\r\n\r\nIf the circuit is at a station,
        this value will represent the station code.  Otherwise, it will be be NULL.
        Use this value in other rail-related APIs to retrieve data about a station."
      operationId: getStandardroutes
      x-api-path-slug: standardroutes-get
      parameters:
      - in: query
        name: contentType
        description: Returns response in the specified format
      responses:
        200:
          description: OK
      tags:
      - Transit
      - Subway
      - Routes
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