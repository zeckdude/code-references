# Backbone.js

### Models
```js 
// Create a Model
var song = Backbone.Model.extend();

// Instantiate the Model
var song = new Song();

// Create a Model that will run a constructor-like function each time an instance is created
var song = Backbone.Model.extend({
    initialize: function() {
        console.log("I am the constructor function")
    }
});

// Create a Model that will pass default values to each instance that is created
var song = Backbone.Model.extend({
    defaults: {
        genre: "rock-n-roll"
    }
});

// Set a single attribute
song.set("title", "Thriller");

// Set multiple attributes
song.set({
    artist: "Michael Jackson",
    title: "Thriller"
});

// Setting attributes when initializing a model object
var song = new Song({
    artist: "Michael Jackson",
    title: "Thriller"
});

// Get a JSON-representation of model
song.toJSON(); // Object { artist: "Michael Jackson", title: "Thriller" }

// Get an attribute
song.get("title");

// Remove a single attribute
song.unset("title");

// Remove all attributes
song.clear();

// Check if a model has a specified attribute
song.has("title");

test2
```









