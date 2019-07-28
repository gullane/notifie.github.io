---
layout: post
title:  "Styled Components"
date:   2019-07-24 19:37:43 +0200
categories: fold styled-components
---
Styled components - all the main concepts in 10 easy steps !


Step 0 - Without styled-components

```html
    <div style={ background-color: red; }>Div with red border</div>
```

```css
   background-color: red;
```



Step 1 - With styled-components

```html
    <Box>Div with red border</Box>
```

```javascript
const Box = styled.div`
    background-color: red;
`
```


Step 2 - pass it a parameter

```html
    <Box fancy={true}>Boo</Box>
```

```javascript
const Box = styled.div`
    background-color: red;
    ${props => props.fancy ? "border: 1px dashed red" : ""};
`
```



Step 3 - overload another styled component

```html
    <BigBox>A big box - based on Box</BigBox>
```

```javascript
const Button = styled(Box)`
    padding: 20px;
`
```

Step 4 - props on steroids

```html
    <Box fancy={true} size="big">Boo</Box>
```

```javascript
const LabelledBox = styled(Box).attrs(({ disabled, size }) => ({
    fontSize: size === "small" ? '8px' : '14px',
    type: danger ? "danger" : "normal"
}))`
    display: block;
    padding: 0px 4px 0 5px;
    font-size: ${fontSize}

`
```