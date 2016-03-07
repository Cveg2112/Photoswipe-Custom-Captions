

== Photoswipe custom caption ==

A caption that moves and resizes accoeding to image width and height.


== How me add? ==

First off, you'll need the file [which can be found]
'''Its probably best not to copy script from this page, the formatting for the wiki is terrible and you may end up missing out bits.'''

You'll need to include the links for the photoswipe JS / CSS:

```html

<!-- put in header -->
<link rel="stylesheet" href="//photoswipe.s3.amazonaws.com/pswp/dist/photoswipe.css">
<link rel="stylesheet" href="//photoswipe.s3.amazonaws.com/pswp/dist/default-skin/default-skin.css">
<!-- end header -->

<!-- put in footer -->
<script src="//photoswipe.s3-eu-west-1.amazonaws.com/pswp/dist/photoswipe.min.js"></script>
<script src="//photoswipe.s3-eu-west-1.amazonaws.com/pswp/dist/photoswipe-ui-default.min.js"></script>
<!-- end footer -->

```

Then you'll need to add the generic markup for photoswipe:

```html
<!-- Root element of PhotoSwipe. Must have class pswp. -->
<div class="pswp" tabindex="-1" role="dialog" aria-hidden="true">

    <!-- Background of PhotoSwipe. 
         It's a separate element, as animating opacity is faster than rgba(). -->
    <div class="pswp__bg"></div>

    <!-- Slides wrapper with overflow:hidden. -->
    <div class="pswp__scroll-wrap">

        <!-- Container that holds slides. PhotoSwipe keeps only 3 slides in DOM to save memory. -->
        <div class="pswp__container">
            <!-- don't modify these 3 pswp__item elements, data is added later on -->
            <div class="pswp__item"></div>
            <div class="pswp__item"></div>
            <div class="pswp__item"></div>
        </div>

        <!-- Default (PhotoSwipeUI_Default) interface on top of sliding area. Can be changed. -->
        <div class="pswp__ui pswp__ui--hidden">

            <div class="pswp__top-bar">

                <!--  Controls are self-explanatory. Order can be changed. -->

                <div class="pswp__counter"></div>

                <button class="pswp__button pswp__button--close" title="Close (Esc)"></button>

                <button class="pswp__button pswp__button--share" title="Share"></button>

                <button class="pswp__button pswp__button--fs" title="Toggle fullscreen"></button>

                <button class="pswp__button pswp__button--zoom" title="Zoom in/out"></button>

                <!-- Preloader demo http://codepen.io/dimsemenov/pen/yyBWoR -->
                <!-- element will get class pswp__preloader--active when preloader is running -->
                <div class="pswp__preloader">
                    <div class="pswp__preloader__icn">
                      <div class="pswp__preloader__cut">
                        <div class="pswp__preloader__donut"></div>
                      </div>
                    </div>
                </div>
            </div>

            <div class="pswp__share-modal pswp__share-modal--hidden pswp__single-tap">
                <div class="pswp__share-tooltip"></div> 
            </div>

            <button class="pswp__button pswp__button--arrow--left" title="Previous (arrow left)">
            </button>

            <button class="pswp__button pswp__button--arrow--right" title="Next (arrow right)">
            </button>

            <div class="pswp__caption">
                <div class="pswp__caption__center"></div>
            </div>

          </div>

        </div>

</div>
```


Next step is to add the script. Make sure that this is added after the call to the '''photoswipe.min.js''' etc. Either add it to '''main.js''' or make a new file which you can load conditionally (something like '''floor-plan-pswp.js''' or whatever tickles your pickle).


And then you'll need something like this for the HTML:

'''Data size is needed! You can also add other data attribute tags if you need extra stuff'''

```html

<div class="gallery-album">
    <a href="http://www.placehold.it/800x600/22313F/C5EFF7" data-size="800x600" data-title="Test image 1" data-description="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tenetur, expedita." data-booking="https://secure3.hilton.com">
        <img src="http://www.placehold.it/200x200/22313F/C5EFF7" alt="" />
    </a>
</div>

```


And here be the generic CSS, customise as needed:

```css
    .pswp__caption { position:absolute; opacity: 1; transition:all .15s ease-in-out; }
    .pswp__caption.active { opacity: 0; }
    .pswp__caption__center { transition:all .15s ease-in-out; }
    .caption-text-section { width: 70%; display: inline-block; vertical-align: middle; transition:all .2s ease-in-out; }
    .caption-text-section .caption-title, .caption-text-section .caption-copy { display: inline-block; width: 100%; }
    .caption-text-section .caption-title { font-size: 1.5em; color:#3a9fd2; }
    .caption-text-section .caption-copy { color: #fff; }
    .caption-book-section { width: 30%; display: inline-block; text-align: center; vertical-align: middle; transition:all .2s ease-in-out; }
    .caption-book-section .caption.button { vertical-align: middle; display:inline-block; text-decoration:none; text-transform: uppercase; font-size: 1.2em; padding: .7em .85em; background-color:#3a9fd2; color:#fff; }

    .pswp__caption__center { width: 100%; max-width: 1920px; padding:1em; }
    .pswp__caption__center * { box-sizing:border-box; font-family: Arial, sans-serif; }
```


== Notes ==

If you need to add additional fields to the caption, you can do so by adding extra '''"data-[name]"''' attributes to the '''<a>''' tag. Then edit the script & HTML template to inlclude this. For example, if you needed to add an extra button link for, say, Gift Vouchers - you can do it like so:

```javascript

//CUSTOM VARS
var capDesc = $link.data('description');
var capBook = $link.data('booking');

// oor new variable

var capGiftCTA = $link.data('gift-voucher');

// end

var item = {
    src: link.href,
    msrc: link.children[0].getAttribute('src'),
    w: parseInt(size[0], 10),
    h: parseInt(size[1], 10),
    title: "<a class='caption button' href=" + capGiftCTA + ">Buy Gift Voucher</a>",
    el: link
}

```



== Description ==



== Installation ==



== Extra ==

**  **


```php


```


```javascript

jQuery(document).ready(function($){
    $('.color-1').wpColorPicker();
    $('.color-2').wpColorPicker();
    $('.color-3').wpColorPicker();
});

```

```php



```