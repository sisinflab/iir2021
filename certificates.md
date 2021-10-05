---
title: 'Attendance Certificates'
date: 2018-02-22T17:01:34+07:00
layout: page
bodyClass: page-about
---

Use the email address you used to register to __IIR 2021__ to download your attendance certificate!

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
  box-sizing: border-box;" placeholder="Insert your email here..."></div>
<div style="margin-left:10px" id="status"></div>
<div style="flex-basis:100%;height: 0;"></div>
<div style="margin-top:20px" id="message"></div>
</div>

<script>
function createCORSRequest(method, url) {
  var xhr = new XMLHttpRequest();
  if ("withCredentials" in xhr) {
    // XHR for Chrome/Firefox/Opera/Safari.
    xhr.open(method, url, true);
  } else if (typeof XDomainRequest != "undefined") {
    // XDomainRequest for IE.
    xhr = new XDomainRequest();
    xhr.open(method, url);
  } else {
    // CORS not supported.
    xhr = null;
  }
  return xhr;
}

function UrlExists(url) {
  try {
    var xhr = createCORSRequest('HEAD', url);
    if (!xhr) {
      console.log('CORS not supported');
    }
    xhr.onreadystatechange = function() {
      if (this.readyState !== 4) {
        return;
      };
      if (this.status !== 200) {
        $('#message').html('<span style="vertical-align: middle;" class="material-icons">warning</span> Certificate not found');
      } else {
        $('#message').html('<span style="vertical-align: middle;" class="material-icons">check_circle</span> <a href="#" onclick="location.href=`' + url + '`">Download your attendance certificate</a>');
      }
    };
    xhr.onerror = function() {
      $('#message').html('<span style="vertical-align: middle;" class="material-icons">warning</span> Certificate not found');
    };
  } catch (error) {}
  try {
    xhr.send();
  } catch (error) {}
  console.clear()
}
//setup before functions
var typingTimer; //timer identifier
var doneTypingInterval = 1000; //time in ms, 5 second for example
var $input = $('#email');

//on keyup, start the countdown
$input.on('keyup', function() {
  clearTimeout(typingTimer);
  typingTimer = setTimeout(doneTyping, doneTypingInterval);
});

//on keydown, clear the countdown
var manageTyping = function() {
  $input.one('input', function() {
    $('#message').html('');
    $('#status').html('<img style="margin:0" src="../images/typing_small.gif" />');
    clearTimeout(typingTimer);
  })
};

$(function() {
  manageTyping();
});

//user is "finished typing," do something
function doneTyping() {
  if ($('#email').val() == '') {
    $('#message').html('');
    $('#status').html('');
    manageTyping();
  } else {
    var url = 'https://www.clusterchoral.it/certificates/' + $('#email').val() + '.pdf'
function createCORSRequest(method, url) {
  var xhr = new XMLHttpRequest();
  if ("withCredentials" in xhr) {
    // XHR for Chrome/Firefox/Opera/Safari.
    xhr.open(method, url, true);
  } else if (typeof XDomainRequest != "undefined") {
    // XDomainRequest for IE.
    xhr = new XDomainRequest();
    xhr.open(method, url);
  } else {
    // CORS not supported.
    xhr = null;
  }
  return xhr;
}

function UrlExists(url) {
  try {
    var xhr = createCORSRequest('HEAD', url);
    if (!xhr) {
      console.log('CORS not supported');
    }
    xhr.onreadystatechange = function() {
      if (this.readyState !== 4) {
        return;
      };
      if (this.status !== 200) {
        $('#message').html('<span style="vertical-align: middle;" class="material-icons">warning</span> Certificate not found');
      } else {
        $('#message').html('<span style="vertical-align: middle;" class="material-icons">check_circle</span> <a href="#" onclick="location.href=`' + url + '`">Download your attendance certificate</a>');
      }
    };
    xhr.onerror = function() {
      $('#message').html('<span style="vertical-align: middle;" class="material-icons">warning</span> Certificate not found');
    };
  } catch (error) {}
  try {
    xhr.send();
  } catch (error) {}
  console.clear()
}
//setup before functions
var typingTimer; //timer identifier
var doneTypingInterval = 1000; //time in ms, 5 second for example
var $input = $('#email');

//on keyup, start the countdown
$input.on('keyup', function() {
  clearTimeout(typingTimer);
  typingTimer = setTimeout(doneTyping, doneTypingInterval);
});

//on keydown, clear the countdown
var manageTyping = function() {
  $input.one('input', function() {
    $('#message').html('');
    $('#status').html('<img style="margin:0" src="../images/typing_small.gif" />');
    clearTimeout(typingTimer);
  })
};

$(function() {
  manageTyping();
});

//user is "finished typing," do something
function doneTyping() {
  if ($('#email').val() == '') {
    $('#message').html('');
    $('#status').html('');
    manageTyping();
  } else {
    var url = 'https://www.clusterchoral.it/certificates/' + $('#email').val() + '.pdf'
    UrlExists(url);
    console.clear()
    $('#status').html('');
    manageTyping();
  }
}    UrlExists(url);
    console.clear()
    $('#status').html('');
    manageTyping();
  }
}
</script>
