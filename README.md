#### An ESLint [Shareable Config](http://eslint.org/docs/developer-guide/shareable-configs) for [javascript postmodern style](https://github.com/valedaemon/eslint-config-postmodern)

## Install

```bash
npm install eslint-config-postmodern
```

## Usage

Shareable configs are designed to work with the `extends` feature of `.eslintrc` files.
You can learn more about
[Shareable Configs](http://eslint.org/docs/developer-guide/shareable-configs) on the
official ESLint website.

To use the javascript postmodern style shareable config, first run this:

```bash
npm install --save-dev eslint-config-postmodern eslint-plugin-promise eslint-plugin-import eslint-plugin-node
```

Then, add this to your .eslintrc file:

```
{
  "extends": "postmodern"
}
```

You can override settings from the shareable config by adding them directly into your
`.eslintrc` file.

## Rules
So, what exactly does postmodern give you? First and foremost, semicolons are required to enforce readability. Beyond that, below is a visual guide to the rules. Code samples are taken straight from eslint.org.
Second, postmodern follows eslint's **recommended** rules and, as such, those will not be listed below.

##### Arrow spacing
Require a space before/after arrow function's arrow:
```
(a) => {}
```  

##### Brace style
Postmodern follows the *one true brace style* where the opening brace of a block is placed on the same line as its corresponding statement of declaration.
```
if (foo) {
  bar();
} else {
  baz();
}  
```

##### Camelcase
Postmodern follows camelcase (*camelCase*) rather than snake case (*snake_case*) for functions and variables. However, errors are not thrown if an object property is snake case as sometimes that is unavoidable.
```
function myNewFunction() {
  ...
}
const myVariable;
```

##### Comma Dangle
Postmodern disallows comma dangles for arrays, objects, imports, exports, and functions.
```
  const foo = {
    bar: 'baz',
    qux: 'quux' // No comma!
  };
  const arr = ['one', 'two'];  
```

##### Comma spacing
Requires a space after a comma
```
foo(a, b);
```

##### Comma Style
Requies a comma after and on the same line as an array element, or object property.
```
  const obj = {
    a: 1, // Comma is required to be on this line and not the following
    b: 2
  };  
```

##### Curly
Requires curly braces in cases where they can be omitted.
```
  if (foo) {
    foo++;
  }
  // Does not allow for if (foo) foo++;  
```

##### Dot location
Enforced for objects and properties, requires the dot should be on the same line.
```
  const foo = obj.property;
```

##### EOL last
Requires a newline at the end of a file

##### EQEQEQ
Requires === and !== in lieu of == and != to take advantage of type safety.
```
 if (x === 42) { // x == 42 throws an error
   ...
 };  
 if (y !== x) {
   ...
 };  
```

##### Function call spacing
Disallows a space between function identifiers and their invocations.
```
  new Date(); // new Date (); throws an error
```

##### Handle Callback Error
In node.js, a common pattern for dealing with asynchronous behavior is called the callback pattern. This pattern expects an Error object or null as the first argument of the callback.
```
  function loadData(err, data) {
    ...
  }  
```

##### Indent
Requires consistent indentation of code blocks. Postmodern requires two spaces.
```
  if (a) {
    b = c;
    const foo = (d) => {
      e = f;
    };
  }
  
  switch(a) {
    case 1:
      b = c;
      break;
    case 2:
      c = d;
      break;
    default:
      d = e;
      break;
  }            
```

##### Key spacing
Requires a space after a colon.
```
  const obj = {
    foo: 42 // Space required here
  };  
```

### Keyword Spacing
Requires a space before and after syntax keywords such as **as**, **async**, **await**, **break**, **case**, **catch**, **class**, **const**, etc.

Bad formatting:
```
  if(foo) { // Error
    ...
  }else{ // Error
    ...
  }    
```
Correct:
```
  if (foo) {
    ...
  } else {
    ...
  }
  const a = 'b';
  await Promise.all(promises);
  let a = [100, this.foo, this.bar];   
```

##### New Cap
Requires all **new** operators to be called with uppercase-started functions
```
  const friend = new Person();
```

##### New Parens
Disallows the omission of parentheses when invoking a function via the **new** keyword.
```
   const person = new Person(); // Calling new Person results in an error
```

##### No Console
Gives a warning on the use of **console.log**, **console.warn**, **console.error**, etc.

##### Operator Linebreak
When a statement is too long to fit onto a single line, the operator follows on the next line.
```
  const fullHeight = borderTop
    + innerHeight
    + boderBottom;
```

##### Padded blocks
Block statements will never begin or end with a newline.
```
  if (a) {
    b();
  }  
```

##### Quotes
Only single quotes are accepted as valid.

##### Rest spread spacing
Disallows spacing the spread operator and its expression.
```
  let {x, y, ...z} = {x: 1, y: 2, a: 3, b: 4};
```

##### Semi spacing
Disallows spaces before semicolons but enforces them after.
```
  for (let i = 0; i < 10; i++) {
    ...
  }  
```

##### Space before Blocks
Blocks must always have at least one preceding space.
```
  if (a) {
    b();
  }
  
  function a() {
    ...
  }
  
  try {
    ...
  } catch(e) {
    ...
  }        
```

##### Space before Function Paren
Disallows spaces before the parentheses of a function
```
  function withoutSpace(x) { // Cannot use withSpace (a)
    ...
  }  
```

##### Space in Parens
Disallows spaces within parentheses
```
  foo('bar'); \\ Not foo( 'bar' );
  const foo = (1 + 2) * 3; // Not ( 1 + 2 )
```

##### Space infix Ops
Requires spacing around operators
```
  const sum = 1 + 2; // Not 1+2
```

##### Space Unary Ops
Requires spaces for words **new**, **delete**, **typeof**, **void**, **yield**

##### Spaced Comment
`//` must be followed by a space.
```
// See, the comment marker is followed by a space
```

##### Template Curly Spacing
Disallows spaces within `${}`
```
  const template = `Disallow spaces within ${tempVar}`;
```

