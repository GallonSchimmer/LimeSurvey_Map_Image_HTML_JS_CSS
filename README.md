# LimeSurvey_Map_Image_HTML_JS_CSS
# Help Script for CKEditor

## Introduction
This project provides an HTML, JavaScript, and CSS script specifically designed to enhance the functionality of the HTML CKEditor in the Question Administration module. It focuses on manipulating the logic, the HTML view, and dynamically saving data in questions from a survey. The script includes interactive image mapping, dynamic image loading based on dropdown selection, and position marking on images.

## Features
1. **Dynamic Image Loading**: Changes the displayed image based on a selected option from a dropdown menu.
2. **Interactive Image Mapping**: Allows users to click on specific areas of an image to place a marker.
3. **Data Saving**: Captures and saves the coordinates of the placed marker in hidden input fields.

## Implementation Details
The script is divided into several key sections:

### HTML Structure
- A main container (`#image-container`) for displaying the interactive image.
- Hidden input fields (`#xCoordinateField` and `#yCoordinateField`) for storing the x and y coordinates.
- An image map (`<map name="stagemap">`) with defined clickable areas (`<area>` elements).

### JavaScript Functions
1. **Window.onload Function**:
   - Hides the question containing the position fields.
   - Initializes references to various DOM elements.
   - Checks if all necessary elements exist.
   - Calls the `updateImage()` function when the dropdown selection changes.
   - Adds event listeners to the image for setting the marker and to the clickable areas in the image map.

2. **setMarker(event)**:
   - Triggered when a user clicks on a predefined area in the image map.
   - Calculates the clicked position relative to the image.
   - Adjusts the marker's position and makes it visible at the click location.
   - Example:
     ```javascript
     area.addEventListener('click', function(event) {
       setMarker(event);
     });
     ```

3. **updateImage()**:
   - Triggered when the venue selection in the dropdown changes.
   - Constructs the file path for the new image based on the selected option's text.
   - Updates the image source to the new file path.
   - Example:
     ```javascript
     venueDropdown.addEventListener('change', updateImage);
     ```

4. **Event Listener for Clicking on the Image**:
   - Attached to the image element.
   - Calculates the coordinates where the user clicked.
   - Updates the hidden fields with these calculated values.
   - Example:
     ```javascript
     image.addEventListener('click', function(event) {
       // Calculations and updates
     });
     ```

### CSS Styling
- Positions and styles the `#image-container` and `#marker`.
- Initially hides the marker and displays it only after a click event.

## Usage
To use this script:
1. Include the HTML structure in your CKEditor content area.
2. Ensure the JavaScript section is properly linked or embedded within your page.
3. Add the CSS styles to your page's stylesheet or within a `<style>` tag.

## Requirements
- CKEditor environment.
- Understanding of HTML, CSS, and JavaScript to integrate and customize the script.

## Conclusion
This script enhances interactivity and functionality in survey questionnaires within the CKEditor environment. Its modular design allows for easy integration and customization to fit specific survey needs.
