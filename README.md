# ng-custom-color-picker
A beautiful, customizable Angular color picker component with support for hex, RGB inputs and intuitive gradient-based color selection.

## Features

- 🎨 **Multiple Input Methods**: Hex input, RGB inputs, hue slider, and gradient picker
- 🔧 **Highly Customizable**: Configurable width, height, and component visibility
- 📱 **Responsive**: Works on desktop and mobile devices  
- ♿ **Accessible**: Proper ARIA labels and keyboard navigation
- 🔄 **Reactive Forms**: Full support for Angular reactive forms and ngModel
- 🎯 **TypeScript**: Written in TypeScript with full type definitions

## Installation

```bash
npm install ng-custom-color-picker
````
Usage
1. Import the module
typescriptimport { NgCustomColorPickerModule } from 'ng-custom-color-picker';

@NgModule({
  imports: [
    NgCustomColorPickerModule
  ]
})
export class AppModule { }

2. Use in your template
<!-- Basic usage -->
<ng-custom-color-picker 
  [(ngModel)]="selectedColor"
  (colorChange)="onColorChange($event)">
</ng-custom-color-picker>

<!-- Advanced usage -->
<ng-custom-color-picker
  [(ngModel)]="selectedColor"
  [width]="350"
  [height]="200"
  [showRgbInputs]="true"
  [showHexInput]="true"
  [disabled]="false"
  placeholder="Choose Color"
  (colorChange)="onColorChange($event)">
</ng-custom-color-picker>

Component Properties - 

export class MyComponent {
  selectedColor: string = '#ff5733';
  
  onColorChange(color: string) {
    console.log('Selected color:', color);
  }
}

API
Inputs
PropertyTypeDefaultDescriptioncolorstring'#000000'The selected color valuewidthnumber280Width of the color picker dialogheightnumber200Height of the color picker dialogdisabledbooleanfalseWhether the picker is disabledshowPreviewbooleantrueShow/hide color previewshowHexInputbooleantrueShow/hide hex input fieldshowRgbInputsbooleantrueShow/hide RGB input fieldsplaceholderstring'Select Color'Placeholder text for trigger buttonstyleClassstring''Custom CSS class for styling
Outputs
EventTypeDescriptioncolorChangeEventEmitter<string>Emitted when color changescolorSelectEventEmitter<string>Emitted when color is selected
Methods
The component implements ControlValueAccessor and works seamlessly with Angular forms.
Examples
With Reactive Forms
typescriptimport { FormBuilder, FormGroup } from '@angular/forms';

export class MyComponent {
  form: FormGroup;
  
  constructor(private fb: FormBuilder) {
    this.form = this.fb.group({
      backgroundColor: ['#ffffff']
    });
  }
}
html<form [formGroup]="form">
  <ng-custom-color-picker formControlName="backgroundColor">
  </ng-custom-color-picker>
</form>
Custom Styling
html<ng-custom-color-picker
  [(ngModel)]="color"
  styleClass="my-custom-picker">
</ng-custom-color-picker>
css.my-custom-picker .ng-color-picker-wrapper {
  /* Your custom styles */
}
Browser Support

Chrome (latest)
Firefox (latest)
Safari (latest)
Edge (latest)

Contributing
Issues and pull requests are welcome! Please check the contribution guidelines.

License
MIT © [ameyb2018@gmail.com]
