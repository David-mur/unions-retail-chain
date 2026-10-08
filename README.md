# unions-retail-chain

FAQ:
1. ¿Cuántas filas devuelve cada consulta y por qué son distintas?
   R/. La primera consulta, donde se usó UNION, generó 11 filas, esto debido a que hay algunos productos que están en ambas sedes, y el objetivo de este UNION es hacer una unión de ambos conjuntos, pero sin duplicados. Por otro lado, la segunda consulta generó 14 filas, usando UNION ALL, donde se incluyen todos los de la anterior más los duplicados. Por ejemplo, los id_producto 103, 104 y 106 están en ambas sucursales, por lo que son duplicados, entonces solo salen en la consulta los primeros en ser registrados con ese id.

2. ¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?
   R/. UNION ALL es más eficiente porque solo junta todos los conjuntos sin importar lo que haya en ellos, en cambio UNION añade una condición disyuntiva, es decir, hace una conjunción de los conjuntos y a lo que salga le resta la intersección de los conjuntos.

3. ¿En qué casos de negocio usarías cada uno?
   R/. El UNION lo podría usar en una situación en la que quisiera ver qué clientes son recurrentes de una sucursal específica de una marca, o también cuando quisiera saber en qué ciudades en total hay un suministro de repuestos de motocicletas (sin contar que en una ciudad haya más de una sucursal que tiene el producto). Por otro lado, el UNION ALL lo usaría cuando quisiera ver todas las marcas que tienen estaciones de servicio y cuántas tienen en una ciudad determinada, o también los precios de la gasolina de esas estaciones de servicio y averiguar en cuales se aleja más del precio que se repita normalmente.

4. ¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?
  R/. Es porque se estaría intentando juntar un tipo de información que solo está en una tabla, al hacer esto, SQL no ejecuta la consulta.
