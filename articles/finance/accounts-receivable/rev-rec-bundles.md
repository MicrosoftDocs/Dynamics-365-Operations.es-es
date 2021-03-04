---
title: Agrupaciones de reconocimiento de ingresos
description: Este tema describe la funcionalidad de agrupación que se incluye en la capacidad de reconocimiento de ingresos en Clientes. Una agrupación comprende un elemento principal y varios elementos componentes.
author: kweekley
manager: aolson
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: cf4d03c1a697259899c419ce084b35f4eddf13fe
ms.sourcegitcommit: bd53794cb94f8c1ce29a7d6102119a0975f155e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "5142308"
---
# <a name="revenue-recognition-bundles"></a>Agrupaciones de reconocimiento de ingresos

[!include [banner](../includes/banner.md)]

Este tema describe la funcionalidad de agrupación que se incluye en la capacidad de reconocimiento de ingresos en Clientes. Una agrupación comprende un elemento principal y varios elementos componentes. El elemento principal se introduce en un pedido de ventas, por lo que la entrada de pedidos es más eficiente. Sin embargo, luego se desglosa en los elementos componentes. Los documentos internos, como el albarán, enumerarán los elementos componentes. Sin embargo, los documentos externos solo mostrarán el elemento principal.

> [!NOTE]
> Los canales de Microsoft Dynamics 365 Commerce, como en línea, punto de venta (PDV) y centros de llamadas, no admiten el reconocimiento de ingresos (incluida la funcionalidad de agrupación). Esto también incluye la solución Cliente potencial a efectivo para Dynamics 365 Supply Chain Management y Dynamics 365 Sales. Los elementos que están configurados para usar el reconocimiento de ingresos no deben agregarse a pedidos o transacciones creados en los canales de Commerce ni en la solución Cliente potencial a efectivo.

Para configurar agrupaciones, debe introducir las claves de configuración para el reconocimiento de ingresos. Sin embargo, puede usar agrupaciones incluso si el reconocimiento de ingresos no está configurado. De igual forma, puede usar el reconocimiento de ingresos si las agrupaciones no están configuradas. Si se configura el reconocimiento de ingresos, los elementos componentes determinan el precio de ingresos y la programación de ingresos que se utiliza para el reconocimiento o aplazamiento de ingresos cuando se factura un pedido de ventas.

La configuración de las agrupaciones utiliza la funcionalidad de lista de materiales (L. MAT). Para obtener información sobre cómo configurar un elemento de agrupación, consulte [Configuración de Reconocimiento de ingresos](revenue-recognition-setup.md). Si el elemento principal está marcado como agrupación, se trata de manera diferente a otros elementos de la lista de materiales. Esta es una lista de las diferencias:

- Las agrupaciones deben desglosarse mediante la confirmación del pedido de venta, seleccionando **Confirmar orden de venta** en la pestaña **Vender** del panel de acciones, en la página del pedido de ventas. Los elementos de la agrupación nunca deben desglosarse seleccionando **Línea de lista de materiales**, en **Desglosar**, en el menú **Línea de pedido de ventas** de la ficha desplegable **Líneas de pedido de ventas**. De lo contrario, el elemento se tratará como una lista de materiales, no como una agrupación.
- Un pedido de ventas que contiene un elemento de agrupación debe confirmarse antes de crear el albarán o la factura.
- Cuando se desglosa una agrupación a través de la confirmación del pedido de ventas, el elemento principal se cancela y el precio unitario y los descuentos se asignan a los elementos componentes de la agrupación.
- La suma de los elementos componentes siempre debe ser igual al precio del elemento principal. Por lo tanto, existen limitaciones en los campos que pueden actualizarse o cambiarse para los elementos componentes. Por ejemplo, el precio unitario no se puede cambiar manualmente. Tampoco se puede cambiar indirectamente haciendo que entre en vigor un nuevo acuerdo de precios. Para evitar un nuevo acuerdo de precios, las dimensiones del inventario no se pueden cambiar en los elementos componentes.
- Cuando se imprime un documento de cara al exterior, como la confirmación del pedido de ventas o la factura, se imprime el elemento principal y no los elementos componentes.

## <a name="bundles-on-sales-orders"></a>Agrupaciones en pedidos de ventas

La empresa de demostración USMF incluye la siguiente configuración de agrupación. Tenga en cuenta que toda la configuración para el reconocimiento de ingresos, como la configuración de programaciones de ingresos, se ha eliminado de los elementos que se incluyen en este escenario.

**Elemento principal:** Agrupación de portátil

- **Elemento componente:** una cantidad de 1 del elemento 1000
- **Elemento componente:** una cantidad de 1 del elemento S0021
- **Elemento componente:** una cantidad de 1 del elemento Soporte

El *precio de venta base* de los elementos componentes es una parte esencial de la configuración de los componentes. El precio de venta base se define en la ficha desplegable **Vender** de un elemento. Se utiliza para calcular el factor de asignación cuando el precio unitario del elemento principal se asigna a los elementos componentes. Los precios de venta del acuerdo comercial nunca se utilizan con esta finalidad.

Los siguientes precios de venta base se definen para los elementos componentes:

- **1000:** 1.900,00 $
- **S0021:** 150,00 $
- **Soporte:** 500,00 $

Se introduce un pedido de ventas para el cliente US-004, Cave Wholesales. La única línea que se introduce es para el elemento Agrupación de portátil. El precio unitario predeterminado para la línea principal se puede tomar de varios lugares, como el acuerdo comercial o el precio de venta base. En este ejemplo, se introdujo 2.300 $ como precio unitario.

[![Elemento de agrupación de portátil en un pedido de ventas](./media/bundle-01.png)](./media/bundle-01.png)

Debido a que el pedido de ventas contiene una agrupación, debe confirmarse. El cuadro de diálogo de confirmación muestra los componentes de la agrupación.

[![Confirmar el cuadro de diálogo del pedido de ventas que muestra los elementos componentes](./media/bundle-02.png)](./media/bundle-02.png)

Sin embargo, el informe de confirmación impreso mostrará solo el elemento principal del paquete, porque ese informe es el documento de cara al exterior para el cliente.

[![Informe de confirmación que muestra solo el elemento principal](./media/bundle-03.png)](./media/bundle-03.png)

Una vez confirmado el pedido de ventas, el elemento principal sigue apareciendo en el pedido de ventas, pero su estado se ha cambiado a **Cancelado**. Además, el importe neto puede seguirse en el campo **Importe neto de la agrupación**. Esta cantidad es necesaria para imprimir la factura, porque la factura muestra el elemento principal y no los elementos componentes.

La suma de los elementos componentes debe ser igual al valor del **Importe neto de la agrupación** del artículo principal, porque ese valor es la cantidad que se presenta al cliente en la factura impresa. Para asegurarse de que la factura coincida con los importes registrados en la contabilidad general, están limitadas las modificaciones de los elementos componentes. Por ejemplo, el sitio y el almacén no se pueden cambiar, porque esos cambios pueden desencadenar un cambio de precio, según un acuerdo comercial.

El precio unitario de la línea del elemento principal se asigna a los componentes de la siguiente manera:

**Precios de venta base totales de componentes:** 1.900 $ + 500 $ + 150 $ = 2.550 $

- **Componente 1:** 2.300 $ × (1.900 ÷ 2.550) = 1.713,73 $
- **Componente 2:** 2.300 $ × (500 ÷ 2.550) = 450,98 $
- **Componente 3:** 2.300 $ × (150 ÷ 2.550) = 135,29 $

La suma de los componentes debe ser igual a 2.300 $ y, en efecto, es así (1.713,73 $ + 450,98 $ + 135,29 $ = 2.300 $).

Si se requieren cambios para todos los elementos componentes, se puede eliminar el elemento principal. En este caso, los elementos componentes también se eliminan. El elemento principal se puede volver a agregar, y las ediciones necesarias se pueden completar antes de confirmarse el pedido de ventas.

[![Agrupación de elementos que incluye cambios en los elementos componentes](./media/bundle-04.png)](./media/bundle-04.png)

Cuando se selecciona y empaqueta el pedido de ventas, los documentos incluirán solo los componentes de la agrupación. El albarán y la factura deben incluir una agrupación completa. De lo contrario, no se pueden registrar. Por ejemplo, el cuadro de diálogo muestra tres elementos componentes. Si intenta eliminar uno de ellos, recibirá un mensaje de error que indica que todos los productos de la agrupación deben enviarse antes de facturarlos.

Una agrupación debe enviarse y facturarse como una agrupación completa. Por ejemplo, si cambia la cantidad del elemento 1000 a 4, pero deja la cantidad del resto de elementos componentes en 5, el albarán y la factura no se pueden registrar.

Se puede enviar y facturar una cantidad parcial solo si la cantidad se reduce para todos los componentes de la agrupación. Por ejemplo, se ingresa una cantidad de 5 del elemento de la agrupación Portátil en un pedido de ventas. Una vez confirmado el pedido de ventas, los tres elementos componentes se muestran en el pedido de ventas y la cantidad de cada uno es 5. De forma predeterminada, durante el envío y la facturación, la cantidad se establecerá en 5 para cada componente. Sin embargo, puede rebajar la cantidad a 3 para los tres elementos componentes. En este caso, se enviarán y facturarán tres agrupaciones completas. Los dos elementos restantes de la agrupación (una cantidad de 2 de cada uno de los tres elementos componentes) se pueden enviar y facturar más tarde.

El último paso es facturar el pedido de ventas. Durante la facturación, el cuadro de diálogo de la factura mostrará los elementos componentes.

[![Cuadro de diálogo de factura que muestra los elementos componentes](./media/bundle-06.png)](./media/bundle-06.png)

Sin embargo, la factura impresa solo mostrará el elemento principal.
 
[![Factura impresa que muestra solo el elemento principal](./media/bundle-07.png)](./media/bundle-07.png)

El diario de facturas que se crea después del registro no incluye el elemento principal de la agrupación, porque dicho elemento tiene un estado de **Cancelado**.

[![Diario de facturas que no incluye el elemento principal](./media/bundle-08.png)](./media/bundle-08.png)

Es importante que el diario de facturas no incluya el elemento principal de la agrupación, porque los procesos que se realizan después de registrar la factura se basan en ese diario de facturas. Por ejemplo, si crea una nota de crédito desde la pestaña **Vender** del panel de acciones, la nota de crédito que se crea incluirá los elementos componentes, pero no el elemento principal.

[![Nota de crédito que muestra los elementos componentes pero no el elemento principal](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]