# A Simple Academic Personal Website Template
This project provides a simple template for researchers to showcase their publications.

The main functionality provided by this template is automatic grouping and displaying publications based on different criteria. It frees researchers from tedious web page updating.


## Add publications

index.html is the main file in this template. Ideally, you only need to change index.html and simplest.css to make your web page work. index.html links to JQuery, toggle.js, and mergeSort.js.

Add your publications as items in `<div id="publicationdatabase">`. `<div id="publicationdatabase">` serves as the publication database, and it is set as `style="display: none;"`. Here is an example:
```html
<div id="publicationdatabase" style="display: none;">
	<ul>
            <li class="publication" data-time="20150901" data-venue="ICGP" data-topic="Soccer Games" data-type="Conference Papers">
               <span class="paper_title">Pro Evolution Soccer in a Nutshell</span>&nbsp;&nbsp;<a href="./.pdf">[PDF]</a>&nbsp;<a href="./.bib">[Bib]</a>
               <br />		
               <span class="self">Your Name</span>, Co-author-1, Co-author-2<br />
               International Conference on Game Playing (ICGP), 2015
               <br />
			   <br />
            </li>
	</ul>
</div>
```

Your publication `<li>` should have the following attributes: 1) `class="publication"`, toggle.js uses this to find your publications; 2) `data-time="20150901"`, the publication date in the format of YYYYMMDD; 3) `data-venue="ICGP"`, the venue of a publication; 4) `data-topic="Soccer Games"`, the topic of a publication; 5) `data-type="Conference Papers"`, the type of this publication.

## Add new attribute to `<li>`

Feel free to add new attributes to `<li>` as long as you add correspoding links to trigger to sortment based on those attributes. A link looks like this:
```html
<a class="toggle_link" href="javascript:toggle('data-mycriterion', true, true)">Sort by mycriterion</a>
```


## Function `toggle()`

`toggle` is the entry point of toggle.js. It takes three parameters: 1) `type`, the attribute you want to sort on; 2) `ordered_list`, a boolean value to decide whether to display ordered list for your publications. The default parameter is `true`; 3) `generate_anchors`, a boolean value to decide whether to display links to anchors for different publication categories. The default parameter is `true`.

```javacript
function toggle(type, ordered_list, generate_anchors)
```

## Change the default way to sort

You can change the default way to sort your publications by changing the parameters of

```javascript
$(document).ready(toggle('data-time'));	
```

## Contact

Contact me at ziming.zhao at gmail.com