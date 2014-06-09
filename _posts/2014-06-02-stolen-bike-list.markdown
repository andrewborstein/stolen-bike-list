---
layout: post
title:  "Stolen Bike List"
date:   2014-06-02 10:27:09
categories: ajax js
---

<a href="#" class="jquery">jQuery Toggle Test</a>

<div class="excontainer">

<h4>Display (via AJAX) results from <a href="https://bikeindex.org/api/v1/bikes?stolen=true" target="_blank">https://bikeindex.org/api/v1/bikes?stolen=true</a></h4>
<button id="loadbasic" style="
    padding: 8px;
    font-size: 12px;
">Submit</button>

<div id="result" style="padding-top:20px;">
    
</div>
 
</div>

<script src="/stolen-bike-list/js/jquery-2.1.1.min.js">
</script>

<script type="text/javascript">
$(document).ready(function(){
    var test = $('<p class="hi" style="display:none;">Hi!</p>');
    $('article a:first').after(test);
    $( "article" ).find("a.jquery").click(function() {
        $( ".hi" ).toggle( "normal", function() {
            return false;
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

<script type="text/javascript">
// learn jquery ajax 
// http://net.tutsplus.com/tutorials/javascript-ajax/5-ways-to-make-ajax-calls-with-jquery/

// no need to specify document ready

$(function(){
    // don't cache ajax or content won't be fresh
    $.ajaxSetup ({
        cache: false
    });
    var ajax_load = "<img src='http://automobiles.honda.com/images/current-offers/small-loading.gif' alt='loading...' />";
    
    // load() functions
    var loadUrl = "https://bikeindex.org/api/v1/bikes?stolen=true";
    $("#loadbasic").click(function(){
        $("#result").html(ajax_load).load(loadUrl);
    });

// end  
});
</script>


[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll]:    http://jekyllrb.com
