element.moscovium = {
color: ["#e0e0e0"],
behavior: behavior.wall,
category: "powders",
state: "solid",
conduct: 0.8,
        if(elements.nihonium){
            if(Math.random()<0.038){
                for (var i = 0; i < adjacentCoords.length; i++){
                    var coord = adjacentCoords[i];
                    var x = pixel.x+coord[0];
                    var y = pixel.y+coord[1];
                    if (isEmpty(x, y) && Math.random()<0.01){
                        createPixel(x, y, "nihinoum")
                        pixelMap[x][y].temp += 250
                        break;
                    }
                }
                changePixel(pixel, "nihonium", false)
                pixel.temp += 100
            }
        }else{
            if(Math.random()<0.038){
                for (var i = 0; i < adjacentCoords.length; i++){
                    var coord = adjacentCoords[i];
                    var x = pixel.x+coord[0];
                    var y = pixel.y+coord[1];
                    if (!isEmpty(x, y, true) && Math.random()<0.01){
                        pixel.temp += 100
                    }
                }
                changePixel(pixel, "nihonium", false)
                pixel.temp += 250
            }
        }
        for (var i = 0; i < adjacentCoords.length; i++){
            var coord = adjacentCoords[i];
            var x = pixel.x+coord[0];
            var y = pixel.y+coord[1];
            if (isEmpty(x, y) && Math.random() < 0.01){
                createPixel("radiation", x, y);
            }
        }
    }
} 	
element.antimony = {
color: ["#8c8a84","ffffff", "#36363","#b0d7ff"],
	hidden: false,
	category: "solids",
	behavior.wall
tempHigh: 630,
stateHigh: "molten_antimony",
density: 6697,
conduct: 2.5
reactions: {
    "chlorine": { elem2: "explosion" },
	"fluorine": { elem2: "explosion" },
	"bromine": {elem2: "explosion" },
	"iodine": {elem2: "explosion" },
	"hydrochloric_acid" {elem2: "explosion" },
	"sulfuric_acid {elem2: "explosion" },
	"nitric_acid {elem2: "explosion" },
	"oxygen" {elem1: null, elem2: "antimony_oxide"},
	"sulfur" {elem1: null, elem2:"antimony_sulfide},
}
element.antimony_oxide = {
	color: ["#ffffff"]
	category: "powders"
	behavior.powder
	state: "solid"
	density: 307,
}
element.antimony_sulfide = {
    color: ["#ffffff", "#36363"],
	category: "powders"
	behavior.powder
	state: "solid"
	density: 4640
}
element.arsenic = {
    color: ["#f2f2f2", "#8c8c8c"],
	category: "powders,
	behavior.powder,
	state: "solid",
	concuct: 3.3,
	density: 5727,
}
element.phosphorus = {
	color: ["#c42121", "#a12323"],
	category: "powders",
	state: "solid",
	behavior.powder,
	tempHigh: 44
	stateHigh: "liquid_phosphorus
	conduct: 10,
	density: 1823,
	reactions: {
	"chlorine": { elem2: "explosion" },
	"fluorine": { elem2: "explosion" },
	"bromine": {elem2: "explosion" },
	"iodine": {elem2: "explosion" },
	"astatine": {elem2: "explosion"},
	}
}
element.liqud_phosphorus = {
	burn: 80,
	burnTime: 500,
	behavior.molten_antimony,
	stateLow: "phosphorus",
	tempLow: 44,
	density: 1823,
	color: ["#dea94e", "#ffa200"],
	reactions: {
	"chlorine": { elem2: "explosion" },
	"fluorine": { elem2: "explosion" },
	"bromine": {elem2: "explosion" },
	"iodine": {elem2: "explosion" },
	"astatine": {elem2: "explosion"},
	}
}
