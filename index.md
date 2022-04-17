-----------Javascript-------------

var prevScrollpos = window.pageYOffset;

/* Get the header element and it's position */
var headerDiv = document.querySelector("header");
var headerBottom = headerDiv.offsetTop + headerDiv.offsetHeight;

window.onscroll = function() {
  var currentScrollPos = window.pageYOffset;

  /* if we're scrolling up, or we haven't passed the header,
     show the header at the top */
  if (prevScrollpos > currentScrollPos  || currentScrollPos < headerBottom){  
      headerDiv.style.top = "0";
  }
  else{
      /* otherwise we're scrolling down & have passed the header so hide it */
      headerDiv.style.top = "-7.2rem";
  } 

  prevScrollpos = currentScrollPos;
}

-----------CSS-------------

header {
    background: blue;
    height: 7.2rem;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    transition: top 0.2s ease-in-out;
    z-index: 100;
}

.content { 
    height:1000px; 
    margin-top:8rem; /* add space for fixed header */
}

-----------HTML-------------

<header></header>
<div class="content" id="contentdiv">
<h1>My Page</h1>
<p>Content 1</p><p>Content 2</p><p>Content 3</p><p>Content 4</p><p>Content 5</p>
<p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p>
<p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p><p>Content</p>
</div>
