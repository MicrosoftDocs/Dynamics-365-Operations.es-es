---
title: Retenciones de crédito para pedidos de ventas
description: En este tema se describe la configuración de las reglas utilizadas para colocar un pedido de ventas en retención de crédito.
author: JodiChristiansen
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 14cafa69e75d7e8a0f08fb385a8c364c0162da1ec609a4e0b3cad6178ec3f716
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723976"
---
# <a name="credit-holds-for-sales-orders"></a>Retenciones de crédito para pedidos de ventas
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este tema se describe la configuración de las reglas utilizadas para colocar un pedido de ventas en retención de crédito. Las reglas de bloqueo de la administración de crédito pueden aplicarse a un cliente individual o a un grupo de clientes. Las reglas de bloqueo definen respuestas a las siguientes circunstancias:

1. Número de días vencido
2. Estado de cuentas
3. Condiciones de pago
4. Límite de crédito vencido
5. Importe vencido
6. Importe de pedido de ventas
7. Parte usada del crédito disponible

Además, hay dos parámetros que controlan escenarios adicionales que bloquearán un pedido de ventas

1. Cambio en las condiciones de pago
2. Cambio en los descuentos de liquidación

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Configurar reglas de bloqueo y reglas de exclusión

Cuando un cliente inicia una transacción de ventas, la información en el pedido de ventas se revisa con un conjunto de reglas de bloqueo que guían la decisión de ampliar o no el crédito al cliente, y permitir continuar con la venta. También puede definir exclusiones que anulen las reglas de bloqueo y permitan que se procese un pedido de ventas. Puede configurar reglas de bloqueo y reglas de exclusión en la página **Administración de crédito > Configuración > Configuración de administración de crédito> Reglas de bloqueo**.

A partir de la versión 10.0.21, las reglas de bloqueo de la Administración de crédito se han rediseñado de las siguientes formas para proporcionar más flexibilidad:

- Se han habilitado las solicitudes de extensibilidad para que pueda crear sus propias reglas de bloqueo.
- La casilla **Despachar pedido de venta** ahora está disponible para todas las reglas de bloqueo. Anteriormente, solo estaba disponible para la regla de bloqueo Pedido de ventas. Cuando se activa esta casilla, la regla de exclusión liberará el pedido de ventas sin tener en cuenta ninguna otra regla que pueda bloquear los pedidos de ventas. Esta casilla solo está disponible para el tipo de regla **Exclusión**.

### <a name="days-overdue"></a>Días desde el vencimiento

Abre la pestaña **Días desde el vencimiento** si la regla de bloqueo se aplica al cliente con una o más facturas vencidas durante un número de días determinado.
1. Seleccione el rango de clientes al que se aplica esta regla, según **Válido para**.
   - Seleccione **Tabla** si la regla se aplica a un cliente específico.
   - Seleccione **Grupo** si la regla se aplica a nivel de grupo de clientes. 
   - Seleccione **Todos** si la regla se aplica a todos los clientes.
2. Cuando haya especificado el rango, debe especificar qué **Cuenta/grupo** se usará en el rango.
   - Para el rango **Tabla**, la búsqueda proporcionará una lista de clientes que se pueden seleccionar. 
   - Seleccione un **Grupo** si la regla se aplica a un grupo de crédito de clientes.
   - Seleccione **Todos** si la regla se aplica a todos los clientes. 
3. Seleccione **Grupo de riesgo** con el fin de utilizar criterios para aplicar una retención de la administración de créditos a los clientes agrupados por un conjunto de factores comunes, como su calificación Dun and Bradstreet, la cantidad de años que han estado en el negocio, la cantidad de tiempo que han sido su cliente, etc.  
4. Seleccione el tipo de proyecto que está configurando. La opción **Bloqueo** creará una regla que bloquea un pedido. La opción **Exclusión** creará una regla que excluirá a otra regla de bloquear un pedido. 
5. Seleccione un **Tipo de valor**. La entrada predeterminada es un número fijo de días. Si va a crear una exclusión, puede especificar un número fijo de días o un importe en su lugar. 
6. Introduzca en **Vencido** el número de días vencidos que se permitirán para la regla de bloqueo seleccionada antes de colocar un pedido en espera de administración de crédito para su revisión. El número de días vencidos representa un número adicional de días de gracia que se agregan al número de días más allá de la fecha de vencimiento del pago que puede tener la factura antes de que se considere vencida. Si especificó el **Tipo de valor** como un importe para una exclusión, introduzca un importe y una divisa para ese importe.

### <a name="account-status"></a>Estado de cuenta

Abre la pestaña **Estado de cuentas** si la regla de bloqueo se aplica a un cliente con el estado de cuentas seleccionado.
1. Seleccione el tipo de proyecto que está configurando.  La opción **Bloqueo** creará una regla que bloquea un pedido. La opción **Exclusión** creará una regla que excluirá a otra regla de bloquear un pedido. 
2. Seleccione el **Estado de cuentas** que hará que la regla coloque un pedido de ventas en espera o lo excluya.

### <a name="terms-of-payment"></a>Condiciones de pago

Seleccione **Condiciones de pago** si la regla de bloqueo se aplica al plazo de pago seleccionado.
1. Seleccione el tipo de proyecto que está configurando.  La opción **Bloqueo** creará una regla que bloquea un pedido. La opción **Exclusión** creará una regla que excluirá a otra regla de bloquear un pedido. 
2. Seleccione las **Condiciones de pago** que harán que la regla coloque un pedido de ventas en espera o lo excluya.

### <a name="credit-limit-expired"></a>Límite de crédito vencido

Abre la pestaña **Límite de crédito vencido** si la regla de bloqueo se aplica a clientes con límites de crédito que han expirado.
1. Seleccione el rango de clientes al que se aplica esta regla, según **Válido para**.
   - Seleccione **Tabla** si la regla se aplica a un cliente específico.
   - Seleccione **Grupo** si la regla se aplica a nivel de grupo de clientes. 
   - Seleccione **Todos** si la regla se aplica a todos los clientes.
2. Cuando haya especificado el rango, debe especificar qué **Cuenta/grupo** se usa en el rango.
   - Para el rango **Tabla**, la búsqueda proporcionará una lista de clientes que se pueden seleccionar. 
   - Seleccione un **Grupo** si la regla se aplica a un grupo de administración de crédito de cliente.
   - Seleccione **Todos** si la regla se aplica a todos los clientes. 
3. Seleccione un **Grupo de riesgo** para limitar todavía más la lista de clientes que se pondrán en espera de administración de crédito. 
4. Seleccione el tipo de proyecto que está configurando. 
   - Seleccione **Bloqueo** para crear una regla que bloquea un pedido. 
   - Seleccione **Exclusión** para crear una regla que excluirá a otra regla de bloquear un pedido. 
5. Introduzca los **Días de límite de crédito vencido** para la regla de bloqueo seleccionada antes de que se coloque un pedido en espera de administración de crédito. El número de días vencidos representa días de gracia adicionales que se agregan al número de días de vencimiento del límite de crédito.

### <a name="overdue-amount"></a>Importe vencido

Abra la pestaña **Importe vencida** si la regla de bloqueo se aplica a clientes con importes vencidos.
1. Seleccione el rango de clientes al que se aplica esta regla, según **Válido para**.
   - Seleccione **Tabla** si la regla se aplica a un cliente específico.
   - Seleccione **Grupo** si la regla se aplica a nivel de grupo de clientes. 
   - Seleccione **Todos** si la regla se aplica a todos los clientes.
2. Cuando haya especificado el rango, debe especificar qué **Cuenta/grupo** se usa en el rango.
   - Para el rango **Tabla**, la búsqueda proporcionará una búsqueda de clientes. 
   - Seleccione un **Grupo** si la regla se aplica a un grupo de administración de crédito de cliente.
   - Seleccione **Todos** si la regla se aplica a todos los clientes. 
3. Seleccione un **Grupo de riesgo** si desea limitar todavía más la lista de clientes que se pondrán en espera de administración de crédito. 
4. Seleccione el tipo de proyecto que está configurando. 
   - Seleccione **Bloqueo** para crear una regla que bloquea un pedido. 
   - Seleccione **Exclusión** para crear una regla que excluirá a otra regla de bloquear un pedido. 
5. Introduzca el **Importe vencido** para la regla de bloqueo seleccionada antes de que se coloque un pedido en espera de administración de crédito. 
6. Seleccione el **Tipo de valor** que define el tipo de valor que se usará para probar también cuánto del límite de crédito se ha usado. Las reglas de bloqueo y las reglas de exclusión solo permiten un porcentaje para **Importe vencido**. El umbral se relaciona con el límite de crédito.
7. Introduzca el valor del **Umbral de límite de crédito** para la regla seleccionada antes de que un cliente quede en espera de administración de crédito. Puede ser un importe o un porcentaje según el tipo de valor seleccionado en el tipo de valor.
8. La regla comprueba que se superan el **Importe vencido** y el **Umbral de límite de crédito**. 

### <a name="sales-order"></a>Pedido de ventas 

Seleccione **Pedido de ventas** si la regla de bloqueo se aplica al valor del pedido de ventas.
1. Seleccione el rango de clientes al que se aplica esta regla, según **Válido para**.
   - Seleccione **Tabla** si la regla se aplica a un cliente específico.
   - Seleccione **Grupo** si la regla se aplica a nivel de grupo de clientes. 
   - Seleccione **Todos** si la regla se aplica a todos los clientes.
2. Cuando haya especificado el rango, debe especificar qué **Cuenta/grupo** se usa en el rango.
   - Para el rango **Tabla**, la búsqueda proporcionará una búsqueda de clientes. 
   - Seleccione un **Grupo** si la regla se aplica a un grupo de administración de crédito de cliente.
   - Seleccione **Todos** si la regla se aplica a todos los clientes. 
3. Seleccione un **Grupo de riesgo** si desea limitar todavía más la lista de clientes que se pondrán en espera de administración de crédito. 
4. Seleccione el tipo de proyecto que está configurando.  
   - Seleccione **Bloqueo** para crear una regla que bloquea un pedido. 
   - Seleccione **Exclusión** para crear una regla que excluirá a otra regla de bloquear un pedido. 
5. Introduzca el **Importe de pedido de ventas** para la regla de bloqueo seleccionada antes de que se coloque un pedido en espera de administración de crédito. 

### <a name="credit-limit-used"></a>Límite de crédito utilizado

Seleccione **Límite de crédito utilizado** si la regla de bloqueo se aplica al importe de límite de crédito del cliente utilizado.
1. Seleccione el rango de clientes al que se aplica esta regla, según **Válido para**.
   - Seleccione **Tabla** si la regla se aplica a un cliente específico.
   - Seleccione **Grupo** si la regla se aplica a nivel de grupo de clientes. 
   - Seleccione **Todos** si la regla se aplica a todos los clientes.
2. Cuando haya especificado el rango, debe especificar qué **Cuenta/grupo** se usa en el rango.
   - Para el rango **Tabla**, la búsqueda proporcionará una búsqueda de clientes. 
   - Seleccione un **Grupo** si la regla se aplica a un grupo de administración de crédito de cliente.
   - Seleccione **Todos** si la regla se aplica a todos los clientes. 
3. Seleccione un **Grupo de riesgo** si desea limitar todavía más la lista de clientes que se pondrán en espera de administración de crédito. 
4. Seleccione el tipo de proyecto que está configurando.
   - Seleccione **Bloqueo** para crear una regla que bloquea un pedido. 
   - Seleccione **Exclusión** para crear una regla que excluirá a otra regla de bloquear un pedido. 
5. Selecciona el **Umbral restante** que define el porcentaje del límite de crédito que bloqueará el pedido de ventas. Si el valor de un pedido aumenta el importe del límite de crédito utilizado por encima del porcentaje, el pedido se pondrá en espera. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Poner un pedido de cliente en espera según otros criterios
  
### <a name="rank-payment-terms"></a>Clasificar condiciones de pago  

Puede forzar la ejecución de las reglas de control de crédito cuando se cambian las condiciones de pago. Debe clasificar las condiciones de pago y asignarles un valor de clasificación. Si cambia las condiciones de pago en el pedido a condiciones de pago que están clasificadas por encima de las condiciones de pago anteriores, el pedido se enviará a la administración de crédito y requerirá aprobación.

Puede configurar las clasificaciones de condiciones de pago en la página **Administración de crédito > Configuración > Configuración de administración de crédito > Clasificar condiciones de pago**.

1. Seleccione las condiciones de pago en el campo **Condiciones de pago** para clasificar; al seleccionar unas condiciones, su descripción se mostrará en el campo **Descripción**.
2. Seleccione la clasificación de las condiciones en el campo **Clasificación**. Todos los valores son relativos entre sí, por lo que puede usar 1,2,3 o 10,20,30. También puede usar el mismo valor para la mayoría de las condiciones de pago, de forma que solo una o dos condiciones de pago activen la comprobación de crédito.

### <a name="rank-settlement-discounts"></a>Clasificar descuentos de liquidación   

Puede forzar la ejecución de las reglas de control de crédito cuando se cambian los descuentos de liquidación. Debe clasificar los descuentos de liquidación y asignarles un valor de clasificación. Si cambia los descuentos de liquidación en el pedido a descuentos de liquidación que están clasificados por encima de los descuentos de liquidación anteriores, el pedido se enviará a la administración de crédito y requerirá aprobación.

Puede configurar las clasificaciones de condiciones de pago en la página **Administración de crédito > Configuración > Configuración de administración de crédito > Clasificar descuentos de liquidación**.

1. Seleccione el **Descuento por pronto pago** que desee clasificar. Se mostrará la **Descripción** del descuento de liquidación.
2. Seleccione el valor **Clasificación**. Todos los valores son relativos entre sí, por lo que puede usar 1,2,3 o 10,20,30. También puede usar el mismo valor para la mayoría de los descuentos de liquidación, de forma que solo uno o dos descuentos de liquidación activen la comprobación de crédito.

## <a name="sequence-the-application-of-rules"></a>Secuenciar la aplicación de reglas

Las reglas se ejecutan en un orden específico que cambia para adaptarse a las necesidades de su organización. 

- Una instancia de las reglas de exclusión de pedidos de ventas le permite anular todas las reglas que pueden bloquear un pedido de ventas. Cree una regla de exclusión de pedidos de ventas y marque la opción **Liberar pedido de ventas**. El pedido no se pondrá en espera si esa regla de exclusión es verdadera, y no se comprobará ninguna otra regla.
- Las reglas de bloqueo pueden poner el pedido en espera.
- Las reglas de exclusión se ejecutan a continuación de las reglas de bloqueo. Las reglas de exclusión solo afectarán a la regla en la que se definen. 
- Las reglas de bloqueo y exclusión se ejecutan en Tabla, a continuación en Grupo y después en Todos los pedidos. Debido a este orden de procesamiento, es posible tener una regla de bloqueo del nivel Todas que no se ejecutará porque se ejecuta una regla de exclusión en el nivel de Tabla o Grupo.
- Las exclusiones no anulan la regla de bloqueo si están en el mismo nivel. Por ejemplo, una regla de exclusión a nivel de grupo no anulará la regla de bloqueo a nivel de grupo. No necesitará configurar exclusiones en el nivel Todas excepto como se indicó anteriormente con la instancia de la regla de exclusión de pedidos de ventas. 

El comportamiento de la regla **Límite de crédito utilizado** cambiará en función de la configuración del parámetro **Comprobar el límite de crédito para el pedido de ventas** que se encuentra en el formulario de parámetros de Crédito y cobros.
- Si el parámetro se establece en No, la regla de límite de crédito utilizado no se ejecutará.
- Si el parámetro se establece en Sí y el **Mensaje que aparece al exceder el límite de crédito** está configurado como advertencia, recibirá una advertencia cuando se exceda el límite de crédito. Las reglas de **Límite de crédito utilizado** se ejecutarán para ver si tiene reglas que desea ejecutar. Sin embargo, normalmente no agregaría ninguna regla para este escenario.
- Si el parámetro se establece en Sí y el **Mensaje que aparece al exceder el límite de crédito** se establece en error, se comprobará el límite de crédito y el pedido se pondrá en espera si se excede el límite de crédito. Además, se ejecutarán las reglas de **Límite de crédito utilizado** para ver si hay reglas adicionales que deban ejecutarse. No se mostrará un mensaje de error, pero se mostrará el motivo de bloqueo del **Límite de crédito excedido**. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>Valores de configuración que cambiarán la forma en que se pone un pedido en espera

Los pedidos se pueden excluir de la administración de crédito aunque haya reglas vigentes. 

- Si cambia la opción de configuración **Excluir cliente de la administración de crédito** en **Todos los clientes > Ficha desplegable Crédito y y cobros** a **Sí**, no se procesarán pedidos para ese cliente
- Si cambia el valor **Excluir de la administración de crédito** en el **encabezado de pedidos de ventas** en la **Ficha desplegable Administración de crédito** a **Sí**, las reglas de administración de crédito no se procesarán. Esta opción de configuración solo la puede establecer el empleado de crédito o el administrador de crédito.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>Procesamiento de pedidos en espera mediante la lista de retención de la administración de crédito

La lista de retención de Administración de crédito permite a los administradores de crédito ver todos los pedidos de ventas que se han puesto en espera y les permite quitar las retenciones cuando se hayan solucionado los problemas de crédito. La página **Lista de retención de administración de crédito** muestra todos los pedidos de ventas que se han puesto en espera. Puede ver la lista de retención en la página **Todas las retenciones de crédito** (**Administración de crédito > Lista de retención de administración de crédito> Todas las retenciones de crédito**).
Los pedidos de ventas de todas las entidades jurídicas se envían a la misma lista de retención de administración de crédito, lo que proporciona una vista centralizada de todas las transacciones que requieren atención. Los usuarios solo verán información para las entidades jurídicas a las que tienen acceso.

Se puede colocar un pedido de ventas en la lista de retención por los siguientes motivos:
1. El cliente tiene una factura vencida por un número específico de días. 
2. El pedido tiene un estado de cuenta específico.
3. El pedido tiene condiciones de pago específicas.
4. El cliente tiene un límite de crédito vencido.
5. El cliente tiene un importe vencido y ha utilizado un porcentaje específico de su límite de crédito.
6. El pedido de ventas supera un importe determinado.
7. El cliente ha superado un porcentaje determinado de su límite de crédito.
8. Las condiciones de pago difieren de las condiciones de pago predeterminadas para el cliente.
9. Los descuentos de liquidación difieren del descuento de liquidación predeterminado para el cliente.

El motivo de bloqueo se muestra para cada pedido de ventas en la lista de retención. Si hay más de una razón para la retención, se mostrará como **Varios**. Puedes usar el menú **Motivos del bloqueo** en el panel de acciones para ver todos los motivos por los que el pedido de ventas se puso en espera. También puede ver los **Motivos del bloqueo** en un cuadro informativo.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Liberación de pedidos de la lista de retención para su procesamiento

Cuando haya investigado los motivos de la retención y los haya solucionado, puede liberar los pedidos de ventas para su posterior procesamiento.

1) Seleccione una línea en la lista de retención. Puede liberar varios pedidos seleccionando más de una línea.
2) Seleccione un **Motivo de liberación** para el pedido que se ha seleccionado para su liberación.  
3) Introduzca la **Fecha de revisión** para cada pedido que se haya seleccionado para su liberación.  
4) Selecciona el menú **Liberar** en el panel de acciones para liberar un pedido. Este menú solo estará disponible después de que se hayan seleccionado transacciones. Al usuario se le presentan dos opciones:
   - Seleccione **Con registro** para eliminar la retención y registrar el documento mediante el mismo proceso de registro que se utilizó cuando se puso en espera. Por ejemplo, si la confirmación del pedido de ventas se puso en espera, la confirmación del pedido de ventas se completará después de la liberación. Se mostrará el formulario de registro de pedidos de ventas que permite al usuario registrar la confirmación.
   - Seleccione **Sin registrar** para eliminar la retención sin realizar ningún procesamiento adicional. El pedido de ventas se puede registrar manualmente.

### <a name="rejecting-orders-in-the-hold-list"></a>Rechazar pedidos en la lista de retención
Puede usar el menú **Rechazar** en el panel de acciones para rechazar un pedido de ventas
1. Seleccione una línea en la lista de retención. Puede liberar varios pedidos seleccionando más de una línea.
2. El pedido se quitar de la lista de retención y el encabezado del pedido de ventas se actualizará para mostrar que se rechazó el pedido.

### <a name="automatically-releasing-credit-management-holds"></a>Liberación automática de retenciones de administración de crédito
Los pedidos de ventas se colocan en la lista de retención según las reglas de bloqueo. Sin embargo, algunas razones para las retenciones pueden cambiar con el tiempo si el pedido de ventas permanece en la lista de retención por un período de tiempo. Por ejemplo, un cliente puede pagar su factura, liberando así su límite de crédito. 

Puedes usar el menú **Evaluar para liberar** para revisar los pedidos de ventas de la lista de retención y liberarlos automáticamente si se ha solucionado el motivo de la retención.
1.  Seleccionar el menú **Evaluar para liberar**
2.  Seleccione **Procesar reglas de bloqueo** para revisar todos los pedidos de ventas. Seleccione **Procesar reglas de bloqueo para líneas seleccionadas** para revisar únicamente las líneas que ha seleccionado.
3. Aparecerá un control deslizante para que pueda seleccionar un solo cliente. Deje el menú desplegable del cliente en blanco para todos los clientes. 
4. Cuando haga clic en Aceptar, el proceso se ejecutará en segundo plano y podrá continuar trabajando en otras tareas. Si selecciona el procesamiento por lotes antes de hacer clic en Aceptar, el proceso se ejecutará por lotes cuando haga clic en Aceptar. El procesamiento de los pedidos en espera de la lista puede tardar. Para actualizar el estado de los pedidos, haga clic en Actualizar. 
5.  Si un motivo de bloqueo ya no es aplicable para un pedido, se considerará que el motivo de bloqueo ya no es válido y, cuando vea los motivos de bloqueo, dejará de ver una marca de verificación junto al motivo.
6.  Si se borran todos los motivos de bloqueo, se agrega una nueva razón, **Listo para liberar**, a la lista de motivos de bloqueo. El pedido de ventas se puede liberar automáticamente.
7.  Si el parámetro **Liberar automáticamente** de la pestaña **Crédito y cobros > Configuración > Parámetros de crédito y cobros > Crédito > Liberación automática** se establece en **Con registro**, se le pedirá que registre con el formulario de registro para el documento bloqueado.
8.  Si el parámetro **Liberar automáticamente** de la pestaña **Crédito y cobros > Configuración > Parámetros de crédito y cobros > Crédito > Liberación automática** se establece en **Sin registro**, se le pedirá que registre el pedido manualmente.

### <a name="credit-management-approval-workflow"></a>Flujo de trabajo de aprobación de administración de crédito

También puede crear **Flujos de trabajo de administración de crédito** para controlar la liberación de las retenciones de crédito. Una vez que haya configurado el flujo de trabajo a través de la página **Administración de crédito > Configuración> Flujos de trabajo de administración de crédito**, los pedidos marcados para liberación o rechazo se enviarán al flujo de trabajo donde deben ser aprobados antes de ser liberados o rechazados. 

Si incluye las tareas de liberación con registro o liberación sin registro en su flujo de trabajo, la aprobación del flujo de trabajo también liberará el pedido de ventas. Sin embargo, en caso de error en el proceso de liberación por falta de información de configuración u otras causas, deberá recuperar el pedido de ventas del flujo de trabajo, solucionar el problema que causó el error y luego volver a enviar el pedido al flujo de trabajo.

Si no incluye las tareas para la liberación con registro o la liberación sin registro en su flujo de trabajo, el proceso de aprobación del flujo de trabajo simplemente le permitirá liberar el pedido de ventas manualmente una vez que se haya completado la aprobación.

### <a name="forced-credit-hold"></a>Retención crediticia forzada  
  
A veces, puede ser necesario bloquear los pedidos de ventas aunque el pedido no cumpla los criterios de las reglas de bloqueo. Por ejemplo, un administrador de crédito puede recibir una notificación de un problema no relacionado con el cliente y decidir poner manualmente los pedidos en espera de inmediato hasta que se resuelva el problema. Puede forzar manualmente que un pedido de ventas esté en espera si se produce esa situación.

1. Abra el pedido de ventas que desea poner en espera.  
2. Seleccione **Forzar retención de crédito** en la pestaña **Administración de crédito** en el panel de acciones de **Administración de crédito**.
3. Seleccione un **Motivo de retención forzada**.
4. Haga clic en **Aceptar**. El pedido de ventas se devolverá a la lista de retención de Administración de crédito.

También puede forzar la espera de varios pedidos en la página **Administración de crédito > Tareas periódicas > Forzar retención de crédito**. Puede, por ejemplo, poner todos los pedidos de ventas en espera para un cliente determinado.
1. Seleccione el **Motivo de retención forzada**. 
2. Hacer clic **Registros que incluir** para seleccionar los pedidos de ventas que desea poner en espera. 
3. Haga clic en **Aceptar** para procesar los pedidos de ventas seleccionados.

Los pedidos de ventas que se han en espera de manera forzada no se pueden procesar con el flujo de trabajo.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>Liberación de pedidos que se agregaron a la lista de retención de administración de crédito con una retención de crédito forzada
Los pedidos de ventas que tienen un motivo de retención forzada no se pueden liberar automáticamente. Si el pedido de ventas se puso en espera de manera forzada y ha utilizado un proceso que libera automáticamente pedidos de ventas, el pedido de ventas se mostrará como **Listo para liberar** y permanecer en la lista de espera. Debe usar el menú **Liberar** para liberar el pedido.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Compatibilidad con facturas de servicios, pedidos y soporte de facturas de proyectos en Administración de crédito 
Actualmente, la administración de crédito solo se puede usar para pedidos de ventas. Las facturas de servicios, los pedidos de punto de venta y los pedidos de centro de llamadas utilizarán los límites de crédito temporales y los seguros/garantías que agregue para ajustar el límite de crédito. No utilizarán las reglas de bloqueo y no se incluirán en la lista de retención si hay un problema con el límite de crédito.

En la administración de crédito no se admiten facturas de proyectos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
