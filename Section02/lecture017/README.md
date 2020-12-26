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
   |<h1 class="blog-post">Our header</h1> | blog-post{       |
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