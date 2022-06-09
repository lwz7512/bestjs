<img src="assets/images/fabio-oyXis2kALVg-center-md.jpg">

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

```javascript
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

```jsx
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

along with a good partner for validation schema definition with [Yup](https://github.com/jquense/yup).

### #5. What is the best javascript tutorials site up to date and modern?

[JAVASCRIPT.INFO](https://javascript.info/)

### #6. What is the best ReactJS tutorials for free?

[30 Days of React](https://github.com/Asabeneh/30-Days-Of-React)

### #7. What is the best open source Firebase alternative?

- [Appwrite](https://appwrite.io/)
- [Supabase](https://supabase.com/)
- [Parse](https://parseplatform.org/)

### #8. What is the best open source Headless CMS 

- [strapi](https://strapi.io/)
- [payload](https://github.com/payloadcms/payload)

### #9. What is the best open-source Shopify alternative ?

[medusa](https://medusajs.com/)

### #10. What is the best Nodejs ORM framework?

[Prisma](https://www.prisma.io/)

### #11. What is the best javascript 2D game engine?

[phaser](https://phaser.io/)

### #12. What is the best javascript code style?

[Clean code javascript](https://github.com/ryanmcdermott/clean-code-javascript)

### #13. What is the best svg image embedding solution in ReactJS ?

in package.json:

```json
"devDependencies": {
    "babel-plugin-inline-react-svg": "^1.1.2"
}
```

in YourComponent.js file:

```
import { ReactComponent as CalendarIcon } from '../../assets/icons/calendar.svg'
```

### #14. What is the best way to detect view in viewport in ReactJS ?

Use Case:

Video playing is expected to pause while it is invisible on the screen.

Solution:

[react-in-viewport](https://github.com/roderickhsiao/react-in-viewport)

Usage:

```
import handleViewport from 'react-in-viewport'

const AnywhereVideoBlock = ({inViewport, ...}) => ()

const AnywhereVideo = handleViewport(AnywhereVideoBlock)

export default AnywhereVideo

```

### #15. What is the best slider or carousel component in ReactJS ?

[React Slick](https://react-slick.neostack.com/)

### #16. What is the best modal solution in ReactJS ?

[react-modal](https://github.com/reactjs/react-modal)

### #17. What is the best click away handler wrapper in ReactJS ?

Solution one:

```jsx
import React, { useEffect, useRef } from 'react'

const ClickAwayHandler = ({ handleClickAway, classNames, children }) => {
  const ref = useRef(null)

  useEffect(() => {
    function handleOutSideClick(e) {
      if (!ref.current || !ref.current.contains(e.target)) {
        handleClickAway()
      }
    }

    function handleEscKey(e) {
      if (e.keyCode === 27) {
        handleClickAway()
      }
    }

    window.addEventListener('click', handleOutSideClick)
    window.addEventListener('keydown', handleEscKey)

    return () => {
      window.removeEventListener('click', handleOutSideClick)
      window.removeEventListener('keydown', handleEscKey)
    }
  })

  return (
    <div className={classNames} ref={ref}>
      {children}
    </div>
  )
}

export default ClickAwayHandler
```

### #18. What is the best hover away handler wrapper in ReactJS ?

Solution one:

```jsx
import React, { useEffect, useRef } from 'react'

const HoverAwayHandler = ({ handleHoverAway, classNames, children }) => {
  const ref = useRef(null)

  useEffect(() => {
    function handleOutSideClick(e) {
      if (!ref.current || !ref.current.contains(e.target)) {
        handleHoverAway()
      }
    }

    function handleEscKey(e) {
      if (e.keyCode === 27) {
        handleHoverAway()
      }
    }

    window.addEventListener('mouseout', handleOutSideClick)
    window.addEventListener('keydown', handleEscKey)

    return () => {
      window.removeEventListener('mouseout', handleOutSideClick)
      window.removeEventListener('keydown', handleEscKey)
    }
  })

  return (
    <div className={classNames} ref={ref}>
      {children}
    </div>
  )
}

export default HoverAwayHandler
```

### #19. What is the best way to safely and dynamically import component in Next.js ?

```
const layoutName = 'YourComponentFileName'

const errorInfo = () => <p>{layoutName}.js not found</p>
// safe way to load a component at runtime
// https://github.com/vercel/next.js/issues/7480
const LayoutComponent = dynamic(
  () => import(`src/components/flex-layouts/${layoutName}.js`).catch(() => errorInfo)
)

return (<LayoutComponent />)
```

### #20. What is the best input format library ?

[Cleave.js](https://nosir.github.io/cleave.js/)

### #21. What is the best Tailwind CSS open source components ?

- [HyperUI](https://www.hyperui.dev/)
- [daisyUI](https://daisyui.com/)

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

### 31. What is the best ... ?

...

### #32. What is the best ... ?

...


