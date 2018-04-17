# Assignment-1
Using the Github for to display the information of the pokemon(questin 2 a)


var FullGame = {
  "pokemon": [{
    "id": 1,
    "num": "001",
    "name": "Bulbasaur",
    "img": "http://www.serebii.net/pokemongo/pokemon/001.png",
    "type": [
      "Grass",
      "Poison"
    ],
    "height": "0.71 m",
    "weight": "6.9 kg",
    "candy": "Bulbasaur Candy",
    "candy_count": 25,
    "egg": "2 km",
    "spawn_chance": 0.69,
    "avg_spawns": 69,
    "spawn_time": "20:00",
    "multipliers": [1.58],
    "weaknesses": [
      "Fire",
      "Ice",
      "Flying",
      "Psychic"
    ],
    "next_evolution": [{
      "num": "002",
      "name": "Ivysaur"
    }, {
      "num": "003",
      "name": "Venusaur"
    }]
  }, {
    "id": 2,
    "num": "002",
    "name": "Ivysaur",
    "img": "http://www.serebii.net/pokemongo/pokemon/002.png",
    "type": [
      "Grass",
      "Poison"
    ],
    "height": "0.99 m",
    "weight": "13.0 kg",
    "candy": "Bulbasaur Candy",
    "candy_count": 100,
    "egg": "Not in Eggs",
    "spawn_chance": 0.042,
    "avg_spawns": 4.2,
    "spawn_time": "07:00",
    "multipliers": [
      1.2,
      1.6
    ],
    "weaknesses": [
      "Fire",
      "Ice",
      "Flying",
      "Psychic"
    ],
    "prev_evolution": [{
      "num": "001",
      "name": "Bulbasaur"
    }],
    "next_evolution": [{
      "num": "003",
      "name": "Venusaur"
    }]
  }, {
    "id": 3,
    "num": "003",
    "name": "Venusaur",
    "img": "http://www.serebii.net/pokemongo/pokemon/003.png",
    "type": [
      "Grass",
      "Poison"
    ],
    "height": "2.01 m",
    "weight": "100.0 kg",
    "candy": "Bulbasaur Candy",
    "egg": "Not in Eggs",
    "spawn_chance": 0.017,
    "avg_spawns": 1.7,
    "spawn_time": "11:30",
    "multipliers": null,
    "weaknesses": [
      "Fire",
      "Ice",
      "Flying",
      "Psychic"
    ],
    "prev_evolution": [{
      "num": "001",
      "name": "Bulbasaur"
    }, {
      "num": "002",
      "name": "Ivysaur"
    }]
  }]
};

//2.a)Function to take pokemon's name as argument and display the information of that pokemon.

var name = prompt('Enter the name of Pokemon'); //Input the name of the pokemon 

var DetailOfPokemon = function(name, FullGame) 
{
  for (var currentPokemon in FullGame.pokemon)//iterate through each object of pokemon array
  {
    if (FullGame.pokemon[currentPokemon].name == name)    //condition to check the given name matches with pokemon name
    {
      var Detail = FullGame.pokemon[currentPokemon];
      console.log(Detail);//if matches print the information of that pokemon
      return;
    }
    else 
    {
    console.log("Type Again");      
    }
  }
};
DetailOfPokemon(name, FullGame);//calling the function



//2.b)Function that takes pokemon's name as an argument to find out which all pokemon have that name in their "next_evolution" field.
var evolvedName = window.prompt("enter the name evolvedname of a pokeman");//Input the pokemon name
var next_evolution = function(evolvedName,FullGame)//assigning declared function to a new variable
{
  for(var someName in FullGame.pokemon)//iterate through each object of pokemon array
  {
    for(var anyName in FullGame.pokemon[someName].next_evolution)//iterate through next_evolution property of that object
    {
      if(FullGame.pokemon[someName].next_evolution[anyName].name==evolvedName)//condition to check next_evolution and input pokemon name matches or not
      {
        var evolved = FullGame.pokemon[someName].name
        alert(evolved);//if matches print the name of those pokemon
      }
      else
      {
       
      }
    }
  }
};
next_evolution(evolvedName,FullGame);//calling the function




//2.c)Function that take "weakness" as input and gives the names of all pokemon who have that weakness.
function pokemonweaknesses(FullGame,pokemonweakness,weaknesses)//Declaration of function
{
 
 var flag = false;//assigning flag value false to a new variable
 for(var x in FullGame.pokemon)//iterate through each object of pokemon array
 {
   for(var y in FullGame.pokemon[x].weaknesses)//iterate through weaknesses array inside each pokemon
   {
     if(FullGame.pokemon[x].weaknesses[y]==pokemonweakness)//condition to search which pokemon have the weakness
     {
       var pokeweakname = alert(FullGame.pokemon[x].name)//if found append the pokemon name to this variable and flag value as true
       flag = true
      }
    }
  }
  if(flag == true)//if the flag value is set to true then print the pokemon name
  {
  alert()
  }
  else{
  alert("not found")
  }
}
var pokemonweakness = window.prompt("enter the pokemon weakness");//Input the weakness
pokemonweaknesses(FullGame,pokemonweakness);//calling the function
