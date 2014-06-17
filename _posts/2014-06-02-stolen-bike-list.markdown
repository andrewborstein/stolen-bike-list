---
layout: post
title:  "Stolen Bike List"
date:   2014-06-02 10:27:09
categories: ajax js
---

<a href="#" class="jquery" onclick="return false">jQuery Toggle Test</a>
{% highlight js %}
$(document).ready(function(){
    var test = $('<p class="hi" style="display:none;">Hi!</p>');
    $('article a:first').after(test);
    $( "article" ).find("a.jquery").click(function() {
        $( ".hi" ).toggle(function() {
            return false;
        });
    });
});
{% endhighlight html %}
<div class="excontainer">

<h4>AJAX Code provided by Seth</h4>
{% highlight js %}
// script provided by seth
$(document).ready(function(){
    $.ajax({
        type: "GET",
        url: "https://bikeindex.org/api/v1/bikes?stolen=true",
        success: function(data, textStatus, jqXHR) {
            $.each(data["bikes"], function(index, value) { 
                list_item = '<img src=' + value["thumb"] + '>';
                list_item += '<p><span>' value["manufacturer_name"] + '</span>';
                list_item += ' stolen on ' value["stolen_record"]["date_stolen"];
                // You should parse the date to make it more readable
                $('#bike-list').append("<li>" +  list_item + "</li>");
                console.log(index);
            }); 
        } 
    });
});
{% endhighlight html %}

<h4>Display (via AJAX) results from <a href="https://bikeindex.org/api/v1/bikes?stolen=true" target="_blank">https://bikeindex.org/api/v1/bikes?stolen=true</a></h4>
<button id="loadbasic" style="
    padding: 8px;
    font-size: 12px;
">Submit</button>
</div>

{% highlight js %}
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
{% endhighlight html %}

<div id="result" style="padding-top:20px;">
    
</div>

<script src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>

<script type="text/javascript">
$(document).ready(function(){
    var test = $('<p class="hi" style="display:none;">Hi!</p>');
    $('article a:first').after(test);
    $( "article" ).find("a.jquery").click(function() {
        $( ".hi" ).toggle(function() {
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

<script type="text/javascript">
// script provided by seth
$(document).ready(function(){
    $.ajax({
        type: "GET",
        url: "https://bikeindex.org/api/v1/bikes?stolen=true",
        success: function(data, textStatus, jqXHR) {
            $.each(data["bikes"], function(index, value) { 
                list_item = '<img src=' + value["thumb"] + '>';
                list_item += '<p><span>' value["manufacturer_name"] + '</span>';
                list_item += ' stolen on ' value["stolen_record"]["date_stolen"];
                // You should parse the date to make it more readable
                $('#bike-list').append("<li>" +  list_item + "</li>");
                console.log(index);
            }); 
        } 
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
            $('body').append($('<div>', {
                text: value.name
            }));
        });
    }
});
});
</script>

[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll]:    http://jekyllrb.com
