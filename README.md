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

## Attributes (l2t-paper-stepper)

### Public

| Attribute Name | Functionality | Type | Default |
|----------------|-------------|-------------|-------------|
| closed | If true, start with all steps closed | Boolean | false |
| finish | Used to indicate if the stepper require users to complete one step in order to move on to the next. | Boolean | false |
| nonLinear | Used to indicate if the stepper is finished or not | Boolean | false |

### Private

| Attribute Name | Functionality | Type | Default |
|----------------|-------------|-------------|-------------|
| _activeStepIndex | Contains the index of the active step. | Number | NULL |
| _steps | Contains all the steps registered. | Array | [] |

## Attributes (l2t-paper-step)

### Public

| Attribute Name | Functionality | Type | Default |
|----------------|-------------|-------------|-------------|
| active | indicating if the step is currently active | Boolean | false |
| backLabel | label for back button | String | 'Back' |
| continueLabel | label for continue button | String | 'Continue' |
| editable | indicating if the step is editable | Boolean | false |
| finishLabel | label for finish button | String | 'Finish' |
| label | label for step | String | '' |
| locked | indicating if the step is locked | Boolean | false |
| optional | indicating if the step is optional | Boolean | false |
| save | indicating if the step is saved | Boolean | false |
| skipLabel | label for skip button | String | 'Skip' |
| updateLabel | label for update button | String | 'Update' |
| invalid | indicating if the step is invalid | Boolean | false |

### Private

| Attribute Name | Functionality | Type | Default |
|----------------|-------------|-------------|-------------|
| _stepIndex | stores own index in _steps array. | Number | NULL |

## Methods (l2t-paper-stepper)

### Public

| Method Name | Action |
|----------------|-------------|
| closeAll() | Function: used to close all the steps |
| isFinalStep() | Return: used to inicate is current step is the final step |
| nextStep() | Function: used to open the next step, it will save and close the current step |
| prevStep() | Function: used to open the previous step, it will close, not save, the current step |
| reset() | Function: used to unsave all steps |
| setActiveByIndex(i) | Function: used to set the active step by number/index |
| skipStep() | Function: used to open the next step, it will close, not save, the current step |

### Private

| Method Name | Action |
|----------------|-------------|
| _calcNextStep() | Return: provides the index closest valid step, going forwards through the array |
| _calcPrevStep() | Return: provides the index closest valid step, going backwards through the array |
| _finishStep() | Function: used to fire stepper-finished |
| _registerStep(el) | Function: used by `l2t-paper-step` to add itself into the _steps array |

## Methods (l2t-paper-step)

### Public

| Method Name | Action |
|----------------|-------------|
| activeStepObserver() | Observer: setActiveByIndex to active |
| fireInvalidStep() | Function: fire step-invalid event |
| ready() | Function: register step with parent |

### Private

| Method Name | Action |
|----------------|-------------|
| _badgeNum(i) | Return: badge number |
| _fireEvent(e) | Function: fire clicked event for button |
| _getIcon() | Return: icon name |
| _setActive() | Function: makes self active step |
| _setValidActive() | Function: checks if can be set to active, if passes call _setActive() |
| _showBack()  | Return: indicates if back button should be shown |
| _showContinue() | Return: indicates if continue button should be shown |
| _showFinish() | Return: indicates if finish button should be shown |
| _showSkip() | Return: indicates if skip button should be shown |
| _showUpdate() | Return: indicates if update button should be shown |

## Credit

I adapted this project from [Arthur Tressol](https://github.com/caribouflex)'s project [Caribou Stepper](https://github.com/caribouflex/caribou-stepper).