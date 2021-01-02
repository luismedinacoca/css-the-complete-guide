# css-the-complete-guide
css the complete guide include flexbox grid and sass

SECTION 02 - LECTURE 017:
=========================

More About Selectors:
*********************

1. Elements:

   |HTML:               | CSS            |
   |:------------------:|:--------------:| 
   |<h1>Our header</h1> | h1{            |
   |                    |     color: red;|
   |                    | }              |

2. Classes:

   |HTML:                                 | CSS              |
   |:------------------------------------:|:----------------:| 
   |<h1 class="blog-post">Our header</h1> | .blog-post{      |
   |                                      |     color: red;  |
   |                                      | }                |

3. Universal: rarely use

   |HTML:                 | CSS              |
   |:--------------------:|:----------------:| 
   |<h1>Our header</h1>   | * {              |
   | <p>The blog post</p> |     color: red;  |
   |                      | }                |
   
4. IDs:

   |HTML:                 | CSS              |
   |:--------------------:|:----------------:| 
   |<h1 id="main-title">  | #main-title {    |
   |                      |     color: red;  |
   |                      | }                |
   
5.  Attributes:

   |HTML:                 | CSS              |
   |:--------------------:|:----------------:| 
   |<button disabled>     | [disabled] {     |
   |    click             |     color: red;  |
   |</button>             | }                |




SECTION 02 - LECTURE 018:
=========================

Cascading Style Sheets & Specificity
************************************

1. Cascading => Multiple RULEs can apply to the same element
    
    h1 {
        color: white;
        font-family: 'Anton', sans-serif;
    }

    h1 {
        font-family: sans-serif;
    }

2. Specficity => resolve conflicts arising from multiple rules

    2.1 Inline style
    2.2 #ID selectors
    2.3 .class :pseudo-class and [attributes]
    2.4 <tag> and ::pseudo-elements selectors


SECTION 02 - LECTURE 020: Combinators
=====================================

Combinator: combinator: an ID and a tag or anything else
***********

   #product-overview h1 {
      color: white;
      font-family: 'Anton', sans-serif;
   }


SECTION 02 - LECTURE 021: Theory Times - Combinators
=====================================================

1. Adjancent Siblings:
   - elements share the same parent
   - second element comes immediately after the first element

   CSS:
   h2 + p {
      color:red;
   }

   HTML:
   <div>
      <h2>Not applied</h2>
      <p> ****** CSS applied ****** </p> <!--changes applied here-->
      <h3>Not applied</h3>
      <p>CSS NOT applied</p> <!--changes NOT applied here, they're NOT immediately -->
      <h2>Not applied</h2>
      <p> ****** CSS applied ****** </p> <!--changes applied here-->
   </div>

2. General Siblings:

   - Elements share the same parent
   - Second element comes after first element but not immediately

   CSS:
   h2 ~ p {
      color:red;
   }

   HTML:
   <div>
      <h2>Not applied</h2>
      <p> ****** CSS applied ****** </p> <!--changes applied here-->
      <h3>Not applied</h3>
      <p>CSS NOT applied</p> <!--changes NOT applied here-->
      <h2>Not applied</h2>
      <h3>Not applied</h3>
      <p> ****** CSS applied ****** </p> <!--changes applied here-->
   </div>

3. Child:
   - second element is a direct child of first element

   CSS:
   div > p {
      color: red;
   }

   HTML:
   <div>
      <div>Not Applied</div>
      <p> ******** CSS applied ******** </p>
      <div>Not applied</div>
      <article>
         <p> CSS NOT applied</p>
      </article>
      <p> ******** CSS applied ******** </p>
   </div>

4. Descendant:
   - Second element is a descendant of the first element

   CSS:
   div p{
      color: red;
   }

   HTML:
   <div>
      <div>Not Applied</div>
      <p> ******** CSS applied ******** </p>
      <div>Not applied</div>
      <article>
         <p> ******** CSS applied ******** </p>
      </article>
      <p> ******** CSS applied ******** </p>
   </div>

SECTION 02 - LECTURE 022: Summarizing Properties & Selectors
============================================================

| Selectors      | Properties         | Values    |
|:--------------:|:------------------:|:---------:|
| div            | background-color   | red       |
| .blog-post     | width              | 30%       |
| #main-title    | color              | #fa923f   |
| [disabled]     | margin             | 10px      |
| *              | display            | block     |

look for "MDN CSS reference" on google
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference


SECTION 03 - LECTURE 026: Box Model:
====================================

//by default:
h1 {
    margin: 19.920,
    border: 0,
    padding: 0,
}

 ------------------------------------
|  margin 19.920                     |
|   -------------------------------  |
|   |   border         ---         | |
|   |      ----------------------  | |
|   |     |  padding    ---      | | |
|   |     |      -------------   | | |
|   |     |     |     text    |  | | |

SECTION 03 - LECTURE 027: Understanding the Box Model:
======================================================

By default:
h1 {
    padding: 20px;
    /*border: 5px greenyellow solid;*/ /*many attribute in one line*/
    border-style: solid;
    border-color: black;
    border-width: 5px;
    margin: 20px;
}


 ------------------------------------
|  margin: 20px                      |
|   -------------------------------  |
|   |   border: 5px                | |
|   |      ----------------------  | |
|   |     |  padding: 20px       | | |
|   |     |      -------------   | | |
|   |     |     |     text    |  | | |


SECTION 03 - LECTURE 028: Margin collapsing & Removing default margins:
=======================================================================

 ------------------------------------
|  margin: 20px                      |
|   -------------------------------  |
|   |   border: 5px                | |
|   |      ----------------------  | |
|   |     |  padding: 20px       | | |
|   |     |      -------------   | | |
|   |     |     |   text01    |  | | |
|   |     |      -------------   | | |
|   |      ----------------------  | |
|    ------------------------------  |
|  margin: 20px                      |  <---
 ------------------------------------       |
                                            |
>>>>>>>>  collapsing margin  <<<<<<<<        >  chose the bigger margin 
                                            |
 ------------------------------------       |
|  margin: 19.920                    |  <---
|   -------------------------------  |
|   |   border: 5px                | |
|   |      ----------------------  | |
|   |     |  padding: 20px       | | |
|   |     |      -------------   | | |
|   |     |     |   text02    |  | | |
|   |     |      -------------   | | |
|   |      ----------------------  | |
|    ------------------------------  |
|  margin: 19.920                    |
 ------------------------------------   

 1. between two sibbling elements, the bigger margin "wins"
 2. in general: use either margin-top or margin-bottom

SECTION 03 - LECTURE 029: Deep Dive on "Margin Collapsing"
==========================================================

When working with margins, you can get unexpected results. 

Why are two adjacent elements sharing one margin even though each element has its own one?
Why does a parent element (e.g. <section>  as in the videos) suddenly take on the margin of the child element (e.g. <h1> )?
It's always related to margin collapsing. You can dive deeply into it with the help of the following awesome article: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing

There, three base cases are described:

Adjacent siblings which both have margins
A parent which holds one or more child elements where the first and/ or last (or the only) child has margins
An element without content, padding, border and height
Let's explore these cases:

1. Adjacent Siblings

In this case, the first element might have a margin of 10px  (on all sides let's say) and the second one has 5px  (or 20px  - the values don't matter).

CSS will collapse the margins and only add the bigger one between the elements. So if we got margins of 10px  and 5px , a 10px  margin would be added between the elements?

2. A parent with children that have a margin

To be precise, the first and/ or last or the only child has to have margins (top and/ or bottom). In that case, the parent elements margin will collapse with the child element(s)' margins. Again, the bigger margin wins and will be applied to the parent element.

If the parent element has padding, inline content (other than the child elements) or a border, this behavior should not occur, the child margin will instead be added to the content of the wrapping parent element.

3. An empty element with margins

This case probably doesn't occur that often but if you got an element with no content, no padding, no border and no height, then the top and bottom margin will be merged into one single margin. Again, the bigger one wins.
