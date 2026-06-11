---
aliases:
  - September 2023
tags:
  - PYQ
  - HTML
  - CSS
  - JavaScript
Creation Date: 2024-09-19
Finished Date: 2024-09-19
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
```html
<img>, <meta>, <input>, <source>, <link>, <br>, <hr>
```
### Question B
1. **Add subtitles to the videos**. 
	1. This can help those who have hearing problems as they can see what is being spoken in the videos. 
	2. The caption may also include description of the audio or background noises in the video to increase understanding.
2. **Add audio descriptions**. 
	1. The audio description can provide accurate descriptions to what is happening in the movie such as describing the facial expressions on the characters during a conversation, describing the scenery or the setting of the place in the movie, or describing any actions taken by the characters in the movie.
	2. This is played alongside the movie to allow the users to follow along the movie, even if they have vision problems 
### Question C
```html
<h1>Feedback Form</h1>
<p>Thank you for using our services</p>
<form>
	<ul style="list-style-type:none;">
		<li>
			<label>NameL</label>
			<input type = "text" id = "name"/>
		</li>
		<li>
			<label>Age:</label>
			<input type = "text" id = "age"/>
		</li>
		<li>
			<label>Comments:</label> <br>
			<textarea id = "comments" rows = "25" cols = "50"></textarea>
		</li>
		<li>
			<input type = "submit" value = "Submit"/>
			<input type = "reset" value = "Clear"/>
		</li>
	</ul>
</form>
```

```html
<h1>Feedback Form</h1>
<p> Thank you for using our services</p>
<form>
	<label>Name: </label>
	<input type = "text" id = "name"/>
	<label>Age: </label>
	<input type ="text" id = "age"/>
	<label>Comments: </label> <br>
	<textarea 
		id = "comments" 
		rows = "10" 
		cols = "20">
	Enter comments here.
	</textarea><br>
	<input type = "submit" value = "Submit"/>
	<input type = "reset" value = "Clear"/>	
</form>
```

```html
<!DOCTYPE html>
<html lang = "en">
	<head>
		<title>Form</title>
		<meta charset = "UTF-8"/>
		<meta name = "viewport" content ="width=device-width, initial-scale = 1.0"/>
	</head>
	<body>
		<h1>Feedback Form</h1>
		<p>Thank you for using our services</p>
		<form id = "form">
			<p>
				<label>Name: </label>
				<input name = "name" id = "name" type = "text"/>
			</p>
			<p>
				<label>Age: </label>
				<input name = "age" id = "age" type = "text"/>
			</p>
			<p>
				<label>Comments: </label><br>
				<textarea id = "comments" rows = "5" cols = "30">
				</textarea> 
			</p>
			<p>
				<input type = "submit" value = "Submit"/>
				<input type = "reset" value = "Clear"/>
			</p>
		</form>
	</body>
</html>
```
### Question D
`colspan` is used to combine 2 or more horizontally adjacent cells while `rowspan` is used to combine 2 or more vertically adjacent cells. Applied at `<th>` and `<td>`.

With `rolspan`,

|       |         |
| ----- | ------- |
| Breed |         |
| ^     | hgfhgfh |

With `colspan`,

| Names | <   | <   | <   |
| ----- | --- | --- | --- |
|       |     |     |     |
## Question 2
### Question A
A domain name is the text representation of the unique IP address of a computer that is typed in to a web browser. It is used to identify a website on the Internet. Users can use the domain name instead of having to remember the IP address. 
### Question B
1. Security risks or vulnerability
	1. If one website is compromised, it may act as a backdoor and inadvertently compromise other websites hosted on the server. 
2. Limited ability to handle high traffic or spikes in traffic
	1. Since the resources are shared, if one website suddenly gains more activity compared to other sites, other websites hosted on the same server will have their performance affected.
3. The performance of a site can be affected by other sites hosted on the same server
	1. If one website is using more resources, the other websites will be affected. 
### Question C
#### Question I
A selector are patterns to selectively choose the elements in the `HTML` that you wish to apply the CSS styling to. It is possible to combine different selectors together to create more specific selectors, or nest selectors together. An example of a basic CSS selector is, 
```css
p{} 
```
This selects every p element in the file. 
### Question II
1. tag selector
	1. `p{}`
2. class selector
	1. `.my-class{}`
3. id selector
	1. `#unique-id`
4. attribute selector
	1. `a[href]`
#### Question III
A declaration is a property value pair that defines the style to apply to the elements that are selected. The property defines the type of styling to apply while the value defines the changes to apply.
#### Question IV
```css
p{
	color: white; 
	background-color: black;
	padding: 10px;
}
```
### Question D
```css
p:hover
li:nth-child(odd)
li:nth-child(even)
li:first-of-type
a:link
```
## Question 3
### Question A
#### Question I
It is a scripting language that is used to enhance the appearances and functionalities of webpages. JavaScript makes the website more dynamic by dynamically generating content. JavaScript can be used to add event handlers in response to user interactions
#### Question II
jQuery and Anime.js
### Question B
```js
const name = prompt("Please enter your name");
document.write(name);
```
### Question C
```js
const number = parseInt(prompt("Please enter a number"));
const message = (isEven(number)) ? "The number is even" : "The number is odd";
alert(message);
```
### Question D
1. Can ask for user input
	1. Displays a dialog box with a specified message and an input field for the user to enter their value
2. Can provide visible default value to the user
	1. Can pass an optional default value to the `prompt()` method and the value will be returned if the user does not change the value
3. Handles user cancellation
	1. If the user presses cancel, `null` will be returned. This can be used to check if the user inserted a value or just pressed cancelled.
# Section B
## Question 4
### Question A
1. JavaScript is a programming language and JSON is a plain-text tool used to store data.
3. JavaScript can be used to add interactivity and improve websites' appearances but JSON cannot be used to add interactivity and improve websites' appearances.
4. JavaScript can support complex data structures such as objects, arrays, functions, and more but JSON is only limited to key-value pair to store data.
### Question B
1. Insufficient storage.
	1. Cookies have very limited storage which is around 4kB of data. 
	2. So it is not suitable for websites that require extensive storage or complex database
2. The user can choose to delete the cookie if they want or choose to not accept cookies.
	1. This means that some website features is not able to be shown off to everyone
3. Complex data is not allowed
	1. The data is only stored in plain text
4. Cookies can slow down the website since it is included in every HTTP request. 
### Question C
```js
for(let i = 0; i <= 60; i+=15)
	document.writeln(`${(5.5 * i).toFixed(2)}<br>`);
```
### Question D
jQuery is a JavaScript library that is meant to simplify the client-side scripting of HTML. Essentially, the programmer gets to write lesser lines to achieve the same results as using plain JavaScript. 
## Question 5
### Question A
1. Write lesser to do more
	1. Instead of `document.getElementById("id")`, jQuery simplifies it to `$("#id")`
2. Lightweight
	1. You can import the CDN to use jQuery
3. Easy to understand and learn
	1. Familiar syntax
	2. Since it is a JavaScript library, a lot of syntax in jQuery is the same as the syntax in JavaScript itself.
### Question B
1. expires
	1. Establish the expiration date of the cookie. If not set, the cookie is deleted after the user quits the browsing session.
2. domain
	1. Contains the domain of the website
3. path
	1. Path to the webpage or directory that set the cookie. 
	2. Leaving this blank will leave the cookie to accept data from any directory or webpage
4. secure
	1. Only allows cookies to be retrieved from secure servers
	2. If the field is blank, such restriction does not exist.
5. samesite
	1. Prevent the cookies from sending along cross-site requests
		1. Lax
			1. Cookies are only sent to target sites in the context of same-site requests or top-level navigation GET requests. 
			2. This is sufficient for user tracking and prevents Cross Site Forgery Attacks
			3. This is the default for any modern browser
		2. None
			1. No restriction is put in place
				1. Cookies can be sent to target sites in both same-site and cross-site contexts.
		3. Strict
			1. No cookies are sent to target site in the all of cross-site contexts.
### Question C
```js
let arrayOfNumber = [];
for(let i =0; i < 3; i++)
	arrayOfNumber[i] = parseFloat(prompt("Number"));
let total = 0;
arrayOfNumber.forEach( number =>{
	total+=number;
});
document.writeln(`The average is ${total/3}`);
```
# Next Paper
[[Past Year Papers/Year 2/Semester 1/Front-End Web Development/May 2023|May 2023]]
