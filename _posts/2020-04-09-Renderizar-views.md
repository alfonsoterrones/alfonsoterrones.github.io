---
layout: post
title: Renderizar vistas!
---
![File View](/images/files.jpg "File View")
Como enlazar el título de un nodo a un fichero que se encuentre dentro del mismo nodo.

<h1> Introducción </h1>.

En primer lugar vamos a hacer una pequeña introducción de que son las vistas en Drupal. Las vistas en drupal nos
permiten hacer un listado sobre unos nodos en concreto, tambien podremos listar usuarios, comentarios, términos de
taxonomía, etc. El funcionamiento de una vista basicamente es el de buscar todos los contenidos que tengamos en nuestro
sitio web y presentarlos en el formato que nosotros le queramos dar, algunos de esos formatos son en table HTML, un feed RSS,
un documento PDF, un documento CSV, un mapa interactivo, un carrusel de imágenes, aunque una misma vista puede tener múltiples
formatos de presentación al mismo tiempo.

En este caso vamos a listar un tipo de contenido de Drupal (Publicaciones), dicho tipo contenido esta compuesto entre otros campos
de un campo 'portada' (tipo imagen) y un campo 'título' (texto sin formato) que nos indicará el nombre de la publicación
en al que nos encontramos.

Lo que queremos intentar hoy es que en el listado que nos devuelva la vista nos muestre todos los títulos de las publicaciones, y que
dicho título nos enlace directamente a la portada, y nos muestre la portada en vez de enlazarnos al nodo.

Vamos a comenzar, nos encontramos en la edición de la vista Publicaciones, es una vista muy muy básica en la que estamos mostrando
únicamente el título y filtrando por los contenidos de tipo Publicacion que estén publicados.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url1.png)

Cuando nos creamos una vista, por defecto el título nos enlaza con el nodo, por lo que si clicamos sobre el título nos llevará al nodo,
pero nosotros queremos que el título nos lleve a mostrarnos la portada, por lo que tendremos que modificar el "a href" del enlace, así es
como lo tenemos sin tocar absolutamente nada.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url2.png)

Lo primero que vamos a hacer es añadir el campo 'portada' que es el campo que queremos mostrar al clicar sobre el título, para ello
clicamos sobe el botón 'añadir' dentro del apartado de campos.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url3.png)

Buscaremos el campo que queremos añadir y lo agregaremos como aparece en la siguiente captura.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url4.png)

Una vez lo hayamos agregado, tenemos la configuración del campo, en dicha configuración marcaremos la opción
"Excluir de la presentacion" ya que no queremos que nos muestre la URL en el listado de resultados de la vista,
nosotros lo que queremos es obtener la URL para asignarselo al enlace "a href" del título. También modificaremos la opción
del formateador ya que nos puede mostrar directamente la entidad o mostrarnos la URL del enlace al contenido, en este
caso seleccionaremos la opcion "URL de la imagen".

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url5.png)

Puede darse el caso que entre las opciones del formateador no nos de la opción de "URL de la imagen" y si nos aparezca
"Entidad representada" en ese caso cuando elijamos esta opción se nos tiene que desplegar un segundo dropdown que si nos
permitirá elegir la opción "URL de la imagen", si aún así no obtenemos esta opción es posible que debamos modificar
los modos de presentación dentro de las opciones de ese campo para que aparezca la opción que queremos.

En todos los casos es muy importante que desmarquemos la opción "Eliminar etiquetas HTML", normalmente no da problema, pero
si estamos mostrando la URL como "Entidad referenciada" es posible que nos de problemas a la hora de pegar la URL en
el enlace, por lo que recomiendo desmarcarlo siempre.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url6.png)

Una vez añadido el campo vamos a reordenar los campos ya que el campo que tenemos como campo oculto necesitamos que se encuentre
por encima del campo que vamos a utilizar

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url7.png)

En esta nueva ventana nos mostraran todos lso campos que tenemos dentro de los resultados de la vista, arrastraremos
en este caso el campo 'portada' y lo pondre justo por encima del campo título como se muestra en la siguiente imagen.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url8.png)

Guardaremos el nuevo orden que hemos asignado para que se muestren en la vista y ahora modificaremos el campo título.

El campo título lo editaremos, editaremos más concretamente el apartado 'rescribir resultado', reescribiremos el resultado, no es una técnica aconsejable pero en muchos casos, evita tocar las plantillas. Lo que vamos a hacer es modificar directamente el renderizado de
los campos del regitro que nos llegan directmente del entorno de administración de la vista. Para ello utilizaremos los patrones
de reemplazo que nos ayudará a encontra los nodos que necesitamos.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url9.png)

Como podemos ver en la imagen anterior podemos apreciar los patrones twig que podemos utilizar para rescribir el resultado, estos patrones corresponden a los campos que tenemos agregados en los resultados de la vista. En este caso hemos creado un "a href" para mostrar el título y que nos enlace directamente a la imagen de la portada mediante el patrón URL que hemos obtenido. Importante desmarcar la opción "enlazar al contenido".

Guardaremos y como podemos mostrar en la siguiente imagen podemos apreciar que estamos mostrando el titulo y nos enlaza a la portada directamente.

![Picture from Unsplash, by @hannahmgibbs]({{ site.baseurl }}/images/imagespostAccesoUrl/url10.png)

























