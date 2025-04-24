# Diseño de Solucion
![Diseño de solucion](https://github.com/LuisCif-20/PatternChallenge/blob/main/patternChallenge.png)

# Justificacion del Diseño

Se utilizaron los siguientes patrones de diseño para resolver algunos de los problemas:

## Patron Composite
Se puedo identificar una estructura jerarquica en los items (Platos, Bebidas, Extras) que una lista de estos a su vez hacen un combo. En este caso se utilizo la interface Item, que la implementan otros objetos.

## Patron Builder
Se utilizo para construir pedidos flexibles con items obligatorios y opcionales, en este caso para la construccion de combos o menus predifinidos donde de forma obligatorio tenia que existir un plato principal.Se utilizo el PedidoBuilder que se encargara de construir pedidos de forma flexible tomando en cuenta los campos obligatorios y opcionales.

## Patron Strategy
Se utilizo para aplicar diferentes tipos de descuentos sin estar utilizando if o switch al aplicarlo en codigo esto nos permite implementar promociones independientemente si los diferentes tipos de estas aumenta.Se creo una interface DescuentoStrategy que utilizaran o implementaran las otras clases relacionadas con descuentos o promociones que no son acumulables, en este caso la de DescuentoClienteFrecuente y DescuentoPastaMartes.

## Patron Adaptador
Este se tendra que utilizar para podernos comunicar con el sistema de cocina en donde nos dicen que este espera los pedidos en XML, y como el sistema de clientes trabaja con JSON entonces se implemento este para poder realizar esta conversion sin mayores complicaciones o incompatibilidades en los elementos. En este caso se utilizo el cocinaAdapter que es implementado en el pedidoXMLAdapter para poder realizar las conversiones teoricamente.

## Patron Command
Este se puede utilizar para manejar las acciones que se ejecutaran o revertiran dentro del restaurante para esto se utilizo una clase controladora de pedidos y una interface de accion de la que heredan otras clases para ejecutar o deshacer pedidos en base al historial que se tenga.