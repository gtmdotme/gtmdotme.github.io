---
layout: archive # or splash
permalink: /photo-gallery/
title: "Photo Gallery"
author_profile: true
redirect_from:
  - /wordpress/blog-posts/
---



<!-- LR export settings: 50% quality, '© Gautam Choudhary', white-lower_right-6-72-3-2 -->
<!-- for gallery code, codepen: 'https://codepen.io/markpraschan/pen/rNNByGG' or refer 1st comment in 'https://css-tricks.com/adaptive-photo-layout-with-flexbox/'-->
	
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/gh/fancyapps/fancybox@3.5.7/dist/jquery.fancybox.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/fancybox/3.5.7/jquery.fancybox.min.js"></script>

<style type="text/css">

  div.gallery ul {
    display: flex;
    flex-wrap: wrap;
    padding: 0;
  }

  div.gallery li {
    height: 30vh;
    flex-grow: 1;
    margin: 1vmin;
    list-style: none;
  }

  div.gallery li:last-child {
    flex-grow: 10;
  }

  div.gallery img {
    max-height: 100%;
    min-width: 100%;
    object-fit: cover;
    vertical-align: bottom;
    border-radius: 0.1vmin;
  }

  @media (max-aspect-ratio: 1/1) {
    li {
      height: 30vh;
    }
  }
  @media (max-height: 480px) {
    li {
      height: 80vh;
    }
  }
  @media (max-aspect-ratio: 1/1) and (max-width: 480px) {
    ul {
      flex-direction: row;
    }

    li {
      height: auto;
      width: auto;
    }

    img {
      width: 100%;
      max-height: 75vh;
      min-width: 0;
    }
  }
</style>

<div id='gallery-div' class="gallery"></div>

<script>
  var gallery = [
    ["./IMG_20201230_080854.jpg", "caption"],
    ["./20201215090038_IMG_0039.jpg", "caption"],
    ["./IMG_20210404_095647.jpg", "caption"],
    ["./IMG_20190907_111327_Bokeh.jpg", "caption"],
    ["./IMG_5425.jpg", "caption"],
    ["./IMG_5419.jpg", "caption"],
    ["./IMG_20201226_120600.jpg", "caption"],
    ["./IMG_5492.jpg", "caption"],
    ["./IMG_20210403_094026.jpg", "caption"],
    ["./IMG_20201130_123421.jpg", "caption"],
    ["./IMG_20180805_184314_Bokeh.jpg", "caption"],
    ["./IMG_20180816_125807_Bokeh.jpg", "caption"],
    ["./IMG_5422-Edit.jpg", "caption"],
    ["./20210101165821_IMG_3591-Edit.jpg", "caption"],
    ["./IMG_20200428_182232.jpg", "caption"],
    ["./IMG_20190929_135820.jpg", "caption"],
    ["./18985.jpg", "caption"],
    ["./IMG_5416.jpg", "caption"],
    ["./IMG_20201226_122901.jpg", "caption"],
    ["./IMG_20210327_171041.jpg", "caption"],
    ["./IMG_5424-Edit-Edit.jpg", "caption"],
  ];
  var str = '<ul>';

  gallery.forEach(function(photograph) {
    str += `
      <li>
        <a href="/images/gallery/${photograph[0]}" data-fancybox data-caption="${photograph[1]}">
          <img src="/images/gallery/${photograph[0]}" alt="${photograph[1]}" loading="lazy">
        </a>
      </li>
    `;
  }); 
  str += '<li></li>';
  str += '</ul>';
  document.getElementById("gallery-div").innerHTML = str;

</script>
