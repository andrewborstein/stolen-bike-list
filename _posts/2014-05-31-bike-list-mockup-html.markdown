---
layout: post
title:  "Bike List Mockup HTML"
date:   2014-05-31 18:17:09
categories: jekyll bikeindex
---

<ul class="bike-list">
<li>
<img src="http://placehold.it/800x450&text=super+cool+bike">
<p><span>Cannondale</span> stolen on <span>XXXX</span></p>
</li>

<li class="no-img">
<p><span>Trek</span> stolen on <span>YXYX</span> from <span>Location</span></p>  
</li>

<li>
<img src="http://placehold.it/800x450&text=another+sweet+bike">
<p><span>Bianchi</span> stolen on <span>XXXX</span></p>  
</li>
</ul>

<style>

body {
  font-size: 2em;
  line-height: 1.5; 
  background: #e7e7e7 url(../images/body-bg.png) 0 0 repeat;
  font-family: 'Open Sans','Helvetica Neue', Helvetica, Arial, serif;
  text-shadow: 0 1px 0 rgba(255, 255, 255, 0.8);
  color: #6d6d6d;
}

a {
  color: #d5000d;
}
a:hover {
  color: #c5000c;
}

ul.bike-list {
    margin-left: 0;
    padding-left: 0;
}

ul.bike-list li {
    border-bottom: 1px dashed;
    padding-bottom: 2em;
    margin-bottom: 2em;
    position: relative;
    list-style: none;
    padding-left: 0;
}

ul.bike-list li span {
  color: #3a3a3a;
  font-weight: 300;
}

ul.bike-list li:after {
  content: 'Display photo if they have it';
  width: 130px;
  position: absolute;
  top: 0px;
  right: -150px;
  display: block;
  font-size: .5em;
  font-style: italic;
  color: rgb(153, 153, 153);
}

ul.bike-list li.no-img:after {
  content: 'No photo';
}

ul.bike-list img {
    max-width: 100%;
}

</style>

[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll]:    http://jekyllrb.com
