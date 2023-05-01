# <p align="center">HTML Cheat Sheet</p>

### General
- For comments, the format is: ```<!-- Place comment here -->```
- Instead of adding padding, set overflow to hidden - in what cases
- Add emphasis to a range of text with the ```<em></em>``` tags - italics
- Italicize a range of text with ```<i></i>```
- Indicate that a range of text has importance with the ```<strong>``` open and closing tags - aka bold text
- Bolden a range of text with the ```<b>``` open and closing tags
- **Responsive design** is the combination of 3 techniques
  1. Flexible grids - made up of columns, gutters (space b/w between columns), and l/r margin
  2. Fluid images - set max-width to 100%
  3. Media queries - allows devs to query the display size, aspect ratio, and orientation to conditionally apply css rules

### Head
- Start with a ```<DOCTYPE html>``` and a ```<html lang="en">```
- Set the meta element: ```<meta charset="UTF-8"/>```, can add multiple
- If using a stylesheet, add: ```<link rel="stylesheet" href="styles.css" />``` or use ```<style></style>```
- Use a title element to add a tab title

### Body
- Can nest an h1 element inside of a header element to set a doc header.
- ```<fieldset>``` is great for grouping elements
- ```<div>``` is also great for grouping elements, everything after will be placed on a new line
- ```<br>``` is a self closing tag that signifies a line break
- Lists can be unordered ```<ul>``` which'll add a dot to there side or ordered ```<ol>``` which'll number the list:
  ~~~html
  <ul>
   <li>Tea</li>
   <li>Sugar</li>
   <li>Milk</li>
  </ul>

  <ol>
   <li>Rocky</li>
   <li>Rocky II</li>
   <li>Rocky III</li>
  </ol>
  ~~~
- add links with the anchor tag:
  ~~~html
  <a href="other_page.html">Other page</a>
  ~~~
- add images with the self closing **img** tag
  ~~~html
  <img src="image.png" width="240" height="140" alt="an image">
  <!-- Alt text isn't displayed on the screen, but will be read by assistive technologies like screen readers-->
  ~~~
- Tables are a great way to organize data
  ~~~html
  <table>
    <tr> <!--Table row-->
      <th>header 1</th>
      <th>header 2</th>
    </tr>
    <tr> 
      <td>under header 1</td> <!--Table data, one per column-->
      <td>under header 2</td>
    </tr>
  </table>
  ~~~
- Forms are useful for data that needs to be submitted
  ~~~html
  <!--method can be POST or GET-->
  <form action="/registration" method="POST">
    <label for="username">Username:</label><br>
    <input type="text" name="username"/>

    <label for="password">Password:</label><br>
    <input type="password"/>

    <input type="submit"/> <!--performs form method when pressed-->
  </form>
  ~~~
  ##### Inputs
  - Add label elements to each input, give the **for** attribute the same value as the input's id to link them together.
  - Other input types include email, radio, and checkbox
  - Some input types don't use the input tag like textareas and dropdown lists
    ~~~html
    <textarea name="multiline" rows="5"></textarea>

    <select name="food">
      <option value="choco">Chocolate</option>
      <option value="pb">Peanut Butter</option>
    </select>
    ~~~
  - Add ```required``` to an input's attributes to make it required
  - Set the ```placeholder``` attribute to add placeholder text
  - Text: ```<label for="last-name"><input id="last-name" name="last-name" type="text" required />Last Name</label>```
    - Special types include email and password.
    - Can use an additional attribute called ```pattern``` to set a limit using regex: 
      - ```pattern="[a-z0-5]{8,}"``` this makes sure inputs are lowercase, more than 8 characters, and only include the numbers 0-5.
  - 