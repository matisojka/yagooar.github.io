---
layout: post
title: "What is a compiler?"
date: 2014-04-13 22:43:06 +0200
comments: true
categories: compilers
published: false
---

{% blockquote John Backus, Creator of Fortran %}
  Much of my work has come from being lazy.
{% endblockquote %}

### A compiler is a translator.
Simple, huh? Indeed, the concept behind a compiler is pretty straight forward.
We have a program written in one language, and ask our hero - The Compiler -
to translate it into another language.

But when it comes to the very process of translating, things get a little bit
involved. A compiler takes care of a lot of different processes that put
together allow to create a new version of a program. The most common use case
is translating a high-level programming language into a low-level one
(hint: assembly). Sometimes the translation is done straight into machine or
byte code.

### Why do we even need code compilation?
In order to answer that question, we have to go back in history. Back in the
50s, programming was quite different than now. Resources were limited and
 software costs passed those of hardware. Scientists and engineers began to
worry about reducing programmers' productivity in order to cut those huge costs.

{% pullquote %}
At this point, the name of John Backus became popular because he was the creator
of the first high-level programming language for an IBM computer, called
"Speedcoding". While the language itself improved programmers' productivity,
{" translating the source code "on the fly" came at a huge cost of memory and
execution speed "}. With this approach, Backus created an interpreter, which I am
going to cover in another article.
{% endpullquote %}

Soon enough, Backus realized that what would greatly improve speed of execution
and reduce memory consumption would be a program that would _translate_ a
a complete program written in a high-level language into machine code, and than
execute the translated program. This is how Fortran and its compiler were
created.

What's interesting is, that even today, programming languages that are compiled
run faster and consume less memory than the interpreted ones, so it still holds
true after 60 years of computer science.

### The benefits of compilers are immense
Compilers not only allow to program in a more user-friendly language, but also
allow to abstract machine differences. We write the code once, and compilers
translate our code into different machine languages and dialects.

But after finding out all those benefits, we still don't actually know how
compilers do their job. Let's change that.

### The compilation process
Take a look at the following graph:

{% img /images/posts/compiler.svg %}

What we see here is that first of all, the compiler takes care of the
translation of the source code into a target code. After that, we just take the
_target code_, also called _target program_, and run it by providing it some
data. In this scenario, the compiler's work actually finishes after the first
step. So let's try to find out how this _Compiler_ box actually works.

### How compilation works
Explaining the whole process of compilation is definitely too much for one
single blog post, so let's just get a quick overview of the different steps:

* __Lexical Analysis__: the source code is read and converted into meaningful
units, called _lexemes_. Those are then converted into _tokens_.
* __Syntax Analysis__ or __Parsing__: the tokens are parsed into an intermediate
representation, called _syntax tree_.
* __Semantic Analysis__: The _syntax tree_ is used to check the semantic
consistency with the language grammar.
* __Intermediate Code Generation__: the compiler creates a low-level
representation of the program. It is often built for an abstract machine,
but can easily be translated into real machine code.
* __Code Optimization__: optimization rules are applied to the intermediate
code, in order to increase speed of execution or minimize memory or resource
consumption. This is one of the most complex and unique parts of the
compilation process.
* __Code Generation__: the intermediate, optimized code is finally translated
into the target language.

### Summary

We have seen that a compiler is actually a translator, which makes programmers
more productive and happy and the programs more universal and portable.
To accomplish this task, there are some required steps like analyzing the input
and generating the new output.

