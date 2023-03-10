<!-- TOC start -->
- [Retrieve All Information ](#retrieve-all-information)
  * [`GET /all.json`  ](#get-alljson)
- [Retrieve All Cards ](#retrieve-all-cards)
  * [`GET /card/[{arcana}]/all.json`  ](#get-cardarcanaalljson)
- [Retrieve All Cards in a Minor Acana Symbol ](#retrieve-all-cards-in-a-minor-acana-symbol)
  * [`GET /card/minor/{symbol}/all.json`  ](#get-cardminorsymbolalljson)
- [Retrieve a Single Card From Major Arcana](#retrieve-a-single-card-from-major-arcana)
  * [`GET /card/major/{cardName}.json`  ](#get-cardmajorcardnamejson)
- [Retrieve a Single Card From Minor Arcana](#retrieve-a-single-card-from-minor-arcana)
  * [`GET /card/minor/{symbol}/{cardNumber}.json`  ](#get-cardminorsymbolcardnumberjson)
- [Retrieve All Cards by Element ](#retrieve-all-cards-by-element)
  * [`GET /card/element/{element}/all.json`](#get-cardelementelementalljson)
- [Retrieve Minor or Major Arcana Cards by Element ](#retrieve-minor-or-major-arcana-cards-by-element)
  * [`GET /card/element/{element}/{arcana}.json`](#get-cardelementelementarcanajson)
- [Retrieve All Astrology Modality](#retrieve-all-astrology-modality)
  * [`GET /astrologyModality/all.json`  ](#get-astrologymodalityalljson)
- [Retrieve a Single Astrology Modality](#retrieve-a-single-astrology-modality)
  * [`GET /astrologyModality/{modality}.json`  ](#get-astrologymodalitymodalityjson)
- [Retrieve All Zodiac Sign Information](#retrieve-all-zodiac-sign-information)
  * [`GET /zodiac/all.json`  ](#get-zodiacalljson)
- [Retrieve Zodiac Sign Information](#retrieve-zodiac-sign-information)
  * [`GET /zodiac/{sign}.json`  ](#get-zodiacsignjson)
- [Retrieve All Element Information](#retrieve-all-element-information)
  * [`GET /element/all.json`  ](#get-elementalljson)
- [Retrieve Element Information](#retrieve-element-information)
  * [`GET /element/{element}.json`  ](#get-elementelementjson)
<!-- TOC end -->
<!-- TOC --><a name="retrieve-all-information"></a>
## Retrieve All Information 

<!-- TOC --><a name="get-alljson"></a>
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
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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



<!-- TOC --><a name="retrieve-all-cards"></a>
## Retrieve All Cards 

<!-- TOC --><a name="get-cardarcanaalljson"></a>
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
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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
		"second_element": "earth"
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



<!-- TOC --><a name="retrieve-all-cards-in-a-minor-acana-symbol"></a>
## Retrieve All Cards in a Minor Acana Symbol 

<!-- TOC --><a name="get-cardminorsymbolalljson"></a>
### `GET /card/minor/{symbol}/all.json`  
Retrieve all the cards for the minor arcana symbol.

#### Resource URL
https://dajeki.github.io/tarot-api/card/{symbol}/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| symbol | string | yes | One of the four tarot symbols sword, pentacle, wand, cup | 

#### Example Request
GET https://dajeki.github.io/tarot-api/card/pentacle/all.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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



<!-- TOC --><a name="retrieve-a-single-card-from-major-arcana"></a>
## Retrieve a Single Card From Major Arcana

<!-- TOC --><a name="get-cardmajorcardnamejson"></a>
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
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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



<!-- TOC --><a name="retrieve-a-single-card-from-minor-arcana"></a>
## Retrieve a Single Card From Minor Arcana

<!-- TOC --><a name="get-cardminorsymbolcardnumberjson"></a>
### `GET /card/minor/{symbol}/{cardNumber}.json`  
Retrieve a single minor arcana card

#### Resource URL
https://dajeki.github.io/tarot-api/card/minor/{symbol}/{cardNumber}.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| symbol | string | yes | One of the four tarot symbols sword, pentacle, wand, cup | 
| cardNumber | number | yes | number of the card in its suit. 1 for ace and 14 for king |

#### Example Request
GET https://dajeki.github.io/tarot-api/card/minor/sword/11.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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



<!-- TOC --><a name="retrieve-all-cards-by-element"></a>
## Retrieve All Cards by Element 

<!-- TOC --><a name="get-cardelementelementalljson"></a>
### `GET /card/element/{element}/all.json`
Retrieve all the cards for the minor arcana symbol.

#### Resource URL
https://dajeki.github.io/tarot-api/card/element/{element}/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| element | string | yes | One of the four elements | 

#### Example Request
GET https://dajeki.github.io/tarot-api/card/element/fire/all.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
{ 
	"The Emperor": {
		"id": 4,
		"upright": "authority, structure, control, fatherhood",
		"reversed": "tyranny, rigidity, coldness",
		"first_element": "aether",
		"second_element": "fire"
	},
	"Strength": {
		"id": 8,
		"upright": "inner strength, bravery, compassion, focus",
		"reversed": "self doubt, weakness, insecurity",
		"first_element": "aether",
		"second_element": "fire"
	},
	"Knight of Pentacles": {
		"id": 75,
		"upright": "efficiency, hard work, responsibility",
		"reversed": "laziness, obsessiveness, work without reward",
		"first_element": "earth",
		"second_element": "fire"
	},
	"Two of Wands": {
		"id": 23,
		"upright": "planning, making decisions, leaving home",
		"reversed": "fear of change, playing safe, bad planning",
		"first_element": "fire",
		"second_element": null
	},
	// rest of cards with a fire element
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



<!-- TOC --><a name="retrieve-minor-or-major-arcana-cards-by-element"></a>
## Retrieve Minor or Major Arcana Cards by Element 

<!-- TOC --><a name="get-cardelementelementarcanajson"></a>
### `GET /card/element/{element}/{arcana}.json`
Retrieve all the cards for the minor arcana symbol.

#### Resource URL
https://dajeki.github.io/tarot-api/card/element/{element}/{arcana}.json 

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| element | string | yes | One of the four elements | 
| arcana | string | no | Can be either `minor` or `major` to denote what arcana you would like to get cards from. |

#### Example Request
GET https://dajeki.github.io/tarot-api/card/element/fire/major.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
{ 
	"The Emperor": {
		"id": 4,
		"upright": "authority, structure, control, fatherhood",
		"reversed": "tyranny, rigidity, coldness",
		"first_element": "aether",
		"second_element": "fire"
	},
	"Strength": {
		"id": 8,
		"upright": "inner strength, bravery, compassion, focus",
		"reversed": "self doubt, weakness, insecurity",
		"first_element": "aether",
		"second_element": "fire"
	},
	"Wheel of Fortune": {
		"id": 10,
		"upright": "change, cycles, inevitable fate",
		"reversed": "no control, clinging to control, bad luck",
		"first_element": "aether",
		"second_element": "fire"
	},
	"Temperance": {
		"id": 14,
		"upright": "middle path, patience, finding meaning",
		"reversed": "extremes, excess, lack of balance",
		"first_element": "aether",
		"second_element": "fire"
	
	},
	// rest of major arcana cards with a fire element
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



<!-- TOC --><a name="retrieve-all-astrology-modality"></a>
## Retrieve All Astrology Modality

<!-- TOC --><a name="get-astrologymodalityalljson"></a>
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
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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



<!-- TOC --><a name="retrieve-a-single-astrology-modality"></a>
## Retrieve a Single Astrology Modality

<!-- TOC --><a name="get-astrologymodalitymodalityjson"></a>
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
`HTTP/1.1 200 OK Content-Type: application/json`
```json
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



<!-- TOC --><a name="retrieve-all-zodiac-sign-information"></a>
## Retrieve All Zodiac Sign Information

<!-- TOC --><a name="get-zodiacalljson"></a>
### `GET /zodiac/all.json`  
Retrieve an astrology modal

#### Resource URL
https://dajeki.github.io/tarot-api/zodiac/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| N/A | N/A | N/A | N/A | 

#### Example Request
GET https://dajeki.github.io/tarot-api/zodiac/all.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
{
	"Cancer": {
		"element": "water",
		"nature": "security",
		"astrologyModality": "cardinal",
		"rulingBodyModern": "Moon",
		"rulingBodyTraditional": null
	},
	"Scorpio": {
		"element": "water",
		"nature": "power",
		"astrologyModality": "fixed",
		"rulingBodyModern": "Pluto",
		"rulingBodyTraditional": "Mars"
	},
	"Pisces": {
		"element": "water",
		"nature": "connection",
		"astrologyModality": "mutable",
		"rulingBodyModern": "Neptune",
		"rulingBodyTraditional": "Jupiter"
	},
	// rest of zodiac signs
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |   
| {zodiacSign} | object | Name of the zodiac sign |
| {zodiacSign}.element | string | One of the four elements | 
| {zodiacSign}.nature | string | nature of the zodiac sign | 
| {zodiacSign}.astrologyModality | string | One of the three astrology modalities |  
| {zodiacSign}.rulingBodyModern | string | Ruling celestial body according to modern idea |
| {zodiacSign}.rulingBodyTraditional | "string" |  Ruling celestial body according to traditional idea |



<!-- TOC --><a name="retrieve-zodiac-sign-information"></a>
## Retrieve Zodiac Sign Information

<!-- TOC --><a name="get-zodiacsignjson"></a>
### `GET /zodiac/{sign}.json`  
Retrieve an astrology modal

#### Resource URL
https://dajeki.github.io/tarot-api/zodiac/{sign}.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| sign | string | yes | Sign in the zodiac | 

#### Example Request
GET https://dajeki.github.io/tarot-api/zodiac/aquarius.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
{
	"element": "air",
	"nature": "innovation",
	"astrologyModality": "fixed",
	"rulingBodyModern": "Uranus",
	"rulingBodyTraditional": "Saturn"
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |   
| element | string | One of the four elements | 
| nature | string | nature of the zodiac sign | 
| astrologyModality| string | One of the three astrology modalities |  
| rulingBodyModern | string | Ruling celestial body according to modern idea |
| rulingBodyTraditional | "string" |  Ruling celestial body according to traditional idea |



<!-- TOC --><a name="retrieve-all-element-information"></a>
## Retrieve All Element Information

<!-- TOC --><a name="get-elementalljson"></a>
### `GET /element/all.json`  
Retrieve an astrology modal

#### Resource URL
https://dajeki.github.io/tarot-api/element/all.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| N/A | N/A | N/A | N/A | 

#### Example Request
GET https://dajeki.github.io/tarot-api/element/all.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
{
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
	},
	"earth": {
		// element information
	},
	// other elements
}
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |   
| {element} | string | One of the four elements | 
| {element}.minor | string | Minor arcana symbol | 
| {element}.colors | string[] | Array of colors |  
| {element}.zodiac | string[] | Zodiac signs associated with the element |
| {element}.animals | string |  Animals associated with the element |
| {element}.expression | string |  Element personal expression |
| {element}.attribute | string |  Elemental personal attribute |
| {element}.meaning | string |  Elemental meaning |



<!-- TOC --><a name="retrieve-element-information"></a>
## Retrieve Element Information

<!-- TOC --><a name="get-elementelementjson"></a>
### `GET /element/{element}.json`  
Retrieve an astrology modal

#### Resource URL
https://dajeki.github.io/tarot-api/element/{element}.json

#### Parameters
| Name | Type | Required | Description | 
| ---- | ---- | -------- | ----------- | 
| element | string | yes | One of the four elements | 

#### Example Request
GET https://dajeki.github.io/tarot-api/element/fire.json

#### Example Response
`HTTP/1.1 200 OK Content-Type: application/json`
```json
{
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
```

#### Response Properties
| Name | Type | Description | 
| ---- | ---- | ----------- |
| minor | string | Minor arcana symbol | 
| colors | string[] | Array of colors |  
| zodiac | string[] | Zodiac signs associated with the element |
| animals | string |  Animals associated with the element |
| expression | string |  Element personal expression |
| attribute | string |  Elemental personal attribute |
| meaning | string |  Elemental meaning |


