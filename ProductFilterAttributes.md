
## Product Filter - Attributes

This section of the tutorial focuses more on styling the [Product Filter - Attributes](https://docs.woocommerce.com/document/woocommerce-product-search/widgets/product-filter-attributes/). 

We will be exploring how to change the look and feel of the Product Filter - Attributes.
> 
> Though we assume you know your way around with CSS rules. Here's a good resource to help refresh your mind on CSS rules and how to target HTML elements with CSS.
> * [CSS rules reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
> * [How to target HTML with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)



### Customizing Product Filter - Attributes with style option set to List
**Atrribute: Product Color**

Once the widget or shortcode of **Product Filter - Attributes** is placed on your site, you should have the following HTML structure:

``` html
<div class="widget widget_woocommerce_product_search_filter_attribute_widget">
    <div class="product-search-filter-terms-heading product-search-filter-attribute-heading" id="product-search-filter-attribute-heading-0">Color</div>
    <ul class="product-attribute product-search-filter-items style-inline">
        <li class="product-search-attribute-filter-item"> <a href=""> <img src="..."/> </a> </li>
        <li class="product-search-attribute-filter-item"> <a href=""> <img src="..."/> </a> </li>
        <li class="product-search-attribute-filter-item"> <a href=""> <img src="..."/> </a> </li>
        ...
    </ul>
</div>
```

One top customization requests received for Product Filter - Attributes is the ability to modify the style of the selected color attribute.

#### Style selected color term.
In this example we'll be styling the color filter and making it distinctive as you select a color term. 

For instance, assume we wish you filter all yellow products and we would want to blur out the selected color so it stands out from the rest. 

![Product Filter - categories Example 1](/afcolor-before.jpg)

**Classes** we are interested in:
```css
.product-search-attribute-filter-item, .current-attribute
```
These are the CSS rules we apply:


``` css
/* Style for currently selected attribute */
.product-search-attribute-filter-item.current-attribute img {
	filter: blur(0.15rem);
	border-color: #16c0f4;
}
/* Style to keep all the other unselected attribute terms sharp and NOT blurred */
.product-search-attribute-filter-item img {
    filter: blur(0);
}
/* Changing the color of the circular indicator which appears on selected attribute terms*/
.product-search-attribute-filter-item.current-attribute > a::after{
	color: #16c0f4 !important;
}
```
With the above CSS rules applied and two colors selected(yellow and navy blue), here's how the Product Filter - Attribute looks within the context of our demo store...

![Product Filter - categories Example 2](/afcolor-after.jpg)

### How to apply CSS with WPS inline stylesheet.
The Animated GIF below demonstrates how you would apply your custom styles to your website.

Inorder to access the inline stylesheet, from your admin dashboard you would;
* Navigate to: **WooCommerce -> Settings -> Search -> CSS**
* Make sure the **Use inline styles** option is enabled
* Paste your CSS rules in the **Inline styles** stylesheet provided