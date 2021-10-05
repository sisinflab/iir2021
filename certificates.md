---
title: 'Attendance Certificates'
date: 2018-02-22T17:01:34+07:00
layout: page
bodyClass: page-about
---

prova

<link href="https://fonts.googleapis.com/icon?family=Material+Icons"
      rel="stylesheet">
<script src="https://code.jquery.com/jquery-3.6.0.slim.min.js" integrity="sha256-u7e5khyithlIdTpu22PHhENmPcRdFiHRjhAuHcs05RI=" crossorigin="anonymous"></script>

<div style="display:flex;flex-wrap:wrap;align-items:center">
<div><input type="text" id="email" name="email" style="padding: 12px 20px;
  width:300px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;" placeholder="Email used for IIR registration"></div>
<div style="margin-left:10px" id="status"></div>
<div style="flex-basis:100%;height: 0;"></div>
<div style="margin-top:20px" id="message"></div>
</div>

<script>
function UrlExists(url) {
    var http = new XMLHttpRequest();
    http.open('GET', url, false);
    http.send();
    if (http.status != 404)
        return true;
    else
        return false;
}
//setup before functions
var typingTimer;                //timer identifier
var doneTypingInterval = 1000;  //time in ms, 5 second for example
var $input = $('#email');

//on keyup, start the countdown
$input.on('keyup', function () {
  clearTimeout(typingTimer);
  typingTimer = setTimeout(doneTyping, doneTypingInterval);
});

//on keydown, clear the countdown
var manageTyping = function() {
  $input.one('keydown', function () {
  $('#status').html('<img style="margin:0" src="../images/typing_small.gif" />');
  clearTimeout(typingTimer);
})};

$(function(){ manageTyping(); });

//user is "finished typing," do something
function doneTyping () {
  var url = 'https://sciueferrara.altervista.org/iir2021/certificates/' + $('#email').val() + '.pdf'
  if (UrlExists(url)) {
    $('#message').html('<span class="material-icons">check_circle</span> <a href="#" onclick="location.href=url">Download your attendance certificate</a>');
  } else {
    $('#message').html('<span class="material-icons-outlined">warning</span> Certificate not found');
  }
  $('#status').html('');
  manageTyping();
}
</script>
