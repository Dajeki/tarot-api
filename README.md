## Retrieve All Information 

### `GET /all.json`  
Retrieves all the information the API has to offer.

#### Resource URL
https://dajeki.github.io/tarot-api/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| N/A | N/A | N/A | N/A | 

#### Example Request
GET [https://dajeki.github.io/tarot-api/all.json](https://dajeki.github.io/tarot-api/all.json)

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{ 
	"element": {
		"fire": {
			"minor": "Wands",
			"gender": "masculine",
			"colors": [
				"red",
				"orange"
			],
			"zodiac": [
				"Aries",
				"Leo",
				"Sagittarius"
			],
			"animals": "reptiles, insects, lizards",
			"expression": "I do",
			"attribute": "power of vitality",
			"meaning": "passion, creativity, lifeforce, growth, sexuality, humor, anger, spirituality, energy, motivation"
		}
		// earth | air | water
	},
	"zodiac": {
		"Cancer": {
			"element": "water",
			"nature": "security",
			"astrologyModality": "cardinal",
			"rulingBodyModern": "Moon",
			"rulingBodyTraditional": null
		},
		// zodiac sign
	},
	"courtElementalCorrespondence": {
		"page": {
			"element": "earth",
			"meaning": "inexperience, desires stability"
		},
		// knight | queen | king
	},
	"astrologyModality": {
		"cardinal": {
			"card": "queen",
			"attribute": "signs that begin seasons",
			"meaning": "initiators, self-starters, assertive, decisive and sometimes aggressive",
			"fire": {
				"zodiac": "Aries",
				"season": "spring"
			},
			"earth": {
				//...
			},
			"air": {
				//...
			},
			"water": {
				//...
			}
		},
		// fixed | mutable
	},
	"card": {
		//...Major Arcana Cards,
		"The Fool": {
			"id": 0,
			"upright": "innocence, new beginnings, free spirit",
			"reversed": "recklessness, taken advantage of, inconsideration",
			"first_element": "aether",
			"second_element": "air"
		},
		//...Minor Arcana Cards
		"Ace of Wands": {
			"id": 22,
			"upright": "creation, willpower, inspiration, desire",
			"reversed": "lack of energy, lack of passion, boredom",
			"first_element": "fire",
			"second_element": null
		},
		"Three of Cups": {
			//...
		},
		"Page of Swords": {
			//...
		},
	}
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- | 
| element | object | Information about the element like color, minor arcana, or zodiac signs.  | 
| zodiac | object | Information about zodiac sign like element, ruling celestial body, or nature.| 
| courtElementalCorrespondence | object | Court cards secondary element and sub meaning. | 
| astrologyModality | object | Information that relates season timing, elements, and zodiac signs to meaning. | 
| card | object | Tarot card information like id, meaning, and element. |  

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



## Retrieve All Cards 

### `GET /card/[{arcana}]/all.json`  
Retrieve all the cards or all the cards in either the major or minor arcana

#### Resource URL
https://dajeki.github.io/tarot-api/card/[{arcana}]/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| arcana | string | no | Can be either `minor` or `major` to denote what arcana you would like to get all of the cards from. | 

#### Example Request
GET [https://dajeki.github.io/tarot-api/card/all.json](https://dajeki.github.io/tarot-api/card/all.json)

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{ 
	//...major arcana cards,
	"The Fool": {
		"id": 0,
		"upright": "innocence, new beginnings, free spirit",
		"reversed": "recklessness, taken advantage of, inconsideration",
		"first_element": "aether",
		"second_element": "air"
	},
	//...minor arcana cards
	"Ace of Wands": {
		"id": 22,
		"upright": "creation, willpower, inspiration, desire",
		"reversed": "lack of energy, lack of passion, boredom",
		"first_element": "fire",
		"second_element": null
	},
	"Three of Cups": {
		//...
	},
	"Page of Swords": {
		"id": 60,
		"upright": "curiosity, restlessness, mental energy",
		"reversed": "deception, manipulation, all talk",
		"first_element": "air",
		"second_element": "earth".
	},
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- | 
| {cardName} | object | Information about the card. Will be accessed by the name of the card  | 
| {cardName}.id | number | Number of the card in a tarot deck. | 
| {cardName}.upright | string | Meaning of card in the upright position. | 
| {cardName}.reversed | string | Meaning of card in the downward position | 
| {cardName}.first_element | string | Main elemental alignment of the card |  
| {cardName}.second_element | string | Secondary elemental alignment of the card |

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



## Retrieve All Cards in a Minor Acana Symbol 

### `GET /card/minor/{symbol}/all.json`  
Retrieve all the cards for the minor arcana symbol.

#### Resource URL
https://dajeki.github.io/tarot-api/card/{symbol}/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| symbol | string | yes | One of the 4 tarot symbols sword, pentacle, wand, cup | 

#### Example Request
GET https://dajeki.github.io/tarot-api/card/pentacle/all.json

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{ 
	"Ace of Pentacles": {
		"id": 64,
		"upright": "opportunity, prosperity, new venture",
		"reversed": "lost opportunity, missed chance, bad investment",
		"first_element": "earth",
		"second_element": null
	},
	"Two of Pentacles": {
		"id": 65,
		"upright": "balancing decisions, priorities, adapting to change",
		"reversed": "loss of balance, disorganized, overwhelmed",
		"first_element": "earth",
		"second_element": null
	},
	"Three of Pentacles": {
		"id": 66,
		"upright": "teamwork, collaboration, building",
		"reversed": "lack of teamwork, disorganized, group conflict",
		"first_element": "earth",
		"second_element": null
	},
	"Four of Pentacles": {
		"id": 67,
		"upright": "conservation, frugality, security",
		"reversed": "greediness, stinginess, possessiveness",
		"first_element": "earth",
		"second_element": null
	},
	// rest of the pentacles
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- | 
| {cardName} | object | Information about the card. Will be accessed by the name of the card  | 
| {cardName}.id | number | Number of the card in a tarot deck. | 
| {cardName}.upright | string | Meaning of card in the upright position. | 
| {cardName}.reversed | string | Meaning of card in the downward position | 
| {cardName}.first_element | string | Main elemental alignment of the card |  
| {cardName}.second_element | string | Secondary elemental alignment of the card |

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



## Retrieve a Single Card From Major Arcana

### `GET /card/major/{cardName}.json`  
Retrieve a single major arcana card

#### Resource URL
https://dajeki.github.io/tarot-api/card/major/{cardName}.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| cardName | string | yes | Name of the major arcana card all lowercase and with underscores |

#### Example Request
GET https://dajeki.github.io/tarot-api/card/major/wheel_of_fortune.json

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{ 
	"id": 10,
	"upright": "change, cycles, inevitable fate",
	"reversed": "no control, clinging to control, bad luck",
	"first_element": "aether",
	"second_element": "fire"
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |  
| id | number | Number of the card in a tarot deck. | 
| upright | string | Meaning of card in the upright position. | 
| reversed | string | Meaning of card in the downward position | 
| first_element | string | Main elemental alignment of the card |  
| second_element | string | Secondary elemental alignment of the card |

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



## Retrieve a Single Card From Minor Arcana

### `GET /card/minor/{symbol}/{cardNumber}.json`  
Retrieve a single minor arcana card

#### Resource URL
https://dajeki.github.io/tarot-api/card/minor/{symbol}/{cardNumber}.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| symbol | string | yes | One of the 4 tarot symbols sword, pentacle, wand, cup | 
| cardNumber | number | yes | number of the card in its suit. 1 for ace and 14 for king |

#### Example Request
GET https://dajeki.github.io/tarot-api/card/sword/11.json

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{ 
	"id": 60,
	"upright": "curiosity, restlessness, mental energy",
	"reversed": "deception, manipulation, all talk",
	"first_element": "air",
	"second_element": "earth"
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |  
| id | number | Number of the card in a tarot deck. | 
| upright | string | Meaning of card in the upright position. | 
| reversed | string | Meaning of card in the downward position | 
| first_element | string | Main elemental alignment of the card |  
| second_element | string | Secondary elemental alignment of the card |

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



## Retrieve All Astrology Modality

### `GET /astrologyModality/all.json`  
Retrieve all astrology modal

#### Resource URL
https://dajeki.github.io/tarot-api/astrologyModality/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| N/A | N/A | N/A | N/A | 

#### Example Request
GET https://dajeki.github.io/tarot-api/astrologyModality/all.json

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{ 
	"cardinal": {
        "card": "queen",
        "attribute": "signs that begin seasons",
        "meaning": "initiators, self-starters, assertive, decisive and sometimes aggressive",
        "fire": {
            "zodiac": "Aries",
            "season": "spring"
        },
        "earth": {
            "zodiac": "Capricorn",
            "season": "winter"
        },
        "air": {
            "zodiac": "Libra",
            "season": "fall"
        },
        "water": {
            "zodiac": "Cancer",
            "season": "summer"
        }
    },
    "fixed": {
	    //fixed information
	},
	"mutable": {
	    //mutable information
	}
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |  
| {astrologyModality} | object | Information about the modality between seasons, zodiacs, and court cards | 
| {astrologyModality}.card | string | Card that aligns with the modality | 
| {astrologyModality}.attribute | string | Attribute related to the time of the season | 
| {astrologyModality}.meaning | string | Meaning of modality |  
| {element} | object | elements related to the cardinal |
| {element}.zodiac | "string" | Zodiac sign for the particular element in the particular modality |
| {element}.season | "string" | Season related to the particular element within the particular modality |

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



## Retrieve a Single Astrology Modality

### `GET /astrologyModality/{modality}.json`  
Retrieve an astrology modal

#### Resource URL
https://dajeki.github.io/tarot-api/astrologyModality/{modality}.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| modality | string | yes | One of the three modalities available. cardinal, fixed, mutable | 

#### Example Request
GET https://dajeki.github.io/tarot-api/astrologyModality/cardinal.json

#### Example Response
```json
HTTP/1.1 200 OK Content-Type: application/json

{
	"card": "queen",
	"attribute": "signs that begin seasons",
	"meaning": "initiators, self-starters, assertive, decisive and sometimes aggressive",
	"fire": {
		"zodiac": "Aries",
		"season": "spring"
	},
	"earth": {
		"zodiac": "Capricorn",
		"season": "winter"
	},
	"air": {
		"zodiac": "Libra",
		"season": "fall"
	},
	"water": {
		"zodiac": "Cancer",
		"season": "summer"
	}
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |   
| card | string | Card that aligns with the modality | 
| attribute | string | Attribute related to the time of the season | 
| meaning | string | Meaning of modality |  
| {element} | object | elements related to the cardinal |
| {element}.zodiac | "string" | Zodiac sign for the particular element in the particular modality |
| {element}.season | "string" | Season related to the particular element within the particular modality |

#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



