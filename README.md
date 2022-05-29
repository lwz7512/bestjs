<img src="assets/images/fabio-oyXis2kALVg-md.jpg">

BestJS.solutions
------------------------------

@2022/05/28

> Tiny solutions for Javascript development from real projects.

Hero image credit to [fabio](https://unsplash.com/photos/oyXis2kALVg).

Contributions(PR, Issue) to this repo are welcome!


## Origin

[agilejs@2022/05/12](./AgileJS.md)


## Solutions

each solution is expected to include:

- Tile
- Description or Challenge
- Code snippte


### #1. How to render html in Reactjs safely


Challenge: html string may invalid or unclosed to parse directly unless severside sanitized.


Snippet:

```
import renderHTML from 'react-render-html'

export default function parseValidHtmlString(string) {
  // check string for valid markup and render elements OR
  // strip tags and render string.
  if (
    !/<(br|basefont|hr|input|source|frame|param|area|meta|!--|col|link|option|base|img|wbr|!DOCTYPE).*?>|<(a|abbr|acronym|address|applet|article|aside|audio|b|bdi|bdo|big|blockquote|body|button|canvas|caption|center|cite|code|colgroup|command|datalist|dd|del|details|dfn|dialog|dir|div|dl|dt|em|embed|fieldset|figcaption|figure|font|footer|form|frameset|head|header|hgroup|h1|h2|h3|h4|h5|h6|html|i|iframe|ins|kbd|keygen|label|legend|li|map|mark|menu|meter|nav|noframes|noscript|object|ol|optgroup|output|p|pre|progress|q|rp|rt|ruby|s|samp|script|section|select|small|span|strike|strong|style|sub|summary|sup|table|tbody|td|textarea|tfoot|th|thead|time|title|tr|track|tt|u|ul|var|video).*?<\/\2>/i.test(
      string,
    )
  ) {
    return string.replace(/<[^>]*>?/gm, '')
  } else {
    return renderHTML(string)
  }
}
```

Usage:

```
<div>{parseValidHtmlString(htmlString)}</div>
```


Created @2022/05/12


### #2. What is the best calendar component in ReactJS?


available calendar components are:

- react-dates
- react-datepicker
- react-day-picker

...

### #3. What is the best map library in javascript?

Available map library are:

- [mapbox](https://www.mapbox.com/), [react-map-gl](https://github.com/visgl/react-map-gl)
- [Openlayer](https://openlayers.org/)
- [leaflet](https://leafletjs.com/)

Comparision:

...

### #4. What is the best form creation & validity library in ReactJS?

Challenge: create form in reactjs could be cubersome if you choosing manage form state mannually.

Solution:

[Formik](https://formik.org/)

```
Build forms in React, without the tears
```

### #5. What is the best javascript tutorials site up to date and modern?

[JAVASCRIPT.INFO](https://javascript.info/)

### #6. What is the best open source Firebase alternative?

- [Appwrite](https://appwrite.io/)
- [Supabase](https://supabase.com/)
- [Parse](https://parseplatform.org/)

### #7. What is the best open source Headless CMS 

[strapi](https://strapi.io/)

### #8. What is the best open-source Shopify alternative ?

[medusa](https://medusajs.com/)

### #9. What is the best Nodejs ORM framework?

[Prisma](https://www.prisma.io/)

### #10. What is the best javascript 2D game engine?

[phaser](https://phaser.io/)

### #11. What is the best javascript code style?

[Clean code javascript](https://github.com/ryanmcdermott/clean-code-javascript)

### #11. What is the best ... ?

...

### #12. What is the best ... ?

...

### #13. What is the best ... ?

...

### #14. What is the best ... ?

...

### #15. What is the best ... ?

...

### #16. What is the best ... ?

...

### #17. What is the best ... ?

...

### #18. What is the best ... ?

...

### #19. What is the best ... ?

...

### #20. What is the best ... ?

...

### #21. What is the best ... ?

...

### #22. What is the best ... ?

...

### #23. What is the best ... ?

...

### #24. What is the best ... ?

...

### #25. What is the best ... ?

...

### #26. What is the best ... ?

...

### #27. What is the best ... ?

...

### #28. What is the best ... ?

...

### #29. What is the best ... ?

...

### #30. What is the best ... ?

...


