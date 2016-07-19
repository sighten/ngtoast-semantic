ngToast [![Code Climate](http://img.shields.io/codeclimate/github/tameraydin/ngToast.svg?style=flat-square)](https://codeclimate.com/github/tameraydin/ngToast/dist/ngToast.js) [![Build Status](http://img.shields.io/travis/tameraydin/ngToast/master.svg?style=flat-square)](https://travis-ci.org/tameraydin/ngToast)
=======

ngtoast-semantic is a modified version of [ngToast](https://github.com/tameraydin/ngToast) with customized styling for [SemanticUI](http://semantic-ui.com/)

**[Demo](http://tameraydin.github.io/ngToast)**

## Usage

1. Installed via [NPM](http://www.npmjs.org):
  Included as a depency in `clint/ui/package.json`
  ```"ng-toast": "sighten/ngtoast-semantic",
  ```

2. Included as a dependency in your application module (`clint/ui/src/app.js`:
  ```javascript
  import 'ng-toast'
  angular.module('hyper-gen', [
    ...
    'ngSanitize',
    'ngAnimate',
    'ngToast'
  ```

4. Place `toast` element into your HTML:
  ```html
  <body>
    <toast></toast>
    ...
  </body>
  ```

5. Inject ngToast provider in your controller:
  ```javascript
  class MyController {
    constructor(ngToast) {
      'ngInject'

      ngToast.create({'Here is an example message'})
    }
  }
  // for more info: http://tameraydin.github.io/ngToast/#api
  ```

## Usage
ngtoast-semantic has been customized for use with SemanticUi's [Messages](http://semantic-ui.com/collections/message.html)

**Types**
To create a message of a varrying type, simply use as the create function:
```javascript
ngToast.success({'Success (green) message!'})
ngToast.error({'Error (red) message!'})
ngToast.warning({'Warning (orange) message!'})
ngToast.info({'Info (blue) message!'})
```

**Semantic-specific Customization**
ngtoast-semantic has been set up to accept an optional **header** and **iconClass** with any of SemanticUI's [icons](http://semantic-ui.com/elements/icon.html) available
```javascript
ngToast.success({
  header: 'Good Job!', // optional (but encouraged!)
  content: 'You got a success message!'
})
ngToast.create({
  iconClass: 'birthday purple',
  content: 'Purple Birthday message'
})
```

**Defaults**
ng-toast-semantic defaults have been set up in `src/provider.js` as such:
* Note default timeout is **4 seconds** for all messages
```javascript
var defaults = {
  animation: 'fade',
  className: 'white',
  iconClass: 'info',
  additionalClasses: null,
  dismissOnTimeout: true,
  timeout: 4000,
  dismissButton: true,
  dismissButtonHtml: '&times;',
  dismissOnClick: true,
  onDismiss: null,
  compileContent: false,
  combineDuplications: false,
  horizontalPosition: 'right', // right, center, left
  verticalPosition: 'top', // top, bottom,
  maxNumber: 0,
  newestOnTop: true
};
```

**Additional Customization**
In addition to the Semantic-specific customization, you can always override defaults by using any of the parameters above and from [ngToast](http://tamerayd.in/ngToast/)

**Recommended**
To conform uniformly, please adhere to these principals:
- Make use of `header: ` in addition to `content: ` *- Nice UX*
- Use type creation for most (if not all messages) *- Consistency*
- Avoid overriding defaults unless necessary/appropriate

## CSS/Animations
ngToast comes with optional animations, which we have used with ngtoast-semantic

**Built-in**
  1. Included the ngToast animation stylesheet:
  
  in `clint/src/core/core.styl`
  ```css
  @require '../node_modules/ng-toast/dist/ngToast.css'
  @require '../node_modules/ng-toast/dist/ngToast-animations.css'
  ```

  2. Animation is defaulted to `'fade'`.
  ```javascript
  var defaults = {
    animation: 'fade',
    ...
  ```
  Built-in ngToast animations include `slide` & `fade`.
  

## Development

* Branch off of ``master``
* Install dependencies: ``npm install && bower install``
* Build: ``grunt``
* PR in to ``master``

## TODO
- Additional Customization of the `loading` message for dismissal/timeout overrides
