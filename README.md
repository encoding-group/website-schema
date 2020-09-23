# Website Schema

## Unified data schema for content

Typically, a websites content can be structured in 5-6 different types of data:
- `site`: General information about the website
- `pageAbstract`: All information needed to render a preview of a single page
- `page`: All information needed to render a full single page view
- `pages`: A list of (abstracted) `page` objects, required to render a list of pages
- `file`: All information to render a file (e.g. image)
- `files`: A list of `file` objects

**site** obejct
```js
const site = {
    title: 'Website title',
    url: 'https://example.com',
    description: 'Website description ...',
    tags: ['keyword 1', 'keyword 2'],
    language: 'en',
    contact: {
        name: 'Person or company Name',
        company: 'Legal Name',
        mail: 'info@example.com',
        tel: '+49 160 123456789',
        street: 'Street Name 1',
        zip: '01234',
        city: 'City',
        country: 'Country',
    },
    links: [
        ['Instagram','https://instagram.com/example'],
        ['Facebook','https://facebook.com/example'],
    ],
    image: 'image-1000px.jpg',
    logo: 'logo.svg'
};
```

**pageAbstract** object
```js
const pageAbstract = {
    title: 'Example Post',
    slug: 'example-post',
    image: file,
    date: '1999-12-31',
    tags: ['keyword 1', 'keyword 2']
};
```

**page** object
```js
const page = { ...pageAbstract,
    images: images,
    pages: pages,
    text: '<p>Page content</p>'
};
```

**pages** array
```js
const pages = [ pageAbstract, pageAbstract, ... ];
```

**file** obejct
```js
const file = {
    name: 'image-1.jpg',
    caption: 'Image description',
    width: 3000,
    height: 2400,
    sizes: [
        {
            src: 'image-1-s.jpg',
            width: 600
        },
        {
            src: 'image-1-m.jpg',
            width: 1200
        },
        {
            src: 'image-1-l.jpg',
            width: 2000
        },
        {
            src: 'image-1-xl.jpg',
            width: 3000
        },
    ]
};
```

**files** array
```js
const files = [ file, file, ... ];
```

These objects can be extended, but the properties above should be included.
If a property value is unknown or empty, do:
```
empty string: ''
empty array: []
empty int: false
empty object: false
```

## GoLive Checklist
1. Check for browser compability
2. Check if HTML `<head>` is valid and complete
3. Add HTML, OpenGraph and JsonLD metadata and validate
4. Add a `robots.txt` and `sitemap.xml` and validate
5. Switch on server side caching
6. Add leverage browser caching to file assets
7. Check browser and server console for unneccessary output and errors
8. Validate Html and CSS
9. Test page speed
10. Submit website url and sitemap to search engines
