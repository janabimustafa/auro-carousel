## auro-carousel

`<auro-carousel>` is a [HTML custom element](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) that displays a group of elements in a scrollable container.

auro-carousel improves the experience of assistive technology users by managing the tabIndex and hidden state of items in the carousel. Elements not currently visible in the scrollable container are removed from the tab
order and removed from the accessibility tree. This is to prevent users from tabbing through a large amount of items in the carousel that would otherwise be out of view. When elements are scrolled into view using the shoulder buttons, they are put back into the tab order and unhidden.

Note that on mobile we do not manage the tab order and hidden state of carousel items since the shoulder buttons are not visible. Because of this, be careful putting too many elements into this on mobile, as users of assistive technologies will have to navigate through each element in the carousel, whether or not it's visible.

## UI development browser support

For the most up to date information on [UI development browser support](https://auro.alaskaair.com/support/browsersSupport)

## Install

[![Build Status](https://img.shields.io/github/workflow/status/AlaskaAirlines/auro-carousel/Test%20and%20publish?branch=master&style=for-the-badge)](https://github.com/AlaskaAirlines/auro-carousel/actions?query=workflow%3A%22test+and+publish%22)
[![See it on NPM!](https://img.shields.io/npm/v/@alaskaairux/auro-carousel?style=for-the-badge&color=orange)](https://www.npmjs.com/package/@alaskaairux/auro-carousel)
[![License](https://img.shields.io/npm/l/@alaskaairux/auro-carousel?color=blue&style=for-the-badge)](https://www.apache.org/licenses/LICENSE-2.0)

```shell
$ npm i @alaskaairux/auro-carousel
```

Installing as a direct, dev or peer dependency is up to the user installing the package. If you are unsure as to what type of dependency you should use, consider reading this [stack overflow](https://stackoverflow.com/questions/18875674/whats-the-difference-between-dependencies-devdependencies-and-peerdependencies) answer.

### Design Token CSS Custom Property dependency

The use of any Auro custom element has a dependency on the [Auro Design Tokens](https://auro.alaskaair.com/getting-started/developers/design-tokens).

### CSS Custom Property fallbacks

[CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) are [not supported](https://auro.alaskaair.com/support/custom-properties) in older browsers. For this, fallback properties are pre-generated and included with the npm.

Any update to the Auro Design Tokens will be immediately reflected with browsers that support CSS custom properties, legacy browsers will require updated components with pre-generated fallback properties.

### Define dependency in project component

Defining the component dependency within each component that is using the `<auro-carousel>` component.

```javascript
import "@alaskaairux/auro-carousel";
```

**Reference component in HTML**

```html
<auro-carousel label="Images">
    <img src="./image1" alt="Image 1 alt" />
    <img src="./image2" alt="Image 2 alt" />
    <img src="./image3" alt="Image 3 alt" />
    <img src="./image4" alt="Image 4 alt" />
    <img src="./image5" alt="Image 5 alt" />
</auro-carousel>
```

## Install bundled assets from CDN

In cases where the project is not able to process JS assets, there are pre-processed assets available for use.

**NOTE:** Be sure to replace `:version` in the URL with the version of the asset you want.

```html
<link rel="stylesheet" href="https://unpkg.com/@alaskaairux/design-tokens@:version/dist/tokens/CSSTokenProperties.css" />
<link rel="stylesheet" href="https://unpkg.com/@alaskaairux/webcorestylesheets@:version/dist/bundled/baseline.css" />

<script src="https://unpkg.com/@alaskaairux/auro-carousel@:version/dist/polyfills.js"></script>
<script src="https://unpkg.com/@alaskaairux/auro-carousel@:version/dist/auro-carousel__bundled.js"></script>
```

### polyfills.js

The `polyfills.js` is packaged with this component, but **IT IS NOT NEEDED** to load a polyfill per component. The `polyfills.js` will work for all additional components added to the project.

### IE11 Support

**Displaimer:** While these components are supported in IE, there may be issues with loading the [web components polyfill](https://www.webcomponents.org/polyfills). Please consult their documentation when supporting IE11.


## auro-carousel use cases

The `<auro-carousel>` element should be used in situations where users may:

* scroll through multiple flight date options or "shoulder dates"
* scroll through multiple images

## API Code Examples

Default auro-carousel

```html
<auro-carousel label="accessible label">
    <img src="./image1" alt="Image 1 alt" />
    <img src="./image2" alt="Image 2 alt" />
    <img src="./image3" alt="Image 3 alt" />
    <img src="./image4" alt="Image 4 alt" />
    <img src="./image5" alt="Image 5 alt" />
</auro-carousel>
```

auro-carousel with scroll distance set

```html
<auro-carousel scrolldistance=500 label="accessible label">
    <img src="./image1" alt="Image 1 alt" />
    <img src="./image2" alt="Image 2 alt" />
    <img src="./image3" alt="Image 3 alt" />
    <img src="./image4" alt="Image 4 alt" />
    <img src="./image5" alt="Image 5 alt" />
</auro-carousel>
```

## Development

In order to develop against this project, if you are not part of the core team, you will be required to fork the project prior to submitting a pull request.

Please be sure to review the [contribution guidelines](https://auro.alaskaair.com/getting-started/developers/contributing) for this project. Please make sure to **pay special attention** to the **conventional commits** section of the document.

### Start development environment

Once the project has been cloned to your local resource and you have installed all the dependencies you will need to open three different shell sessions. One is for the **Gulp tasks**, the second is for a series of **npm tasks** and the last is to run the **Polymer server**.

**Peer dependency:** Please make sure Polymer is installed globally in order to run the Polymer server. See [Auro Component Development Details](https://github.com/AlaskaAirlines/auro_docs/blob/master/src/TECH_DETAILS.md) for more information.

```shell
// shell terminal one
$ npm run dev

// shell terminal two
$ npm run serve
```

Open [localhost:3001](http://localhost:3001/)

### Testing
Automated tests are required for every Auro component. See `.\test\auro-carousel.test.js` for the tests for this component. Run `npm test` to run the tests and check code coverage. Tests must pass and meet a certain coverage threshold to commit. See [the testing documentation](https://auro.alaskaair.com/support/tests) for more details.
