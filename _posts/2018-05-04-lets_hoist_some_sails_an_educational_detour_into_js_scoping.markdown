---
layout: post
title:      "'LET's HOIST Some Sails': An Educational Detour into JS Scoping"
date:       2018-05-04 17:48:05 -0400
permalink:  lets_hoist_some_sails_an_educational_detour_into_js_scoping
---


Recently, I was challenged to write a blog post about my understanding of hoisting as it exists within Javascript. This was a great challenge for me, as hoisting and scope is something that I have had some difficulties with, even as I wrap up my jQuery Front-End App project. 

Initially the concept was a little over my head, and seemed like superfluous knowledge, to be frank. I got the jist: declarations go at the top, assignments occur later. But I didn't grasp much past that, and especially struggled with understanding the applicable consequences of the concept. I'm confident to say that after some more in-depth research, I have begun to develop a greater handling of the concept.

As I mentioned, the surface-level aspect about hoisting is that javascript is handling two separate processes: first, the process of handling declarations('var x' as an example), then it handles the actual assignments('x=2'). Moving from there, it's important to therefore realize that 'var x = 2' represents two different things conceptually to javascript, which is what allows for functions to be called before they are declared. 

The important aspect to remember about this is that hoisting only happens within it's scope, which means that this two-step process is completed once for each scope level. 

`var x = 2; 
function() {
var y=3;
}` 

can also be written as 

`var x;
x=2;
function() {
var y; 
y=2
}`  

However, one important concept that I didn't fully comprehend previously was what exactly it meant for 'let' and 'const' to be block-level scoped. I had never really noticed that by assigning 'var' a value outside of a function, then changing that assignment within a block would change the global scope, which is not the case with 'let'. This helped me finally start to understand why 'let' is better to use than 'var'; you have less opportunities to accidentally override the values of variables. Further, this block-level scope can prevent some weird errors from occurring. The following is a sample of code from an article (https://www.digitalocean.com/community/tutorials/understanding-variables-scope-hoisting-in-javascript) that was sent to me that gives a perfect example:

`var x = 100;
function hoist() {
  if (false) {
    var x = 200;
  }
  console.log(x);
}
hoist();`

At first glance, it seems obvious that the function call would result in a console.log of '100'. Afterall, the if loop can't have any effect since its condition is definitively false. However, the output of 'hoist()' would actually be undefined! This is due to the lack of block-level scoping of 'var'; the declaration of x was still hoisted to the top of the function, resulting in 'x' being declared but now existing as undefined within the scope of 'hoist()'. However, simply by using 'let' instead of 'var', this issue can be completely avoided!

