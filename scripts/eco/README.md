# ECO Dev

## About

Some document being used to explore Data Commons at ECO.  
More a learn by inspection process right now.



## Notes

* Fukushima test dataset:  https://www.bco-dmo.org/dataset/3566  
* Frictionless package   https://github.com/ashepherd/Fukushima-Radionuclide-Levels_Niskin-bottle-samples_2011-10-20  
* One can see how the colunms become nodes.  So it is interesting to think about 


```json
{
    "@type": "PropertyValue",
    "@id": "https://www.bco-dmo.org/dataset-parameter/26201",
    "name": "o2_nis",
    "alternateName": "O2_ml_L",
    "description": "Dissolved oxygen from Niskin bottle sample",
    "valueReference": {
        "@type": "PropertyValue",
        "name": "dissolved Oxygen",
        "@id": "https://www.bco-dmo.org/parameter/1198",
        "propertyID": "https://www.bco-dmo.org/parameter/"
    },
    "unitText": "milliliters/liter"
},
```

to something like

```
Node: E:Niskin_bottle_samples->E2
typeOf: dcid:StatVarObservation
observationDate: C:Niskin_bottle_samples->date
observationAbout: E:Niskin_bottle_samples->E0
containedIn: E:Niskin_bottle_samples->E1
observationPeriod: "P1M"   # NOTE  Where is this defined?
variableMeasured: dcid:Dissolved_oxygen_from_Niskin_bottle_sample  # NOTE  Do we make this?????
measuredProperty: dcs:concentration   # Note:   interesting..   this is ml / L  so use..   ontology of measurements?  
value: C:Niskin_bottle_samples->"dissolved Oxygen"
unit: dcid:MillilitrePerLitre  #  NOTE  made this up too  
```

based on


```
Node: E:India_WRIS_Surface->E2
typeOf: dcid:StatVarObservation
observationDate: C:India_WRIS_Surface->Month
observationAbout: E:India_WRIS_Surface->E0
containedIn: E:India_WRIS_Surface->E1
observationPeriod: "P1M"
variableMeasured: dcid:Concentration_Aluminium_BodyOfWater_SurfaceWater
measuredProperty: dcs:concentration
value: C:India_WRIS_Surface->"Aluminium (Al)"
unit: dcid:MilligramsPerLitre
```