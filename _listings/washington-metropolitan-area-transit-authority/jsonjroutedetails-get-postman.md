{
  "info": {
    "name": "WMATA Bus Route and Stop Methods JSON - Path Details",
    "_postman_id": "4980652a-6b76-4305-afb2-cc9e9f23493c",
    "description": "Description\r\n\r\nFor a given date, returns the set of ordered latitude/longitude points along\r\na route variant along with the list of stops served.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nStructures describing path/stop\r\ninformation.\r\n\r\nMost routes will return content in both Direction0 and\r\nDirection1 elements, though a few will return NULL for Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name for the route.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant (e.g.: 10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated. Use the\r\nDirectionText element to denote the general direction of the route\r\nvariant.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nGeneral direction of the route variant (NORTH, SOUTH, EAST,\r\nWEST, LOOP, etc.).\r\n\r\n\r\n\r\nShape\r\n\r\n\r\nArray containing shape point information (ShapePoint).\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray containing stop information (Stop).\r\n\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive text of where the bus is headed. This is similar,\r\nbut not necessarily identical, to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\n\r\n\r\nShapePoint\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide service at this\r\nstop. Note that these are not date-specific; any route variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Buses",
      "item": [
        {
          "id": "0621ef74-ba28-4353-9d32-640fdf324303",
          "name": "5476362a281d830c946a3d68",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jBusPositions?Lat=%7B%7D&Lon=%7B%7D&Radius=%7B%7D&RouteID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\n\nReturns bus positions for the given route, with an optional search radius.\nIf no parameters are specified, all bus positions are returned.\n\nNote that the RouteID parameter accepts only base route names and no\nvariations, i.e.: use 10A instead of 10Av1 or 10Av2.\n\nBus positions are refreshed approximately every 20 to 30 7 to 10 seconds.\n\nResponse Elements\n\n\n\n\nElement\n\nDescription\n\n\n\n\n\nBusPositions\n\n\nArray containing bus position information (BusPositions).\n\n\n\n\n\n\nBusPosition\nElements\n\n\n\n\n\nDateTime\n\nDate and time (Eastern Standard Time) of last position update.\nWill be in YYYY-MM-DDTHH:mm:ss format (e.g.:\n2014-10-27T13:23:40).\n\n\n\nDeviation\n\nDeviation, in minutes, from schedule. Positive values indicate\nthat the bus is running late while negative ones are for buses\nrunning ahead of schedule.\n\n\n\nDirectionNum\n\nDeprecated. Use the\nDirectionText for a customer-friendly description of\ndirection.\n\n\n\nDirectionText\n\nGeneral direction of the trip, not the bus itself (e.g.: NORTH,\nSOUTH, EAST, WEST).\n\n\n\nLat\n\nLast reported Latitude of the bus.\n\n\n\nLon\n\nLast reported Longitude of the bus.\n\n\n\nRouteID\n\nBase route name as shown on the bus. Note that the base route\nname could also refer to any variant, so a RouteID of 10A could\nrefer to 10A, 10Av1, 10Av2, etc.\n\n\n\nTripEndTime\n\nScheduled end date and time (Eastern Standard Time) of the\nbus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\n2014-10-27T13:17:00).\n\n\n\nTripHeadsign\n\nDestination of the bus.\n\n\n\nTripID\n\nUnique trip ID. This can be correlated with the data returned\nfrom the schedule-related methods.\n\n\n\nTripStartTime\n\nScheduled start date and time (Eastern Standard Time) of the\nbus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\n2014-10-27T12:40:00).\n\n\n\nVehicleID\n\nUnique identifier for the bus. This is usually visible on the\nbus itself."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "fb46420c-e924-4fe4-b239-8f4c115298e2"
            }
          ]
        },
        {
          "id": "4fefa6ed-a470-4472-a682-95d246edfb87",
          "name": "5476362a281d830c946a3d69",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jRouteDetails?Date=%7B%7D&RouteID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nFor a given date, returns the set of ordered latitude/longitude points along\r\na route variant along with the list of stops served.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nStructures describing path/stop\r\ninformation.\r\n\r\nMost routes will return content in both Direction0 and\r\nDirection1 elements, though a few will return NULL for Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name for the route.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant (e.g.: 10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated. Use the\r\nDirectionText element to denote the general direction of the route\r\nvariant.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nGeneral direction of the route variant (NORTH, SOUTH, EAST,\r\nWEST, LOOP, etc.).\r\n\r\n\r\n\r\nShape\r\n\r\n\r\nArray containing shape point information (ShapePoint).\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray containing stop information (Stop).\r\n\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive text of where the bus is headed. This is similar,\r\nbut not necessarily identical, to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\n\r\n\r\nShapePoint\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide service at this\r\nstop. Note that these are not date-specific; any route variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "25c2f635-b51d-40bf-9461-454e12f87f5c"
            }
          ]
        }
      ]
    }
  ]
}