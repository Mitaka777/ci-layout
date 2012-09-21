# [ci-layout](http://roumen.me/projects/ci-layout) library

A layout manager library for CodeIgniter.

## Installation

To install just copy/paste the content of ci-layout in your application folder and

then edit ``application/config/autoload.php`` to autoload this library:

```php
$autoload['libraries'] = array('layout');
```

## Example

```php
public function something()
{
    // layout
    $this->layout->name = 'default';

    // set title, canonical, keywords, description and robots meta tags for this action
    $this->layout->title = 'Your page title';
    $this->layout->canonical = 'http://yoursite.tld';
    $this->layout->keywords = 'yoursite, keywords, goes here';
    $this->layout->description = 'Description of your site.';
    $this->layout->robots = 'all';

    // css assets
    $this->layout->assets('css/style.css');
    $this->layout->assets('css/print.css');

    // js asset to be loaded in the footer (before body close tag)
    $this->layout->assets('js/script1.js', 'footer');
    $this->layout->assets('js/script2.js');

    // js asset to be loaded in the header (before head close tag)
    $this->layout->assets('js/footer.js', 'header');

    // script to be loaded in the header
    $this->layout->scripts($script1, 'header');

    // script to be loaded in the footer
    $this->layout->scripts($script2, 'footer');

    // script to be loaded in the footer in $(document).ready() function
    $this->layout->scripts($script3, 'ready');

    // load a view (params: view, views-data)
    $this->layout->view('site/index', $data);
}
```