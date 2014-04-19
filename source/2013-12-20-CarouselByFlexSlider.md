---
title: Carousel by blex slider
date: 2013-12-20 18:57
tags: javascript, css
---

こんな感じ

css

    <link href="flexslider.css" rel="stylesheet" />

html body

    <div class="flexslider">
     <ul class="slides">
       <li>
         <img src="sample1.jpg" />
         <p class="flex-caption">image 1</p>
       </li>
       <li>
         <img src="sample2.jpg" />
         <p class="flex-caption">image 2</p>
       </li>
       <li>
         <img src="sample3.jpg" />
         <p class="flex-caption">image 3</p>
       </li>
       <li>
         <img src="sample4.jpg" />
         <p class="flex-caption">image 4</p>
       </li>
       <li>
         <img src="sample5.jpg" />
         <p class="flex-caption">image 5</p>
       </li>
     </ul>
    </div>

js

    <script src="jquery.flexslider.js"></script>
    <script type="text/javascript">
    $("document").ready(function(){
      $('.flexslider').flexslider({
        animation: "slide",
        animationLoop: false,
        itemWidth: 100,
        maxItems: 2,
        itemMargin: 0
      });
    });
    </script>

