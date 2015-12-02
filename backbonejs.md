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
```













