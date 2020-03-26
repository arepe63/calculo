---
title: "Tema 2.1 - Series numéricas"
author: "Juan Gabriel Gomila, Arnau Mir y Llorenç Valverde"
date: ''
output: 
  ioslides_presentation: 
    css: Mery_style.css
    fig_caption: yes
    keep_md: yes
    logo: Images/calculus.gif
    widescreen: yes
---



# Tema

## Series numéricas

Veremos en este apartado un tipo especial de sucesiones que nos permiten tratar sumas de infinitos términos cuya suma es finita. 

La suma de los términos de una progresión geométrica constituye uno de los ejemplos más conocidos de este tipo de sumas.

Recordemos que una progresión geométrica és una sucesión $\{a_n\}$ tal que el cociente entre un término y el anterior $\dfrac{a_{n+1}}{a_n}$ es constante, es decir una sucesión de la forma 

$$
a,ar,ar^2, \ldots, ar^n, \ldots
$$

## Series numéricas

Es relativamente sencillo calcular la suma de los $n$ primeros términos de este tipo de sucesiones, dado que  $S_n = a+ar+ar^2+ \ldots +ar^n$ y que $rS_n =   ar+ar^2+ \ldots +ar^n + ar^{n+1}$, por lo que
$$
(1-r)S_n = S_n-rS_n= a(1-r^{n+1})
$$
es decir 
$$
S_n = a \dfrac{\quad \, 1-r^{n+1}}{1-r}
$$
Si $|r|<1$, entonces $\lim r^{n+1} = 0$ y, por lo tanto
$$
a+ar+ar^2 \ldots + ar^n + \ldots = \lim_{n \rightarrow \infty} S_n = \dfrac{a}{1-r}
$$

## Series numèricas

<l class="definition"> **Definición** </l>

Llamaremos **serie** generada por una sucesión de números reales $\{a_n \}_{n \in \mathbb{N}}$ a la sucesión 
$$
S_1 = a_1, \; S_2=a_1+a_2,  \ldots, S_n=a_1+a_2+ \ldots +a_n
$$
 $\{S_n \}_{n \in \mathbb{N}}$ recibe el nombre de sucesión de las **sumas parciales** de la serie.

$\displaystyle{\sum_{n=1}^{\infty}a_n}$ y también $\displaystyle{\sum a_n}$ son las notaciones que se usan habitualmente para denotar la serie generada por la sucesión $a_n$. 

## Series numéricas: Convergencia

<l class="definition"> **Definición** </l>

Una serie $\displaystyle{\sum_{n=1}^{\infty}a_n}$ es **convergente** si su sucesión de sumas parciales $S_n$ tiene límite, en cuyo caso, dicho límite recibe el nombre de **suma** de la serie.


Una serie **divergente** es aquella para la que $S_n$ no tiene límite finito y se denota por $\displaystyle{\sum_{n=1}^{\infty}a_n} = \infty$ 

Una serie **absolutamente convergente** es aquella tal que la serie de valores absolutos $\displaystyle{\sum_{n=1}^{\infty}|a_n| < \infty}$ es convergente.




## Series numéricas: Ejemplos. 

<div class="example"> **Ejemplos**

Ejemplo 1: La **serie geomètrica**, generada por una progresión geomètrica $a,ar,ar^2, \ldots, ar^n, \ldots$, 
$$
\sum_{n=1}^{\infty} ar^n
$$
que ya hemos visto que es convergente si $|r|<1$.



Ejemplo 2: La **serie armónica**, $\displaystyle{\sum_{n=1}^{\infty}}\dfrac{1}{n}$, generada por la sucesión $\left\{\dfrac{1}{n} \right\}_{n \in \mathbb{N}}$.

Se trata de una serie divergente, como se verá más adelante. 

Ejemplo 3. La  **serie armónica generalizada**, $\displaystyle{\sum_{n=1}^{\infty}}\dfrac{1}{n^\alpha}$, generada por la sucesión $\left\{\dfrac{1}{n^\alpha} \right\}_{n \in \mathbb{N}}$.

Má adelante veremos que esta serie es convergente si $\alpha >1$
</div>

## Series convergentes.

<l class="prop"> **Proposición (Criterio de Cauchy para series numéricas)** </l>

La serie $\displaystyle{\sum_{n=1}^{\infty}a_n}$ es convergente si para todo $\epsilon > 0$ existe $n_0 \in \mathbb{N}$ tal que para todo $n \geq n_0$ y todo $k \in \mathbb{N}$ es 
$$
|a_{n+1}+ a_{n+2}+ \cdots + a_{n+k}|<\epsilon
$$

<div class="dem"> **Demostración** 

Que la serie sea convergente quiere decir que la sucesión de umas parciales $S_n$ es convergente y, por lotanto, verifica el criterio de Cauchy para sucesiones, es decir, para todo $\epsilon >0$, existe $n_0$ tal que para todo $n,m > n_0$ es $|S_m-S_n| < \epsilon$. Ahora, podemos suponer que $m>n$, por lo que $m = n+k$, para algún $k \in \mathbb{N}$. En consecuencia:
$$
|S_m-S_n| = |a_{n+1}+a_{n+2}+ \cdots + a_m| < \epsilon
$$

</div>

## Corolario: La serie armònica es divergente

<l class="prop"> **Corolario** </l>

La serie armónica es divergente.

<div class="dem"> **Demostración**

Será suficiente de mostrar que existe un $\epsilon > 0$,tal que para todo $n_0 \in \mathbb{N}$ existen $m>n>n_0$ tales que 
$$
|S_m-S_n| = |a_{n+1}+a_{n+2}+ \cdots + a_m| \geq \epsilon
$$
Sea $0<\epsilon < \dfrac{1}{2}$, dado un $n_0 \in \mathbb{N}$ cualquiera, consideremos Un $n >n_0$ y $m=2n$. Tenemos
$$
a_{n+1}+a_{n+2}+ \cdots + a_m = \dfrac{1}{n+1} + \dfrac{1}{n+2} +\cdots +\dfrac{1}{2n} \geq \dfrac{1}{2n}+\cdots +\dfrac{1}{2n} = \dfrac{n}{2n}=\dfrac{1}{2}
$$


## Condición necesaria

<l class="prop"> **Corolario (Condición suficiente de convergencia)** </l>

Si la serie $\displaystyle{\sum_{n=1}^{\infty}a_n}$ es convergente, entonces $\lim_{n \rightarrow \infty}  a_n = 0$

<div class="dem"> **Demostración**

Es suficiente considerar la condición de Cauchy con $m=n+1$, en este caso resulta que para todo $\epsilon >0$ existe $n_0$ tal que para todo $m,n \geq n_0$ es $|S_m -S_n| < \epsilon$, pero si $m=n+1$ entonces $|S_{n+1}-S_n| = |a_{n+1}| < \epsilon$, es decir que $\lim_{n \rightarrow \infty} a_n = 0$.

</div>

Es importante tener en cuenta que esta és una condición **necesaria** pero no suficiente, como evidencia el caso de la seria armónica, que es divergente aunque $\lim_{n \rightarrow \infty}  \dfrac{1}{n}=0$