# Coding standards

This is the living document that is [Nomensa's](http://www.nomensa.com/) front-end coding standards. They are formed from various sources including our own preferred approach to front-end development.

- [HTML](./html/)
- [CSS](./css/)
- [SCSS](./scss/)
- [JavaScript](./javascript/)
- [jQuery](./jquery/)


## Guiding principles

### Progressive enhancement

Webpages should first work as plain HTML. A larger audience can read content inside of HTML, compared to CSS and JS. Technologies such as CSS and JS can be layered on top of HTML to enhance the user experience.

#### Further reading
- [Gov UK: Progressive enhancement](https://www.gov.uk/service-manual/making-software/progressive-enhancement.html)

### Mobile first

Create your styles for the smallest device first and then progress to larger devices. This creates advantages for both developer and user:

- CSS is inherited in larger devices without duplication of code;
- Mobile devices will only load resources necessary for the device.

#### Further reading
- [LukeW: Mobile first](http://www.lukew.com/resources/mobile_first.asp)

### DRY: Don't repeat yourself

Try to refactor code so that it is not repeated. Repeating code can affect the following aspects of the code:

- Maintainability
- Readability
- Efficiency

Each one is as important the next and focusing on just one can detriment the other.

#### Further reading
- [C2.com: Dry](http://c2.com/cgi/wiki?DontRepeatYourself)
- [jQuery.com: Keep Things DRY](http://learn.jquery.com/code-organization/dont-repeat-yourself/)
- [Steve Kwan: Best practices](https://github.com/stevekwan/best-practices/blob/master/javascript/best-practices.md#excessive-optimization)

### Be consistent

Above all:

> If you're editing code, take a few minutes to look at the code around you and determine its style. If they use spaces around all their arithmetic operators, you should too. If their comments have little boxes of hash marks around them, make your comments have little boxes of hash marks around them too. *- Google HTML/CSS Style Guide*


## References

These coding standards have been inspired by great work from the following sources:

- [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.xml)
- [airbnb css](https://github.com/airbnb/css)
- [airbnb javascript](https://github.com/airbnb/javascript)
- [Learn jQuery](http://learn.jquery.com/)
- [Mozilla Developer Network](https://developer.mozilla.org/)
- [Smashing Magazine](https://www.smashingmagazine.com)
