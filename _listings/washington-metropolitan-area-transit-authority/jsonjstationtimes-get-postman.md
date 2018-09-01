{
  "info": {
    "name": "WMATA Rail Station Information JSON - Station Timings",
    "_postman_id": "7a1bdec1-335e-4e0a-89d7-269e6aef3a46",
    "description": "Description\r\n\r\nReturns opening and scheduled first/last train times based on a given\r\nStationCode. Omit the StationCode to return timing information for all\r\nstations.\r\n\r\nNote that for stations with multiple platforms (e.g.: Metro Center, L'Enfant\r\nPlaza, etc.), a distinct call is required for each StationCode to retrieve the\r\nfull set of train times at such stations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStationTimes\r\n\r\n\r\nArray containing station timing information (StationTime).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationTime\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code for this station. Use this value in other\r\nrail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull name of the station.\r\n\r\n\r\n\r\n*Day Elements\r\n\r\n\r\nContainer elements containing timing information based on\r\nday of the week.\r\n\r\n\r\n\r\n\r\n\r\n\r\nMonday/Tuesday/Wednesday/etc.\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nOpeningTime\r\n\r\nStation opening time. Format is HH:mm.\r\n\r\n\r\n\r\nFirstTrains\r\n\r\n\r\nStructure containing first train\r\ninformation.\r\n\r\n\r\n\r\n\r\nLastTrains\r\n\r\n\r\nStructure containing last train\r\ninformation.\r\n\r\n\r\n\r\n\r\n\r\n\r\nFirstTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nFirst train leaves the station at this time. Format is\r\nHH:mm.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation code for the train's destination. Use this value in\r\nother rail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\n\r\n\r\nLastTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nLast train leaves the station at this time. Format is HH:mm.\r\nNote that when the time is AM, it signifies the next day. For\r\nexample, a value of 02:30 under a Saturday element means the last\r\ntrain leaves on Sunday at 2:30 AM.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation code for the train's destination. Use this value in\r\nother rail-related APIs to retrieve data about a station.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "37e6c73a-67fb-4e6c-afa9-07a5c5d224f4",
          "name": "getJsonJstationparking",
          "request": {
            "url": "http://api.wmata.com/Rail.svc/json/jStationParking?StationCode=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\n\nReturns parking information at a station based on a given StationCode. Omit\nthe StationCode to return parking information for all stations.\n\nIf a station has no parking, the StationsParking element will contain no\nchild elements.\n\nResponse Elements\n\n\n\n\nElement\n\nDescription\n\n\n\n\n\nStationsParking\n\n\nArray containing station parking information (StationParking).\n\n\n\n\n\n\nStationParking\nElements\n\n\n\n\n\nCode\n\nStation code. Useful when returning parking information for all\nstations. Use this value in other rail-related APIs to retrieve\ndata about a station.\n\n\n\nNotes\n\nWhen not NULL, provides additional parking resources such as\nnearby lots.\n\n\n\nAllDayParking\n\n\nStructure describing all-day\nparking options.\n\n\n\n\nShortTermParking\n\n\nStructure describing short-term\nparking options.\n\n\n\n\n\n\nAllDayParking\nElements\n\n\n\n\n\nTotalCount\n\nNumber of all-day parking spots available at a station.\n\n\n\nRiderCost\n\nAll-day cost per day (weekday) for Metro riders. NULL when no all-day\nspots are available. For most stations, this value is identical to\nthe NonRiderCost.\n\nFor cases where the NonRiderCost is different, the lower cost per\nday requires a valid rail trip using a SmarTrip&reg; card\noriginating from a station other than the one where the patron\nparked. To receive this lower rate, patrons must pay for their\nparking with the same SmarTrip&reg; card used to enter/exit\nMetrorail, and must exit the parking lot within two hours of\nexiting Metrorail.\n\n\n\nNonRiderCost\n\nAll-day cost per day (weekday) for non-Metro riders. NULL when no all-day\nspots are available.\n\n\n\n\n\nShortTermParking Elements\n\n\n\n\n\nSaturdayRiderCost\n\nSimilar to RiderCost, except denoting Saturday prices.\n\n\n\nSaturdayNonRiderCost\n\nSimilar to NonRiderCost, except denoting Saturday prices.\n\n\n\nTotalCount\n\nNumber of short-term parking spots available at a station\n(parking meters).\n\n\n\nNotes\n\nMisc. information relating to short-term parking. NULL when no\nshort-term spots are available."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "27bbd935-20fe-4873-8898-e8b28568bbda"
            }
          ]
        },
        {
          "id": "889252e0-60a3-4e3c-bedc-b9979cf411a0",
          "name": "getJsonJstationentrances",
          "request": {
            "url": "http://api.wmata.com/Rail.svc/json/jStationEntrances?Lat=%7B%7D&Lon=%7B%7D&Radius=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of nearby station entrances based on latitude, longitude, and\r\nradius (meters). Omit search parameters to return all station entrances.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nEntrances\r\n\r\n\r\nArray containing detailed information about station entrances\r\n(StationEntrance).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationEntrance Elements\r\n\r\n\r\n\r\n\r\n\r\nDescription\r\n\r\nAdditional information for the entrance, if available.\r\nCurrently available data usually shows the same value as the Name\r\nelement.\r\n\r\n\r\n\r\nID\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nName of the entrance (usually the station name and nearest\r\nintersection).\r\n\r\n\r\n\r\nStationCode1\r\n\r\nThe station code associated with this entrance. Use this value\r\nin other rail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\nStationCode2\r\n\r\nFor stations containing multiple platforms (e.g.: Gallery\r\nPlace, Fort Totten, L'Enfant Plaza, and Metro Center), the other\r\nstation code."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "eb9e97eb-e73d-4414-b73d-ceafe0db0f2c"
            }
          ]
        },
        {
          "id": "95262174-b237-4ad2-bec2-a66cf48646c0",
          "name": "getJsonJstationinfo",
          "request": {
            "url": "http://api.wmata.com/Rail.svc/json/jStationInfo?StationCode=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns station location and address information based on a given\r\nStationCode.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nAddress\r\n\r\n\r\nStructure describing address information.\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code. Repeated from input.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLineCode1\r\n\r\nTwo-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) served by this station.\r\n\r\n\r\n\r\nLineCode2\r\n\r\nAdditional line served by this station. This is often the case\r\nwhen stations have multiple platforms (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center).\r\n\r\n\r\n\r\nLineCode3\r\n\r\nSimilar to function as LineCodeX.\r\n\r\n\r\n\r\nLineCode4\r\n\r\nSimilar to function as LineCodeX. Currently not in use.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStation name.\r\n\r\n\r\n\r\nStationTogether1\r\n\r\nFor stations with multiple platforms (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center), the additional\r\nStationCode will be listed here.\r\n\r\n\r\n\r\nStationTogether2\r\n\r\nSimilar in function to StationTogether2. Currently not in\r\nuse.\r\n\r\n\r\n\r\n\r\n\r\nAddress Elements\r\n\r\n\r\n\r\n\r\n\r\nCity\r\n\r\nCity.\r\n\r\n\r\n\r\nState\r\n\r\nState (abbreviated).\r\n\r\n\r\n\r\nStreet\r\n\r\nStreet address (for GPS use).\r\n\r\n\r\n\r\nZip\r\n\r\nZip code."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b17dc52a-cb6b-4f8c-bad3-b246a9c68ac1"
            }
          ]
        },
        {
          "id": "94ea4e9c-c506-45fe-be77-0b444b65927d",
          "name": "getJsonJstations",
          "request": {
            "url": "http://api.wmata.com/Rail.svc/json/jStations?LineCode=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of station location and address information based on a given\r\nLineCode. Omit the LineCode to return all stations. The response is an array of\r\nobjects identical to those returned in the Station Information method.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStations\r\n\r\n\r\nArray containing station information (Station).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStation Elements\r\n\r\n\r\n\r\n\r\n\r\nAddress\r\n\r\n\r\nStructure describing address information.\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code. Repeated from input.\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLineCode1\r\n\r\nTwo-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV) served by this station.\r\n\r\n\r\n\r\nLineCode2\r\n\r\nAdditional line served by this station. This is often the case\r\nwhen stations have multiple platforms (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center).\r\n\r\n\r\n\r\nLineCode3\r\n\r\nSimilar to function as LineCodeX.\r\n\r\n\r\n\r\nLineCode4\r\n\r\nSimilar to function as LineCodeX. Currently not in use.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStation name.\r\n\r\n\r\n\r\nStationTogether1\r\n\r\nFor stations with multiple platforms (e.g.: Gallery Place, Fort\r\nTotten, L'Enfant Plaza, and Metro Center), the additional\r\nStationCode will be listed here.\r\n\r\n\r\n\r\nStationTogether2\r\n\r\nSimilar in function to StationTogether2. Currently not in\r\nuse.\r\n\r\n\r\n\r\n\r\n\r\nAddress Elements\r\n\r\n\r\n\r\n\r\n\r\nCity\r\n\r\nCity.\r\n\r\n\r\n\r\nState\r\n\r\nState (abbreviated).\r\n\r\n\r\n\r\nStreet\r\n\r\nStreet address (for GPS use).\r\n\r\n\r\n\r\nZip\r\n\r\nZip code."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "488b5d84-b42d-4e40-a04f-96cbeb41973b"
            }
          ]
        },
        {
          "id": "f193f906-9045-4c57-99f7-9cec563dec4c",
          "name": "getJsonJstationtimes",
          "request": {
            "url": "http://api.wmata.com/Rail.svc/json/jStationTimes?StationCode=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns opening and scheduled first/last train times based on a given\r\nStationCode. Omit the StationCode to return timing information for all\r\nstations.\r\n\r\nNote that for stations with multiple platforms (e.g.: Metro Center, L'Enfant\r\nPlaza, etc.), a distinct call is required for each StationCode to retrieve the\r\nfull set of train times at such stations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStationTimes\r\n\r\n\r\nArray containing station timing information (StationTime).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStationTime\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nCode\r\n\r\nStation code for this station. Use this value in other\r\nrail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull name of the station.\r\n\r\n\r\n\r\n*Day Elements\r\n\r\n\r\nContainer elements containing timing information based on\r\nday of the week.\r\n\r\n\r\n\r\n\r\n\r\n\r\nMonday/Tuesday/Wednesday/etc.\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nOpeningTime\r\n\r\nStation opening time. Format is HH:mm.\r\n\r\n\r\n\r\nFirstTrains\r\n\r\n\r\nStructure containing first train\r\ninformation.\r\n\r\n\r\n\r\n\r\nLastTrains\r\n\r\n\r\nStructure containing last train\r\ninformation.\r\n\r\n\r\n\r\n\r\n\r\n\r\nFirstTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nFirst train leaves the station at this time. Format is\r\nHH:mm.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation code for the train's destination. Use this value in\r\nother rail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\n\r\n\r\nLastTrains Elements\r\n\r\n\r\n\r\n\r\n\r\nTime\r\n\r\nLast train leaves the station at this time. Format is HH:mm.\r\nNote that when the time is AM, it signifies the next day. For\r\nexample, a value of 02:30 under a Saturday element means the last\r\ntrain leaves on Sunday at 2:30 AM.\r\n\r\n\r\n\r\nDestinationStation\r\n\r\nStation code for the train's destination. Use this value in\r\nother rail-related APIs to retrieve data about a station."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9cede03e-8870-44d6-aaab-a9f4fecf771a"
            }
          ]
        }
      ]
    }
  ]
}