# HVST Framework (CSS/JS)

1. Colors
2. Typography
3. Common Classes and CSS Functions
  * 3.1 Alignment
  * 3.2 Text formatting
  * 3.3 General formatting
  * 3.4 Animations
4. Buttons
5. Forms
6. Components
  * 6.1 Tabs
  * 6.2 Toggle
  * 6.3 Dropdown Menu
  * 6.4 Ticker
  * 6.5 Avatar
  * 6.6 Tooltips
7. Layout
  * 7.1 Columns
  * 7.2 Dashboard
8. JS Plugins
  * Modals - [Magnific Popup Documentation](http://dimsemenov.com/plugins/magnific-popup/documentation.html)
  * Touch - [jQuery Finger Documentation](http://ngryman.sh/jquery.finger/)
  * Form Validation - [Parsley Documentation](http://parsleyjs.org/documentation.html)
  * Slider/Carousel - [OWL Carousel Documentation](http://owlgraphic.com/owlcarousel/)
  * Select Dropdowns - [Chosen Documentation](http://harvesthq.github.io/chosen/)
  * Layouts - [Isotope Documentation](http://isotope.metafizzy.co/)
  * Charts/Graphs - [Highstock Documentation](http://api.highcharts.com/highstock)
  * Tooltips - [tipsy Documentation](http://onehackoranother.com/projects/jquery/tipsy/)
  * Read More - [Readmore.js Documentation](http://jedfoster.com/Readmore.js/)

## 1. Colors
Use these within a class whenever you need a color. For example `color: $black; background: $white;`. If the color is not exact, please use the closest one or assign the issue to Sterling. We really shouldn't be getting too crazy with tons of varying colors all over the site.

* `$black`
* `$white`
* `$lightPurple`
* `$purple`
* `$darkPurple`
* `$lightGray`
* `$gray`
  * For text elements use `.gray-text` `<span class="gray-text">Gray Text</span>`
  * Or use `.inactive` for semantics.
* `$darkGray`
  * For text elements use `.darkgray-text` `<span class="darkgray-text">Dark Gray Text</span>`
* `$blue`
* `$orange`
* `$green`
  * For text elements use `.positive` `<span class="positive">+0.89%</span>`
* `$red`
  * For text elements use `.negative` `<span class="negative">-0.89%</span>`

## 2. Typography
Our global default font-size is 14px, with a line-height of 20px. `<p>` tags receive a margin top and bottom of 5px and 15px respectively. (Fonts are in em's, however these are their approximate pixel sizes)
* `h1` or `.gigantic`: font-size 28px, line-height 21px
* `h2` or `.huge`: font-size 24px, line-height 25.2px
* `h3` or `.bigger`: font-size 18px
* `h4` or `.big`: font-size 16px, line-height 18px
* `.normal`: font-size 14px, line-height 20px
* `small` or `.huge`: font-size 12px, line-height 16.8px
* `.tiny`: font-size 8px, line-height 16.8px
* `strong, b` or `.bold`
* `i, em` or `.italic`

## 3. Common Classes and CSS Functions
* `border-radius` or `.border-radius` defaults to 4px
  * To change this within a class use: `@include border-radius(<any number or percentage>)`
* `box-shadow` defaults to x: 0, y: 2px, blur: 2px, color: black at 45% opacity
  * Use `@include box-shadow`
  * To change `@include box-shadow(0 4px 16px transparentize($black, 0.8))`

### 3.1 Alignment
* Float right `.right`
* Float left `.left`
* Center (When centering an element) `.center`
* Clear `.clear`

### 3.2 Text formatting
* Text flush left `.text-left`
* Text flush right `.text-right`
* Text centered (When centering objects within the element) `.text-center`
* Truncate text `.truncate-text`

### 3.3 General formatting
* Hide an element `.hidden`
* Display a horizontal list `.inline-list`
* Center a basic site building block `.wrapper`
  * This is a responsive element
* Make element the full width of parent container `.full-width`
* Padding top and bottom defaults to 20px `.padding-top-bottom`
* Padding left and right defaults to 20px `.padding-left-right`
* Add purple divider to the top of an element `.border-top-purple`
* Add purple divider to the bottom of an element `.border-bottom-purple`

### 3.4 Animations
* `transition` defaults to `all 0.5s ease`
  * Use `@include transition`
  * To change, use short hand: `@include transition(<property> <duration> <function> <delay>)`
* `animate`
  * Use `@include animate(<name>, <duration>)`
  * Current animations are:
    * `bounce`
    * To add additional animations, please add them to the animations stylesheet

## 4. Buttons
To create a button, just add `.btn` to your element. Preferred elements are `<a>`, `<input type="button" />`, `<button>` or `<input type="submit" />`

To add style to the button, follow the `.btn` class with a theme. Some element types already have defaults. Themes are:
* `.btn.blue` or `<input type="submit" />`
* `.btn.gray` or `<input disabled="disabled" />`
* `.btn.light-gray`
* `.btn.orange`
* `.btn.green`

## 5. Forms
For any questions with form structure visit http://www.w3schools.com/html/html_forms.asp
* For checkboxes or radio buttons wrap the input with a label in a `div.checkbox-wrap` or `div.radio-wrap` respectively.
  * Example: `<div class="checkbox-wrap><input type="checkbox" /><label>Awesome</label></div>`
* To give checkboxes and radio buttons our fancy style, add `.effeckt-ckbox` or `.effeckt-rdio` to the input respectively.

## 6. Components
* Tabs
* Toggle (like Tabs w/o tab container)
* Dropdown Menu
* Ticker

### 6.1 Tabs
This works with the Ruby on Rails tabs_tag helper. Put tabs in an unordered list `<ul><li></li></ul>` with a `.nav-tabs` class. Use with `.inline-list` class to layout nav-tabs next to each other. Add `.active` classes to the nav-tab and tab-pane you want highlighted first.

You can also use the tab style without the tab functionality by placing `data-link="true"` inside the parent `<li></li>`. This will make the link change pages.

If using with `.inline-list`, layout list elements as in the example. This prevents whitespace between each tab.

Example:

    <ul class="nav-tabs inline-list">
        <li class="active"><a href="#tabOne">Tab 1</a></li><li>
            <a href="#tabTwo">Tab 2</a></li><li>
            <a href="#tabThree">Tab 3</a></li>
    </ul>

    <div class="tab-content">
        <div class="tab-pane active" id="tabOne">Tab content 1</div>
        <div class="tab-pane" id="tabTwo">Tab content 2</div>
        <div class="tab-pane" id="tabThree">Tab content 3</div>
    </div>

### 6.2 Toggle
This is similar to a tab except without the tab-pane, and the `.active` class is on the anchor tag.

Example:

    <ul class="toggle-group inline-list">
        <li><a href="#" class="active">Toggle 1</a></li><li>
            <a href="#">Toggle 2</a></li><li>
            <a href="#">Toggle 3</a></li>
    </ul>

### 6.3 Dropdown Menu
Create a dropdown menu by adding `.dropdown-menu` class to an unordered list `<ul><li></li></ul>`.

To break up list items, add an empty list item with the `.divider` class

Example:

    <ul class="dropdown-menu">
        <li><a href="#">Dropdown Menu Item 1</a></li>
        <li><a href="#">Dropdown Menu Item 2</a></li>
        <li class="divider"></li>
        <li><a href="#">Dropdown Menu Item 3</a></li>
    </ul>

### 6.4 Ticker
An example of a basic ticker symbol:

    <div class="ticker-token">
        <a href="/search?query=aapl&amp;type=companies" title="APPLE INC">aapl</a>
        <a href="javascript:void(0);" class="dropdown-toggle" data-toggle="dropdown"><span class="icon-arrow-down"></span></a>
    </div>

An example of a ticker symbol with dropdown menu:

    <div class="ticker-token dropdown">
        <a href="/search?query=aapl&amp;type=companies" title="APPLE INC">aapl</a>
        <a href="javascript:void(0);" class="dropdown-toggle" data-toggle="dropdown"><span class="icon-arrow-down"></span></a>

        <div class="arrow"></div>
        <ul class="dropdown-menu">
            <li class="position-info"><a href="/search?query=aapl&amp;type=companies">aapl</a></li>
            <li><a href="/posts/365/positions/new?type=investment&amp;symbol=aapl" rel="modal">Add to Portfolio</a></li>
            <li><a href="/search?query=aapl&amp;type=companies">Search 'aapl'</a></li>
        </ul>
    </div>

### 6.5 Avatar
Wrap avatars with a `div` and an `.avatar-block` class. This helps make sure images stay correctly formatted, especially when resizing the window.

To add information over the avatar, either place an anchor tag inside the `.avatar-block` or put anything in a div with an `.over` class.

### 6.6 Tooltips
To add a tooltip to an element, just put the message in a `title` attribute, and add the class `.icon-tip`

To add a tooltip with HTML to an element, place the content requiring the tooltip and the HTML tooltip in a parent with the class `html-tip`. Enter the ID of the HTML tooltip as the parents title. Make sure the HTML tooltip is wrapped in a container with this ID, and that it is hidden.

Example:

    <div class="html-tip" title="#html-tooltip">
        I have an HTML tooltip!
        <div id="html-tooltip hidden">
            <img src="example.png" />
            <h1>Example with <strong>HTML</strong></h1>
        </div>
    </div>

## 7. Layout
Every major section that spans across the viewport should be wrapped in a `.wrapper` class. This helps the site remain responsive. `.wrapper` will conform correctly to the viewport.

Use percentages whenever possible to aid in keeping the site responsive as well.

### 7.1 Columns
When using columns, there are 3 different styles. Each involves creating `div` wrappers with `.col`. Then wrapping it in a parent `div` with one of the below classes:

* 2 columns `.two_col`
* 3 columns `.three_col`
* Master-Detail `.master_detail_col` (This is iPad app style)

Example:

    <div class="two_col">
        <div class="col">Column 1</div>
        <div class="col">Column 2</div>
    </div>

For additional structure, you can nest columns.

Example for 4 columns:

    <div class="two_col">
        <div class="col">
        	<div class="two_col">
		        <div class="col">Column 1</div>
		        <div class="col">Column 2</div>
		    </div>
        </div>
        <div class="col">
        	<div class="two_col">
		        <div class="col">Column 3</div>
		        <div class="col">Column 4</div>
		    </div>
        </div>
    </div>

### 7.2 Dashboard
For content that needs to stay below the fixed header, wrap with `.row`

* Cards should be wrapped with `.content-card-container`
* Card Header should be wrapped with `.header`
* Card Footer should be wrapped with `.footer`
