#  Naming conventions

* All names should be chosen to be descriptive (is possible and you find
a matching name)
* Types (classes!) should use camel case starting with upper case:
```
MyFunClass
```
* Variable should use camel case starting with lower case:
```
myFunVariable
```

* Constants should be upper case:
```
const float PI=3.14;
#define PI_DEFINE 3.14
```

* Depending on their usage variables should have a prefix:
 * g - for global Variables - gSettings
 * m - for members of a class - mMyFunMember

* Namespaces should be lowercase like
```
ogon::sessionmanager::call
```
this has the advantage that you immediately see what a class and what a
namespace is e.g:
```
ogon::sessionmanager::call::CallFactory
```

* function names should be camel case and start with a lower case later:
```
processThisCrap();
```
 * function name should be verbs
 * if the name of the object can be implied it needs to be left out
```
message.process() //instead of message.processMessage()
````

 * boolean methods should have an is or can prefix
```
isEnabled();
isRunning();
canConnect();
canRun();
```

* One class one file - always put one class in one file where the
filename is called after the class - Note: This is meant for public
(exposed) classes. For private classes it's up to the author and
perfectly fine to have multiple classes in one header (to save compile
time) or cpp file.

# Layout and style

* If working with other projects keep the coding style of that project
(e.g for FreeRDP, wayland, xorg, ..)

* Tab is used for indentation. One level is one tab space.

* Braces should be opened on the same line as the statement or function
```
int foo() {
...
}
```
Only exception is for an opening brace after a line break:
```c
if (!someFunctionCalledWithParametersThatRequireLineBreak(
    parameterOne, parameterTwo, parameterThree. parameterFour, 
    parameterFive, parameterSix, parameterSeven)
{
    fprintf(stderr, "%s failed to whatever bla bla bla\n", __FUNCTION__);
    rebootMainframe(true);
    return false;
}
```

* if (else) statements should always have a {} even if it's only one
command. Example:
```
// GOOD syntax
if (command.isAvailable()) {
    command.run();
} else if (command.canNotify()) {
    command.notify();
} else {
    command.configure();
}
```

* Comparisons should be clear but it is up to the author what type of comparison
is used (so it's optional if one uses == or !).

* The asterisk in pointer/reference definitions should be close to the variable
```
// BAD
char* hugo;
// good
char *hugo;
```

* *endifs* should always come with a comment that refers to where it
belongs to
```
#ifndef CALL_H_
....
...
#endif // CALL_H_
```
most IDE Editors support collapsing defines very well or at all...
Note: defines starting with __ are usually "reserved" for the compiler.

* remove trailing unnecessary wide spaces at the end of a line
```
// wrong
xxx;' '\n
// right
xxx;\n
```
or on empty lines
```
// wrong
' '\n
// right
''\n
```
git usually shows stuff like this in red - we can also add a pre-commit
hook that doesn't allow commit if there is a problem like this.

* use spacing in function calls (one space after an ,)
```
// BAD
doCall(arg1,arg2,arg3);
// GOOD
doCall(arg1, arg2, arg3) 
```
* Use spaces for arithmetical expressions
```
ptr+1 // BAD
ptr + 1 // GOOD
```
This rule can be relaxed for obvious expressions to have a compact form.

* **Try** to keep a 80 character limit as good as possible (limit should be measured with a tab stop of 4).

* Use a single indentation for all namespaces 
```
// Don't
namespace n1 {
    namespace n2 {
        namespace n3 {
            ... finally the code
        }
    }
} 
// DO
namespace n1 {
namespace n2 {
namespace n3 {
  code
  code
  code
} // namespace n3
} // namespace n2
} // namespace n1 
```
* For namespace the following alternative syntax is also permitted. But the above one, single indentation, is the preferred one.
```
namespace n1 { namespace n2 { namespace n3 {
} } }
```

* use pre-defined licensing headers where possible (that the files look alike)

* Commenting function,methods,classes is optional expect for public interfaces (API). For commenting doxygen style comments should be used.

# Guidelines

* do early return when possible Examples 
```
// BAD!
if (cond1) {
     if (cond2) {
         ....
         return  v1
     } else
         return v2
} else {
     return v3;
} 

// GOOD
if (!cond1)
    return v3;

if (!cond2)
    return v2;
...
return v1; 
```

* **Don't enforce your style** - For situation where the defined coding style is optional, isn't specific enough or leaves room for interpretation leave the style the original author has chosen. This should be done because:
  * Non functional (just reformatting) in commits enlarges the change set and makes review more time consuming
  * Might be frustrating for the original author

* **Be gentle when reviewing code** - In case you see _only_ coding style violations it might be better if you embrace the opportunity to fix the the complete file with a non-logic changes pull request after the proposed changes got merged. On the other hand if you detect other errors or issues during the review you should always let the author know that he should also fix the coding style issues when fixing the issues.
