{
  "info": {
    "name": "WMATA Incidents JSON - Bus Incidents",
    "_postman_id": "911a03b4-a351-4836-86c5-4375ce6e10a0",
    "description": "Description\r\n\r\nReturns a set of reported bus incidents/delays for a given Route. Omit the\r\nRoute to return all reported items.\r\n\r\nNote that the Route parameter accepts only base route names and no\r\nvariations, i.e.: use 10A instead of 10Av1 and 10Av2.\r\n\r\nBus incidents/delays are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nBusIncidents\r\n\r\n\r\nArray containing bus incident information (BusIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nBusIncident\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) of last update. Will be\r\nin YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).\r\n\r\n\r\n\r\nDescription\r\n\r\nFree-text description of the delay or incident.\r\n\r\n\r\n\r\nIncidentID\r\n\r\nUnique identifier for an incident.\r\n\r\n\r\n\r\nIncidentType\r\n\r\nFree-text description of the incident type. Usually\r\nDelay or Alert but is subject to change at any time.\r\n\r\n\r\n\r\nRoutesAffected\r\n\r\nArray containing routes affected. Routes listed are usually\r\nidentical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),\r\nbut may differ from what our bus methods return.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "aa0bebe2-4c2b-4ddc-8bcc-4b6987cf6fc1",
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
              "id": "d340aedf-c2e1-4747-bb11-89ff926d0550"
            }
          ]
        }
      ]
    }
  ]
}