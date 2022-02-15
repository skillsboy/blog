---
title: "How to Center an Element Horizontally and Vertically (CSS)"
date: 2021-12-10T21:07:42Z
draft: true
---

# How to center an element horizontally and vertically (CSS)

## Intro

Here you will find multiple ways to center an element horizontally and vertically with CSS.

---

## Examples

### 1. Center with position absolute and transform

This example is probably one of the oldest ways how to center an element.

The ``parent`` has to have:

```css
.container {
	position: relative;
}
```

The ``child`` you want to center:

```css
.center {
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
}
```

<p class="codepen" data-height="450" data-default-tab="html,result" data-slug-hash="Exwyjpm" data-editable="true" data-user="skillsboy" style="height: 450px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/skillsboy/pen/Exwyjpm">
  Horizontal and vertical div center with position absolute and transform.</a> by skillsboy (<a href="https://codepen.io/skillsboy">@skillsboy</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


<p align="center" style="margin-top: 40px;">
<svg version="1.0" xmlns="http://www.w3.org/2000/svg"
width="250"  height="20" viewBox="0 0 250 20" preserveAspectRatio="xMidYMid meet">
<g transform="translate(0.000000,20.000000) scale(0.100000,-0.100000)" fill="currentColor"  stroke="none">
<path d="M156 139 c-10 -6 -27 -20 -38 -31 -10 -10 -31 -23 -45 -29 -19 -7 -23 -13 -15 -21 15 -15 52 -3 92 32 19 16 42 30 52 30 9 0 35 -16 58 -35 53 -44 88 -45 133 -6 53 47 77 48 126 7 60 -51 100 -47 163 16 10 10 27 18 38 18 11 0 28 -8 38 -18 63 -63 103 -67 163 -16 49 41 73 40 126 -7 45 -39 80 -38 133 6 47 39 68 43 96 17 76 -70 132 -70 208 0 28 26 49 22 96 -17 53 -44 88 -45 133 -6 53 47 77 48 126 7 55 -46 87 -47 141 -1 47 39 72 43 98 17 63 -63 103 -67 163 -16 49 41 73 40 126 -7 19 -16 40 -29 48 -29 29 0 13 25 -38 63 -67 48 -99 48 -152 2 -22 -19 -47 -35 -55 -35 -8 0 -35 16 -59 35 -62 49 -97 46 -165 -17 -28 -26 -46 -22 -91 17 -53 46 -87 46 -148 -1 -51 -40 -69 -39 -114 2 -50 46 -97 44 -153 -6 -43 -39 -77 -39 -120 0 -56 50 -103 52 -153 6 -45 -41 -63 -42 -114 -2 -61 47 -95 47 -148 1 -22 -19 -47 -35 -55 -35 -8 0 -35 16 -59 35 -26 21 -55 35 -71 35 -16 0 -45 -14 -71 -35 -24 -19 -51 -35 -59 -35 -8 0 -33 16 -55 35 -53 47 -87 46 -149 -2 l-47 -36 -34 16 c-19 9 -35 21 -35 25 0 12 -46 32 -73 32 -12 0 -30 -5 -41 -11z"/>
</g>
</svg>
<p>

###  2. Center with flexbox

In this example, the centering is done in the ``parent`` so it affects all children:

- Don't forget to add the ``center`` class to the parent.

```css
.center {
	display: flex;
	align-items: center;
	justify-content: center;
}
```

<p class="codepen" data-height="450" data-default-tab="html,result" data-slug-hash="gOGMPWW" data-editable="true" data-user="skillsboy" style="height: 450px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/skillsboy/pen/gOGMPWW">
  Horizontal and vertical div center with flexbox.</a> by skillsboy (<a href="https://codepen.io/skillsboy">@skillsboy</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<p align="center" style="margin-top: 40px;">
<svg version="1.0" xmlns="http://www.w3.org/2000/svg"
width="250" height="20" viewBox="0 0 250 20" preserveAspectRatio="xMidYMid meet">
<g transform="translate(0.000000,20.000000) scale(0.100000,-0.100000)" fill="currentColor"  stroke="none">
<path d="M156 139 c-10 -6 -27 -20 -38 -31 -10 -10 -31 -23 -45 -29 -19 -7 -23 -13 -15 -21 15 -15 52 -3 92 32 19 16 42 30 52 30 9 0 35 -16 58 -35 53 -44 88 -45 133 -6 53 47 77 48 126 7 60 -51 100 -47 163 16 10 10 27 18 38 18 11 0 28 -8 38 -18 63 -63 103 -67 163 -16 49 41 73 40 126 -7 45 -39 80 -38 133 6 47 39 68 43 96 17 76 -70 132 -70 208 0 28 26 49 22 96 -17 53 -44 88 -45 133 -6 53 47 77 48 126 7 55 -46 87 -47 141 -1 47 39 72 43 98 17 63 -63 103 -67 163 -16 49 41 73 40 126 -7 19 -16 40 -29 48 -29 29 0 13 25 -38 63 -67 48 -99 48 -152 2 -22 -19 -47 -35 -55 -35 -8 0 -35 16 -59 35 -62 49 -97 46 -165 -17 -28 -26 -46 -22 -91 17 -53 46 -87 46 -148 -1 -51 -40 -69 -39 -114 2 -50 46 -97 44 -153 -6 -43 -39 -77 -39 -120 0 -56 50 -103 52 -153 6 -45 -41 -63 -42 -114 -2 -61 47 -95 47 -148 1 -22 -19 -47 -35 -55 -35 -8 0 -35 16 -59 35 -26 21 -55 35 -71 35 -16 0 -45 -14 -71 -35 -24 -19 -51 -35 -59 -35 -8 0 -33 16 -55 35 -53 47 -87 46 -149 -2 l-47 -36 -34 16 c-19 9 -35 21 -35 25 0 12 -46 32 -73 32 -12 0 -30 -5 -41 -11z"/>
</g>
</svg>
<p>

###  3. Center with css grid

This is like flexbox, the centering is done in the ``parent`` so it affects all children:

- Don't forget to add the ``center`` class to the parent.

```css
.center {
	 display: grid;
	 align-content: center;
	 justify-content: center;
}
```

<p class="codepen" data-height="450" data-default-tab="html,result" data-slug-hash="JjrKpqO" data-editable="true" data-user="skillsboy" style="height: 450px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/skillsboy/pen/JjrKpqO">
  Horizontal and vertical div center with css grid.</a> by skillsboy (<a href="https://codepen.io/skillsboy">@skillsboy</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br><p  align="center"  style="font-size: 30px;">Have fun 😄</p>