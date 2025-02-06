# Uncommon HTML Bug: DOM Element Access Before Loading

This repository demonstrates a subtle bug that can occur in HTML when JavaScript code attempts to access and manipulate a DOM element before the browser has fully parsed and rendered that element.  The bug arises from incorrect script placement within the HTML document.

## Bug Description

The `bug.html` file contains a `div` element and a JavaScript script that tries to change the display style of the div.  However, if the script runs *before* the div element is fully loaded into the DOM, it will result in a `TypeError: Cannot read properties of null (reading 'style')` because `document.getElementById("myDiv")` will return `null`.

## Solution

The `bugSolution.html` file shows the corrected code.  The solution involves moving the JavaScript script to the end of the `<body>` element, ensuring it executes after the complete DOM has been loaded. Alternatively, you can use the `DOMContentLoaded` event, which ensures your JavaScript executes only when the document's DOM is ready.

This demonstrates an important principle of efficient web development: proper sequencing of script execution to avoid timing-related issues.