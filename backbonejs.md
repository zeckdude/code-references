# Backbone.js

### Models
```js 
// Create a Model
var song = Backbone.Model.extend();

// Instantiate the Model
var song = new Song();

// Using set() method to set a single attribute
song.set("title", "Thriller");

// Using set() method to set multiple attributes
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




```









