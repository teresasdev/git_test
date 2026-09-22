# HTML & CSS

HTML structures content, CSS styles it — together they're the baseline of every web page. This sheet covers the syntax you look up constantly: tags, selectors, box model, layout systems, and the responsive/variable tricks that come up once you're past the basics.

## DOCUMENT SETUP

the skeleton every page starts from

\<!DOCTYPE html>

declare HTML5, must be first line

\<html lang="en">

root element, set page language

\<meta charset="UTF-8">

set character encoding

\<meta name="viewport" content="width=device-width, initial-scale=1">

enable responsive scaling on mobile

\<title>...\</title>

set browser tab / bookmark title

\<link rel="stylesheet" href="\[file\].css">

attach external stylesheet, goes in \<head>

\<script src="\[file\].js" defer>\</script>

attach external script, defer runs after parsing

\<!-- comment -->

HTML comment, not rendered

## TEXT & CONTENT

inline and block elements for content

\<h1>–\<h6>

headings, one \<h1> per page ideally

\<p>

paragraph block

\<a href="\[url\]">

hyperlink, add target="\_blank" to open new tab

\<img src="\[file\]" alt="\[text\]">

image, alt required for accessibility

\<ul>/\<ol>/\<li>

unordered/ordered list and list item

\<strong> / \<em>

bold with semantic importance / italic with emphasis

\<br>

line break, self-closing

\<span>

generic inline container for styling/scripting hooks

\<div>

generic block container

## SEMANTIC LAYOUT

tags that describe page regions, not just divs

\<header>

introductory content or nav for a page/section

\<nav>

navigation links block

\<main>

primary content, one per page

\<section>

thematic grouping of content

\<article>

self-contained, independently distributable content

\<aside>

tangential content, sidebars

\<footer>

closing content for page/section

\<figure>/\<figcaption>

media block with caption

## SELECTORS

targeting elements in CSS

tag { }

select all elements of that tag

.class { }

select by class attribute

#id { }

select by unique id

a, b { }

select both a and b

a b { }

select b that is any descendant of a

a > b { }

select b that is a direct child of a

a + b { }

select b immediately following a (sibling)

	a \~ b { }

	select all b siblings after a

	\[attr="val"\] { }

	select by attribute value

	a:hover / :focus / :active

	select on interaction state

	a:nth-child(\[n\])

	select nth child, accepts odd/even/formula

	a::before / ::after

	insert generated content, needs content: ""

## BOX MODEL

	sizing and spacing every element

	box-sizing: border-box;

	include padding/border in declared width/height

	width / height: \[val\];

	set element dimensions

	margin: \[val\];

	space outside the border, shorthand top/right/bottom/left

	padding: \[val\];

	space inside the border, same shorthand order

	border: \[width\] \[style\] \[color\];

	draw a border around the element

	border-radius: \[val\];

	round the corners

	display: block / inline / inline-block / none;

	set the box's rendering flow

	overflow: hidden / scroll / auto;

	control content that exceeds the box

	box-shadow: \[x\] \[y\] \[blur\] \[color\];

	drop shadow around the box

## TYPOGRAPHY & COLOR

	text appearance and fills

	font-family: \[name\], sans-serif;

	set typeface, always include a fallback

	font-size: \[val\];

	set text size, prefer rem for scalability

	font-weight: 400 / 700 / bold;

	set text boldness

	line-height: \[val\];

	set spacing between lines

	text-align: left / center / right;

	horizontal text alignment

	color: \[val\];

	set text color

	background-color: \[val\];

	set element fill color

	letter-spacing: \[val\];

	adjust space between characters

	text-decoration: none / underline;

	toggle underline/strikethrough

## FLEXBOX

	one-dimensional layout, row or column

	display: flex;

	turn container into a flex container

	flex-direction: row / column;

	set main axis direction

	justify-content: center / space-between / space-around;

	align items along main axis

	align-items: center / flex-start / stretch;

	align items along cross axis

	flex-wrap: wrap;

	allow items to wrap to new lines

	gap: \[val\];

	set spacing between flex/grid items

	flex: \[grow\] \[shrink\] \[basis\];

	set how a child grows/shrinks within remaining space

	align-self: \[val\];

	override align-items for one child

## GRID

	two-dimensional layout, rows and columns

	display: grid;

	turn container into a grid container

	grid-template-columns: \[val\] \[val\];

define column sizes, e.g. 1fr 2fr or repeat(3, 1fr)

	grid-template-rows: \[val\];

	define row sizes

	grid-column: \[start\] / \[end\];

	place item spanning specific columns

	grid-row: \[start\] / \[end\];

	place item spanning specific rows

	grid-template-areas: "\[name\]";

	name regions for readable placement

	place-items: center;

	shorthand for align-items + justify-items

	grid-auto-flow: row / column;

	set auto-placement direction for unplaced items

## POSITIONING

	taking elements out of normal flow

	position: relative;

	offset from normal position, keeps space in flow

	position: absolute;

	positioned relative to nearest positioned ancestor

	position: fixed;

	positioned relative to the viewport, stays on scroll

	position: sticky;

	relative until scroll threshold, then fixed

	top / right / bottom / left: \[val\];

	set offset for a positioned element

	z-index: \[num\];

	set stack order for overlapping elements

## RESPONSIVE DESIGN

	adapting layout to screen size

	@media (max-width: \[val\]) { }

	apply rules below a breakpoint

	@media (min-width: \[val\]) { }

	apply rules above a breakpoint

	@media (prefers-color-scheme: dark) { }

	apply rules when user's OS is in dark mode

	width: \[val\]%;

	relative sizing to parent

	max-width: 100%;

	prevent element from overflowing container

	vw / vh

	units relative to viewport width/height

	rem / em

	units relative to root font-size / parent font-size

	clamp(\[min\], \[preferred\], \[max\]);

	fluid value bounded by a min and max

## FORMS

	collecting user input

	\<form action="\[url\]" method="post">

	wrap inputs, define submission target/method

	\<input type="text/email/password/checkbox">

	single-line input, type controls behavior

	\<label for="\[id\]">

	associate text with an input by matching id

	\<textarea>

	multi-line text input

	\<select>/\<option>

	dropdown menu and its choices

	\<button type="submit">

	submit the form

	required / placeholder="\[text\]"

	input attributes for validation/hint text

## TRANSITIONS & TRANSFORMS

	motion and shape changes

	transition: \[prop\] \[duration\] \[easing\];

	animate a property change smoothly

	transform: translate(\[x\],\[y\]);

	move element without affecting layout flow

	transform: scale(\[val\]);

	resize element visually

	transform: rotate(\[deg\]);

	rotate element

	@keyframes \[name\] { }

	define multi-step animation sequence

	animation: \[name\] \[duration\] infinite;

	apply a keyframe animation to an element

## VARIABLES, SPECIFICITY & EDGE CASES

	config tricks and gotchas that come up eventually

	--name: \[val\]; / var(--name)

	define and consume a custom property (CSS variable), inherits like normal properties

	!important

	override normal cascade, avoid except as a last resort

	\* { }

	universal selector, matches every element — used for resets

	:root { }

	selects the document root, typical place for global variables

	:not(\[selector\])

	select elements that don't match the given selector

	margin: 0 auto;

	horizontally center a block element with a fixed width

	**Specificity gotcha:** inline styles beat IDs beat classes/attributes/pseudo-classes beat tag selectors — a single `#id` selector will silently out-rank a dozen `.class` rules. When a style "isn't applying," check specificity before assuming a typo.

	Reference sheet — HTML5 & CSS3 syntax recall
