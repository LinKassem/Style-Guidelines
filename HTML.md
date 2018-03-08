# HTML Style Guidelines

## Syntax and Semantics

1. Write valid HTML code that follows the [standards](https://www.w3.org/TR/2012/WD-html-markup-20120320/syntax.html) (Syntactically correct HTML). 
   1. Use HTML5 syntax, and make sure to place the ``<!DOCTYPE html>`` at the top of your html documents.

   2. Use the [UTF-8](https://www.w3.org/International/tutorials/tutorial-char-enc/) character encoding by placing ``<meta charset="utf-8">``  tag in the head of the HTML documents.

   3. Avoid the [common causes](https://validator.w3.org/docs/errors.html) of having invalid HTML.


   ​

2. Use HTML according to its purpose ([Semantically correct HTML](https://www.w3schools.com/html/html5_semantic_elements.asp))<sup>[1](https://internetingishard.com/html-and-css/semantic-html/#_=_)<sup>.

   Use elements for what they have been created for. For example, use heading elements  ```h1 to h6```  for headings, `p` elements for paragraphs, `a`elements for anchors, `nav` for navigation, `form` for form elements, etc.

   Using HTML according to its purpose is very important for accessibility, reuse, and code efficiency reasons.

   ```html
   <!-- Not recommended -->
   <div onclick="goToHome();">Home</div>

   <!-- Recommended -->
   <a href="home">Home</a>
   ```

   ​

3. Separate structure from presentation from behavior.

   As much as possible, keep structure (markup), presentation (styling), and behavior (scripting) apart. 

   ​

4. Do not omit optional tags.

   ```html
   <!-- Valid in HTML5 specifications but not recommended for consistency reasons -->
   <ul>
       <li>foo
       <li>bar
   </ul>

   <!-- Recommended -->
   <ul>
       <li>foo</li>
       <li>bar</li>
   </ul>
   ```

   ​

5. Do not explicitly close [void elements](https://www.w3.org/TR/html5/syntax.html#void-elements).

   ```html
   <!-- Valid in HTML5 specifications but not recommended for consistency reasons -->
   <meta charset="UTF-8" />
   <img src="sunset.png" alt="sunset view" />
   <hr />

   <!-- Recommended -->
   <meta charset="UTF-8">
   <img src="sunset.png" alt="sunset view">
   <hr>
   ```

   ​

6. Always use the HTTPS protocol (`https:`) for images and other media files, style sheets, and scripts, unless the respective files are not available over HTTPS.

   ```html
   <!-- Not recommended: omits the protocol -->
   <script src="//ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>

   <!-- Not recommended: uses http protocol -->
   <script src="http://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
   ```

   ```html
   <!-- Recommended -->
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
   ```

   ​

7. Use only lowercase for HTML element names, attributes, attributes values.

   Do not leave space between the attributes and attributes values.

   ![HTML element description](https://github.com/LinKassem/Style-Guidelines/blob/master/images/HTML-element.png)

   ```html
   <!-- Not recommended -->
   <A HREF="#">Home</A>

   <!-- Recommended -->
   <a href="#">Home</a>
   ```

   ​

8. Comment your code as needed where possible:

   1. Comment the start and end of code blocks that resemble a single component.

      ```html
      <!-- Navigation -->
      <nav class="nav">
      	<ul class="nav__options">
      		<li><a href="#">Home</a></li>
      		<li><a href="#">News</a></li>
      	</ul>
      </nav>
      <!-- /Navigation -->
      ```

   2. Comment according to the file type.
      

      ```html
      Razor files .cshtml
      @* Comment *@

      HTML files .html
      <!-- Comment -->
      ```
      Note: In Razor views, you can use both ways to write your comment. However, the razor comments will not be parsed and thus not visible when debugging in the browser.
   ​

9. Provide alternative contents for multimedia.

   For images that means use of meaningful alternative text `alt` and for video and audio transcripts and captions, if available.

   Providing alternative contents is important for accessibility reasons.

   For images whose `alt` attributes would introduce redundancy, and for images whose purpose is purely decorative which you cannot immediately use CSS for, use no alternative text, as in `alt=""`.

   ```html
   <!-- Not recommended -->
   <img src="spreadsheet.png">

   <!-- Recommended -->
   <img src="spreadsheet.png" alt="Spreadsheet screenshot.">
   ```

   ​

10. Do not use entity references.

    There is no need to use entity references like `&mdash;`, `&rdquo;`, or `&#x263a;`. This is due to assuming that the same encoding (UTF-8) is used for all html files and editors as well as among teams.

    The only exceptions apply to characters with special meaning in HTML (like `<` and `&`) as well as control or “invisible” characters (like no-break spaces).

    ```html
    <!-- Not recommended -->
    The currency symbol for the Euro is &ldquo;&eur;&rdquo;.

    <!-- Recommended -->
    The currency symbol for the Euro is “€”.
    ```

    ​

11. Omit `type` attribute when referencing JavaScript or CSS files

    ```html
    <!-- Not recommended -->
    <link rel="stylesheet" href="layout.css" type="text/css">

    <!-- Recommended -->
    <link rel="stylesheet" href="layout.css">
    ```

    ```html
    <!-- Not recommended -->
    <script src="index.js" type="text/javascript"></script>

    <!-- Recommended -->
    <script src="index.js"></script>
    ```
    
    

## Formatting rules :hammer_and_wrench:

1. Use 4 spaces for indentations. 

2. Remove trailing white spaces.

3. Add blank lines to separate large or logical code blocks. However, make sure not to add blank lines without a reason.  

3. Quotation marks

   Use double (`" "`) rather than single quotation marks (`' '`) around attribute values.

   ```html
   <!-- Not recommended -->
   <a class='home-link'>Home</a>

   <!-- Recommended -->
   <a class="home-link">Home</a>
   ```

4. HTML Line wrapping

   Break long lines. There is no column limit recommendation for HTML, however you can consider wrapping long lines if it significantly improves readability.

   Each continuation line should be indented by 4 additional spaces from the original line.

   ```html
   <!-- Not recommended -->
   <md-progress-circular md-mode="indeterminate" class="md-accent" ng-show="ctrl.loading" md-diameter="35">
   </md-progress-circular>

   <!-- Recommended -->
   <md-progress-circular md-mode="indeterminate" class="md-accent"
       ng-show="ctrl.loading" md-diameter="35">
   </md-progress-circular>
   ```

5. Use a new line for every [block](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements), list, or table element and indent child elements. This is done regardless of the styling or presentation of the elements.

   ```html
   <blockquote>
     <p>
         What is Lorem Ipsum?
     </p>
   </blockquote>

   <ul>
     <li>Moe</li>
     <li>Larry</li>
     <li>Curly</li>
   </ul>
   ```

7. Leave space before and after the comment text.

   ```html
   Bad
   <!--Not recommended-->

   Good
   <!-- Not recommended -->
   ```




---

[1] https://internetingishard.com/html-and-css/semantic-html/#_=_

:hammer_and_wrench: : Utilize your coding environment to help you.




**References**

https://google.github.io/styleguide/htmlcssguide.html

https://github.com/springernature/frontend-playbook/blob/master/markup/house-style.md

https://www.w3schools.com/html/html5_syntax.asp

