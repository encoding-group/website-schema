# Website Schema

## Unified data schema for content

Typically, a websites content can be structured in 5 different types of data:
- `site`: General information about the website
- `pageAbstract`: All information needed to render a preview of a single page
- `page`: All information needed to render a full single page view
- `file`: All information to render a file (e.g. image)
- `pages`: A list of (abstracted) page objects, required to render a list of pages
- `files`: A list of `file` objects

**site obejct**
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
        ['Instagram','https://instagram/example'],
        ['Facebook','https://facebook.com/example'],
    ],
    image: 'image-1000px.jpg',
    logo: 'logo.svg'
};
```

**pageAbstract object**
```js
const pageAbstract = {
    title: 'Example Post',
    slug: 'example-post',
    image: file,
    date: '1999-12-31',
    tags: ['keyword 1', 'keyword 2'],
};
```

**page object**
```js
const page = { ...pageAbstract,
    images: images,
    pages: pages,
    text: '<p>Page content</p>'
};
```

**file obejct**
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

**pages array**
```js
const pages = [ pageAbstract, pageAbstract, ... ];
```

**files array**
```js
const files = [ file, file, ... ];
```

These objects can be extended, but the properties above should be included.
If a property value is unknown or empty, do:
```
empty string: ''
empty array: []
unkown int: false
no given object: false
```

## GoLive Checklist
