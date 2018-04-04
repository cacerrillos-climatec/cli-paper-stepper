# < l2t-paper-stepper >

Polymer element for displaying steps in a stepper progression form. 
Have a quick look at the [Component page](https://www.webcomponents.org/element/Link2Twenty/l2t-paper-stepper/l2t-paper-stepper) 

## Install with bower

First you need bower, [see their site](http://bower.io/) for details 

```
bower install --save l2t-paper-stepper
```

## Examples

Each step must be within a l2t-paper-step tag, but other than that you have complete control.

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="l2t-paper-stepper.html">
	<link rel="import" href="l2t-paper-step.html">
	 <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
  <l2t-paper-stepper>
    <l2t-paper-step>#1</l2t-paper-step>
    <l2t-paper-step>#2</l2t-paper-step>
  </l2t-paper-stepper>
```
  
## Styling

The following custom properties are available for styling:

| Custom property | Description | Default |
|----------------|-------------|----------|
| --step-active-label-color| Color of the label when the step is active | --primary-text-color |
| --step-badge-color| Color of the badge when inactive | --secondary-text-color |
| --step-badge-content-color| Color of the number and the icon inside the badge | --primary-background-color |
| --step-badge-height| The height of the badge (without border) | 30px |
| --step-badge-width| The width of the badge (without border) | 30px |
| --step-button-color| Color of action buttons within step | --primary-color |
| --step-button-text-color| Text color of action buttons within step | --primary-background-color |
| --step-connector-line-color | Color of the line that connect the steps | --divider-color |
| --step-label-color| Initial color of the label | --disabled-text-color |
| --step-locked-badge-color| Color of the badge if the step is locked | --disabled-text-color |
| --step-save-badge-color| Color of the badge once the step is saved | --primary-color |
| --step-saved-label-color | Color of the label once it's saved | --primary-text-color |

## Attributes

### Public

| Attribute Name | Functionality | Type | Default |
|----------------|-------------|-------------|-------------|
| totalSlides | Number for storing total number of slides | Number | NULL |
| autoProgress | Boolean value to state if slides should auto proceed | Boolean | false |
| slideDuration | Number of seconds each slide should remain for | Number | 5 |
| hideNav | Boolean value to state if nav should should hidden | Boolean | false |
| position | Number for storing start position of slides | Number | 0 |
| disableSwipe | Boolean value to state if swipe shoud work | Boolean | false |
| sensitivity | String to storing high, low or default swipe sensitivity | String | 'default' |

### Private

| Attribute Name | Functionality | Type | Default |
|----------------|-------------|-------------|-------------|
| _totalDots | Array for storing number leading up to totalSlides | Array | [] |
| _dotStyles | Object for storing all the styles of the dot elements | Object | NULL |

## Methods

### Public

| Method Name | Action |
|----------------|-------------|
| moveNext() | Method for moving to the next slide or back to the first slide |
| movePrev() | Method for moving to the previous slide or to the last slide |
| movePos(slide) | Method for moving to a specific slide |

### Private

| Method Name | Action |
|----------------|-------------|
| _autoProceed() | Method for moving automatically ever slideDuration seconds |
| _countSlides() | Count the slides, and set totalSlides |
| _createDots(t) | Create the nav dots 1 for each slide |
| _animateCSS() | Method for styling and animating dots |
| _listenerInit() | Adds onclick listener To update the position |
| _reInit() | Method to reinitialise on totalSlides change |
| _swipeHandler(e) | Method for adding swipe event handler |

## Credit

I adapted this project from [Arthur Tressol](https://github.com/caribouflex)'s project [Caribou Stepper](https://github.com/caribouflex/caribou-stepper).