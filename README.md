### impress.js
---
https://github.com/impress/impress.js

```sh
npm run build
npm run test
npm run lint
```

```css
.future{
  display: none;
}

.present .rotating {
  transform: rotate(-10deg);
  transition-delay: 0.25s;
}

.past {
  display: none;
}

.step {
  opacity: 0.3;
  transition: opacity 1s;
}

.step.active {
  opacity: 1
}

.impress-on-overview .step{
  opacity: 1;
  cursor: pointer;
}
.impress-on-step-1,
.impress-on-step-2,
.impress-on-step-3{
  background: LightBlue;
}

.impress-not-supported .step{
  display: inline-block;
}
```

```js
var impressAPI = impress( "root" );

impress().init();

var rootElement = document.getElementById( "impress" );
rootElement.addEventListener( "impress:init", function(){
  console.log( "Impress init" );
});
impress().init();

impress().tear();

var api = impress();
api.init();
api.next();

var api = impress();
api.init();
api.prev();

var api = impress();
api.init();
api.goto(7);

var api = impress();
api.init();
api.goto( "overview" );

var overview = document.getElementById( "overview" );
var api = impress();
api.init();
api.goto( overview );

var rootElement = document.getElementById( "impress" );
rootElement.addEventListener("impress:stepnter", function(event){
  vr currentStep = event.target;
  console.log( "Entered the Step Element '" + currentStep.id + "'" );
});

var rootElement = document.getElementById( "impress" );
rootElement.addEventListener("impress:stepenter", function(){
  var currentStep = event.target;
  var nextStep = event.detail.next;
  console.log( "Left the Step Element '" + currentStep.id + "' and about to enter '" + nextStep.id );
});
```

