# robotino-at-hft

## Links

* github client: https://windows.github.com/

## Schnittstellendefinitionen 

### RobotinoAPI

* example(name)

  * Beschreibung: Gibt den Nachnamen anhand eines Vornahmens aus, schaut dafür in der Datenbank nach
  
  * Parameter: 
  
    * name: String: Vorname
  
  * Return: String: Nachname
  
### Steuerung

### Sensorik

### Wegberechnung

### Karte

download und upload-möglichkeit unter settings auf http://robodino.r9u.de

geojson, mit "value": "limit"(limit oder barrier) "name": "ganzeFlaeche"(Beschreibung) in properties
startpunkt = endpunkt

maßstab: vorraussichtlich 1 Meter = 1 Einheit in x3d-Model & geojson

### Visualisierung

Verfügbar unter: http://robodino.r9u.de
Schnittstellen: POSTs mit JSON

* /initSzenario (einmal zum Starten des Szenarios)
  
        {   
            "szenarioname": "erstesSzenario/15.06.11", (unique)   
            "floorplanJSONref": "floorplan_test1.json",  (name der verwendeten json, die online auf dem server liegt)
            "modelX3Dref": "Deer.x3d", (name der verwendeten x3d, die online auf dem server liegt, optional)
            "startpoint": {   
                "x": 6.15234375,   
                "y": 23.1201536216956   
            },   
            "endpoint": {   
                "x": 23.291015625,   
                "y": 30.107117887092382   
            }   
        }

* /newPath (ganzer neuberechnerter Weg)

		{
            "szenarioname": "erstesSzenario/15.06.11",
            "newPath": [
                {
                    "x": 6.15234375,
                    "y": 23.1201536216956
                },
                {
                    "x": 9.140625,
                    "y": 20.673905264672843
                },
                {
                    "x": 13.53515625,
                    "y": 25.839449402063185
                }...
            ]

        }

* /actualPosition (aktuelle Position)

		{
            "szenarioname": "erstesSzenario/15.06.11",
            "actualPosition": {
                "point": 
                {
                    "x": 9.140625,
                    "y": 20.673905264672843
                }
            }
        }
