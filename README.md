# Dog API Testing dog.ceo/dog-api

https://github.com/ElliottLandsborough/dog-ceo-api

https://dog.ceo/dog-api/

https://github.com/jigsawpieces/dog-api-images#dog-api-images

Vanilla JS random dog image example

https://codepen.io/elliottlan/pen/MNEWNx?editors=1111


HTML 
```html
<button onClick="getRandomImage()">Click for a random image</button><br />
<br />
<img id="dogImage" src="https://dog.ceo/img/dog-api-logo.svg">
```

JS
```java
// function to perform a get request
function httpGet(theUrl)
{
    var xmlHttp = new XMLHttpRequest();
    xmlHttp.open( "GET", theUrl, false ); // false for synchronous request
    xmlHttp.send( null );
    return xmlHttp.responseText;
}

// function to get a random image
function getRandomImage()
{
  // get the json from the server
  var json = httpGet('https://dog.ceo/api/breeds/image/random');
  console.log(json);

  // decode the json into an array
  var array = JSON.parse(json);
  console.log(array);
  
  // get the image url from the array
  var url = array.message;
  console.log(url);
  
  // get the image object
  var image = document.getElementById('dogImage');
  
  // set the src of the image object
  image.src = url;
}
```
