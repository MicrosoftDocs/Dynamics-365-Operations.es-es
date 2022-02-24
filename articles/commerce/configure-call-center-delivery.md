---
title: Configurar modos y cargos de entrega del centro de llamadas
description: Este tema describe cómo configurar los modos de entrega y los gastos para un pedido de centro de asistencia telefónica en Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bce2dac680871e14220d3bb94afacea0a617c707
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963119"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Configurar modos y cargos de entrega del centro de llamadas

[!INCLUDE [banner](includes/banner.md)]

Cuando un pedido de ventas se coloca en Dynamics 365 Commerce, si la persona que introdujo el pedido de ventas se vincula a un canal de centro de llamadas, la lógica y las reglas se utilizan para validar el modo de entrega (modo de entrega) y para calcular los gastos del pedido.

Al crear un pedido de ventas, puede seleccionar un modo de entrega en la cabecera del pedido de ventas y las líneas del pedido de ventas. De forma predeterminada, el modo de entrega que seleccione en la cabecera se utiliza para todas las líneas del pedido de ventas. No obstante, puede anular el modo de entrega predeterminada en las líneas de ventas individuales según necesite. También puede definir un modo de entrega en un registro de cliente. A continuación, cuando se crean los pedidos para el cliente, ese modo de entrega se utiliza de forma predeterminada en la cabecera del pedido de ventas.

Commerce tiene capacidades que permiten a los usuarios limitar los modos de entrega que puede utilizar un canal, los modos de entrega que se pueden utilizar para un producto, y los modos de entrega que son válidos para destinos de envío específicos. Los gastos también pueden definirse para que se agreguen comisiones adicionales al pedido de un cliente, en función de los modos de entrega que se seleccionen para el pedido de ventas y el valor del pedido total.

## <a name="define-delivery-modes"></a>Definir modos de entrega

Antes de que especifique los modos de entrega que se pueden utilizar para pedidos de centro de llamadas y definir las reglas y gastos asociados, debe definir los modos de entrega. Vaya a **Ventas y marketing \> Configuración \> Distribución \> Modos de entrega**. Seleccione **Nuevo** para crear un nuevo modo de entrega. De forma alternativa, seleccione un modo de entrega existente en la lista y, a continuación, seleccione **Editar** para hacer cambios.

En el campo **Modo de entrega**, puede introducir cualquier combinación de caracteres alfanuméricos, en función de su requisito empresarial. A continuación, puede utilizar el campo **Descripción** para proporcionar contexto adicional. Los campos **Grupo de gastos** y **Urgente** son opcionales y se explican con más detalle más adelante en este tema.

En la ficha desplegable **Canales de Commerce**, agregue cualquier canal comercial que debe permitirse para utilizar el modo de entrega cuando las transacciones de venta se creen en dicho canal.

En la ficha desplegable **Productos**, puede especificar los productos y/o categorías de productos que se pueden utilizar y no para el modo de entrega. Por ejemplo, si un producto no se puede enviar por aire debido a las restricciones de material peligroso (hazmat), asegúrese de que el producto o la categoría de producto se excluyen de todos los modos de entrega que implican el transporte aéreo.

En la ficha desplegable **Direcciones**, puede especificar los países, regiones o estados que se pueden utilizar y no para el modo de entrega. Por ejemplo, los pedidos que se envían a Hawái o Alaska no son aptos para una entrega terrestre. Por tanto, estos estados deben excluirse de cualquier modo de entrega que esté asociado a un servicio de entrega terrestre pero incluirse en cualquier modo de entrega que esté asociado a un servicio de entrega aérea.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Validar modos de entrega para un pedido de centro de llamadas

Una vez que se han definido los modos de entrega, debe ejecutar el trabajo por lotes **Procesar modos de entrega**. Este trabajo hace que los modos de entrega estén disponibles para que puedan utilizarse en procesos de pedidos de ventas para los canales. Para ejecutar el trabajo **Procesar modos de entrega**, vaya a **Retail y Commerce \> TI de Retail y Commerce \> Procesar modos de entrega**. Este trabajo debe ejecutarse en cualquier momento en que se agreguen nuevos modos de entrega a un canal o se realicen cambios en las relaciones existentes del modo de entrega/canal.

Una vez que ejecute el trabajo por lotes **Procesar modos de entrega**, puede ir a **Retail y Commerce \> Canales \> Centros de llamada \> Todos los centros de llamada**. En la página **Todos los centros de llamada**, en el panel de acciones, en la pestaña **Configurar**, seleccione **Modos de entrega**. La página **Modos de entrega** muestra todos los modos de entrega válidos para el canal de centro de llamadas seleccionado. Para editar modos de entrega existentes o agregar nuevos modos de entrega, seleccione **Administrar modos de entrega**. Tenga en cuenta que el trabajo **Procesar modos de entrega** debe ejecutarse siempre que se realicen cambios.

## <a name="define-charges-for-delivery-services"></a>Definir gastos para servicios de entrega

Cuando se crean pedidos de ventas para clientes, una empresa podría querer agregar gastos que se calculan automáticamente en función de los modos de entrega que se seleccionan para el pedido. Estos gastos se pueden configurar para que sean iguales para todos los clientes y modos de entrega. De forma alternativa, los gastos pueden variar en función del cliente y/o los modos de entrega que se seleccionan para el pedido de ventas.

Para definir los gastos, vaya al **Retail y Commerce \> Configuración de canal \> Cargos \> Gastos automáticos**. Seleccione **Nuevo** para agregar nuevos cargos. De forma alternativa, seleccione una entrada existente y, a continuación, seleccione **Editar**.

Los gastos se pueden definir para calcularlos a nivel de la cabecera del pedido o de las líneas de pedido. Utilice el campo **Nivel** para seleccionar el nivel deseado.

Los gastos se pueden definir para un cliente específico, un grupo de clientes o todos los clientes. En el campo **Código de cuenta**, seleccione **Tabla** para definir los gastos que se aplican solo a un cliente específico. Seleccione **Grupo** para definir los gastos para un grupo de clientes específico. Seleccione **Todos** para aplicar los gastos a cada cliente que coloque un pedido de ventas que utilice el modo de entrega relacionado. Si seleccionó **Tabla** o **Grupo** en el campo **Código de cuenta**, seleccione el cliente o grupo de clientes en el campo **Relación de cuentas**.

Los gastos se pueden configurar para aplicarlos para un modo de entrega específico, un grupo del modo de entrega o todos los modos de entrega. Si selecciona **Tabla** en el campo **Código del modo de entrega**, debe seleccionar un modo de entrega específico en el campo **Relación de modo de entrega**. Si selecciona **Grupo**, debe seleccionar un grupo de modo de entrega en el campo **Relación de modo de entrega**. Los grupos de modo de entrega se definen en **Retail y Commerce \> Configuración de canal \> Gastos \> Grupo de gastos de entrega**. A continuación, pueden vincularle a uno o más modos de entrega en la página **Modos de entrega**. Si selecciona un grupo al definir gastos, cualquier modo de entrega que esté vinculado al grupo de entrega seleccionado utiliza estos gastos. Por último, si selecciona **Todos** en el campo **Código del modo de entrega**, todos los modos de entrega utilizan los gastos. Por tanto, no selecciona un valor en el campo **Relación de modo de entrega**.

En la sección **Líneas**, puede definir uno o varios gastos por divisa, según necesite. Los gastos deben vincularse a un código de gastos que defina las reglas de registro financiero para el gasto. El campo **Categoría** se utiliza para definir cómo se calculan los gastos. Por ejemplo, si a los clientes se les debe cobrar una tarifa fija de 9,95 $ para que un pedido se envíe mediante un modo de entrega específico, utilice la categoría **Fijo**. Si el negocio decide cobrar a los clientes un porcentaje del pedido total para cubrir los gastos de entrega, utilice la categoría **Porcentaje**. El gasto real para los clientes se define en el campo **Valor de gastos**.

Las empresas suelen configurar gastos por niveles. En este caso, el importe que los clientes pagan para la entrega se basa en el valor del pedido. Para configurar los gastos por niveles, introduzca valores en los campos **Importe inicial** e **Importe final** además de definir el propio gasto en el campo **Valor de gastos**. Por ejemplo, para los pedidos que tengan un valor inferior a 50 €, un distribuidor gasta 5,95 $ por el envío terrestre. Para pedidos que tengan un valor que sea igual o superior a 50 $, pero inferior 100 $, el distribuidor gasta 7,95 $. Por último, para pedidos que tengan un valor que sea igual o superior a 50 $, pero inferior 100 $, el distribuidor ofrece un envío gratuito. La siguiente ilustración muestra la configuración de estos gastos.

![Ejemplo de gastos fijos por niveles](media/fixedtieredcharges.png)

Puede utilizar una combinación de categorías para los gastos, en función de sus requisitos empresariales. Por ejemplo, para todos los pedidos que tengan un valor inferior a 100 €, existe un gasto fijo de 9,95 $ por el envío. A continuación, para pedidos que tengan un valor igual o superior 100 $, los gastos de entrega se calculan en un índice del 5 por ciento del valor del pedido. La siguiente ilustración muestra la configuración de estos gastos.

![Ejemplo de gastos mixtos por niveles](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Aplicar modos de entrega durante la entrada de pedidos en un centro de llamadas

Cuando se crea un nuevo pedido de ventas, debe especificarse un valor en el campo **Modo de entrega** en el ficha desplegable **Entrega** de la cabecera del pedido de ventas. Este campo se podría completar automáticamente, en función de los valores predeterminados del registro del cliente.

El modo de entrega que se define en la cabecera del pedido se copia automáticamente en las líneas del pedido de ventas a medida que se crean. Sin embargo, puede cambiar la configuración del modo de entrega para un elemento de línea específico en la pestaña **Entrega** de la sección **Detalles de línea** de la página de entrada de pedidos de ventas.

Si el modo de entrega seleccionado no es válido para el producto o la dirección de entrega que se define para el pedido o la línea de pedido, recibe un mensaje de error. A continuación, debe seleccionar un modo de entrega que se ha definido para admitir esa configuración del producto o dirección.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Cálculo de gastos de entrega durante la entrada de pedidos

Si la configuración **Habilitar finalización de pedidos** está activada para su canal de centro de llamadas, los gastos de envío se calculan automáticamente para los pedidos de ventas cuando los usuarios seleccionan **Completar**. El siguiente mensaje aparece en la parte superior de la página **Resumen de pedido de ventas**: "Gastos por niveles calculados". Los gastos que se calculan se agregan al valor del campo **Total de ventas**. En el ficha desplegable **importe**, el campo **Gastos** muestra el importe total de todos los gastos que se han calculado para el pedido y las líneas. Para ver un desglose más detallado de los gastos, seleccione **Pedido** en la página **Resumen de pedido de ventas** y, a continuación, seleccione la opción **Gastos** para ver, agregar o editar los gastos. Tenga en cuenta que el cálculo de los gastos de entrega en la cabecera del pedido se basa en el modo de entrega que se vincula a la cabecera. Los gastos de entrega de nivel de línea se calculan en función del modo de entrega que se configura para la línea de ventas. Si se utilizan varios modos de entrega en distintas líneas, se pueden aplicar varios gastos y agregarse juntos. A continuación, el importe total se muestra en el campo **Gastos** en la página **Resumen de pedido de ventas**.

Si se desactiva la configuración **Habilitar finalización de pedidos**, los usuarios deben activar manualmente el cálculo de gastos. En la página **Pedido de ventas**, en el panel de acciones, en la pestaña **Vender**, en el grupo **Calcular**, seleccione **Gastos por niveles**. Se muestra el mensaje "Gastos por niveles calculados". A continuación, puede seleccionar la opción **Gastos** en la pestaña **Vender** para ver, editar o eliminar los gastos calculados.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Utilizar modos de entrega urgentes en pedidos de centro de llamadas

De forma opcional, puede vincular un código de urgencia a cualquier modo de entrega que configure. Este código se utiliza como una herramienta de ordenación y generación de informes de priorización. En este momento, no se aplican comisiones adicionales al pedido. Para configurar códigos de urgencia, vaya a **Ventas y marketing \> Configuración \> Distribución \> Código de urgencia**.

Por ejemplo, para pedidos que se enviarán por aire al día siguiente, el picking se debe realizar cada día en el almacén aproximadamente las 13:00. En este caso, se puede crear un código de urgencia, y ese código se puede vincular a cualquier modo de entrega al día siguiente que se configure en el sistema. Cuando el almacén crea su oleada de picking, el código de urgencia adecuado en el campo **Urgente** se pueden utilizar como un filtro, de manera que el picking se ejecuta solo para pedidos que tienen modos de entrega que se vinculan a ese código.

Además, cuando se introduce un pedido del centro de llamadas, se puede aplicar manualmente un código de urgencia a la cabecera del pedido de ventas o a una línea de pedido de ventas individual. Una vez más, el código se puede usar con fines de ordenación o creación de informes A veces, un pedido debe manipularse con cuidado debido a un problema de servicio de atención al cliente. En este caso, se puede aplicar un código de urgencia específico a la cabecera o las líneas del pedido para ayudar a identificar y a dar prioridad al pedido durante el proceso de suministro.
