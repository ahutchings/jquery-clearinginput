# clearingInput: a jQuery plugin

clearingInput is a simple jQuery plugin that provides example text inside
text inputs that automatically clears when the input is focused.  Common
uses are for a hint/example, or as a label when space is limited.

## Usage

The value is taken from the input's label by default.  The label is
positioned off-screen to remain accessible:

  <pre>
    <label for="myInput">The label text</label>
    <input id="myInput" type="text" />

    $('#myInput').clearingInput(); // Input value will be 'The label text'
  </pre>

If there is no label associated with the input (or if the label wraps the
input) then the value of the input is used as the text:

  <pre>
    <label>
      My input
      <input id="myInput" type="text" value="The input text" />
    </label>

    $('#myInput').clearingInput(); // Input value will be 'The input text'
  </pre>

If there is a label but you want to explicitly set the input text:

  <pre>
    <label for="myInput">The label text</label>
    <input id="myInput" type="text" value="The input text" />

    $('#myInput').clearingInput({text: 'Custom text'}); // Value will be 'Custom text'
    // or
    var myInput = $('#myInput');
    myInput.clearingInput({text: myInput.val()})' // Value will be 'The input text'
  </pre>

Note that a limitation of using the input's own value for the text is that the
value may be overwritten with the last submitted value if the user uses the
back button.  For this reason, using the input's own value is discouraged.

You probably want to add a style to your CSS for the blurred state:

  <pre>
    input.blur { color: #CCC; }
  </pre>

Customise the class applied to the input when blurred:

  <pre>
    $('#myInput').clearingInput({blurClass: 'customBlurClass'});
  </pre>

# Licensing

Licensed under the MIT:
http://www.opensource.org/licenses/mit-license.php

Copyright (c) 2008 Stateless Systems (http://statelesssystems.com)