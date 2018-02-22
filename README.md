# Install SASS
    sudo apt-get install ruby-dev
    
    sudo gem install sass
    
    sass --watch app/sass:public/stylesheets

# Variables

    $primary-color: #333;

    body {
      color: $primary-color;
    }

# Nesting

    nav {

      ul {
        margin: 0;
        padding: 0;
        list-style: none;

        li { display: inline-block; 

          a {
            display: block;
          }

        }

      }

    }

O/p

    nav ul {
      margin: 0;
      padding: 0;
      list-style: none;
    }

    nav ul li {
      display: inline-block;
    }

    nav ul li a {
      display: block;
    }

# Mixins

    @mixin border-radius($radius) {
      -webkit-border-radius: $radius;
         -moz-border-radius: $radius;
          -ms-border-radius: $radius;
              border-radius: $radius;
    }

    .box { @include border-radius(10px); }

O/p

    .box {
      -webkit-border-radius: 10px;
      -moz-border-radius: 10px;
      -ms-border-radius: 10px;
      border-radius: 10px;
    }

# Import

  reset.scss

    html,body,ul,ol {
       margin: 0;
      padding: 0;
    }

  style.scss

    @import 'reset';

    body {
      font: 100% Helvetica, sans-serif;
      background-color: #efefef;
    }

O/p

    html, body, ul, ol {
      margin: 0;
      padding: 0;
    }

    body {
      font: 100% Helvetica, sans-serif;
      background-color: #efefef;
    }

# Extend/Inheritance

   .message {
      border: 1px solid #ccc;
      padding: 10px;
      color: #333;
    }

    .success {
      @extend .message;
      border-color: green;
    }

    .error {
      @extend .message;
      border-color: red;
    }

    .warning {
      @extend .message;
      border-color: yellow;
    }
  
 O/p
 
    .message, .success, .error, .warning {
      border: 1px solid #cccccc;
      padding: 10px;
      color: #333;
    }

    .success {
      border-color: green;
    }

    .error {
      border-color: red;
    }

    .warning {
      border-color: yellow;
    }
