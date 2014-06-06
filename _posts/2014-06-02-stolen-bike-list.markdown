---
layout: post
title:  "Stolen Bike List"
date:   2014-06-02 10:27:09
categories: jekyll ajax js list
---

<a href="#" class="jquery">jQuery</a>



<script src="http://0.0.0.0:4000/stolen-bike-list/js/jquery-2.1.1.min.js">
</script>

<script type="text/javascript">
$(document).ready(function(){
    var test = $('<p class="hi" style="display:none;">Hi!</p>');
    $('article').append(test);
    $( "article" ).find("a.jquery").click(function() {
        $( ".hi" ).toggle( "normal", function() {
            // Animation complete.
        });
    });
});
</script>

<script type="text/javascript">
$(document).ready(function(){
$.ajax({
  type: "GET",
  url: "https://bikeindex.org/api/v1/bikes?stolen=true",
  success: function(data, textStatus, jqXHR) {
    $.each(data["bikes"], function(index, value) { 
      console.log(value["title"]);
      console.log(index);
    }); 
  } 
});
</script>

[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll]:    http://jekyllrb.com
