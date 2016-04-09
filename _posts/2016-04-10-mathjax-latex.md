---
layout: post
title:  "MathJax To LaTeX"
date:   2016-04-10 21:54:12
categories: jekyll update
---
[MathJax](http://www.mathjax.org) is a simple way of including $\TeX{}$/$\LaTeX{}$/$MathML$ based mathematics in HTML webpages.
To get up and running you need to include the MathJax script in the header of your github pages page, and then write some maths.
For $\LaTeX{}$, there are two delimiters you need to know about, one for block or displayed mathematics `\[ ... \]`, and the other for inline mathematics `\( ... \)`.

### Installation
You can find the MathJax documentation [here](http://docs.mathjax.org/en/latest/) however, to get up and running quickly, simply put this into the `<head>` section of the page you would like to display mathematics:

    <head>
    ...
        <script type="text/x-mathjax-config">
                MathJax.Hub.Config({
                        tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}
                });
        </script>
        <script type="text/javascript"
                src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
        </script>
    ...
    </head>

If you are using jekyll, in `_config.yml` set
    
    markdown: kramdown

as `discount` for example automatically replaces `x^2` with `x<sup>2</sup>` which interrupts the MathJax rendering.

### Usage
Using it is pretty easy:

    Here is an example MathJax inline rendering \\( 1/x^{2} \\), and here is a block rendering: 
    \\[ \frac{1}{n^{2}} \\]

Here is an example MathJax inline rendering \\( 1/x^{2} \\), and here is a block rendering:
\\[ \frac{1}{n^{2}} \\]

The only thing to look out for is the escaping of the backslash when using markdown, so the delimiters become `\\[ ... \\]` and `\\( ... \\)` for inline and block maths respectively.

### Examples
Add $a$ squared and $b$ squared to get $c$ squared. Or, using a more mathematical approach: $c^{2}=a^{2}+b^{2}$

$\TeX{}$ is pronounced as $\tau\epsilon\chi$. This comes from my $\heartsuit$

Inline formular is as $\lim_{n \to \infty}\sum_{k=1}^n \frac{1}{k^2}= \frac{\pi^2}{6}$

and block formular looks like:

$$\lim_{n \to \infty}
\sum_{k=1}^n \frac{1}{k^2}
= \frac{\pi^2}{6}$$

$$
\mathbf{X} =
\left( \begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ddots
\end{array} \right)
$$

$$
\mathop{\mathrm{corr}}(X,Y)=
\frac{\displaystyle
\sum_{i=1}^n(x_i-\overline x)
(y_i-\overline y)}
{\displaystyle\biggl[
\sum_{i=1}^n(x_i-\overline x)^2
\sum_{i=1}^n(y_i-\overline y)^2
\biggr]^{1/2}}
$$
