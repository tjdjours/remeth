# remeth


remeth() is a Sass mixin that converts pixel values to rem values for whatever property is passed to it in px. 

1. It allows you to work in px and yield rem.
2. It currently yields the px as well as a fallback px for browsers that do not support rem ([currnetly ie8 and below and Opera Mini](http://caniuse.com/#search=rem))

Eg:

```.container {
  @include remeth('padding', 20px 0);
  @include remeth('min-height', 40px);
}
```
Compiles to:

```.container {
  padding: 20px 0;
  padding: 1.25rem 0;
  min-height: 40px;
  min-height: 2.5rem;
}
```

This is a carry-forward fork from https://github.com/bitmanic/rem. It is distinct from the previous in that it strips units before logic tests to mitigate Sass errors and warnings. The mixin named 'rem' was also yielding errors in one Sass environment I was working in, so decided to make it more unique. 
