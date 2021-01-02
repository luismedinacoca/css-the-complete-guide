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



