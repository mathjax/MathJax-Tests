# MathJax Tests
__Tests Repository for MathJax version 3.0 and above.__


## Tests

We use [Jest](https://jestjs.io) as test framework.

### Running Tests

Just go to the root of this repository and run the following two commands:

``` shell
npm install
npm test
```

TeX parser tests in particular are run with the command:

``` shell
npx jest src/parser.test.js
```

To only test a single file run

``` shell
npx jest src/parser.test.js json/FILE.json
```

Tests initially run against `mathjax-full` package. They can be run against your
local repository by rerouting the `js` and `es5` directories.

### Test Format

Tests are provided in a JSON test format.


``` json
{
  "name": NameOfTest,
  "factory": TestFactory,
  "tests": {
    "TEST1": {
    "input": INPUT
    "expected": EXPECTED
    ...rest
    }
    ...more tests
  }
}

```

To add new tests, simply add a new `.json` file in the `json` sub-directory. For
new test classes add a new entry in `src/test-factory.js`.


