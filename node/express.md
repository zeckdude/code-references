## Express

#### Handle an HTTP request
##### [app.get](https://expressjs.com/en/api.html#req.query)
```js
// Define data that can be sent back in response. This would usually be stored in a database.
const courses = [
  { id: 1, name: 'Learn skiing' },
  { id: 2, name: 'Learn chess' },
  { id: 3, name: 'Learn programming' }
];

// GET http://mysite.com/api/courses
// Return all courses
app.get('/api/courses', (req, res) => {
  res.send(courses);
});

// GET http://mysite.com/api/courses/2
// Return a single course
app.get('/api/courses/:id', (req, res) => {
  const course = courses.find(course => course.id === Number(req.params.id));
  if (!course) {
    res.status(404).send('The course with the given ID was not found');
  }
  res.send(course);
});
```

<br>

#### Get the request parameters
##### [req.params](https://expressjs.com/en/api.html#req.params)
```js
// http://mysite.com/api/courses/2018/12
app.get('/api/courses/:year/:month', (req, res) => {
  const year = req.params.year; // 2018
  const month = req.params.month; // 12
})
```

<br>

#### Get the request query string properties
##### [req.query](https://expressjs.com/en/api.html#req.query)
```js
// http://mysite.com/api/courses?name=learn+skiing&couponCode=12345
app.get('/api/courses', (req, res) => {
  const name = req.query.name; // learn skiing
  const couponCode = req.query.couponCode; // 12345
})
```

<br>
