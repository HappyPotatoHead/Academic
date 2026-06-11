---
aliases:
  - September 2022
tags:
  - PYQ
  - CSS
  - JavaScript
  - HTML
Creation Date: 2024-09-19
Finished Date: 2024-09-23
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
```html
<meta>, <input>, <img>, <link>, <source>, <br>, <br>
```
### Question B
```html
<table border = "1">
	<thead>
		<tr>
			<th></th>
			<th>Monday</th>
			<th>Tuesday</th>
			<th>Wednesday</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>9.00am</td>
			<td>Kids Disney</td>
			<td>Money Heist</td>
			<td rowspan = "2">Mat Kilau</td>
		</tr>
		<tr>
			<td>12.00pm</td>
			<td>Romantic comedy</td>
			<td>Minions</td>
		</tr>
	</tbody>
</table>
```
### Question C
1. Tells the browser what kind of document is expected
	1. `<!DOCTYPE html>` tells the browser to expect a html type document, allowing the loading and rendering to be done efficiently since there is no need for the browser to guess what it is
2. Ensures the browser loads the webpage in standard mode
	1. Ensures the latest web standards and specifications are followed when interpreting or displaying the HTML document
### Question D
1. Absolute URL
2. Relative URL
3. Internal
## Question 2
### Question A
1. Inline
	1. The CSS style is placed in the html tags themselves to apply the styles to. This style applies the CSS styling only to html tags that contain them. 
	2. Due to this nature, even if there are multiple similar tags, the styling has to be applied individually.
	3. Placed inside quotation marks in `style` attribute
	4. `<p style ="color:pink;">hello</p>`
2. Embedded/Internal
	1. The CSS styling is not placed in the html tags but rather wrapped inside `style` tag inside the html file.
```html
<style>
p{
	color:pink;
}
</style>
<p>hi</p>
```
3. External
	1. The CSS styling is placed inside a dedicated `.css` file and is linked to the html file with `<link rel = "stylesheet" href = "index.css"/>`
```css
p{
color:pink;
}
```
```html
<link ref = "stylesheet" href = "index.css"/>
```
### Question B
![[wireframe]]
### Question C
```html
<form>
	<h1>Registration Form</h1>
	<ul style="list-style-type:none;">
		<li>
			<label>Name </label>
			<input type = "text" id = "name"/>
		</li>
		<li>
			<label>Id </label>
			<input type = "text" id = "id"/>
		</li>
		<li>
			<label>Address</label>
			<textarea id = "addr" rows = "25" cols  = "25"></textarea>
		</li>
		<li>
			<label>Mobile No.</label>
			<input type = "text" id = "mobile"/>
		</li>
		<li>
			<label>Email</label>
			<input type = "text" id = "mobile"/>
		</li>
		<li>
			<label>Gender</label>
			<input type = "text" id = "gender" list = "gender"/>
			<datalist id = "gender">
				<option value = "m">Male</option>
				<option value = "f">Female</option>
			</datalist>
		</li>
	</ul>
</form>
```
## Question 3
### Question A
```js
document.getElementById("form").addEventListener("submit", e =>{
	e.preventDefault();
	const price = parseFloat(document.getElementById("price").value);
	const discount = parseFloat(document.getElementById("discount").value);
	const total = price - (price * discount);
	document.getElementById("total").value = total.toFixed(2);
});
```
### Question B
**Object literal**
```js
let person = {
	name = "John",
	age = 30,
	eat = function(){
		console.log("eat!");
	}
}
person.eat();
```

**Using function**
```js
function Person(name, age){
	this.name = name;
	this.age = age;
	this.eat = function(){
		console.log("eat!");
	}
}
let person = new Person("John", 30);
person.eat();
```

**Using class**
```js
class Person{
	constructor(name, age){
		this.name = name;
		this.age = age;
	}
	eat(){
		console.log("eat!");
	}
}
```

*Using `new` keyword*
```js
let person = new Object();
person.name = "John";
person.age = 30; 
person.eat = function(){
	console.log("eat!");
};
person["eat"];
```
### Question C
```html
<form id = "form"> 
	<input type = "date" id = "birth">
	<input type = "submit" value = "Calculate Age"/>
</form>
<p id = "age"></p>
<script> 
document.getElementById("form").addEventListener("submit", e=>{
	e.preventDefault();
	let dateOfBirth = new Date(document.getElementById("birth").value);
	document.getElementById("age").textContent = 2024 - dateOfBirth.getFullYear();
});

</script>
```
# Section B
## Question 4
### Question A
HTML is used for structing the content or layout of content on a webpage but CSS is used to style the content. HTML uses tags to mark up content while CSS uses selectors and declarations to apply styling to the elements. HTML are written in HTML files while CSS can be written directly into the HTML file or in its own dedicated file.
### Question B
### Question C
```js
function readCookie(){
	let cookieValue;
	const cookies = document.cookie.split(";");
	for(let index = 0; index < cookies.length; index++){
		const temp = cookies[index].split("=");
		cookieValue+=temp[0];
		cookieValue+="=";
		cookieValue += decodeURIComponent(temp[1]);
	}
	return cookieValue;
}

```
## Question 5
### Question A
#### Question I
Using the `<video>` tag.
#### Question II
`<video>`
- To contain the video
- Have attributes to:
	1. Autoplay
	2. Muted
	3. Loop
	4. Add controls

`<source>`
- To link the video
- Can have multiple video sources

`<track>`
- Add subtitles to the video
- Can make one of the subtitles to be the default
- Can add multiple substitles
### Question B
1. The data stored in local storage persists across multiple browsing session unless manually deleted but the data stored in session storage is deleted once the client logs out of a browsing session.
2. The data in local storage is shared across all tabs but the data is session storage is not shared across all tabs.
	1. This means that if u have multiple tabs of the same website, each website will have access to the same local storage
	2. Data stored in session storage is unique to each tab/browsing session
### Question C
```html
<!DOCTYPE html>
<html lang = "en">
	<head>
		<title>Group member list</title>
		<meta charset = "UTF-8"/>
		<meta name = "viewport" content = "width=device-width, initial-scale = 1.0"/> 
	</head>
	<body>
		<table>
			<thead>
				<tr>
					<th>Group Name</th>
					<th>Group List</th>
					<th>Formed</th>
					<th>City</th>
				</tr>
			</thead>
			<tbody>
			</tbody>
		</table>
	</body>
	<script>
	$(document).ready(function(){
		let aPI = "https://sports/json/hockeygroup.json";
		$.getJSON(data).done(function(data){
			$("tbody").append(
			`<tr>
				<td>${data.groupName}</td>
				<td>${data.groupList}</td>
				<td>${data.formed}</td>
				<td>${data.city}</td>
			</tr>`
			)
		});
	
	});
	</script>
</html>
```


# Next Paper
[[Past Year Papers/Year 2/Semester 1/Front-End Web Development/May 2022|May 2022]]