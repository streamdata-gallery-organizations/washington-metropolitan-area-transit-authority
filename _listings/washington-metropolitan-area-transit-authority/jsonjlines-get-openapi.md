---
swagger: "2.0"
x-collection-name: Washington Metropolitan Area Transit Authority
x-complete: 0
info:
  title: WMATA Rail Station Information JSON - Lines
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
  version: 1.0.0
host: api.wmata.com
basePath: /Rail.svc
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /json/jLines:
    get:
      summary: JSON - Lines
      description: "Description\r\n\r\nReturns information about all rail lines.\r\n\r\nResponse
        Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nLines\r\n\r\n\r\nArray
        containing line information (Line).\r\n\r\n\r\n\r\n\r\n\r\n\r\nLine Elements\r\n\r\n\r\n\r\n\r\n\r\nDisplayName\r\n\r\nFull
        name of line color.\r\n\r\n\r\n\r\nEndStationCode\r\n\r\nEnd station code.
        For example, will be E10 (Greenbelt) for the\r\nGreen Line, B11 (Glenmont)
        for the Red Line, etc. Use this value in\r\nother rail-related APIs to retrieve
        data about a station.\r\n\r\n\r\n\r\nInternalDestination1\r\n\r\nIntermediate
        terminal station code. During normal service, some\r\ntrains on some lines
        might end their trip prior to the\r\nStartStationCode or EndStationCode. A
        good example is on the Red\r\nLine where some trains stop at A11 (Grosvenor)
        or B08 (Silver\r\nSpring). Empty string if not defined.\r\n\r\n\r\n\r\nInternalDestination2\r\n\r\nSimilar
        to InternalDestination1.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter abbreviation
        for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV).\r\n\r\n\r\n\r\nStartStationCode\r\n\r\nStart
        station code. For example, will be F11 (Branch Avenue)\r\nfor the Green Line,
        A15 (Shady Grove) for the Red Line, etc. Use\r\nthis value in other rail-related
        APIs to retrieve data about a\r\nstation."
      operationId: getJsonJlines
      x-api-path-slug: jsonjlines-get
      responses:
        200:
          description: OK
      tags:
      - Transit
      - Lines
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