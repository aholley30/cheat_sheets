# <p align="center">Front End Libraries Cheat Sheet</p>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous"/>
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">

### Bootstrap
- Bootstrap allows for fluid resizing so your website will look nicely on a phone screen or desktop.
  - Add this to the top of your html: ```<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous"/>```
  - Encase all the things you want to be responsive in a div with ```class="container-fluid"```
- To make an image fit the width of a phone's screen, make its class <strong>img-responsive</strong>
- To center a text element (lik h2) add the class name "text-center".
- Bootstrap has a grid that allows you to place elements side by side. 
  - The format is ```col-md-*``` md means medium and * stands for the amount of columns to use.
  - To put all buttons on one line, put them in a div element with the ```class="row"```, then, for example, put each individual one in their own div element with ```class="col-xs-4"```.  
- By using the inline ```span``` element, you can put several elements on the same line, and even style different parts of the same line differently.
  ~~~html
  <p>Top 3 things cats <span class="text-danger">hate:</span></p>
  ~~~
- Create a sense of depth to an element by adding ```well``` elements within a div.
  ~~~html
  <div class="well"></div>
  ~~~
- **ID Attributes** must be unique to a specific element and used only once per page
#### Bootstrap: Buttons
- For a bootstrap styled button add the classes "btn" and "btn-default" to the button element.
  ~~~html
  <p align="center"><button class="btn btn-default">Bootstrap Button</button></p>
  ~~~

- Making the button a block element will stretch it to fill the page's entire horizontal space so that any elements after will go to a new line.
  - Do this by also adding in the class "btn-block" with the previously mentioned classes.
  ~~~html
  <p align="center"><button class="btn btn-default btn-block">Bootstrap Button</button></p>
  ~~~
- Button styles to use instead of "button-default":
  - "btn-primary": makes it a primary (light blue) color.
  - "btn-info": is a lighter color used to call attention to optional actions a user can take.
  - "btn-danger": notifies users that the button performs a destructive action.
#### Font Awesome
- A convenient library of icons (webfonts or vector graphics) that are treated like fonts.
  - You can specify their size using pixels, and they will assume the font size of their parent HTML elements.
- Include font awesome by adding this to the top of your html: ```<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">```
- You can add the Font Awesome classes to the i or span element to turn it into an icon, for example:
  ~~~javascript
  <i class="fas fa-info-circle"></i>
  <span class="fas fa-thumbs-up"></span>
  <i class="fas fa-trash"></i>
  ~~~
  


