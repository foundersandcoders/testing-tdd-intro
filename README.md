# Testing & Test-driven Development

## What is testing?

Testing in general is the process of executing your code to check it does what it's supposed to do. It demonstrates that your code meets the design requirements and can also provide a template for writing new code.

We're mostly concerned with automated unit testing for now, which involves writing code that will call your functions and tell you if they return what you expect. The idea is to test as many small "units" of code as you can, which will give you a good idea if the application as a whole is working.

It's very easy to create bugs in code, especially when you're editing an existing code base. A robust suite of automated tests gives you confidence to make changes, knowing that the tests will tell you if you introduce any bugs.

### Unit test example

Here's a slightly contrived example:

```js
function double(num) {
  return num * 2;
}

function testDouble() {
  var actual = double(2);
  var expected = 4;
  if (actual !== expected) {
    console.log(actual + ' should equal ' + expected + '╳');
  } else {
    console.log('Test passed ✔︎');
  }
}
```

We can run `testDouble` to make sure that our `double` function is still returning the right value. Now if someone else needs to make changes to `double` they have an easy way to see if they broke anything.

### Testing frameworks

Testing like the example above won't get you very far, which is why we use frameworks to help us. We'll be using [Tape](https://github.com/substack/tape) on the course.

Frameworks give you "assertions" like `equal`, `deepEqual` and `ok` to check your values. They also let you easily describe what you're testing and what result was expected, which gives you good test outputs that can act as bug reports when something goes wrong.

A good starter template for writing tests with Tape would look something like this:

```js
// Answer these questions for each unit test you write:
test('What component aspect are you testing?', function(assert) {
  const actual = 'What is the actual output?';
  const expected = 'What is the expected output?';

  assert.equal(actual, expected, 'What should the feature do?');
  assert.end();
});
```
