# status_code_check

# example for chrome bookmark
## codes
### status check all links
*This code able to check only same site you visit, because of [Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)*

```js
Promise.all(
  [...document.querySelectorAll("a")]
    .filter(e => e.href && e.href.length > 0 && e.href.match(location.origin))
    .map(e => fetch(e.href))
)
.then(rs =>
  rs.map(e => console.log(`${e.url}: "success";`))
)
.catch(rs =>
  rs.map(e => console.log(`${e.url}: "fail";`))
);
```

### for chrome bookmark
```js
javascript:Promise.all([...document.querySelectorAll("a")].filter(e=>e.href&&e.href.length>0&&e.href.match(location.origin)).map(e=>fetch(e.href))).then(rs=>rs.map(e=>console.log(`${e.url}: "success";`))).catch(rs=>rs.map(e=>console.log(`${e.url}: "fail";`)))
```
