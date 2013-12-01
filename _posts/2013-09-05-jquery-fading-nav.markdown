---
layout: post
title: "Simple Fade In and Out Fixed Navigation with JQuery"
date: 2013-09-05 16:45:00
tags: note, jquery, javascript
---

I was recently looking to make a navigation bar fade in and out based on the user scrolling. Using JQuery, I believe I figured out a simple and straight forward solution to accomplishing this.

1. Create the HTML skeleton with sections and a navbar.

  **Note**: `head` *has been omitted, see source for full HTML skeleton.*

  ``` html
    <body>
      <nav>
        <h3 class="brand"><a href="#intro">Site Name</a></h3>

        <ul class="menu">
          <li class="menu-item"><a href="#about">About</a></li>
          <li class="menu-item"><a href="#screenshots">Screenshots</a></li>
        </ul>
      </nav>

      <div class="main">
        <section id="intro">
        </section>

        <section id="about">
        </section>

        <section id="screenshots">
        </section>
      </div>
    </body>
  ```

2. Add your content (even if it is placeholder for now).

3. Include JQuery in your HTML skeleton.

  ``` html
    <script src="http://code.jquery.com/jquery-1.10.1.min.js"></script>
  ```

4. Create a JavaScript file and include in your HTML.

  ``` html
    <script src="navigation.js"></script>
  ```

5. Add the following JavaScript to that file.

  ``` js
    $(function() {
      $("nav").hide();

      $(window).scroll(function () {
        if ($(document).scrollTop() >= $("#intro").height() - 200){
          $("nav").fadeIn();
        }
        else {
          $("nav").fadeOut();
        }
      });
    });
  ```

Walking through the code line by line, we make sure the page content is fully loaded before the code executes. We then hide the `nav` element, right off the bat. Next, everytime the user scrolls we check to see if the distance from the current view to the top if greater than half the height of the `#intro` div minus 200 pixels. If so, fade the `nav` in. Otherwise, fade the `nav` out.

[View the demo.](http://brettchalupa.github.io/simple-fading-nav/)

[View the demo source.](https://github.com/brettchalupa/simple-fading-nav)

[Download the demo source.](https://github.com/brettchalupa/simple-fading-nav/archive/gh-pages.zip)
