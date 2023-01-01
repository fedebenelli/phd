---
title: "Ecuaciones de estado multiparamétricas"
author: "Federico Benelli"
institute: "IPQA"
topic: "Termodinámica de fluidos"
theme: "Frankfurt"
colortheme: "beaver"
fonttheme: "professionalfonts"
mainfont: "IBM Plex Serif"
fontsize: 10pt
urlcolor: blue
linkstyle: bold
aspectratio: 169
titlegraphic: $HOME/.config/wallpaper.png
logo: $HOME/pics/firma.png
date:
section-titles: true
toc: true
geometry: margin=2cm
---

# Introducción
Conocimiento preciso de propiedades termodinámicas -> Indispensable

## Ecuaciones de estado
Son ecuaciones que se utilizan para representar una propiedad termodinámica como una función de temperatura, volumen y otros parámetros.

https://gfrc.tamu.edu/wp-content/uploads/2015/04/Atilhan.pdf

- Cubic EOS:
	- PR
	- RK
	- SRK

- Molecular EOS
	- SAFT:
	$\frac{A}{RT} = \frac {A^{seg}} {RT} + \frac{A^{chain}}{RT}$

- Multicomponent EOS
	- AGA8:
	\begin{equation}
	\begin{aligned}
	\alpha^r(\rho, \tau, \overline{x}) = 	 & \delta (\frac{B}{K^3}- \sum\limits_{n=13}^{18}C^*_n\tau^{u_n}) + \\
						 & + \sum\limits_{n=13}^{18}C^*_n\tau^{u_n}\delta^{b_n}exp(-c_n\delta^{b_n})
	\end{aligned}
	\end{equation} 

	- GERG:\begin{equation}
	\begin{aligned}
	\alpha(\rho, \tau, \overline{x}) = 	& \alpha^o(\rho, T, \overline{x}) + \\ 
						& + \sum\limits_{i=1}^N x_i\alpha_{oi}^r(\delta,\tau) + \Delta\alpha^r(\delta,\tau,\overline{x})
	\end{aligned}
	\end{equation}
	
# Ecuaciones de estado multifluidos

Están basadas en aproximaciones de múltiples fluidos y usualmente son explícitas en la energía libre de Helmholtz.

$A(T,V) = U(T,V) - TS(T,V)$

Estos modelos usan ecuaciones de estado en la forma de ecuaciones de estado fundamentales para cada componente junto con correlaciones para tener en cuenta comportamiento residual de mezclado

Se basan en datos experimentales. 

Kunz et al (paper 2004/2) desarrollaron la ecuación GERG-2004 de estado para gases naturales y otras mezclas.


## Descripción general

Gran parte de estas ecuaciones se estructuran como:

$a(\rho, T, \overline{x}) = a^o(\rho, T, \overline{x}) + a^r(\rho, T, \overline{x})$

$\alpha(\delta, \tau, \overline{x}) = \alpha^o(\delta, T, \overline{x}) + \alpha^r(\rho, \tau, \overline{x})$

$\delta = \rho/\rho_r(\overline{x})$

$\tau = \tau_r(\overline{x})/\tau$

$\alpha^o(\rho,T,\overline{x}) = \sum\limits_{i=1}^{N}x_i [\alpha^o_{oi}(\rho, T) + ln(x_i)]$

## Descripción Términos

Donde el primer término es el valor de la energía de Helmholtz adimensional para el estado de gas ideal del componente $i$ y el término $x_i ln x_i$ corresponde a la entropía de mezclado.

$\alpha^r(\delta, \tau, \overline{x}) = \sum\limits_{i=1}^{N}x̣_i\alpha^r_{oi}(\delta, \tau) + \Delta\alpha^r(\delta, \tau, \overline{x})$

Donde $\alpha^r_{io}$ es la parte residual de la energía de Helmholtz reducida para el componente $i$ y $\delta \alpha^r$ es la función de departura. Generalmente, el aporte de la función de departura es menor al de los compuestos puros.


En resumen, el desarrollo de modelos de mezcla basados en aproximación multifluido requieren tres elementos:

- Ecuaciones de estado de compuesto puro para todos los compuestos de la mezcla.
- Funciones reductoras de densidad y temperatura.
- Función de departura/desviación.

# GERG-2004/8

## Origen
La ecuación AGA8-DC92 es muy precisa para aplicaciones en gasoductos, pero se
encuentra limitada a rangos muy acotados ($260 K \le T \le 330 K$ y
$P \le 12 MPa$) y presenta mayores incertidumbres al tratar con mezclas de 
composiciones inusuales. 

Debido a estas limitaciones, el grupo GERG desarrolló una nueva ecuación,
buscando:

- Ser válida en toda la región de fluidos.
- Incertidumbres menores a 0,1% en densidad y velocidad de sonido, y menores a 
1% para el resto de propiedades.
- Incertidumbre similar a ecuaciones cúbicas de estado para cálculos de
equilibrios de fases.
- Comportarse de manera aceptable en rangos con datos de baja calidad.
- Mantener una estructura simple para facilitar su aplicación en programas,
permitiendo la utilización de alogrimos eficientes de cálculo.

## Ecuación de estado de compuestos puros

Estructura general:

- $\alpha(\rho,T)=\alpha^o(\delta,\tau) + \alpha^r(\delta,\tau)$
- $\delta = \rho/\rho_c$
- $\tau = T_c/T$

### Ecuación de energía libre de Helmholtz para el gas ideal

$a^o(\rho,T)=h^0(T)-RT-Ts^0(\rho,T)$

# Datos experimentales

## Calculos
Las ecuaciones de estado multiparamétricas se obtienen a partir de: 

- Ecuaciones de estado estado de sustancias puras.
- Correlaciones en base a datos experimentales.

Requieren una gran cantidad de datos experimentales (En el caso de la GERG-2008 se utiliza una base de datos de más de 125000 datos de propiedades térmicas y calóricas de mezclas binarias, gases naturales y otras mezclas multicomponentes. Descriptas en alrededor de 650 fuentes distintas)


## Propiedades
Las propiedades más comunes son:

- $p \rho T$
- Capacidades caloríficas: $c_v$ y $c_p$
- Velocidad del sonido: $w$
- Diferencias de entalpía: $\Delta h$
- Densidad de líquido saturado: $\rho^{'}$
- VLE (principalmente $p T xy$)

# Desarrollo

# Comparaciones de datos calculados con experimentales

## Casos

### $p \rho T$

## Limitaciones

# Bibliografía
