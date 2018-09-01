{
  "info": {
    "name": "WMATA Incidents XML - Bus Incidents",
    "_postman_id": "c52326c3-a2d5-47e7-81f2-814fad05227c",
    "description": "Description\r\n\r\nReturns a set of reported bus incidents/delays for a given Route. Omit the\r\nRoute to return all reported items.\r\n\r\nNote that the Route parameter accepts only base route names and no\r\nvariations, i.e.: use 10A instead of 10Av1 and 10Av2.\r\n\r\nBus incidents/delays are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nBusIncidents\r\n\r\n\r\nArray containing bus incident information (BusIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nBusIncident\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text description of the delay or incident.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description of the incident type. Usually\r\nDelay or Alert but is subject to change at any time.\r\n\r\n\r\n\r\nRoutesAffected\r\n\r\nArray containing routes affected. Routes listed are usually\r\nidentical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),\r\nbut may differ from what our bus methods return.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "f7c75634-c3d8-4c04-9286-1ac74b5834e3",
          "name": "54763641281d830c946a3d75",
          "request": {
            "url": "http://api.wmata.com/Incidents.svc/json/BusIncidents?Route=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a set of reported bus incidents/delays for a given Route. Omit the\r\nRoute to return all reported items.\r\n\r\nNote that the Route parameter accepts only base route names and no\r\nvariations, i.e.: use 10A instead of 10Av1 and 10Av2.\r\n\r\nBus incidents/delays are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nBusIncidents\r\n\r\n\r\nArray containing bus incident information (BusIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nBusIncident\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text description of the delay or incident.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description of the incident type. Usually\r\nDelay or Alert but is subject to change at any time.\r\n\r\n\r\n\r\nRoutesAffected\r\n\r\nArray containing routes affected. Routes listed are usually\r\nidentical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),\r\nbut may differ from what our bus methods return."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6c0d7576-2bba-4bf7-b379-908bd82ceed6"
            }
          ]
        },
        {
          "id": "f6c6e16d-01da-44d7-b554-552154ce34ee",
          "name": "54763641281d830c946a3d77",
          "request": {
            "url": "http://api.wmata.com/Incidents.svc/json/Incidents",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns reported rail incidents (significant disruptions and delays to\r\nnormal service). The data is identical to WMATA's Metrorail Service Status\r\nfeed.\r\n\r\nRail incidents are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nIncidents\r\n\r\n\r\nArray containing rail disruption information (Incident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nIncident Elements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).\r\n\r\n\r\n\r\nDelaySeverity\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text description of the incident.\r\n\r\n\r\n\r\nEmergencyText\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nEndLocationFullName\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description of the incident type. Usually Delay or\r\nAlert but is subject to change at any time.\r\n\r\n\r\n\r\nLinesAffected\r\n\r\nSemi-colon and space separated list of line codes (e.g.:\r\nRD; or BL;\r\nOR; or BL; OR; RD;). We do\r\nplan to update this to return something more reasonable like an\r\narray, but until then, use code similar to the following:\r\n\r\n\"RD; GR; BL;\".split(/;[\\s]?/).filter(function(fn) { return fn\r\n!== ''; })\r\n\r\n\r\n\r\nPassengerDelay\r\n\r\nDeprecated.\r\n\r\n\r\n\r\n\r\nStartLocationFullName\r\n\r\nDeprecated."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "d598d6ce-6d1d-4ae1-930b-373a0d4de648"
            }
          ]
        },
        {
          "id": "eb24c0bd-bd14-4dfd-9c32-db7e5297d642",
          "name": "54763641281d830c946a3d78",
          "request": {
            "url": "http://api.wmata.com/Incidents.svc/BusIncidents?Route=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a set of reported bus incidents/delays for a given Route. Omit the\r\nRoute to return all reported items.\r\n\r\nNote that the Route parameter accepts only base route names and no\r\nvariations, i.e.: use 10A instead of 10Av1 and 10Av2.\r\n\r\nBus incidents/delays are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nBusIncidents\r\n\r\n\r\nArray containing bus incident information (BusIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nBusIncident\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text description of the delay or incident.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description of the incident type. Usually\r\nDelay or Alert but is subject to change at any time.\r\n\r\n\r\n\r\nRoutesAffected\r\n\r\nArray containing routes affected. Routes listed are usually\r\nidentical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),\r\nbut may differ from what our bus methods return."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b5ed76f9-8ca8-43be-8d47-51f526b88641"
            }
          ]
        }
      ]
    }
  ]
}