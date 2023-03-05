Javascript [[Library]] for frontend. jQuery is a fast, small, and feature-rich JavaScript library.
- HTML document traversal
- and Manipulation
- Event Handling
- Animations
- Ajax (fetch APIs)

### DOM Traversal and Manipulation
```javascript
$( "button.continue" ).html( "Next Step..." )
```

### Event Handling
```js
var hiddenBox = $( "#banner-message" );

$( "#button-container button").on( "click", function( event ) {

  hiddenBox.show();

});
```

### [[AJAX]]
```js
$.ajax({

  url: "/api/getWeather",

  data: {
	  zipcode: 97201
  },

  success: function( result ) {

    $( "#weather-temp" ).html( "<strong>" + result + "</strong> degrees" );
  }

});
```

