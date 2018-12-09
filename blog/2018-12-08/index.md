---
date: "2018-12-08"
title: "Basic Flexbox concepts explained in 5 minutes"
category: "CSS"
---

## Aligning elments


The two main components of a Flexbox layout are the container and child items which are controlled by flow direction. The width of flex items is automatically adjusting to fit the container.


By applying property of display with a value of flex, we are enabling a flex context for all its direct children.

```css
.container {
	display:flex;
}
```

If the `<div>` elements are one after another than all siblings will  be positioned horizontally within the container. 

<iframe height='365' scrolling='no' title='Flexbox - Horizontal Layout' src='//codepen.io/marthehe/embed/wERmNb/?height=265&theme-id=dark&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/marthehe/pen/wERmNb/'>Flexbox - Horizontal Layout</a> by Marta (<a href='https://codepen.io/marthehe'>@marthehe</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>


In the example above we have two axes:
- Main-axis **X** (horizontal) 
- Cross-axis **Y** (vertical) 

If we want to swap the axis vertically we just need to add property flex-direction with value of column.

```css
.container {
	display: flex;
	flex-direction: column;
}
```


<iframe height='465' scrolling='no' title='Flexbox - VerticalLayout' src='//codepen.io/marthehe/embed/QVzmoW/?height=265&theme-id=dark&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/marthehe/pen/QVzmoW/'>Flexbox - VerticalLayout</a> by Marta (<a href='https://codepen.io/marthehe'>@marthehe</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Property flex-direction establishes the main-axis, therefore defining the direction of flex items. For me it is easy to think of flex items as being laid out either in:
- horizontal rows (value row or row-reverse)
- vertical columns (column or column-reverse)

Now the main-axis of the container is set vertically and the cross-axis horizontally, which  results in items being stacked vertically.

The reason the axes are important to understand is because the properties justify-content and align-items control how the items are positioned along the main-axis and cross-axis respectively.



## Distributing elements

In this section we are going to cover two following properties: `justify-content` and `align-items`.

I noticed that the property that I'm using the most is `justify-content`. It allows to distribute elements along main axis.

For example `justify-content: center` will center the elements:


```css
.container {
	display: flex;
	justify-content: center;
}
```

<iframe height='365' scrolling='no' title='Flexbox - Justify-Content' src='//codepen.io/marthehe/embed/eLbMMJ/?height=265&theme-id=dark&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/marthehe/pen/eLbMMJ/'>Flexbox - Justify-Content</a> by Marta (<a href='https://codepen.io/marthehe'>@marthehe</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>


<!-- TODO add examples for most of the values below -->

Other values that we can set for `justify-content` are: 
- `flex-start`: items are packed toward the start line
- `flex-end`: items are packed toward to end line
- `space-between`:  items are distributed evenly in the line
- `space-around`: items are distributed evenly in the line with equal space around them
- `space-evenly`: items are distributed so that the spacing between any two items (and the space to the edges) is equal.

In the example below `align-items` defines the default behavior for how items are laid out along the cross-axis on the current line. We can think of it as the `justify-content` version for the cross-axis.

```css
.container {
	display: flex;
	align-items: center;
}
```

<iframe height='365' scrolling='no' title='Flexbox - VerticalLayout' src='//codepen.io/marthehe/embed/QVzmoW/?height=265&theme-id=dark&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/marthehe/pen/QVzmoW/'>Flexbox - VerticalLayout</a> by Marta (<a href='https://codepen.io/marthehe'>@marthehe</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Values that we can set for align-items are: 
- `flex-start`: cross-start margin edge of the items is placed on the cross-start line
- `flex-end`: cross-end margin edge of the items is placed on the cross-end line
- `center`: items are centered in the cross-axis
- `baseline`: items are aligned such as their baselines align
- `stretch`: stretch to fill the container (still respect min-width/max-width).
To center items along both axis, we can use justify-content and align-items. And give them value of center.

```css
.container {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
}
```

<iframe height='365' scrolling='no' title='Justify-Content and Align-Items' src='//codepen.io/marthehe/embed/MZWWMK/?height=265&theme-id=dark&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/marthehe/pen/MZWWMK/'>Justify-Content and Align-Items</a> by Marta (<a href='https://codepen.io/marthehe'>@marthehe</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Positioning single elements

The one last thing are the items themselves and how specific styles are being applied to them.
If we want to adjust the position of any item we can do this by applying CSS property `align-self`. It does accept exactly the same values as `align-items`.

```css
.&__item--bottom  {
	align-self: flex-end;
}
```

<iframe height='365' scrolling='no' title='Flexbox - Align-Self' src='//codepen.io/marthehe/embed/rZodEj/?height=265&theme-id=dark&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/marthehe/pen/rZodEj/'>Flexbox - Align-Self</a> by Marta (<a href='https://codepen.io/marthehe'>@marthehe</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

As you can see, flexbox is pretty neat. The prime characteristic of the flex container is the ability to modify the width or height of its children to fill the available space in the best possible way on different screen sizes. If we need to control the position of elements on the website it can make our lives much more easier and we can achieve more complex layouts with less code and time.




