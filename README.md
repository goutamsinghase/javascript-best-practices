**JavaScript Programming Best Practices**

This document&#39;s primary motivation is twofold:

1) code consistency and

2) best practices

By maintaining consistency in coding style and conventions, we can ease the burden of legacy code maintenance, and mitigate risk of breakage in the future.

By adhering to best practices, we ensure optimized page loading, performance and maintainable code.Therefore, at Innofied, we follow these guidelines strictly while programming.

## JavaScript Files

a) Use constructor function name as file names, So as per example, file name will be Hero.js

_ **For example:** _

_function Hero() {_

_This.occupation= &#39;Ninja&#39;;_

_}_

b) Choose meaningful file names for your JavaScripts files like the file names should be derived Or chosen by focusing on what the file holds and use camelcase for your file names.

## **Indentation**

a) The unit of indentation is 4 spaces.

b) Use of tabs should be avoided.

c) Use &quot;format&quot; option of your IDE.

## LineLength

a) Avoid line length more than 80 characters.

## **Comments**

a) It is important that comments be kept up-to-date.

b) Make comments meaningful.

## Variable Declarations

a) All variables should be declared before use.

b) The &#39;var&#39; statement should be the first statement in function body.

c) It is preferred that each variable be given its own line &amp; comment.

_For example_:

var currentEntry; // currently selected table entry

var level; // indentation level

var size; // size of table

d) Use of global variables should be minimised.

e) Implied global variables should never be used.

## **Function Declaration**

a) All functions used should be declared before use.

b) There should be no space between the name of the function and the ( (left parenthesis of its parameter list. There should be 1 space between the ) ( right parenthesis) and the [ (left curly brace) that begins the statement body. The right } (right curly brace) is aligned with the line containing the beginning of the declaration of the function.

_For example:_

_function outer(a, b) {_

_var e=c\*d;_

_function inner(a, b) {_

_return (e\*a) + b;_

_}_

_return inner(0, 1);_

_}_

## Names

a) Names should be formed from the 26 upper and lower case letters (A..z, a..z), the 10 digits (0..9), and \_(underber).

b) avoid use of international characters.

c) Do not use $(dollar sign) or \ (backslash).

d) Do not use\_(underbar) as the first character of a name.

## **Use ===** i **nstead of ==**

a) JavaScripts utilizes two different kinds of equality operators: === I _! == and ==_ I _! =It is considered best practice to always use the former set when comparing._

## eval is Evil

_a) The eval function is the most misused feature of javaScript. Avoid it._

_b) eval has aliases. Do not use the &#39;Function&#39; constructor. Do not pass strings to &#39;setTimeout&#39; or &#39;setInterval&#39;. Instead pass a function name._

_For example:_

_ **Bad:** _

_setInterval(&quot;document.getelementbyid(&#39;container&#39;).innerHTML +=_

&#39;_My new number:&#39;+ i, 3000);_

_ **Better:** _

_setinterval(someFunction, 3000)_

## Don&#39;t use short-hand ever

Technically, you can get away with omitting most curly braces and semicolons. Most browsers

will correctly interpret the following:

if(someVariableExists)

x=false

anotherFunctioncall();

One might think that the code above would be equivalent to:

if(someVariableExists) {

x=false;

anotherFunctioncall();

}

Unfortunately, he&#39;d be wrong.In realty, it means:

if(someVariableExists) {

x=false;

}

anotherFunctionCall();

As you&#39;ll notice, the indentation mimics the functionality of the curly brace. Needless to say, this

is a terrible practice that should be avoided at all costs.

## U **tilize JS Lint**

JSLint is a debugger written by Douglas Crockford. Simply paste in your script, and it&#39;ll quickly scan for any noticeable issues and errors in your code.

## **Place scripts at the bottom of your page**

The primary goal is to make the page load as quickly as possible for the user.

## The fastest way to build your string

Don&#39;t always reach for your handy-dandy &quot;for&quot; statement when your need to loop through an array or object. Be creative and find the quickest solution for the job at hand.

_For example:_

var arr = [&#39;item 1&#39;, &#39;item 2&#39;, &#39;item 3&#39;, ....];

var list = &#39;\&lt;ul\&gt;\&lt;li\&gt;&#39; + arr.join(&#39;\&lt;/li\&gt;\&lt;li\&gt;&#39;) + &#39;\&lt;/li\&gt;\&lt;/ul\&gt;&#39;;

## **Don&#39;t use the &#39;with&#39; statement**

At first glance, &quot;with&quot; statements seem like a smart idea. The basic concept is that they can be

Used to provide a shorthand for accessing deeply nested objects.

_For example:_

With ( being.person.man.bodyparts) {

arms=true;

legs=true;

Unfortunately, after some testing, it was found that they &quot;behave very badly when setting new

Members. &quot;Instead you should use var.

_For example:_

_var o = being.person.man.bodyparts;_

_o.arms = true;_

_o.legs = true;_

## Use {} instead of new object()

There are multiple ways to create objects in Javascript. Perhaps the more traditional method is to use the &quot; **new**&quot; constructor.

For example:

var o = new Object();

o.name = &#39;Jeffrey&#39;;

o.lastName = &#39;Way&#39;;

o.someFunction = function(){

console.log(this.name);

}

However, this method receives the &quot;bad practice&quot; stamp without actually being so, Instead, it is recommended that you use the much more robust object literal method.

For example:

var o = {

name: &#39;Jeffrey&#39;,

lastName: &#39;Way&#39;,

someFunction: function(){

console.log(this.name);

}

};

## Use [] instead of new Array()

The same applies for creating an array.

For example:

**Okay:**

var a = new array();

a[0] = &#39;joe&#39;;

a[1] = &#39;plumber&#39;;

**Better** :

var a = [&#39;joe&#39;, &#39;plumber&#39;];

## Long list of variables? Omit the &#39;var&#39; keyword and use commas instead

For example:

**Okay** :

var someItem =&#39;some string&#39;;

var anotherItem = &#39;another string&#39;;

var oneMoreItem = &#39;one more string&#39;;

**Better** :

var someItem = &#39;some string&#39;;

anotherItem = &#39;another string&#39;;

oneMoreItem = &#39;one more string&#39;;

## Always use semicolons

Technically, most browsers will allow you to get away with omitting semicolons.

For example:

var someItem = &#39;some string&#39;;

function doSomething(){

Return &#39;something&#39;;

}

## Remove &#39;language&#39;

Years ago, it wasn&#39;t uncommon to find the &quot;language&quot; attribute within script tags.

For example:

<script type="text/javascript" language="javascript"/> </script>

However, this attribute has long since been deprecated; so leave it out.
