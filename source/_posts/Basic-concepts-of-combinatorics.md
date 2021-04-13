---
title: Basic Concepts of Combinatorics
date: 2021-04-12 03:37:59
tags:
---
Combinatorics is a field of mathematics in which we basically count things. In the following article, we're going to discover some of the basics of that field.

# Permutations 
As its name indicates, the number of permutations of a certain number of elements is the number of possible rearrangments of those elements. For example, the permutation of three digits let's say 3, 2 and 1 for example is the "number of numbers" we can get using only those three specific digits : 3,2 and 1.
Let's see a more visual example, say that we want to calculate the number permutations of three balls of different colors: blue, red, and green. Given the small number of balls we have, we can do this pretty easily by hand to find the following possible permutations : 
<p align="center">
  <img width="200" height="300" src="/images/dark1.png">
</p>

Notice that if we fix the color of the first ball as blue for instance, we have only two cases left, either the second ball is green and the third one is red, or the second one is red and the third one is green. Same thing applies if we fix the color of the fist ball as green or red. 
So for the first ball, we have three choices : Red, green, and blue. However, for the second ball, we have only two choices left because one ball is already taken. Similarly, for the last ball, we have only one choice left. 
We get the number of permutations by multiplying : {% mathjax %}3*2*1{% endmathjax %} which is {% mathjax %}3!{% endmathjax %}.
<p align="center">
  <img src="/images/bitmap.png">
</p>
Let's generalize the concept.
Say that we want to know the number of permutations of n distinct items. Analogically to our previous example, we have n possible choices for the first place, {% mathjax %}(n-1){% endmathjax %} possibilities for the second choice, {% mathjax %}(n-2){% endmathjax %} choices for the third, and so on until we have only one choice left. So the total number of cases is : 
{% mathjax '{ "conversion": { "em": 14 }, "tex": { "tags": "ams" }, "svg": { "exFactor": 0.03 } }' %}n(n-1)(n-2)\dots 1 = n! {% endmathjax %}


# k-permutations of n
Imagine 12 people are competing on a race, and we want to compute the number of possible podiums that can probably be made with that number of racers. Using the same previous reasonning, we have 12 possiblities for the first rank, 11 for the second rank, and 10 for the third. In total, we have {% mathjax %}12*11*10{% endmathjax %} different cases.
It's kind of an unfinished factorial where we only stop on the third number : 10 in our example. Mathematically, we can write it as : 

{% mathjax '{ "conversion": { "em": 14 }, "tex": { "tags": "ams" }, "svg": { "exFactor": 0.03 } }' %}\frac{12!}{(12-3)!} = \frac{12*11*10*9*\dots*1}{9*8*7*\dots*1} = 12*11*10 {% endmathjax %}
This is called 3-permutation of 12, and it is noted : {% mathjax %}P(12,3){% endmathjax %} 
![racers](/images/racers.png)
In general, k-permutations of n is : {% mathjax '{ "conversion": { "em": 14 }, "tex": { "tags": "ams" }, "svg": { "exFactor": 0.03 } }' %}P(n,k) = \frac{n!}{(n-k)!}{% endmathjax %}

it represents the number of possible subsets of k elements we can get from that initial set of n elements, with order taken into consideration. (racer A first, B second, and C third is not the same as : racer B first, A second, and C third).

# Combinations 

Pretend that we have a group of 10 tennis players, and we want to calculate the number of different teams of two players we can make out of them, this number is called the number of combinations of 2 elements in a set of 10 elements.

To come up with a formula for that, let's return to the k-permutations of n problem, in fact we can see it from a different perspective; "first grab k elements, then rearrange them", in other words, calculating k-permutations of n can be done like this
* Calculate the number of combinations of k elements in a set of n elements
* multiply it by the number of their permutations
Mathematically : 
{% mathjax %}P(n,k)={n \choose k}*k!{% endmathjax %} 

knowing that : {% mathjax %}P(n,k) = \frac{n!}{(n-k)!}{% endmathjax %} 
we conclude that: {% mathjax '{ "conversion": { "em": 14 }, "tex": { "tags": "ams" }, "svg": { "exFactor": 0.03 } }' %}
{n \choose k} = \frac{n!}{k!*(n-k)!}
{% endmathjax %}

# Finally
This is my first article in this blog, I hope it was useful, I will hopefully post more articles soon, we are probably going to cover the topic of Newton's Binomial.
