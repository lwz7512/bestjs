AgileJS
----------------------

@2022/05/12


> Tiny solutions for Javascript development from real projects.

> Liberate javascript developers from repetitive work.


## Notion Page

[Here](https://glow-pint-f73.notion.site/3a8b8df7cd044237b29357c071a60f44?v=4e3a4f476bcd412190802f91fb285bb8)


## 1. How to render html in Reactjs safely


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


## 2. What is the best calendar component in ReactJS?


available calendar components are:

- react-dates
- react-datepicker
- react-day-picker

...

## 3. What is the best map library in javascript?


available map library are:

- mapbox, react-map-gl
- openlayer
- leaflet

...

## 4. What is the best form creation & validity library?

...

## 5. ...

...

## 6. ...

...

## 7. ...

...

## 8. ...

...

## 9. ...

...

## 10. ...

...


