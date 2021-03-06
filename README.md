#jquery.popuper

Extremely lightweight jquery plugin script to show popup blocks. No fancy effects and redundant gimmicks, full
control over the process instead.

##Usage

Get the [`jquery.popuper.js`](https://github.com/chesco-als/popuper/raw/master/jquery.popuper.js).
Add to page:

```html
<script src="jquery.js" type="text/javascript"></script>
<script src="jquery.popuper.js" type="text/javascript"></script>
```

###Possible options
```js
/**
 * @param {Object} hParam Options:
 * @option {String} hiddenClass CSS class name for block hiding, 'g-hidden' by default.
 * @option {String} animatedClass CSS class name for animation purposes (see the example).
 * @option {Number} hideDelay Delay between `hiddenClass` and `animatedClass` assignation, defaults to 0.
 * @option {String|Element|jQuery} fader Fader block (selector, DOM-element or jQuery), optional.
 * @option {String|Element|Array[Element]|jQuery} open Popup runner block or link.
 * @option {String|Element|Array[Element]|jQuery} close Inner Popup close element, will be searched inside main element.
 * @option {Function} onShow Callback, being called upon show event.
 * @option {Function} onHide Callback, being called upon hide event.
 */
```

Use page fader to make block it "modal".

###Example

```js
$(function () {
	var container = $('.popup-container');
	container.popuper({
		hiddenClass: 'g-hidden',
		fader: '.page-fader',
		open: 'span.show-popup',
		close: container.find('.icon-close'),
		onShow: function () {
			// do some useful stuff here,
			// positioning for example
		},
		onHide: function () {
			// do some unuseful stuff here
		}
	});
});
```

```css
.g-hidden {
	display: none;
}

.page-fader {
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	height: 100%;
	background: #000;
	opacity: 0.35;
	z-index: 1000;
	filter: alpha(opacity=35);
}

.popup-container {
	position: fixed;
	left: 50%;
	top: 33%;
	width: 24em;
	margin-left: -12em;
	z-index: 1001;
}
```

###Example with CSS animations
[It's here](https://rawgithub.com/chesco-als/popuper/master/example.html).
