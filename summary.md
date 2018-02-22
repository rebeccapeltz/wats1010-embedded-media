## HTML Tags

**Block vs Inline**

 - Block elements render vertically and inline elements render
   horizontally.
 - Block elements occupy the entire space of the parent element.
 - The concept of layout takes advantage of the fact that block elements
   occupy the whole are of the parent.
 - Block elements can have height properties assigned to them.
 - Block elements can contain other block elements or inline elements
   (called nesting of elements).
 - You can't put block elements inside of inline elements.

This is a no-no:

          <span><div> hello </div></span>
        

 - You can switch between block and inline using CSS (display: block,
   display:block-inline, display:inline)

## Block

Examples of block level elements: [MDN Block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
**Inline**
Examples of inline elements: [MDN Inline-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
**Box Model**

 - Use border, height, width, padding and margins to construct "boxes"
   to contain content with block element.
 - Inline elements can have border, margin and padding but width and
   height properties are not supported in all browsers for inline
   elements.
 - Margin: defines space between border and other outer elements.

In the image below the total height is: 169px and the total width is: 646px. You add (height or width) + margin + padding + border to get the dimensions of the box.

![Box Model from Chrome Dev Tools](http://www.beckypeltz.online/wats1010-embedded-media/img/box-model.jpg)

## CSS classes, id and element selectors

**Tag or Element**
for example div, span, footer, section
**id**
add the id attribute with an id value to an element and then select using #, for example #right-nav
**class**
add the class attribute with a name value to an element and then select using . for example .right-nav

## Navigation: internal and external

**Internal**
add an id attribute to a section of the page and then in then set up the anchor tag like this

          <a href="#about">About</a>
        
**External within web site**
set up a tag like this for a static page in a file named about.html located under the component's folder

        <a href="components/about.html">About</a>
      
**External outside of web site**
set up a tag like this for google

        <a href="https://www.google.com">Google</a>
      
**Open page in new tab**
add target="_blank" to any of the above anchors, for example

        <a href="https://www.google.com" target="_blank">Google</a>
      
**Stay where you are - used with JavaScript to add your own click event**
set up a tag like this to stay on the same page in the same location

        <a href="">Click me</a>
      

## File access: absolute, relative, relative to root

**Absolute**
for "https://www.google.com"
**Relative**
for example "img/red_ball.png"
**Relative to Root**
for example "/index.html"
**Tables**
Use these tags (table, th, tr, td) to construct a table for tabular data. Nesting of these tags is prescribed by standards.

      <table>
        <tr>
          <th></th>
          <th></th>
        </tr>
        <tr>
          <td></td>
          <td></td>
        </tr>
      </table>
    

## Background styles

**color**

        background-color: red;
      
**image**

        background-image: url("img.png")
      
**repeat**

        background-repeat: no-repeat;
      
**position**
Starting position of the element (horizontal and vertical). If you only use on3 value the second is 'center' by default

        background-position: center center;
      
**attachment**
If "fixed", the background won't scroll with rest of page. Used for parallax scrolling.

        background-attachment: fixed;
      
**size**

        background-size: cover;
      

## Horizontal Layout: inline-block, float, flex, grid

see this: [https://www.w3schools.com/css/css_navbar.asp](https://www.w3schools.com/css/css_navbar.asp) It's common to use an unordered list for navigation. Whether horizontal or verical, remove the default bullet points with this. The UL tag is the parent container for the LI list items. Let's say we have this html:

      <ul class="navigation">
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#portfolio">Portfolio</a>/li>
      </ul>

Remove underscores from links and bullet points from list items.    

    .navigation a { 
      text-decoration: none; 
    } 
    
     ul.navigation {
      list-style-type: none; 
     }
    
**Inline-Block**

      li { 
	   display: inline; 
	  }
      
**Float**

      li { 
	    float: left; 
	  } 
      a { 
	    display: block; 
        padding: 10px; 
        color: black; 
        background-color: lightblue; 
      }
      
**Flex**

       ul.navigation { 
         width: 300px; 
         height: 30px; 
         display: flex; 
         justify-content: space-around; 
         list-style-type: none; 
       } 
       .navigation a { 
         text-decoration: none; 
       }
        
**Grid**


          ul.navigation { 
            display:grid; 
            grid-template-columns: 
            repeat(3, 70px); 
          } 
          .navigation a { 
	        text-decoration: none; 
          } 
          .navigation li { 
            list-style-type: none; 
          }
        

## Images

**JPG or JPEG**
This is a lossy format. Lossy compression is characterized by sampling from the raw data and throwing out some of the data, so that you really have an approximation. If you don't use tools to resize you can get a image that looks different at a larger size than intended. This is not the skewed image that you get when you violate aspect ratios (for example, making a 100px x 200px image into a 70px x 150px image). Look for this with digital photos and these can get quite big. **Think photos**.
**GIF**
Gifs are lossless. Their compression algorithm does not involve the sampling you see with JPG. They tend to be smaller because they use an indexed color pallette which is a subset of all colors and therefore some approximation occurs in coloring. You see the gif format used a lot in animation. **Think animation.**
**PNG**
Png files contain raster graphics with lossless data compression and is the formal replacement for gifs, but pngs are not used for animation. Pngs are "indexed" meaning they used a fixed color pallette. Indexed color means that you have a predefined set of color that you map the original colors too. You can read more here on indexed color: [Png](https://en.wikipedia.org/wiki/Indexed_color) **Think drawings.**

## Video/Audio

**Audio**
add controls and a statement incase the browser doesn't suppor the audio tag

       <audio controls>
         <source src="horse.ogg" type="audio/ogg">
         <source src="horse.mp3" type="audio/mpeg">
         Your browser does not support the audio element.
       </audio>
        
**Video**
Best to add several audio formats as different browsers support different formats. The "controls" attribute provides user with ability to control. Height and width can be added in style sheet

       <video width="320" height="240" controls>
         <source src="movie.mp4" type="video/mp4">
         <source src="movie.ogg" type="video/ogg">
       Your browser does not support the video tag.
       </video>
      
**Video with poster**
If your video is big and takes time to download this will give the user something to look at. See this in action here: Video with [poster example.](https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_video_poster)

      <video width="320" height="240" poster="/images/poster.gif" controls>
       <source src="movie.mp4" type="video/mp4">
       <source src="movie.ogg" type="video/ogg">
       Your browser does not support the video tag.
    </video>
        
**Downloadable Audio/Video**
Add the work download to the video or audio tag.

     <video width="320" height="240" controls download>
       <source src="movie.mp4" type="video/mp4">
       <source src="movie.ogg" type="video/ogg">
     Your browser does not support the video tag.
     </video>
            

## Mobile First: Responsive layout and media queries

"Mobile First" means we code the layout that we want for the mobile device, which usually tends to be vertical ranther than employing horizontal layouts. Then we add media queries for the different break points.
**CSS Media query**
To get 3 sizes add 2 media queries that alter the layout of the vertical mobile layout. With the queries below we'll see a different layout for screen sizes smaller than 400px, between 400-800px and greater than 800px. This roughly corresponds to phone, tablet and laptop(or desktop). See this [for example](https://www.w3schools.com/cssref/tryit.asp?filename=trycss3_media2)

      @media screen and (min-width: 400px) {
   	    body { 
   	      background-color: lightgreen; 
   	    } 
       }
       @media screen and (min-width: 800px) { 
   	    body { 
   	      background-color: lavender; 
   	    }
      }
    
**Common breakpoints**
320px, 480px, 768px, 1024px are common breakpoints for small mobile, larger mobile, tablet, laptop
**Bootstrap grid system**
The grid system uses CSS Flex to layout containers horizontally and it wraps when the count for a given media breakpoint totals 12. Bootstrap uses classes to define a container which holds rows containing the items it lays out. The sample below will have 6 columns for devices above 768px(md breakpoint), then 3 columns, and then 2 columns as the width of the container decreases.

      <div class="container">
        <div class="row">
          <div class="col-xs-6 col-sm-4 col-md-2">
            <h3>Column 1</h3>
            <div>Lorem ipsum dolor..</div>
            <div>Ut enim ad..</div>
          </div>
          <div class="col-xs-6 col-sm-4 col-md-2">
            <h3>Column 2</h3>
            <div>Lorem ipsum dolor..</div>
            <div>Ut enim ad..</div>
          </div>
          <div class="col-xs-6 col-sm-4 col-md-2">
            <h3>Column 3</h3>
            <div>Lorem ipsum dolor..</div>
            <div>Ut enim ad..</div>
          </div>
          <div class="col-xs-6 col-sm-4 col-md-2">
            <h3>Column 4</h3>
            <div>Lorem ipsum dolor..</div>
            <div>Ut enim ad..</div>
          </div>
          <div class="col-xs-6 col-sm-4 col-md-2">
            <h3>Column 5</h3>
            <div>Lorem ipsum dolor..</div>
            <div>Ut enim ad..</div>
          </div>
          <div class="col-xs-6 col-sm-4 col-md-2">
            <h3>Column 6</h3>
            <div>Lorem ipsum dolor..</div>
            <div>Ut enim ad..</div>
          </div>
        </div>
      </div>
    
