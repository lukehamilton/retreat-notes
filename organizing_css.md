## Overview

### Objective

Understand Front-End Challenges

### Outcomes

A plan for how to address front-end challenges

### Process

1. Dakota & Luke to present CSS challenges, and solutions

2. Group discusses a plan to tackle these and developers OKRs around them

3. Dakota documents our front-end plan in Trello


## Current CSS Challenges
* we don't follow best practices in many places
* no consistent naming convention
* no consistent use of variables
* no use of mixins

## CSS Best Practices

* Use a CSS pre-processor - DONE


# CSS Naming Conventions

## BEM - Block, Element, Modifier

Dakota is already using this in some places.

BEM (Block, Element, Modifier) is a component-based approach to web development. The idea behind it is to divide the user interface into independent blocks. This makes interface development easy and fast even with a complex UI, and it allows reuse of existing code without copying and pasting.

### Block

A functionally independent page component that can be reused. In HTML, blocks are represented by the class attribute.


* The block name describes its purpose ("What is it?" — `menu` or `button`), not its state ("What does it look like?" — `red` or `big`).


**Example**

```
<!-- Correct. The `error` block is semantically meaningful -->
<div class="error"></div>

<!-- Incorrect. It describes the appearance -->
<div class="red-text"></div>
```

### Element

A composite part of a block that can't be used separately from it.

* The element name describes its purpose ("What is this?" — `item`, `text`, etc.), not its state ("What type, or what does it look like?" — `red`, `big`, etc.).
* The structure of an element's full name is `block-name__element-name`. The element name is separated from the block name with a double underscore (`__`).

**Example**

```
<!-- `search-form` block -->
<form class="search-form">
    <!-- `input` element in the `search-form` block -->
    <input class="search-form__input">

    <!-- `button` element in the `search-form` block -->
    <button class="search-form__button">Search</button>
</form>
```

### Should I create a block or an element?

If a section of code might be reused and it doesn't depend on other page components being implemented, you should create a block.

If the section of code can't be used separately without the parent entity (the block), an element is usually created.

### Modifier

An entity that defines the appearance, state, or behavior of a block or element.

* The modifier name describes its appearance ("What size?" or "Which theme?" and so on — `size_s` or `theme_islands`), its state ("How is it different from the others?" — `disabled`, `focused`, etc.) and its behavior ("How does it behave?" or "How does it respond to the user?" — such as `directions_left-top`).

* The modifier name is separated from the block or element name by a single underscore (`_`).

### Types of modifiers

#### Boolean

* Used when only the presence or absence of the modifier is important, and its value is irrelevant. For example, `disabled`. If a Boolean modifier is present, its value is assumed to be `true`.

* The structure of the modifier's full name follows the pattern:
	* `block-name_modifier-name`
	* `block-name__element-name_modifier-name`

**Example**

```
<!-- The `search-form` block has the `focused` Boolean modifier -->
<form class="search-form search-form_focused">
    <input class="search-form__input">

    <!-- The `button` element has the `disabled` Boolean modifier -->
    <button class="search-form__button search-form__button_disabled">Search</button>
</form>
```

#### Key-value

Used when the modifier value is important. For example, "a menu with the islands design theme": `menu_theme_islands`.

* The structure of the modifier's full name follows the pattern:

	* `block-name_modifier-name_modifier-value`
	* `block-name__element-name_modifier-name_modifier-value`

**Example**

```
<!-- The `search-form` block has the `theme` modifier with the value `islands` -->
<form class="search-form search-form_theme_islands">
    <input class="search-form__input">

    <!-- The `button` element has the `size` modifier with the value `m` -->
    <button class="search-form__button search-form__button_size_m">Search</button>
</form>

<!-- You can't use two identical modifiers with different values simultaneously -->
<form class="search-form
             search-form_theme_islands
             search-form_theme_lite">

    <input class="search-form__input">

    <button class="search-form__button
                   search-form__button_size_s
                   search-form__button_size_m">
        Search
    </button>
</form>
```


### Reference

<https://en.bem.info/methodology/quick-start/>

<https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/>

## SMACCS - Scalable  and Modular Architecture for CSS

Another alternative.

### Reference

<https://smacss.com/>

## CSS Style Guide

Even though we already have a basic style guide, I thought it would be beneficial to go over the basics to ensure we are all on the same page.

Additionally, we can create a process moving forward that we can all follow.

### What is a style guide?

A style guide is a living document of code, which details all the various elements and coded modules of your site or application.

It documents the visual language, such as header styles and color palettes, used to create the site

### Why should we use a style guide?

#### Faster development

Anyone joining an ongoing project can refer to the guide for the exact styles to use.

#### Standardize the CSS

Designers and developers can quickly see if new designs deviate from established standards, and decide as a team if it’s worth expanding the codebase or if something already written is easily extended

When you have no guide duplicated styles end up being written resulting in bloated CSS.

#### Design consistency

One place to reference the site’s components and ensure a cohesive look and feel throughout.

### How do we start?

#### Document the basics

Start your guide with some of your site’s foundations.

A foundational element may include the color palette, your grid layout system, or the basic type styles for headers and body text.

Whatever you feel are the very basic elements to create a page.

Create an HTML document with the markup, linking to the application CSS, so any CSS changes would be automatically reflected in the style guide.

#### Add Patterns

A pattern is any self-contained set of markup and styles to make some of your site’s basic objects, like a call-out box used repeatedly, buttons, or the way you lay out a list of links horizontally.

Keep going through your site and add in patterns as you see them; you may use particular layouts over and over, or a media-object pattern, or a vertical list pattern.

#### Document Interactivity

If possible, add the bits of interactivity that your site uses, such as dropdowns, modals, or tooltips, which are small hovers with helpful text that gives the user more information.

This way we are documenting the animations as well as the static versions of components.

### Reference

[SASS Website Styleguide](http://sass-lang.com/styleguide)

[Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css)

[More Examples](https://css-tricks.com/css-style-guides/)

<http://styleguides.io>
