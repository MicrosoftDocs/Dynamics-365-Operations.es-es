---
title: Configurar la validación de conciliación de facturas de proveedores
description: En este tema se brinda información sobre cómo configurar la validación Conciliación de facturas de proveedores.
author: abruer
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 15fbb5481e3ff8760f536f1d5eeff76370216b37
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827755"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Configurar la validación de conciliación de facturas de proveedores

[!include [banner](../../includes/banner.md)]

Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada. Si la entidad jurídica realiza un seguimiento de gastos, como el flete, usando los cargos, asegúrese de que la clave de configuración de cargos esté seleccionada.  La conciliación de facturas de proveedores es el proceso de conciliación de la factura de proveedor, el pedido de compra y la información de recepción de producto. Las diferencias entre estos documentos se denominan "discrepancias coincidentes". Las discrepancias de conciliación se comparan con las tolerancias especificadas. Si una discrepancia de conciliación supera el porcentaje o el importe de tolerancia, se mostrarán iconos de desviación de conciliación en la página **Factura de proveedor** y en la página **Detalles de coincidencia de factura**.

## <a name="determine-which-invoice-matching-validation-to-use"></a>Determinar qué validación de conciliación de facturas utilizar
Hay disponibles cuatro tipos de validación de conciliación diferentes. 

- **Conciliación de nivel de línea**: el tipo más común de conciliación es la conciliación de líneas. La conciliación de nivel del ínea puede ser una doble o una triple conciliación. La conciliación de nivel de línea predeterminada se puede especificar para una entidad jurídica en la página **Parámetros de proveedores**. La doble conciliación compara el precio unitario de la factura con el precio unitario del pedido de compra. La triple conciliación además compara la cantidad de facturas con la cantidad de recepciones de producto conciliado.
- **Conciliación de totales de factura**: concilie los importes totales de la factura con los importes totales del pedido de compra. Este tipo de conciliación de la factura incluye el importe mínimo de detalle, por lo que puede usar esta opción para configurar los controles que minimizan el tiempo de personal necesario para revisar la información de conciliación de facturas. Se comparan seis totales, incluido Subtotal, Descuento total, Gastos, Impuestos, Redondeo e Importe de la factura. El sistema se validará si cualquiera de estos valores en la factura se desvían de los importes previstos en más de una desviación aceptable.
- **Conciliación de gastos**: concilie la información de gastos (importes) de la factura con la información de gastos (importes) del pedido de compra
- **Totales de precio para conciliación de artículo de línea**: este tipo de conciliación es útil para las empresas que suelen recibir varias facturas para una única línea de pedido de compra. Si normalmente recibie solo una factura por línea de pedido de compra, este tipo de conciliación no es necesario. Esta conciliación requiere que se habilite una doble o triple conciliación y sirve como validación de importe neto que no se debe superar, en función de porcentajes de tolerancia e importes.  Este tipo de conciliación compara la información sobre precios del importe neto de cada línea de factura y todas las líneas de factura pendientes y registradas anteriormente, con el importe neto de la línea del pedido de compra correspondiente. El importe neto se determina por la fórmula siguiente: (precio unitario * cantidad de línea) + gastos de línea - descuentos de línea. Al correlacionar los totales de precio por porcentaje, el sistema compara los valores utilizando la divisa de transacción. Al correlacionar los totales de precio por importe, el sistema compara los valores utilizando la divisa de contabilidad.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Configurar parámetros para habilitar la validación de conciliación de facturas
1. Vaya a **Proveedores > Configuración > Parámetros de proveedores**.
2. Seleccione la pestala **Validación de factura**.
3. Active o desactive la casilla **Habilitar validación de conciliación de facturas**.
    * Seleccione si la aprobación es necesaria antes de que se pueda registrar una factura que contenga discrepancias en la conciliación de facturas. Si se define como **Permitir con aviso**, se mostrará una indicación visual cuando una discrepancia de la conciliación de la factura supera la tolerancia. Sin embargo, podrá registrar la factura. Para usar flujos de trabajo junto con la validación de conciliación de facturas, asegúrese de que el campo **Registrar factura con discrepancias** esté establecido en **Permitir con aviso** para evitar que se tenga que aprobar varias veces.  
    * En el campo **Actualizar estado de encabezado de factura automáticamente**, seleccione si la conciliación se realizará automáticamente durante la entrada de datos de la factura por el sistema. La configuración recomendada es **Sí**, a menos que le preocupe el rendimiento de la entrada de datos. Al deshabilitar las actualizaciones automáticas se puede habilitar un rendimiento del sistema más rápido porque la validación de conciliación de facturas se omitirá durante la entrada de datos. El responsable de entrada de datos deberá actualizar manualmente el estado de conciliación de la factura para ver los resultados de validación de conciliación de facturas cuando está establecido en **No**.  
4. Establezca **Conciliación de totales de factura**.
5. Active o desactive la casilla **Totales de factura de conciliación** para conciliar los totales de factura reales con los totales previstos.
    * Seleccione si se debe mostrar un icono si una discrepancia para la conciliación de la factura supera la tolerancia. Puede seleccionar mostrar el icono cuando una discrepancia positiva supere la tolerancia, o cuando una discrepancia positiva o negativa supere la tolerancia.  
    * Por ejemplo, la tolerancia es del 5 por ciento, y el importe total de la factura del pedido de compra es 100,00. Por tanto, se mostrará un icono de conciliación de precio si el importe total de la factura supera 105,00. Si selecciona **Si es superior o inferior a la tolerancia**, también se mostrará el icono si el importe de la factura es inferior a 95,00.  
6. En el campo **Porcentaje de tolerancia de totales de factura**, especifique la desviación porcentual aceptable. Este valor es el valor predeterminado de la empresa. Este valor se puede anular para determinados proveedores, mediante la página **Tolerancias de totales de factura**. Para obtener información acerca de cómo anular el porcentaje de tolerancia de totales de factura para un proveedor determinado, consulte la sección "Configurar tolerancia de conciliación de totales de facturas para proveedores" más adelante en este tema.
7. Establezca **Conciliación de precio y cantidad**.
8. En el campo **Directiva de conciliación de líneas**, seleccione un valor que se usará como directiva predeterminada para la entidad jurídica con la que está trabajando. **No requerido** significa que no existe ninguna verificación de los precios individuales de la línea de factura en las cantidades de precio o de factura del pedido de compra con las cantidades de albarán necesarias. **Doble conciliación** significa que la verificación de las líneas de factura es necesaria pero solo el pedido de compra y los documentos de factura del proveedor están involucrados en la comprobación. La recepción de producto no se descompone en las validaciones de conciliación. **Triple conciliación** significa que el precio unitario neto de la factura se comparará con el precio unitario neto del pedido de compra y la cantidad de recepción de producto conciliada se comparará con la cantidad de la factura.
9. Para permitir que se aplique un nivel diferente de conciliación a un artículo, proveedor, combinación de proveedor y artículo o línea de pedido de compra, seleccione un valor en el campo **Permitir anulación de directiva de conciliación**. La directiva de conciliación de líneas de la entidad jurídica se puede invalidar para un proveedor, artículo o combinación de proveedor y artículo concretos en la página **Directiva de conciliación**.
    * Si usa una directiva de conciliación de líneas de doble conciliación o de triple conciliación, puede configurar porcentajes de tolerancia de precios para la entidad jurídica, los artículos y los proveedores en la página **Tolerancia de precios de artículos**. La tolerancia de precios predeterminada de la entidad jurídica se establecerá en el cero por ciento para la doble y la triple conciliación. Al comparar las facturas de proveedores con la información de los pedidos de compra, se busca el porcentaje de tolerancia de precios aplicable.   
10. Para conciliar los totales de precio de los artículos de línea en las facturas, seleccione un valor en el campo **Conciliar totales de precios**. Este tipo de conciliación es útil cuando el proveedor envía varias facturas para la misma línea de pedido de compra. Puede comparar la información sobre precios del importe neto de cada línea de factura y todas las líneas de factura pendientes y registradas anteriormente, con el importe neto de la línea del pedido de compra correspondiente.  Las opciones incluyen **Ninguno**, **Porcentaje**, **Importe** o **Porcentaje e importe**.
11. En el campo **Porcentaje de tolerancia total de precio de compra**, especifique un porcentaje de la desviación que aceptará. Este campo está disponible cuando **Conciliar totales de precios** se establece en **Porcentaje** o en **Porcentaje e importe**.
12. En el campo **Tolerancia total de precio de compra**, especifique un importe en la divisa de contabilidad. Este campo está disponible cuando **Conciliar totales de precios** se establece en **Importe** o en **Porcentaje e importe**.
13. En el campo **Mostrar icono de conciliación total de precios**, seleccione si un icono debe aparecer si la discrepancia de la conciliación de factura supera la tolerancia. El icono puede aparecer cuando una discrepancia positiva supere la tolerancia, o cuando una discrepancia positiva o negativa supere la tolerancia.
Por ejemplo, la tolerancia es del 5 por ciento, y el total de precio de línea del pedido de compra es 10,00. Por tanto, se mostrará un icono de conciliación de precio si el total de precio de factura supera 10,50. Si selecciona **Si es superior o inferior a la tolerancia**, también se mostrará el icono si el total de precio de la factura es inferior a 9,50.
13. Establezca la conciliación de gastos varios.
14. Para que los cargos reales coincidan con los previstos, según la información del pedido de compra, active la casilla **Conciliar gastos varios**.

## <a name="set-up-unit-price-tolerance-percentages"></a>Configurar porcentajes de tolerancia de precio unitario
Vaya a **Proveedores > Configuración > Configuración de conciliación de facturas > Tolerancias de precios** para definir porcentajes de tolerancia de precios permitidos. Si usa una directiva de conciliación de líneas de doble conciliación o de triple conciliación, puede configurar porcentajes de tolerancia de precios para la entidad jurídica, los artículos y los proveedores. Al comparar las facturas de proveedores con la información de los pedidos de compra, se busca el porcentaje de tolerancia de precios aplicable. El orden de búsqueda predeterminado es el siguiente:
* Tabla/Tabla
* Tabla/Grupo
* Tabla/Todo
* Grupo/Tabla
* Grupo/Grupo
* Grupo/Todo
* Todo/Tabla
* Todo/Grupo
* Todo/Todo

La tolerancia de precios de la entidad jurídica predeterminada es del 0 por ciento y se aplica a todos los artículos y todas las cuentas (Todos, Todos). No se puede eliminar el registro de tolerancia de precios de la entidad jurídica predeterminada.

De forma predeterminada, se permiten las discrepancias de precio negativo. Sin embargo, no puede especificar un número negativo como el porcentaje de tolerancia de precios. Para realizar un seguimiento de los porcentajes de tolerancia de precios negativa, seleccione **Si es superior o inferior a la tolerancia** en el campo **Mostrar icono de conciliación de precios unitarios** en la página **Parámetros de proveedores**. A continuación, especifique los porcentajes de tolerancia de precios en la página **Tolerancias de precios**.

## <a name="set-up-matching-policy-override"></a>Configurar anulación de directiva de conciliación

Vaya a **Proveedores > Configuración > Configuración de conciliación de facturas > Directiva de conciliación** para definir la entrada predeterminada para el campo Directiva de conciliación para las líneas del formulario Pedido de compra. Esta es una configuración opcional. Use este formulario para configurar una directiva de doble o triple conciliación para artículos, proveedores o combinaciones de artículo y proveedor. Estas entradas le permiten definir las directivas de conciliación más granulares que la directiva de conciliación de la entidad jurídica que definió en la página **Parámetros de proveedores**. La política de conciliación de líneas de la entidad jurídica predeterminada se aplica a todos los artículos y los proveedores, excepto a aquellos para los que se especifica una directiva de conciliación de líneas distinta en esta página.

En esta página, seleccione **Nivel de directiva de conciliación**. Seleccione el nivel de la jerarquía de la directiva de conciliación para la cual definir directivas de conciliación de líneas.

- **Artículo y proveedor**: especifique la directiva de conciliación de artículos específicos adquiridos a proveedores específicos.
- **Artículo**: especifique la directiva de conciliación para artículos específicos adquiridos a cualquier proveedor, excepto los especificados en el nivel de artículo y proveedor.
- **Proveedor**: especifique la directiva de conciliación para todos artículos adquiridos a proveedores específicos, excepto los especificados en el artículo y el proveedor y los niveles de artículo.
  
Se usa la jerarquía siguiente para determinar la directiva de conciliación usada:
  *  Artículo y proveedor
  *  Elemento
  *  Proveedor
  *  Entidad jurídica
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Configurar tolerancia de conciliación de totales de facturas para proveedores

Vaya a **Proveedores > Configuración > Configuración de conciliación de facturas > Tolerancias de totales de factura** para especificar tolerancias específicas del proveedor para la coincidencia de totales de factura. El cálculo de la conciliación usa la tolerancia de los totales de factura de la cuenta de proveedor especificada como la cuenta de pedido en la factura del proveedor. Si la cuenta del proveedor no tiene un porcentaje de tolerancia especificado para los totales de factura, se usa el porcentaje de los totales de factura especificado para la entidad jurídica en la página **Parámetros de proveedores**.

1. Para especificar tolerancias para proveedores individuales que anulan la tolerancia predeterminada, seleccione una **Cuenta de proveedor**.
2. Especifique el porcentaje de desviación que aceptará para este proveedor.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]