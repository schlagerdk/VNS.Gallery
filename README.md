# VNS Gallery

A flexible jQuery image gallery plugin with thumbnails, lightbox, carousel, and grid view.

## Features

- 📱 Fully responsive with customizable breakpoints
- 🎨 Carousel or static grid layout
- 🖼️ Modal lightbox with grid and single image views
- ⌨️ Keyboard navigation support
- 🔄 Loop and step navigation options
- 🎯 Thumbnail and fullsize image support for performance
- ⚙️ Highly customizable with extensive options
- 🎪 Interactive demo builder included

## Installation

### Direct Download

Download the files and include them in your HTML:

```html
<link rel="stylesheet" href="dist/vns-gallery.css">
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="dist/vns-gallery.js"></script>
```

## Basic Usage

### HTML Structure

```html
<div class="gallery">
    <img src="img/thumbs/photo-01.jpg" data-fullsize="img/full/photo-01.jpg" alt="Photo 1">
    <img src="img/thumbs/photo-02.jpg" data-fullsize="img/full/photo-02.jpg" alt="Photo 2">
    <img src="img/thumbs/photo-03.jpg" data-fullsize="img/full/photo-03.jpg" alt="Photo 3">
</div>
```

### Initialize Plugin

```javascript
$('.gallery').vnsGallery();
```

### With Options

```javascript
$('.gallery').vnsGallery({
    columns: 4,
    loop: true,
    showAllButton: true,
    modalColumns: 6
});
```

## Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `useCarousel` | Boolean | `true` | Use carousel navigation (if false, shows static grid) |
| `loop` | Boolean | `false` | Enable looping through images |
| `columns` | Number/null | `null` | Number of columns (null = responsive default) |
| `modalColumns` | Number | `4` | Number of columns in modal grid view |
| `modalWidth` | String | `'80vw'` | Width of modal in single view |
| `showAllButton` | Boolean | `true` | Show "See all" button |
| `showNavigation` | Boolean | `true` | Show prev/next arrows in modal |
| `showCounter` | Boolean | `true` | Show image counter |
| `showCloseButtonGrid` | Boolean | `false` | Show close button in grid view |
| `showCloseButtonSingle` | Boolean | `false` | Show close button in single view |
| `enableKeyboard` | Boolean | `true` | Enable keyboard navigation |
| `maxImages` | Number/null | `null` | Maximum images to show initially |
| `step` | Number/null | `null` | Number of items to step (null = auto) |

### Responsive Option

Define different settings for different screen widths:

```javascript
$('.gallery').vnsGallery({
    responsive: {
        0: { columns: 2 },
        768: { columns: 4 },
        1024: { columns: 6 }
    }
});
```

## Image Attributes

Use `data-fullsize` attribute to specify a larger image for single view:

```html
<img src="thumbnail-small.jpg" data-fullsize="photo-large.jpg" alt="Photo">
```

This improves performance by loading small thumbnails for carousel/grid, then loading full-size only when viewing single image.

## Public Methods

```javascript
var gallery = $('.gallery').vnsGallery();

gallery.open();           // Open gallery (grid view)
gallery.open(2);          // Open specific image (index 2)
gallery.close();          // Close gallery
gallery.next();           // Next image
gallery.prev();           // Previous image
gallery.destroy();        // Destroy instance
gallery.refresh();        // Refresh gallery
```

## Events

```javascript
$('.gallery').on('show', function() {
    console.log('Gallery opening...');
});

$('.gallery').on('changed', function(e, index, image) {
    console.log('Image changed to index:', index);
});
```

Available events: `init`, `show`, `shown`, `close`, `closed`, `change`, `changed`, `next`, `prev`, `nextDone`, `prevDone`

## Demo

Open `demo/index.html` in your browser to see all features and the interactive demo builder.

## Browser Support

- Chrome, Firefox, Safari, Edge (latest versions)
- Mobile browsers
- Requires jQuery 3.x

## License

MIT License

## Author

VNS Gallery Plugin
