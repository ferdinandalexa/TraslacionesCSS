# C7 - Transformaciones de traslación

Para realizar las transformaciones de traslación utilizamos la función

```
    transform: translate("valor""unidad");
```
o mediante

```
    translate3d("valor"unidad","valor"unidad","valor"unidad")
```

Existen diferentes formas de usar esta función de acuerdo a nuestras necesidades.

* Con valor positivo:
```
    transform: translate(45px);
```
* Con valor negativo:
```
    transform: translate(-45px);
```
* Trasladando en el eje X:
```
    transform: translateX(45px);
```
* Trasladando en el eje Y:
```
    transform: translateY(45);
```
* Trasladando en el eje Z:
```
    transform: translateZ(45);
```
* Concatenando transformaciones (Podemos usar mas de una transformación ademas de translate)
```
    transform: translateX(45px) translateZ(45);
```
* Usando los tres ejes en los que se trasladara de maneja conjunta (Simplificada)
```
    transform: translate3d(45px,45px,45px);
```

Para poder apreciar los cambios cuando usamos el transformaciones en el eje Z. En este caso _translateZ("valor"unidad")_ o _translate3d"valor"unidad","valor"unidad","valor"unidad")_. Se debe especificar al navegador que estamos trabajando en un ambito 3D. Para comunicarle este dato usamos:

```
    perspective: "valor";
```

En ocasiones esto no sera suficiente. Ya que hay navegadores que requieren que se especifique este hecho cambiando ciertas propiedades. Tal es el caso de _Firefox_ donde ademas usamos:

```
    transform-style: perserve-3d;
```

Estas dos propiedades deben colocarse en el _elemento padre_ del elemento que contiene la animación.

En el caso de ***perspective*** tambien puede colocarse exclusivamente en aquellos elementos que hacen uso de un ambito 3D. La diferencia es que no se hara uso de este como propiedad, sino como función. Por ejemplo:

```
    transform: perspective(200px) translateZ(45px);
```

Hay que tomar que encuenta, que usar ***perspective*** como propiedad (_perspective: "valor"_) o como función (_perspective("valor")_). Genera pequeñas diferencias en el resultado.