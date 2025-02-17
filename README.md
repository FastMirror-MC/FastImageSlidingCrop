# FastImageSlidingCrop

## 1. Overview
FastImageSlidingCrop is a pure front - end web applet crafted for swift image cropping. It harnesses the power of the shadcn, Tailwind CSS v4, and React 19 technology stack. This applet empowers users to upload images, automatically discern the cropping mode (vertical or horizontal) based on the image's aspect ratio, and also offers manual mode switching. It presents a diverse range of preset aspect ratios along with a custom aspect ratio option. The sliding window serves as the default cropping approach, enabling users to crop and download images expeditiously and effortlessly.

## 2. Functional Requirements
### 2.1 Image Upload
- A conspicuous and intuitive upload button or upload area is placed on the page, facilitating users to select images from their local devices.
- Upon successful image upload, it is clearly presented in the designated area on the page, and its aspect ratio is precisely identified.

### 2.2 Cropping Mode
#### 2.2.1 Automatic Determination
The cropping mode is automatically determined according to the aspect ratio of the uploaded image. If the image width exceeds the height, the horizontal cropping mode is enabled by default. Conversely, if the image height is greater than the width, the vertical cropping mode is utilized by default.

#### 2.2.2 Manual Switching
An evident switch button is incorporated on the page. Users can click this button to seamlessly toggle between vertical and horizontal cropping modes.

#### 2.2.3 Aspect Ratio Settings
- **Preset Aspect Ratios**: Common aspect ratio options like 1:1, 9:16, 4:5, 5:4, 3:4, 4:3, 2:3, 3:2, 5:7, 7:5, 1:2, 2:1 are provided. These preset aspect ratios are showcased in the form of buttons or a list within the corresponding quick menu. Users can click to adjust the crop box to the respective aspect ratio.
- **Custom Aspect Ratio**: An input box or interactive interface is set up, enabling users to manually input custom aspect ratio values. The crop box then adjusts automatically in accordance with the input values.

#### 2.2.4 Crop Box Operations
- **Adjust Aspect Ratio**: Users can dynamically modify the aspect ratio by dragging the edges of the crop box with the mouse. During vertical cropping, the horizontal width remains 100% of the original image width during the adjustment process. In horizontal cropping, the vertical width remains 100% of the original image height.
- **Move Crop Box**: Users can freely relocate the crop window by dragging the middle position of the crop box. The crop window features an adsorption function when nearing the edge of the original image and will automatically align with the edge.

### 2.3 Sliding Window (Default Cropping Method)
#### 2.3.1 Vertical Cropping
- The sliding window is adopted as the default cropping method, with the window width defaulting to 100% of the original image width.
- Initially, the window is positioned at the top of the image. After each download operation or when the user presses the Enter key, the window slides downward following the set rules, typically moving to a position beneath the bottom of the previous cropping area.

#### 2.3.2 Horizontal Cropping
- The height of the sliding window defaults to 100% of the original image height.
- Initially, the window is situated on the left side of the image. After each download operation or when the user presses the Enter key, the window slides to the right as per the rules, usually moving to the position on the right side of the previous cropping area.

### 2.4 Download Function
- A distinct and recognizable download button is placed in the quick menu.
- When the user clicks the download button or presses the Enter key after selecting the cropping area, the image within the currently selected area of the sliding window can be downloaded to the local device in suitable formats such as JPEG or PNG.

## 3. Interface Design Requirements
### 3.1 Overall Layout
- A simple and intuitive design style is adopted. The image display area, quick menu area, and other functional areas are rationally partitioned to prevent a cluttered interface, ensuring users can easily locate the operation elements they require.

### 3.2 Quick Menu
- **Vertical Cropping**: The quick menu is positioned on the right side of the screen and displays preset aspect ratio buttons, a custom aspect ratio input box, a download button, a cropping mode switch button, and an offset setting option in a vertical list.
- **Horizontal Cropping**: The quick menu is located at the bottom of the screen and showcases the aforementioned functional elements in a horizontal list.

### 3.3 Crop Box (Sliding Window)
- A striking color and line style are employed to draw the sliding window, ensuring it is clearly visible on the image. In vertical cropping, the default width of the window is 100% of the original image width. In horizontal cropping, the default height of the window is 100% of the original image height.

## 4. Follow - up Operations
### 4.1 Vertical Cropping Follow - up Operations
- After each image download or when the user presses the Enter key to confirm the download:
    - The top of the sliding window descends to a position below the bottom of the previous cropping area.
    - The page automatically scrolls downward to ensure the sliding window remains within the visible range.
    - An input box or adjustment slider is provided, allowing users to set the offset value for fine - tuning the distance the sliding window moves downward.

### 4.2 Horizontal Cropping Follow - up Operations
- After each image download or when the user presses the Enter key to confirm the download:
    - The left edge of the sliding window shifts to the right to the position on the right side of the previous cropping area.
    - The page automatically scrolls to the right to ensure the sliding window remains visible.
    - An input box or adjustment slider is provided, enabling users to set the offset value for fine - tuning the distance the sliding window moves to the right.

## 5. Technical Implementation Details
### 5.1 Front - end Frameworks and Libraries
- React 19 is utilized as the core framework to construct various parts of the page, capitalizing on its component - based development advantage.
- Tailwind CSS v4 is adopted for style design, leveraging its rich class names and responsive layout features to achieve an aesthetically pleasing and flexible interface.
- The component library provided by shadcn is integrated to enhance development efficiency and the interactive effects of components.

### 5.2 Image Processing
- The HTML5 Canvas API is employed to implement image cropping operations, ensuring efficient image processing within the browser environment.
- JavaScript is used to compute the aspect ratio of the image, dynamically adjust the sliding window, and determine the cropping area.

### 5.3 User Interaction
- React's event handling mechanism is utilized to implement interactive effects such as button clicks, mouse dragging, and keyboard key listening.
- Keyboard events are monitored to enable the function of triggering downloads when the Enter key is pressed.

### 5.4 Compatibility
- Assurance is given that the applet can operate normally on mainstream browsers, including Chrome, Firefox, Safari, etc., and is compatible with diverse screen sizes and device types. 
