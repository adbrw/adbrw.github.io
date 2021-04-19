---
layout: post
title:  "On the Leibniz integral rule"
date:   2021-04-19 11:59:43 +0200
categories: jekyll update
katex: True
---
{% include math.html %}
If $$\Omega_t$$ is a family of sets, and $$f_t$$ a family of integrable functions on $$\Omega_t$$, where the parameter $$t$$ varies in $$\mathbb R$$, what is 

$$ \dfrac{d}{dt} \left( \int_{\Omega_t} f_t \right) = \ ?$$

An answer in one dimension is given by the standard Leibniz integration formula, which states that

$$ \dfrac{d}{dt} \left( \int_{a_t}^{b_t} f_t \right)  =\left( \int_{a_t}^{b_t} \dfrac{d f_t}{dt} \right) + f_t(b_t) - f_t(a_t),$$

under some reasonable assumptions on the integrability of $$f$$ and differentiability of $$a, b, f $$ in $$t$$.
This can be proven with a standard argument switching limits and integrals (see https://en.wikipedia.org/wiki/Leibniz_integral_rule). 

In higher dimensions the situation becomes more complicated and the proofs usually more involved. There is however one straightforward argument, using distributional derivatives, which makes this an almost direct corollary of the divergence theorem, but which I have not seen elsewhere. Here it is.

__Theorem__.
Let $$ \Omega $$ be a closed subset of $$ \mathbb R^N$$, with smooth boundary. Let $$ \phi_t : \mathbb R^N \to \mathbb R^N $$ be a diffeomorphism which depends smoothly on the parameter $$t \in \mathbb R$$. Let $$ \Omega_t = \phi_t(\Omega). $$ Then for any reasonable function $$f_t  : \mathbb R^N \to \mathbb R$$,

$$ \dfrac{d}{dt} \left( \int_{\Omega_t} f_t \right) = \int_{\Omega_t} \dfrac{d f_t}{dt} + \int_{\partial \Omega_t} f_t \nu_t \cdot \dfrac{d \phi_t}{dt}, $$

where $$\nu_t$$ is the outward normal to $$\Omega_t$$.

_Proof_.
By the divergence theorem, for any vector function $$F$$ which is divergence free,

$$ \int_{\Omega_t} \nabla 1_{\Omega_t} \cdot F  d \mathcal L^N = - \int_{\partial \Omega_t} F \cdot \nu d \Sigma ^{N-1}.$$

This means that, as distributions, $$\nabla ( 1_{\Omega_t} \mathcal L^N ) = \nu_t \Sigma_t^{N-1}$$.
So, by the chain rule, we have

$$ \dfrac{d}{dt} (1_{\Omega_t} d \mathcal L^N) = \nabla_x (1_{\Omega_t} d \mathcal L^N) \cdot  \dfrac{dx }{dt} = \nu_t \Sigma ^{N-1} \cdot \dfrac{d \phi_t}{dt}. $$

Finally, by the product rule,

$$ \dfrac{d}{dt} (f_t 1_{\Omega_t} \mathcal L^N) = \dfrac{df_t}{dt} 1_{\Omega_t} \mathcal L^N + f_t \nu_t \Sigma ^{N-1} \cdot \dfrac{d \phi_t}{dt},$$

which is the thesis, only in distributional form.

