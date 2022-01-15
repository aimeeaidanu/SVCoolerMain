# SVCoolerMain
Legit Website

# Licensing
This project is licensed under the GNU General Public License v3.0.

If you use ANY code from the source:

You must disclose the source code of your modified work, and the source code you took from this project. This means you are not allowed to use code from this project (even partially) in a closed-source and/or obfuscated application.
You must state clearly and obviously to all end users that you are using code from this project.
Your application must also be licensed under the same license.

# Less files
```
material-cards.less
gm-variables.less
mixin.less
material-color.less
``` 
`material-cards.less` is the main `.less` file that includes the other `.less` files.
`gm-variables.less` contains all the color palette with the color accent.
`mixin.less` contains some utilities.
`material-color.less` contains the material color variant based on `gm-variables.less`

# Installation
You can download full package and check the demo folder for implementation example or you can use bower:

`bower install material-cards` 
Demo files require Font Awesome

# Usage
Material Cards must be used in conjunction with jQuery.

You can choose to use it as a jQuery plugin or not. Demos for both usages are available in the demos folder. Using it as a jQuery plugin easies the management of options, methods and events for full customization.

Inside the `js/` folder you can find the two files: `jquery.material-cards.js` and `jquery.material-cards.min.js`

# Init jQuery Material Card
`$('.material-card').materialCard(options);`

# Options
```ruby
options = {
    icon_close	   : 'fa-arrow-left', //string
    icon_open	   : 'fa-bars',       //string
    icon_spin	   : 'fa-spin-fast',  //string
    card_activator : 'click'          //string: click or hover
});
```
The icons are from Font Awesome, `fa-spin-fast` is similar to `fa-spin` but spin faster.

The default **card_activator** is the **click** event on button card, but you can also use **hover** (this option remove the button).

# Methods
`toggle`: change selected material card state

```ruby
$('.material-card').materialCard('toggle');
```
`open`: open selected material card

```ruby
$('.material-card:eq(1)').materialCard('open');
```
`close`: close selected material card

```ruby
$('.material-card:eq(2)').materialCard('close');
```
`isOpen`: check material card status, return true or false

```ruby
if($('.material-card:eq(3)').materialCard('isOpen') === true) {
	// do something
}
```

# Events
`show.material-card`: triggered immediately when the open instance method is called
`shown.material-card`: triggered when the card becomes visible to the user (will wait the end of the CSS transitions)
`hide.material-card`: triggered immediately when the close instance method is called
`hidden.material-card`: triggered when the card has become hidden to the user (will wait for end of CSS transitions)

# Examples
`$('.material-card').on('shown.material-card', function (event) {
    console.log(event.type, event.namespace, $(this));
    //that return
    //shown material-card [article.material-card...]
});`
var fullCardEvent = 'shown.material-card show.material-card hide.material-cards hidden.material-cards';
$('.material-cards').on(fullCardEvent, function (event) {
	//   do something
});`
