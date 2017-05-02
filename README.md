# SUIT CSS components-form-field

[![Build Status](https://travis-ci.org/simonsmith/suitcss-components-form-field.svg?branch=master)](https://travis-ci.org/simonsmith/suitcss-components-form-field)

A CSS component for rendering form fields. Ensures inputs, labels and help text
behave consistently across browsers.

Read more about [SUIT CSS](https://github.com/suitcss/suit/).

## Installation

* [npm](http://npmjs.org/): `npm install suitcss-components-form-field`
* Download: [zip](https://github.com/simonsmith/suitcss-components-form-field/releases/latest)

## Example

* [**View a demo**](https://simonsmith.io/suitcss-components-form-field/test/demo.html)
* [**View the tests**](https://simonsmith.io/suitcss-components-form-field/test/index.html)

## Available classes

### Component structure

* `FormField` - Containing element. Apply state classes to this
* `FormField-input` - Consistent rendering of various form inputs
* `FormField-label` - Label text for the input
* `FormField-text` - Used to display help text or validation messages
* `FormField-check` - Wraps around `input` and `label` when using either radio
  or checkbox inputs

### States

* `is-error` - Applies the error colours to each element
* `is-warning` - Applies the warning colours to each element
* `is-success` - Applies the success colours to each element

## Usage

### Basic

This works with other inputs such as `textarea`, `range` and `file`.

```html
<div class="FormField">
  <label class="FormField-label" for="surname">Surname</label>
  <input class="FormField-input" type="text" id="surname" placeholder="Enter your surname">
  <p class="FormField-text">Some optional text to the user about the input field</p>
</div>
```

### Using a `label` container

```html
<label class="FormField">
  <span class="FormField-label">Surname</span>
  <input class="FormField-input" type="text" placeholder="Enter your surname">
  <p class="FormField-text">Some text to the user about the input field</p>
</label>
```

### Checkbox or radio input types

Checkbox and radio inputs require an additional container. This controls
positioning and allows the `FormField-text` to be rendered beneath:

```html
<div class="FormField">
  <label class="FormField-check">
    <input class="FormField-input" name="shopping" type="radio">
    <span class="FormField-label">Apples</span>
  </label>
  <label class="FormField-check">
    <input class="FormField-input" name="shopping" type="radio">
    <span class="FormField-label">Oranges</span>
  </label>
  <span class="FormField-text">Some text about the choices above</span>
</div>
```

### Validation states

A state class of `is-error`, `is-success` or `is-warning` can be applied to the
root element:

```html
<div class="FormField is-error">
  <label class="FormField-label">Surname</label>
  <input class="FormField-input" type="text" placeholder="Enter your surname">
  <p class="FormField-text">There was a problem!</p>
</div>
```

### Controlling layout

`FormField` leaves the layout concerns to another component or utility, for
example [suitcss-components-grid](https://github.com/suitcss/components-grid).

#### Vertical spacing

Can be handled by a component that controls the `<form/>` itself:

```html
<form class="UserForm">
  <div class="UserForm-field">
    <div class="FormField">
      // ...
    </div>
  </div>
  <div class="UserForm-field">
    <div class="FormField">
      // ...
    </div>
  </div>
</form>
```

#### Horizontal positioning with `Grid` and `utils-size`

The following achieves an inline form effect

```html
<div class="FormField">
  <div class="Grid Grid--alignMiddle">
    <div class="Grid-cell u-size2of12">
      <label class="FormField-label u-textBold">Username</label>
    </div>
    <div class="Grid-cell u-sizeFill">
      <input class="FormField-input" type="text" value="SomeCoolUsername">
      <p class="FormField-text">That username is already taken!</p>
    </div>
  </div>
</div>
```

### Configurable variables

#### `FormField-label`

* `--FormField-label-color`
* `--FormField-label-marginBottom`

#### `FormField-input`

* `--FormField-input-borderColor`
* `--FormField-input-borderRadius`
* `--FormField-input-borderWidth`
* `--FormField-input-color`
* `--FormField-input-fontFamily`
* `--FormField-input-fontSize`
* `--FormField-input-padding`

#### `FormField-text`

* `--FormField-text-fontSize`
* `--FormField-text-marginTop`

#### `FormField-check`

* `--FormField-check-gutter` - Space between checkbox/radio and the label

#### Validation states

* `--FormField-input-onDisabled-backgroundColor`
* `--FormField-onError-color`
* `--FormField-onWarning-color`
* `--FormField-onSuccess-color`

## Testing

Install [Node](http://nodejs.org) (comes with npm).

```
npm install
```

To generate a build:

```
npm run build
```

To lint code with [postcss-bem-linter](https://github.com/postcss/postcss-bem-linter) and [stylelint](http://stylelint.io/)

```
npm run lint
```

To generate the testing build.

```
npm run build-test
```

To watch the files for making changes to test:

```
npm run watch
```

Basic visual tests are in `test/index.html`.

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox (latest)
* Safari 7.1+
* Internet Explorer 10+
* Android 5+ (Chrome 55, Firefox 51)
* iOS 7+ (Safari)
* Windows phone 8.1+
