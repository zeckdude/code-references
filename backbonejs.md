# Backbone.js

### Models

##### Creating Models
```js 
// Create a Model
var Song = Backbone.Model.extend({
    idAttribute: "songId", // If the primary key is not named "id", the primary key name can be identified here
    urlRoot: "/api/songs", // URL root where the JSON data is supposed to be pulled from
    defaults: { // Default values that are passed to each instance that is created
        downloads: 0
    },
    initialize: function() { // Constructor function that is automatically run each time an instance is created
        console.log("I am the constructor function");
    },
    validate: function(attrs){ // These is where validation rules are established
        if (!attrs.title)
            return "Title is required.";
    },
    play: function() { // Custom function that can be called by an instance of the model
        console.log("Song is playing");
    }
});

// Instantiate the Model
var song = new Song();

// Inherit the functions and default attributes of another model
var Mp3 = Song.extend();
var mp3 = new Mp3();
mp3.play(); // This will run the play() function that was inherited from the Song model
var Mp3 = Song.extend({
    play: function() { // Custom function that will override the "play" function that was inherited from the Song model
        console.log("MP3 is playing");
    }
});
```

##### Working with the Attributes
```js 
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
var title = song.get("title");

// Remove a single attribute
song.unset("title");

// Remove all attributes
song.clear();

// Check if a model has a specified attribute
var hasTitle = song.has("title");
```

##### Validation
```js
var isValid = song.isValid(); // Checks if the song instance is valid according to the validation rules that was set in the model
var lastError = song.validationError; // Returns the last validation error message
```

##### Syncing with the Server
```js
// Fetching a Model
var song = new Song({ id: 1 });
song.fetch({ // Gets the "Song" with the id of 1 from the database
    success: function() {...},
    error: function() {...}
}); // GET /api/songs/1

// Updating a Model
var song = new Song({ id: 1 });
song.fetch();
song.set("title", "Over the Rainbow");
song.save({}, { // Saves the song to the database
    success: function() {...},
    error: function() {...}
}); // PUT /api/songs/1

// Inserting a Model
var song = new Song();
song.set("title", "Over the Rainbow");
song.save(); // POST /api/songs/1

// Deleting a Model
var song = new Song({ id: 1 });
song.destroy({ // Remove a record from the database
    success: function() {...},
    error: function() {...}
}); // DELETE /api/songs/1
```


### Collections

##### Creating Collections
```js 
// Create a Collection
var Songs = Backbone.Collection.extend({
    model: Song // Specify the model that will be in the collection
});

// Instantiating the Collection
var songs = new Songs([ // Adding initial model instances to the collection
    new Song({ title: "Song 1" }),
    new Song({ title: "Song 2" }),
    new Song({ title: "Song 3" })
]);

// Adding model instance to the collection
songs.add(new Song({ title: "Song 4" }));

// Get the model instance at the specified index position in the collection
var firstSong = songs.at(0);

// Get the model instance with the specified client id in the collection
var songWithIdC1 = songs.get("c1");

// Remove a model instance from a collection
songs.remove(firstSong);
```




















