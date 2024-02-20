+++
title="Web Scrapping con python 101"
date=2024-02-19
+++

El arte del web scrapping es uno que todos en el mundo del software deberíamos conocer. Ya sea para crear un comparador de precios como [Compy](https://compy.pe/) o armar datasets para nuestro siguiente modelo de Machine Learning, el saber cómo obtener los datos que necesitamos de una web es una habilidad que no hace daño tener.

Entonces, ¿cómo puedo iniciarme en el oscuro arte del web scrapping?

## Tipos de Web Scrapping

Antes de empezar a robar información de páginas del gobierno, es útil saber qué tipos de escenarios nos podemos encontrar al momento de querer scrappear una web:

### 1. Páginas estáticas

Son aquellas en las que no se requiere interacción alguna para poder acceder a la información que deseamos. Basta con obtener el código html de la página y ya tendremos acceso a toda su información. En el mejor de los casos, la información que queremos está ordenada en una tabla o una lista ordenada, pero la mayoría de las veces tendremos que encontrar el patrón que sigue nuestra página de interés <em>(un div, dentro de otro div, dentro de otro div...)</em>
![Resultados de un examen de admisión ordenados en una tabla](resultados.png)
_[Resultados de un examen de admisión ordenados en una tabla](https://admision.unmsm.edu.pe/WebsiteSimulacro20242/1/202/0.html)_

### 2. Páginas dinámicas

Para acceder a la información que deseamos es necesario interactuar de cierta manera con la web que intentamos scrappear. Simular el click en botones o llenar formularios son algunas de los primeros retos que uno se podría encontrar al iniciarse en el web scrapping.
![Formulario de una aerolina para poder ver los vuelos de Lima a Tarapoto](pagina-latam.png)
_[Formulario interactivo de latam para poder listar vuelos](https://www.latamairlines.com/pe/es)_

### 3. Páginas que requieren a un hechicero de mayor nivel

En ciertas ocasiones, no bastará solo con simular interacciones con nuestra web de interés presionando botones o llenado formularios. Realizar peticiones HTTP, enviar cookies de request a request o usar alguna librería para simular distintos user-agents son algunas de las acciones que tendremos que realizar para poder obtener los datos que necesitamos. Puede darse incluso el caso en el que en un inicio tengamos que interactuar con una web -iniciando sesión por ejemplo- para luego obtener datos estáticos _(comentarios en una red social, listado de seguidores, etc)_

```python
def robar_receta_cangreburger():
    url = 'https://api-totalmente-real/obtener-receta-cangreburger'
    bearer_token = f'Bearer {token}'
    headers = {
        'accept': 'application/json, text/plain, */*',
        'Accept-Encoding': 'gzip',
        'authorization': bearer_token,
        'Connection': 'Keep-Alive',
        'Host': 'don.cangrejo.com',
        'User-Agent': 'okhttp/4.9.2'
    }
    request = requests.get(url, headers=headers, cookies=cookies)
```

_Realizando una solicitud http usando un token de autenticación_

## ¿Qué librerías usar ante cada situación?

Si bien podemos usar distintas librerías para cada situación, existen algunas que suelen ser más usadas y de las que podremos encontrar mayor cantidad de documentación o preguntas en el difunto stackoverflow

- ### Para páginas estáticas

- ### Para páginas dinámicas

- ### Jutsus prohibidos
