# FastImageSlidingCrop

## Overview
FastImageSlidingCrop is a pure front - end web applet designed for quick image cropping. It is built with the shadcn, Tailwind CSS v4, and React 19 technology stack. This applet enables users to upload images, automatically determine the cropping mode (portrait or landscape) based on the image's aspect ratio, and also supports manual mode switching. It offers a variety of preset aspect ratios as well as a custom aspect ratio option. The sliding window is used as the default cropping method, allowing users to crop and download images quickly and conveniently.

## Functional Requirements
### Image Upload
- Place a prominent and intuitive upload button or upload area on the page for users to select images from their local devices.
- Once the image is successfully uploaded, it should be clearly displayed in the designated area on the page, and its aspect ratio should be accurately identified.

### Cropping Mode
#### Automatic Determination
- Automatically determine the cropping mode according to the aspect ratio of the uploaded image. If the width of the image is greater than the height, the landscape cropping mode is enabled by default; if the height of the image is greater than the width, the portrait cropping mode is used by default.

#### Manual Switching
- Set an obvious switch button on the page. Users can click this button to flexibly switch between portrait and landscape cropping modes.

#### Aspect Ratio Settings
- **Preset Aspect Ratios**: Provide common aspect ratio options such as 1:1, 9:16, 4:5, 5:4, 3:4, 4:3, 2:3, 3:2, 5:7, 7:5, 1:2, 2:1. These preset aspect ratios are presented in the form of buttons or a list in the corresponding quick menu. Users can click to adjust the crop box to the corresponding aspect ratio.
- **Custom Aspect Ratio**: Set an input box or interactive interface to allow users to manually enter custom aspect ratio values. The crop box will adjust automatically according to the input values.

#### Crop Box Operations
- **Adjust Aspect Ratio**: Users can dynamically adjust the aspect ratio by dragging the edges of the crop box with the mouse. In portrait cropping, the horizontal width remains 100% of the original image width during the adjustment; in landscape cropping, the vertical width remains 100% of the original image height.
- **Move Crop Box**: Users can freely move the crop window by dragging the middle position of the crop box. The crop window has an adsorption function when approaching the edge of the original image and will automatically fit to the edge.

### Sliding Window (Default Cropping Method)
#### Portrait Cropping
- Use the sliding window as the default cropping method. The width of the window is by default 100% of the original image width.
- Initially, the window is located at the top of the image. After each download operation or when the user presses the Enter key, the window slides down according to the set rules, and by default, it moves to a position below the bottom of the previous cropping area.

#### Landscape Cropping
- The height of the sliding window is by default 100% of the original image height.
- Initially, the window is located on the left side of the image. After each download operation or when the user presses the Enter key, the window slides to the right according to the rules, and by default, it moves to the position on the right side of the previous cropping area.

### Download Function
- Set a clear and recognizable download button in the quick menu.
- When the user clicks the download button or presses the Enter key after selecting the cropping area, the image in the currently selected area of the sliding window can be downloaded to the local device in an appropriate format (such as JPEG, PNG).

## Interface Design Requirements
### Overall Layout
- Adopt a simple and intuitive design style. Reasonably divide the image display area, the quick menu area, and other functional areas to avoid a cluttered interface and ensure that users can easily find the operation elements they need.

### Quick Menu
- **Portrait Cropping**: The quick menu is located on the right side of the screen and displays preset aspect ratio buttons, a custom aspect ratio input box, a download button, a cropping mode switch button, and an offset setting option in a vertical list.
- **Landscape Cropping**: The quick menu is located at the bottom of the screen and displays the above - mentioned functional elements in a horizontal list.

### Crop Box (Sliding Window)
- Use a striking color and line style to draw the sliding window so that it is clearly visible on the image. In portrait cropping, the default width of the window is 100% of the original image width; in landscape cropping, the default height of the window is 100% of the original image height.

## Follow - up Operations
### Portrait Cropping Follow - up Operations
- After each image download or when the user presses the Enter key to confirm the download:
    - The top of the sliding window moves down to a position below the bottom of the previous cropping area.
    - The page automatically scrolls down to ensure that the sliding window is always within the visible range.
    - Provide an input box or adjustment slider to allow users to set the offset value for fine - tuning the distance the sliding window moves down.

### Landscape Cropping Follow - up Operations
- After each image download or when the user presses the Enter key to confirm the download:
    - The left edge of the sliding window moves to the right to the position on the right side of the previous cropping area.
    - The page automatically scrolls to the right to ensure that the sliding window is in the visible state.
    - Provide an input box or adjustment slider to allow users to set the offset value for fine - tuning the distance the sliding window moves to the right.

## Technical Implementation Details
### Front - end Frameworks and Libraries
- Use React 19 as the core framework to build various parts of the page with the advantage of its component - based development.
- Adopt Tailwind CSS v4 for style design, leveraging its rich class names and responsive layout features to achieve a beautiful and flexible interface.
- Combine with the component library provided by shadcn to improve development efficiency and the interactive effects of components.

### Image Processing
- Use the HTML5 Canvas API to implement image cropping operations, ensuring efficient image processing in the browser environment.
- Use JavaScript to calculate the aspect ratio of the image, dynamically adjust the sliding window, and determine the cropping area.

### User Interaction
- Use React's event handling mechanism to implement interactive effects such as button clicks, mouse dragging, and keyboard key listening.
- Listen to keyboard events to implement the function of triggering downloads when the Enter key is pressed.

### Compatibility
- Ensure that the applet can run normally on mainstream browsers (such as Chrome, Firefox, Safari, etc.) and is compatible with different screen sizes and device types.
