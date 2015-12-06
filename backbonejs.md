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
    model: Song, // Specify the model that will be in the collection
    url: "/api/songs" // Specify the url path where to retrieve the collection from
});


// Instantiating the Collection
var songs = new Songs([ // Adding initial model instances to the collection
    new Song({ title: "Song 1" }),
    new Song({ title: "Song 2" }),
    new Song({ title: "Song 3" })
]);
```

##### Modifying Collections
```js 
// Adding model instance(s) to the collection
songs.add(new Song({ title: "Song 4" }), { at: 0 }); // The model instance will be added to the end of the collection unless the 2nd optional argument is provided, which specifies at which index position to add the model instance.

songs.push(new Song({ title: "Song 4" })); // This will do the same thing, but does not support an argument to add the model instance to a specified index position.

// Get the model instance at the specified index position in the collection
var firstSong = songs.at(0);

// Get the model instance with the specified client id in the collection
var songWithIdC1 = songs.get("c1");

// Remove a model instance from a collection
songs.remove(firstSong);

songs.pop(new Song({ title: "Song 4" })); // This will do the same thing, but does not support an argument to add the model instance to a specified index position.

// Get the number of model instances inside the collection
var numModelsInCollection = songs.length;
```

##### Search in Collections
```js
// Get an array of model instances, in a collection, where a specified attribute is equal to specified value
var jazzSongs = songs.where({ genre: "Jazz", title: "Song 2" });

// Get the first model instance, in a collection, where a specified attribute is equal to specified value
var firstJazzSong = songs.findWhere({ genre: "Jazz" });

// Get an array of model instances, in a collection, that meet a custom conditional logic
var topDownloads = songs.filter(function(song) {
    return song.get("downloads") > 100; // This example will return all model instances where the "downloads" attribute is greater than 100
});

// Loop through each model instance in a collection
songs.each(function(song) {
    console.log(song);
});
```

##### Connecting to the Server
```js
var songs = new Songs();
songs.fetch({
    data: {
        page: 2 // Any attributes in the data property are added as GET variables to the end of the URL string
    },
    success: function(){},
    error: function(){}
}); // GET /api/songs?page=2
```


### Views

##### Creating Views
```js 
// Creating a View
var SongView = Backbone.View.extend({
  tagName: "span", // Tag which is created by Backbone, which the View attaches itself to, if no selector is specified when instantiating the view
  className: "song music", // Classes that are placed on the tag which is created by Backbone, which the View attaches itself to, if no selector is specified when instantiating the view
  id: "1234", // ID which is placed on the tag which is created by Backbone, which the View attaches itself to, if no selector is specified when instantiating the view
  attributes: { // Data attributes that are placed on the tag which is created by Backbone, which the View attaches itself to, if no selector is specified when instantiating the view
    "data-genre": "Jazz"
  },

  initialize: function() {
    this.render();
  },

  render: function() {
    this.$el.html("Hello World"); // The "this.$el" is an easy way to access the jQuery object of the element that the view is attached to

    return this; // This is necessary for chaining methods
  }
});


// Instantiating the View
var songView = new SongView(); // Specifying which dom element the view should attach to
$("body").append(songView.$el); // This is appending the entire view jquery object to the specified selector. When it creates the jquery object, since we did not specify a selector on the page when instantiating the view, it will create an element with the options specified in the model above

// This way the jquery object, that the view is attached to, becomes the specified element and it ignores the options specified above (tagName, className, id, attributes)
var songView2 = new SongView({ el: "#container" }); // Specifying which dom element the view should attach to
```

##### Passing data to Views
```js
// Passing a Model to a View
var Song = Backbone.Model.extend();

var SongView = Backbone.View.extend({
  render: function() {
    this.$el.html(this.model.get("title")); // An example of how we can access an attribute value of the model that is assigned to the view

    return this;
  }
});

var song = new Song({ title: "Blue in Green" });

var songView = new SongView({ el: "#container", model: song }); // Specifying which dom element the view should attach to, and which model is assigned to the view
songView.render();


// Passing a Collection to a View
var SongView = Backbone.View.extend({ // This first view is for each list item
  tagName: "li",

  render: function() {
    this.$el.html(this.model.get("title"));

    return this;
  }
});

var SongsView = Backbone.View.extend({
  render: function() {
    var self = this; // Assign the "this" value to another variable so we can access it inside the loop which has its own this value

    this.model.each(function(song){ // Loop through each of the songs in the collection
      var songView = new SongView({ model: song }); // Create an instance of the View for each song that will be assigned the model data for that song and will be eventually added to an "li" tag
      self.$el.append(songView.render().$el); // Append the jquery object that is created, with it's song name, to the current jquery object which will eventually be inserted into the dom element specified in the instantiation (which in this case is "#songs")
    });
  }
});

var Song = Backbone.Model.extend();
var Songs = Backbone.Collection.extend({
  model: Song
});

var songs = new Songs([
  new Song({ title: "Blue in Green" }),
  new Song({ title: "So What" }),
  new Song({ title: "All Blues" })
]);

var songsView = new SongsView({ el: "#songs", model: songs }); // Associating the collection of model instances(songs) to this view, which will loop through each model(song), grab the title and place it into the "li" that it creates, before appending each of those "li's" to the end of the jquery object of which its contents will be placed within the dom element specified in the instantiation(#songs)
songsView.render();
```

##### Handling events in a View
```js
// Handling DOM events in a View
var SongView = Backbone.View.extend({
  events: {
    "click button": "onClick", // Run the "onClick" function when the any button is clicked
    "click button.bookmark": "onClickBookmark", // Run the "onClickBookmark" function when the a button with the class "bookmark" is clicked
    "click input[type=button]": "doSomething" // Shows that you can include the same types of selectors as in jQuery
  },

  onClick: function() {
    console.log("Listen clicked");
  },

  onClickBookmark: function(e) {
    e.stopPropagation(); // Stops the click event on the clicked element to propogate(or move on) to any other handlers that apply to it, so it only runs this function

    console.log("Bookmark Clicked");
  },

  render: function() {
    this.$el.html(this.model.get("title") + " <button>Listen</button> <button class='bookmark'>Bookmark</button>");

    return this;
  }
});

var Song = Backbone.Model.extend();
var song = new Song({ title: "Blue in Green" });
var songView = new SongView({ el: "body", model: song });
songView.render();


// Handling Model events in a View
var Song = Backbone.Model.extend({
  defaults: {
    listeners: 0
  }
});

var SongView = Backbone.View.extend({
  initialize: function() {
    this.render();
    this.model.on("change", this.onModelChange, this); // Model event that listens if any attribute is changed. If it is, it will run the onModelChange() function and pass the "this" value as it relates to the View, since this is looking at any changes in the model and the default "this" would be related to the model, which we don't want in this case
  },

  onModelChange: function() {
    this.render();
    this.$el.addClass("example-class"); // Adds a class to the dom element that is associated with the model
  },

  render: function() {
    this.$el.html(this.model.get("title") + " - Listeners: " + this.model.get("listeners"));

    return this;
  }
});

var song = new Song({ title: "Blue in Green" });
var songView = new SongView({ el: "#container", model: song });


// Handling Collection events in a View
var Song = Backbone.Model.extend();
var Songs = Backbone.Collection.extend({
  model: Song
});

var SongView = Backbone.View.extend({
  tagName: "li",

  render: function() {
    this.$el.html(this.model.get("title"));
    this.$el.attr("id", this.model.id); // Adding an ID attribute so we can refer to a specific selector when we need to remove it from the DOM

    return this;
  }
});

var SongsView = Backbone.View.extend({
  tagName: "ul",

  initialize: function() {
    this.model.on("add", this.onSongAdded, this); // Model event that listens if a model is added to a collection
    this.model.on("remove", this.onSongRemoved, this); // Model event that listens if a model is removed from a collection
  },

  onSongAdded: function(song) {
    var songView = new SongView({ model: song }); // When a model is added, we grab that model and create a new model view
    this.$el.append(songView.render().$el); // Render the new model view and append it to the end of the collection view's DOM element
  },

  onSongRemoved: function(song) {
    this.$("li#" + song.id).remove(); // Remove the DOM element on the page that has the ID attribute of the song that was removed
  },

  render: function() {
    var self = this;

    this.model.each(function(song){
      var songView = new SongView({ model: song });
      self.$el.append(songView.render().$el);
    });
  }
});

var songs = new Songs([
  new Song({ id: 1, title: "Blue in Green" }),
  new Song({ id: 2, title: "So What" }),
  new Song({ id: 3, title: "All Blues" })
]);

var songsView = new SongsView({ el: "#songs", model: songs });
songsView.render();


// Binding and Triggering Custom Events
var person = {
    walk: function(){
        this.trigger("walking", { speed: 10 }); // Trigger a custom event and pass properties with it
    }
};

_.extend(person, Backbone.Events); // Give all the properties and methods of the "Backbone.Events" object to the object "person"

person.on("walking", function(e) { // Listen for any time that the object triggers the custom event and then run the callback function
    console.log(e.speed);
});

person.off("walking"); // Remove the listener for the custom event 
```

##### Using Templates - Underscore.js
*In JS:*
```js
// Using Templates - Underscore.js
var Song = Backbone.Model.extend();

var SongView = Backbone.View.extend({
  render: function() {
    var template = _.template($("#songTemplate").html()); // Finds the Underscore.js template on the page that is specified by the ID attribute, saves the html, and puts it into a variable that is using the _.template() function
    var html = template(this.model.toJSON()); // Grabs the model attributes, converts them to JSON, and runs them through a function which converts it to HTML. The function name is whatever the var from the last step is called.
    this.$el.html(html); // The generated HTML is made to be the contents of the DOM element associated with the view, which in this case is "#container"

    return this;
  }
});

var song = new Song({ id: 1, title: "Blue in Green", plays: 1500 });

var songView = new SongView({ el: "#container", model: song });
songView.render();
```

*In HTML:*
```html
<!DOCTYPE html>
<html class="no-js">
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <title>Code Example</title>
  <meta name="description" content="">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <link rel="stylesheet" href="css/normalize.min.css">
  <link rel="stylesheet" href="css/main.css">
  <link rel="stylesheet" href="css/styles.css">

  <script src="js/lib/modernizr-2.6.2.min.js"></script>
</head>
<body>
  <div id="container"></div>

  <script src="js/lib/jquery-min.js"></script>
  <script src="js/lib/underscore-min.js"></script>
  <script src="js/lib/backbone-min.js"></script>

  <script id="songTemplate" type="text/html">
    <%= title %> <!-- When the "=" sign is used at the beginning of the opening Underscore.js tag, it will display the variable -->
    <button>Listen</button>

    <% if (plays > 1000) { %>  <!-- When the "=" is not present, it will evaluated as normal JavaScript -->
      <span class="popular">Popular</span>
    <% } %>
  </script>

  <script src="js/main.js"></script>
</body>
</html>
```












