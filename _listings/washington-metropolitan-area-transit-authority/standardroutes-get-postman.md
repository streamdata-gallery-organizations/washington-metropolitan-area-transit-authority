{
  "info": {
    "name": "WMATA Train Positions Standard Routes",
    "_postman_id": "f9f9c421-060d-4040-b56d-c2ca07721063",
    "description": "Description\r\n\r\nReturns an ordered list of mostly revenue (and some lead) track circuits, arranged by line and track number.  This data does not change frequently and should be cached for a reasonable amount of time.\r\nPlease refer to this page for additional details.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStandardRoutes\r\n\r\n\r\nArray containing revenue line information (StandardRoute).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStandardRoute Elements\r\n\r\n\r\n\r\n\r\n\r\nLineCode\r\n\r\nAbbreviation for the revenue line.  Note that this also includes YLRP (Yellow Line Rush Plus).\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray containing ordered track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\nTrackNum\r\n\r\nTrack number (1 or 2).\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit Elements\r\n\r\n\r\n        \r\n\r\n\r\nCircuitId\r\n\r\nAn internal system-wide uniquely identifiable circuit number.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder in which the circuit appears for the given line and track.  Sequences go from West to East and South to North.\r\n        \r\n\r\n\r\nStationCode\r\n\r\nIf the circuit is at a station, this value will represent the station code.  Otherwise, it will be be NULL. Use this value in other rail-related APIs to retrieve data about a station.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "3ef1a230-0424-4c33-888d-dfb2ced29574",
          "name": "getStandardroutes",
          "request": {
            "url": "http://api.wmata.com/TrainPositions/StandardRoutes?contentType=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns an ordered list of mostly revenue (and some lead) track circuits, arranged by line and track number.  This data does not change frequently and should be cached for a reasonable amount of time.\r\nPlease refer to this page for additional details.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStandardRoutes\r\n\r\n\r\nArray containing revenue line information (StandardRoute).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStandardRoute Elements\r\n\r\n\r\n\r\n\r\n\r\nLineCode\r\n\r\nAbbreviation for the revenue line.  Note that this also includes YLRP (Yellow Line Rush Plus).\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray containing ordered track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\nTrackNum\r\n\r\nTrack number (1 or 2).\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit Elements\r\n\r\n\r\n        \r\n\r\n\r\nCircuitId\r\n\r\nAn internal system-wide uniquely identifiable circuit number.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder in which the circuit appears for the given line and track.  Sequences go from West to East and South to North.\r\n        \r\n\r\n\r\nStationCode\r\n\r\nIf the circuit is at a station, this value will represent the station code.  Otherwise, it will be be NULL. Use this value in other rail-related APIs to retrieve data about a station."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "0bff0e61-6adc-4554-a38f-5df0edb5c8d5"
            }
          ]
        }
      ]
    }
  ]
}