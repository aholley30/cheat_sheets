# <p align="center">Front End Libraries Cheat Sheet</p>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous"/>

### Bootstrap
- Bootstrap allows for fluid resizing so your website will look nicely on a phone screen or desktop.
  - Add this to the top of your html: ```<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous"/>```
  - Encase all the things you want to be responsive in a div with ```class="container-fluid"```
- To make an image fit the width of a phone's screen, make its class <strong>img-responsive</strong>
- To center something add the class name "text-center".
##### Buttons
- For a bootstrap styled button add the classes "btn" and "btn-default" to the button element.
  <p align="center"><button class="btn btn-primary">Bootstrap Button</button></p>
  <p>&nbsp</p>

- Making the button a block element will stretch it to fill the page's entire horizontal space so that any elements after will go to a new line.
  - Do this by also adding in the class "btn-block" with the previously mentioned classes.
  <p>&nbsp</p>
  <p align="center"><button class="btn btn-primary btn-block">Bootstrap Button</button></p>
  <p>&nbsp</p>
- Button styles to use instead of "button-default":
  - "btn-primary": makes it a primary color.
  - "btn-info": is a lighter color used to call attention to optional actions a user can take.
  - "btn-danger": notifies users that the button performs a destructive action.

