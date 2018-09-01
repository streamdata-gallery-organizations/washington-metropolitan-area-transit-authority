{
  "info": {
    "name": "WMATA Incidents JSON - Elevator/Escalator Outages",
    "_postman_id": "3c668819-f008-4341-b8cc-dd6d2e916813",
    "description": "Description\r\n\r\nReturns a list of reported elevator and escalator outages at a\r\ngiven station. Omit the StationCode parameter to return all reported\r\noutages.\r\n\r\nNote that for stations with multiple platforms and therefore StationCodes\r\n(e.g.: Metro Center, L'Enfant Plaza, etc.), a distinct call is required for\r\neach StationCode.\r\n\r\nElevator and escalator outages are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncidents\r\n\r\n\r\nArray containing elevator/escalator outage information\r\n(ElevatorIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncident Elements\r\n\r\n\r\n\r\n\r\n\r\nDateOutOfServ\r\n\r\nDate and time (Eastern Standard Time) unit was reported out of\r\nservice. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) outage details was last\r\nupdated. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDisplayOrder\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLocationDescription\r\n\r\nFree-text description of the unit location within a station\r\n(e.g.: Escalator between mezzanine and\r\nplatform).\r\n\r\n\r\n\r\nStationCode\r\n\r\nUnit's station code. Use this value in other rail-related APIs\r\nto retrieve data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull station name, may include entrance information (e.g.:\r\nMetro Center, G and 11th St\r\nEntrance).\r\n\r\n\r\n\r\nSymptomCode\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nSymptomDescription\r\n\r\nDescription for why the unit is out of service or otherwise in\r\nreduced operation.\r\n\r\n\r\n\r\nTimeOutOfService\r\n\r\nDeprecated. Use the time\r\nportion of the DateOutOfServ element.\r\n\r\n\r\n\r\nUnitName\r\n\r\nUnique identifier for unit, by type (a single elevator and\r\nescalator may have the same UnitName, but no two elevators or two\r\nescalators will have the same UnitName).\r\n\r\n\r\n\r\nUnitStatus\r\n\r\nDeprecated. If listed here,\r\nthe unit is inoperational or otherwise impaired.\r\n\r\n\r\n\r\nUnitType\r\n\r\nType of unit. Will be ELEVATOR\r\nor ESCALATOR.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "dff93f39-4388-4dda-9815-c07ec57d7e4e",
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
              "id": "b185cefd-83cc-4544-9520-9017748445d0"
            }
          ]
        },
        {
          "id": "3e3967e4-e085-4af0-8cbc-f8ee77e74728",
          "name": "54763641281d830c946a3d76",
          "request": {
            "url": "http://api.wmata.com/Incidents.svc/json/ElevatorIncidents?StationCode=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of reported elevator and escalator outages at a\r\ngiven station. Omit the StationCode parameter to return all reported\r\noutages.\r\n\r\nNote that for stations with multiple platforms and therefore StationCodes\r\n(e.g.: Metro Center, L'Enfant Plaza, etc.), a distinct call is required for\r\neach StationCode.\r\n\r\nElevator and escalator outages are refreshed once every 20 to 30 seconds approximately.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncidents\r\n\r\n\r\nArray containing elevator/escalator outage information\r\n(ElevatorIncident).\r\n\r\n\r\n\r\n\r\n\r\n\r\nElevatorIncident Elements\r\n\r\n\r\n\r\n\r\n\r\nDateOutOfServ\r\n\r\nDate and time (Eastern Standard Time) unit was reported out of\r\nservice. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDateUpdated\r\n\r\nDate and time (Eastern Standard Time) outage details was last\r\nupdated. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T15:17:00).\r\n\r\n\r\n\r\nDisplayOrder\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nLocationDescription\r\n\r\nFree-text description of the unit location within a station\r\n(e.g.: Escalator between mezzanine and\r\nplatform).\r\n\r\n\r\n\r\nStationCode\r\n\r\nUnit's station code. Use this value in other rail-related APIs\r\nto retrieve data about a station.\r\n\r\n\r\n\r\nStationName\r\n\r\nFull station name, may include entrance information (e.g.:\r\nMetro Center, G and 11th St\r\nEntrance).\r\n\r\n\r\n\r\nSymptomCode\r\n\r\nDeprecated.\r\n\r\n\r\n\r\nSymptomDescription\r\n\r\nDescription for why the unit is out of service or otherwise in\r\nreduced operation.\r\n\r\n\r\n\r\nTimeOutOfService\r\n\r\nDeprecated. Use the time\r\nportion of the DateOutOfServ element.\r\n\r\n\r\n\r\nUnitName\r\n\r\nUnique identifier for unit, by type (a single elevator and\r\nescalator may have the same UnitName, but no two elevators or two\r\nescalators will have the same UnitName).\r\n\r\n\r\n\r\nUnitStatus\r\n\r\nDeprecated. If listed here,\r\nthe unit is inoperational or otherwise impaired.\r\n\r\n\r\n\r\nUnitType\r\n\r\nType of unit. Will be ELEVATOR\r\nor ESCALATOR."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "75352934-116d-4ce1-8f68-cf0c9ca08c2e"
            }
          ]
        }
      ]
    }
  ]
}