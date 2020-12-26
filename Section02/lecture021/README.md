More About Selectors:
*********************

1. Elements:

   |HTML:                 | CSS                |
   |:--------------------:|:------------------:| 
   |<h 1>Our header</h 1> | h1{                |
   |                      |     color: red;    |
   |                      | }                  |

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


Combinator: 
***********
/* combinator: an ID and a tag or anything else*/
   #product-overview h1 {
      color: white;
      font-family: 'Anton', sans-serif;
   }


Theory Times - Combinators
**************************

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