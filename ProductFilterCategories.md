
## Product Filter - Categories

This section of the tutorial focuses more on styling the [Product Filter - Categories](https://docs.woocommerce.com/document/woocommerce-product-search/widgets/product-filter-categories/). 

We will be exploring how to change the look and feel of the Product Filter - Categories.

> 
> Though we assume you know your way around with CSS rules. Here's a good resource to help refresh your mind on CSS rules and how to target HTML elements with CSS.
> * [CSS rules reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
> * [How to target HTML with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)



### Customizing Product Filter - Categories with style option set to List

> 

Once the widget or shortcode of **Product Filter - Categories** is placed on your site, you should have the following HTML structure:

``` html
<div id="product-search-filter-category-0" class="product-search-filter-terms ">
    <div class="product-search-filter-terms-heading product-search-filter-category-heading" id="product-search-filter-category-heading-0">Category</div>
    <ul>
        <li> <a href=""> </a> </li>
        <li> <a href=""> </a> </li>
        <li> <a href=""> </a> </li>
        ...
    </ul>
</div>
```
Notes:
> The ID ( `product-search-filter-category-0`) is likely to be different on your setup. Hence, please inspect the element using your browser inspector to identify the ID.


Here's a list of the top customization requests received for Product Filter - Categories:
* Display only child categories
* Change font color of parent categories
* Styling active(selected) term(category)


#### Display only child categories
This is one of our most popular inquiries. If you would love to hide the parent categories and have only the child categories displayed. Please add the CSS snippet below.

_This customization requires you to set the **Expand Child Terms** option to **Expand Child Terms**  in the navigation section of the Product Filter - Categories widgets settings_

This is the appearance of Product Filter - Categories with parent categories visible before we apply our customizations:

![Product Filter - categories Example 1](/hcat-before.jpg)

**ID** and **classes** we are interested in:
```css
#product-search-filter-category-0, .cat-parent, .children
```
These are the CSS rules we apply:


``` css
#product-search-filter-category-0 .cat-parent{
    visibility: hidden;
    margin-top: -30px;
}
#product-search-filter-category-0 .cat-parent .children {
    visibility: initial;
    margin: 0;
}
```
With the above CSS rules applied, here's how the Product Filter - Categories now looks within the context of our demo store with the parent categories removed...

![Product Filter - categories Example 2](/hcat-after.jpg)

#### Change font color of parent categories
In this example, we will be changing the color of the parent categories to blue( #16c0f4 ). 

This is the appearance of Product Filter - Categories with parent categories visible before we apply our customizations:

![Product Filter - categories Example 1](/cpcat-before.jpg)

**ID** and **classes** we are interested in:
```css
    #product-search-filter-category-0, .cat-parent, .children 
```

``` css
#product-search-filter-category-0 .cat-parent a {
    color: #16c0f4;
}
#product-search-filter-category-0 .cat-parent .children a {
    color: #000;
}
```

With the above CSS rules applied, here's the result within the context of our demo store...

![Product Filter - categories Example 1](/cpcat-after.jpg)

#### Styling active(selected) term(category):
In this section we will focus on styling a category(term) which is selected, by setting the selected category's color to blue(#16c0f4).

For instance, we will consider the user has selected the **Women** category from the Product Filter - Categories widget. 

Appearance before we apply our customizations:

![Product Filter - categories Example 1](/scat-before.jpg)

**ID** and **classes** we are interested in:
```css
    #product-search-filter-category-0, .product-search-product_cat-filter-item.current-cat 
```

``` css
.product-search-product_cat-filter-item.current-cat > a {
    color: #16c0f4;
}
```

With the above CSS rules applied, here's the result within the context of our demo store...

![Product Filter - categories Example 1](/scat-after.jpg)

### Customizing Product Filter - Categories with style option set to Dropdown
> 

Once the widget or shortcode of **Product Filter - Categories** is placed on your site and the style option set to **Dropdown**, you should have the following HTML structure:

``` html
<div id="product-search-filter-category-0">
    <div class="product-search-filter-select-product_cat-selectize">
        <div class="selectize-input items"></div>
        <div class="selectize-dropdown multi product-categories">
            <div class="selectize-dropdown-content">
                <div class="option">....</div>
                <div class="option">....</div>
                ...
            </div>
        </div>
    </div>
</div>
```
Notes:
> The ID ( `product-search-filter-category-0`) is likely to be different on your setup. Hence, please inspect the element using your browser inspector to identify the ID.

Examples covered:
* Change the background color of selected items
* Add hover background color to dropdown options


#### Change the background color of selected items 
In this example we'll focus on changing the background color of selected items(categories) to teal and its color to white.

Appearance before we apply our customizations:
![Product Filter - categories Example 2](/dcatselect-before.jpg)

**ID** we are interested in:
```css
    #product-search-filter-category-0
```

``` css
#product-search-filter-category-0 .has-options .item {
    background-color: #16c0f4;
    color: white;
    padding: 4px 5px;
    line-height: initial;
}
```
With the above CSS rules applied, here's the result within the context of our demo store...

![Product Filter - categories Example 1](/dcatselect-after.jpg)


#### Add hover background color to dropdown options
This example demonstrates how you could go about adding a hover background color to the dropdown options.

Appearance before we apply our customizations:
![Product Filter - categories Example 2](/dcathover-before.jpg)

**ID** we are interested in:
```css
    #product-search-filter-category-0
```

``` css
#product-search-filter-category-0  .selectize-dropdown .option:hover {
    background-color: #16c0f4;
    color: #fff;
}
```
With the above CSS rules applied, here's the result within the context of our demo store...

![Product Filter - categories Example 1](/dcathover-after.jpg)


#### Change style of "clear" icon and text when a catgory is selected
In this section we demonstrate how you would go about adding a font color of red to the **Clear** action that is displayed after a user has selected a category

Appearance before we apply our customizations:
![Product Filter - categories Example 2](/dclear-before.jpg)

**ID** and **classes** we are interested inwe are interested in: (In order to style the cancel icon by the Clear label we would also be interested in the psuedo-element ```::before```)
```css
    #product-search-filter-category-0, .nav-back 
```

``` css
/* Styling the icon */
.product-search-filter-terms .nav-back::before{
    color: red;
    padding: 0;
    font-size: 20px;
}
/* Styling the label - Clear */
.product-search-filter-terms .nav-back a{
    color: red;
}
```
With the above CSS rules applied, here's the result within the context of our demo store...

![Product Filter - categories Example 1](/dclear-after.jpg)



### How to apply CSS with WPS inline stylesheet.
The Animated GIF below demonstrates how you would apply your custom styles to your website.

Inorder to access the inline stylesheet, from your admin dashboard you would;
* Navigate to: **WooCommerce -> Settings -> Search -> CSS**
* Make sure the **Use inline styles** option is enabled
* Paste your CSS rules in the **Inline styles** stylesheet provided