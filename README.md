<br>

# Responsive Portfolio





### This is a responsive portfolio for cats. 
### ~~But, you're not a cat, so get the fuck out.~~


---
<br>

## Headers

The header is reformats as you resize the window.  At the largest viewport, the name and the site's pages align, left and right, opposite sides of the header.  At 768px, the right-aligned page links in the main nav are hidden and a second nav shows below with the page links centered.
```
@media only screen and (max-width: 768px) { 
   #subMenu {
      display: block;
      visibility: visible;
   }

   .mainMenu {
      visibility: hidden;
   }
} 
```

<br>

## Footers

The footer was a bit more problematic.  I had trouble overriding the CSS that left-aligns the copyright label and alters its color.  I was able to center it with two artifacts above and below, but subsequently took those out as it seems like a weak solution.  

<br>

## Cards

Cards have a top and bottom margin on every page to make sure there's no overlap with the header or footer.  On smaller monitors (like my Macbook), the Portfolio page is broken and does not display the bottom margin.  I plan to look into further media queries to see how to work with height breakpoints.

<br>

## Images

The cat on the About page was a straightforward bit of float and margin CSS to get the text to wrap.  At 768px, I added a callout for 100% width and an auto height to prevent the image from warping as it scales.
```
.blanketCat {
   float: left;
   margin-right: 15px;
   margin-bottom: 15px; 
}

@media only screen and (max-width: 768px) { 
   .blanketCat {
      width: 100%;
      height: auto;
   }
} 
```
Portfolio images were a decent bit tougher, especially with the addition of labels.  At max screen width, I managed to use relative and absolute positioning to a degree of success.  As soon as the first breakpoint hits though, the labels begin to break, getting progressively worse until the smallest width.  After talking to Emily, I'll have to figure out how to implement z-index for a better solution.
```
.thumbnail {
    position: relative;
}

.caption {
    position: absolute;
    height: 60px;
    width: 70%;
    bottom: 16%;
    background-color: black;
    opacity: .75;
    padding-left: 5%;
    padding-right: 5%;
    text-align: center;
    padding-top: 15px;
    font-size: 18px;
}
```

<br>

---