<!-- TOC start -->
- [Retrieve All Information ](#retrieve-all-information)
  * [`GET /all.json`  ](#get-alljson)
    + [Resource URL](#resource-url)
    + [Parameters](#parameters)
    + [Example Request](#example-request)
    + [Example Response](#example-response)
    + [Response Properties](#response-properties)
    + [Error Responses](#error-responses)
- [Retrieve All Cards ](#retrieve-all-cards)
  * [`GET /card/[{arcana}]/all.json`  ](#get-cardarcanaalljson)
    + [Resource URL](#resource-url-1)
    + [Parameters](#parameters-1)
    + [Example Request](#example-request-1)
    + [Example Response](#example-response-1)
    + [Response Properties](#response-properties-1)
    + [Error Responses](#error-responses-1)
- [Retrieve All Cards in a Minor Acana Symbol ](#retrieve-all-cards-in-a-minor-acana-symbol)
  * [`GET /card/minor/{symbol}/all.json`  ](#get-cardminorsymbolalljson)
    + [Resource URL](#resource-url-2)
    + [Parameters](#parameters-2)
    + [Example Request](#example-request-2)
    + [Example Response](#example-response-2)
    + [Response Properties](#response-properties-2)
    + [Error Responses](#error-responses-2)
- [Retrieve a Single Card From Major Arcana](#retrieve-a-single-card-from-major-arcana)
  * [`GET /card/major/{cardName}.json`  ](#get-cardmajorcardnamejson)
    + [Resource URL](#resource-url-3)
    + [Parameters](#parameters-3)
    + [Example Request](#example-request-3)
    + [Example Response](#example-response-3)
    + [Response Properties](#response-properties-3)
    + [Error Responses](#error-responses-3)
- [Retrieve a Single Card From Minor Arcana](#retrieve-a-single-card-from-minor-arcana)
  * [`GET /card/minor/{symbol}/{cardNumber}.json`  ](#get-cardminorsymbolcardnumberjson)
    + [Resource URL](#resource-url-4)
    + [Parameters](#parameters-4)
    + [Example Request](#example-request-4)
    + [Example Response](#example-response-4)
    + [Response Properties](#response-properties-4)
    + [Error Responses](#error-responses-4)
- [Retrieve All Astrology Modality](#retrieve-all-astrology-modality)
  * [`GET /astrologyModality/all.json`  ](#get-astrologymodalityalljson)
    + [Resource URL](#resource-url-5)
    + [Parameters](#parameters-5)
    + [Example Request](#example-request-5)
    + [Example Response](#example-response-5)
    + [Response Properties](#response-properties-5)
    + [Error Responses](#error-responses-5)
- [Retrieve a Single Astrology Modality](#retrieve-a-single-astrology-modality)
  * [`GET /astrologyModality/{modality}.json`  ](#get-astrologymodalitymodalityjson)
    + [Resource URL](#resource-url-6)
    + [Parameters](#parameters-6)
    + [Example Request](#example-request-6)
    + [Example Response](#example-response-6)
    + [Response Properties](#response-properties-6)
    + [Error Responses](#error-responses-6)
<!-- TOC end -->
<!-- TOC --><a name="retrieve-all-information"></a>
## Retrieve All Information 

<!-- TOC --><a name="get-alljson"></a>
### `GET /all.json`  
Retrieves all the information the API has to offer.

<!-- TOC --><a name="resource-url"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/all.json

<!-- TOC --><a name="parameters"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| N/A | N/A | N/A | N/A | 

<!-- TOC --><a name="example-request"></a>
#### Example Request
GET [https://dajeki.github.io/tarot-api/all.json](https://dajeki.github.io/tarot-api/all.json)

<!-- TOC --><a name="example-response"></a>
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

<!-- TOC --><a name="response-properties"></a>
#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- | 
| element | object | Information about the element like color, minor arcana, or zodiac signs.  | 
| zodiac | object | Information about zodiac sign like element, ruling celestial body, or nature.| 
| courtElementalCorrespondence | object | Court cards secondary element and sub meaning. | 
| astrologyModality | object | Information that relates season timing, elements, and zodiac signs to meaning. | 
| card | object | Tarot card information like id, meaning, and element. |  

<!-- TOC --><a name="error-responses"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



<!-- TOC --><a name="retrieve-all-cards"></a>
## Retrieve All Cards 

<!-- TOC --><a name="get-cardarcanaalljson"></a>
### `GET /card/[{arcana}]/all.json`  
Retrieve all the cards or all the cards in either the major or minor arcana

<!-- TOC --><a name="resource-url-1"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/card/[{arcana}]/all.json

<!-- TOC --><a name="parameters-1"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| arcana | string | no | Can be either `minor` or `major` to denote what arcana you would like to get all of the cards from. | 

<!-- TOC --><a name="example-request-1"></a>
#### Example Request
GET [https://dajeki.github.io/tarot-api/card/all.json](https://dajeki.github.io/tarot-api/card/all.json)

<!-- TOC --><a name="example-response-1"></a>
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

<!-- TOC --><a name="response-properties-1"></a>
#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- | 
| {cardName} | object | Information about the card. Will be accessed by the name of the card  | 
| {cardName}.id | number | Number of the card in a tarot deck. | 
| {cardName}.upright | string | Meaning of card in the upright position. | 
| {cardName}.reversed | string | Meaning of card in the downward position | 
| {cardName}.first_element | string | Main elemental alignment of the card |  
| {cardName}.second_element | string | Secondary elemental alignment of the card |

<!-- TOC --><a name="error-responses-1"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



<!-- TOC --><a name="retrieve-all-cards-in-a-minor-acana-symbol"></a>
## Retrieve All Cards in a Minor Acana Symbol 

<!-- TOC --><a name="get-cardminorsymbolalljson"></a>
### `GET /card/minor/{symbol}/all.json`  
Retrieve all the cards for the minor arcana symbol.

<!-- TOC --><a name="resource-url-2"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/card/{symbol}/all.json

<!-- TOC --><a name="parameters-2"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| symbol | string | yes | One of the 4 tarot symbols sword, pentacle, wand, cup | 

<!-- TOC --><a name="example-request-2"></a>
#### Example Request
GET https://dajeki.github.io/tarot-api/card/pentacle/all.json

<!-- TOC --><a name="example-response-2"></a>
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

<!-- TOC --><a name="response-properties-2"></a>
#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- | 
| {cardName} | object | Information about the card. Will be accessed by the name of the card  | 
| {cardName}.id | number | Number of the card in a tarot deck. | 
| {cardName}.upright | string | Meaning of card in the upright position. | 
| {cardName}.reversed | string | Meaning of card in the downward position | 
| {cardName}.first_element | string | Main elemental alignment of the card |  
| {cardName}.second_element | string | Secondary elemental alignment of the card |

<!-- TOC --><a name="error-responses-2"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



<!-- TOC --><a name="retrieve-a-single-card-from-major-arcana"></a>
## Retrieve a Single Card From Major Arcana

<!-- TOC --><a name="get-cardmajorcardnamejson"></a>
### `GET /card/major/{cardName}.json`  
Retrieve a single major arcana card

<!-- TOC --><a name="resource-url-3"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/card/major/{cardName}.json

<!-- TOC --><a name="parameters-3"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| cardName | string | yes | Name of the major arcana card all lowercase and with underscores |

<!-- TOC --><a name="example-request-3"></a>
#### Example Request
GET https://dajeki.github.io/tarot-api/card/major/wheel_of_fortune.json

<!-- TOC --><a name="example-response-3"></a>
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

<!-- TOC --><a name="response-properties-3"></a>
#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |  
| id | number | Number of the card in a tarot deck. | 
| upright | string | Meaning of card in the upright position. | 
| reversed | string | Meaning of card in the downward position | 
| first_element | string | Main elemental alignment of the card |  
| second_element | string | Secondary elemental alignment of the card |

<!-- TOC --><a name="error-responses-3"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



<!-- TOC --><a name="retrieve-a-single-card-from-minor-arcana"></a>
## Retrieve a Single Card From Minor Arcana

<!-- TOC --><a name="get-cardminorsymbolcardnumberjson"></a>
### `GET /card/minor/{symbol}/{cardNumber}.json`  
Retrieve a single minor arcana card

<!-- TOC --><a name="resource-url-4"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/card/minor/{symbol}/{cardNumber}.json

<!-- TOC --><a name="parameters-4"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| symbol | string | yes | One of the 4 tarot symbols sword, pentacle, wand, cup | 
| cardNumber | number | yes | number of the card in its suit. 1 for ace and 14 for king |

<!-- TOC --><a name="example-request-4"></a>
#### Example Request
GET https://dajeki.github.io/tarot-api/card/sword/11.json

<!-- TOC --><a name="example-response-4"></a>
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

<!-- TOC --><a name="response-properties-4"></a>
#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |  
| id | number | Number of the card in a tarot deck. | 
| upright | string | Meaning of card in the upright position. | 
| reversed | string | Meaning of card in the downward position | 
| first_element | string | Main elemental alignment of the card |  
| second_element | string | Secondary elemental alignment of the card |

<!-- TOC --><a name="error-responses-4"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



<!-- TOC --><a name="retrieve-all-astrology-modality"></a>
## Retrieve All Astrology Modality

<!-- TOC --><a name="get-astrologymodalityalljson"></a>
### `GET /astrologyModality/all.json`  
Retrieve all astrology modal

<!-- TOC --><a name="resource-url-5"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/astrologyModality/all.json

<!-- TOC --><a name="parameters-5"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| N/A | N/A | N/A | N/A | 

<!-- TOC --><a name="example-request-5"></a>
#### Example Request
GET https://dajeki.github.io/tarot-api/astrologyModality/all.json

<!-- TOC --><a name="example-response-5"></a>
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

<!-- TOC --><a name="response-properties-5"></a>
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

<!-- TOC --><a name="error-responses-5"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



<!-- TOC --><a name="retrieve-a-single-astrology-modality"></a>
## Retrieve a Single Astrology Modality

<!-- TOC --><a name="get-astrologymodalitymodalityjson"></a>
### `GET /astrologyModality/{modality}.json`  
Retrieve an astrology modal

<!-- TOC --><a name="resource-url-6"></a>
#### Resource URL
https://dajeki.github.io/tarot-api/astrologyModality/{modality}.json

<!-- TOC --><a name="parameters-6"></a>
#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| modality | string | yes | One of the three modalities available. cardinal, fixed, mutable | 

<!-- TOC --><a name="example-request-6"></a>
#### Example Request
GET https://dajeki.github.io/tarot-api/astrologyModality/cardinal.json

<!-- TOC --><a name="example-response-6"></a>
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

<!-- TOC --><a name="response-properties-6"></a>
#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |   
| card | string | Card that aligns with the modality | 
| attribute | string | Attribute related to the time of the season | 
| meaning | string | Meaning of modality |  
| {element} | object | elements related to the cardinal |
| {element}.zodiac | "string" | Zodiac sign for the particular element in the particular modality |
| {element}.season | "string" | Season related to the particular element within the particular modality |

<!-- TOC --><a name="error-responses-6"></a>
#### Error Responses
| Status Code | Description | 
| ----------- | ----------- | 
| N/A | N/A |



