---
title: Ajustes del límite de crédito
description: En este artículo se explica cómo configurar y agregar ajustes de límite de crédito.
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fa4721be1e213afbaaeaa475be2697c8e55426a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891736"
---
# <a name="credit-limit-adjustments"></a>Ajustes del límite de crédito 

[!include [banner](../includes/banner.md)]

Los ajustes del límite de crédito permiten a los administradores de crédito actualizar los límites de crédito y las fechas de vencimiento de un solo cliente, un grupo de clientes o todos los clientes, a través de un proceso de contabilización. Puede agregar entradas de ajuste de límite de crédito para actualizar clientes y grupos de crédito de clientes, o puede usarlas para calcular límites de crédito automáticos. Estas entradas se pueden revisar, enviar para su aprobación a través de un flujo de trabajo y publicar en las cuentas de los clientes.

## <a name="set-up-credit-limit-adjustments"></a>Configurar ajustes de límite de crédito

Puede crear entradas en el diario de **Ajuste del límite de crédito** en la página **Ajuste del límite de crédito** (**Administración de crédito \> Ajustes de límite de crédito \> Ajustes de límite de crédito**).

1. Seleccione **Nuevo**. Se crea un grupo nuevo de entradas que tiene un número de ajuste de límite de crédito.
2. Seleccione el tipo de ajuste de límite de crédito:

    - Seleccione **Límite de crédito** para cambiar el límite de crédito del cliente.
    - Seleccione **Límite de crédito temporal** para crear un límite de crédito temporal en lugar de cambiar el límite de crédito actual del cliente. Los límites de crédito temporales anulan el límite de crédito de un cliente por un período definido. Una vez finalizado ese período, el límite de crédito del cliente se usa nuevamente.
3. Escribir una descripción. 

Si la casilla **Contabilizado** está activada, se han aplicado los límites de crédito. El campo **Estado de aprobación** el estado del flujo de trabajo del diario. Un flujo de trabajo es opcional.

### <a name="add-credit-limit-adjustments"></a>Agregar ajustes de límite de crédito

Para agregar manualmente ajustes de límite de crédito, seleccione **Líneas** y, a continuación, siga estos pasos.

1. Para agregar un ajuste de límite de crédito para un cliente, use el menú **Ajustes del cliente**. Para agregar un límite de crédito para un grupo de crédito de cliente, seleccione **Ajustes de grupo de crédito de cliente**.
2. Introduzca una cuenta de cliente para la cuenta de cliente de factura que debe actualizarse con el nuevo límite de crédito. Si seleccionó **Ajustes de grupo de crédito de cliente** en el paso 1, introduzca el grupo de crédito de cliente. No puede ingresar una cuenta de cliente y un id. de grupo de crédito de cliente en la misma línea de diario.

    Se muestra el límite de crédito actual y el nombre aparece automáticamente.

3. Introduzca el nuevo límite de crédito que debe reemplazar el límite de crédito actual cuando se registra la entrada de límite de crédito.
4. Introduzca una fecha para definir la nueva fecha de vencimiento para el límite de crédito de cliente. Cuando cree un ajuste de límite de crédito debe introducir una fecha de vencimiento del límite de crédito.

El campo **Estado de aprobación** indica el estado del flujo de trabajo de la línea del diario.

Si desea que los ajustes del límite de crédito se generen automáticamente, puede usar el menú **Generar** en el panel de acciones.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Agregar ajustes temporales de límite de crédito

Para agregar manualmente ajustes temporales de límite de crédito, siga estos pasos para las líneas de diario.

1. Para agregar un ajuste de límite de crédito para un cliente, use el menú **Ajustes del cliente**. Para agregar un límite de crédito para un grupo de crédito de cliente, seleccione **Ajustes de grupo de crédito de cliente**.
2. Introduzca una cuenta de cliente para la cuenta de cliente de factura que debe actualizarse con el nuevo límite de crédito. Si seleccionó **Ajustes de grupo de crédito de cliente** en el paso 1, introduzca el grupo de crédito de cliente. No puede ingresar una cuenta de cliente y un id. de grupo de crédito de cliente en la misma línea de diario.

    Si ya existe un límite de crédito temporal activo o futuro, aparecen el límite de crédito temporal actual y los intervalos de fechas para cada límite de crédito temporal. El nombre aparece automáticamente.

3. Introduzca el nuevo límite de crédito que debe reemplazar al límite de crédito actual.
4. En los campos **Nueva fecha inicial** y **Nueva fecha final**, defina el período en el que el límite de crédito avanzado es válido. Cuando cree un diario de ajuste de límite de crédito debe introducir fechas de vencimiento del límite de crédito.

El campo **Estado de aprobación** indica el estado del flujo de trabajo de la línea del diario.

## <a name="generate-credit-limit-adjustments"></a>Generar ajustes de límite de crédito

También puede hacer que los límites de crédito se ajusten automáticamente. En el panel de acciones, seleccione **Generar** y, a continuación, seleccione una de las opciones siguientes:

- De cliente existente
- De grupo de crédito de cliente existente
- Límites de crédito automáticos

### <a name="from-existing-customer"></a>De cliente existente

Puede crear líneas de diario a partir de clientes existentes. Cuando se selecciona **Generar \> De cliente existente**, aparece un cuadro de diálogo en el que puede proporcionar criterios para seleccionar clientes y calcular los nuevos límites.

1. Introduzca un valor de ajuste para sumar o restar un importe del límite de crédito. Introduzca un valor negativo para disminuir el límite de crédito actual o un valor positivo para aumentarlo.
2. En el **Tipo de valor**, seleccione cómo se debe usar el valor que especificó en el paso 1 para calcular el nuevo límite de crédito:

    - Seleccione **Valor fijo** para cambiar el límite de crédito por un importe.
    - Seleccione **Porcentaje** para cambiar el límite de crédito por un porcentaje.

3. Introduzca un valor que se utilizará para redondear el límite de crédito calculado. Por ejemplo, introduzca **10,00** para redondear el límite de crédito a las 10,00 unidades monetarias más cercanas.
4. Establezca el campo **Forma de redondear** para especificar si el resto debe redondearse hacia arriba o hacia abajo.
5. Seleccione el método utilizado para ajustar las fechas.

    - Si selecciona **Absoluto**, puede ingresar fechas que definan el intervalo de fechas para los límites de crédito.
    - Si selecciona **Relativo**, puede introducir fechas desplazadas para el intervalo. El intervalo de fechas actual para el límite de crédito se ajustará con el desplazamiento.

6. Use la ficha desplegable **Registros que incluir** para filtrar la lista de clientes que están incluidos. Si no incluye filtros, se generarán entradas de límite de crédito para todos los clientes.
7. Seleccione **Aceptar** para crear las entradas de ajuste de límite de crédito.

### <a name="from-existing-customer-credit-group"></a>De grupo de crédito de cliente existente

Puede crear líneas de diario a partir de grupos de crédito de cliente existentes. Cuando se selecciona **Generar \> De grupo de crédito de cliente existente**, aparece un cuadro de diálogo en el que puede proporcionar criterios para seleccionar grupos de crédito de cliente y calcular los nuevos límites. Los criterios son los mismos que se utilizan para crear líneas de diario de clientes existentes. Vea los pasos en la sección anterior.

### <a name="automatic-credit-limits"></a>Límites de crédito automáticos

Puede crear límites de crédito automáticos para definir y actualizar los límites de crédito de cliente. Los límites de crédito automáticos se crean para un grupo de riesgo y se basan en valores específicos que se utilizan en los grupos de puntuación. Puede usar estos límites de crédito automáticos para generar entradas de límite de crédito. Si se ha asignado un cliente a un grupo de riesgo específico y la información de crédito del cliente coincide con los criterios para un límite de crédito automático, se crea una entrada de ajuste de límite de crédito.

#### <a name="create-automatic-credit-limits"></a>Crear límites de crédito automáticos

Los límites de crédito automáticos se crean mediante ajustes de límite de crédito. Al seleccionar **Generar \> Límites automáticos de crédito**, se abre un cuadro de diálogo en el que puede establecer una fecha de vencimiento para los nuevos límites de crédito que se crearán en función de los grupos de riesgo a los que están asignados los clientes. Cuando haya terminado, seleccione **Aceptar** para crear las líneas de ajuste de límite de crédito.

### <a name="post-adjustments"></a>Registrar ajustes

Después de haber creado líneas de ajuste de límite de crédito, puede usar el botón **Registrar** en el panel de acciones para publicar las entradas y actualizar los límites de crédito del cliente. Sin embargo, si ha configurado un flujo de trabajo, debe seleccionar **Flujo de trabajo \> Enviar** en el panel de acciones para enviar el diario para su aprobación.

### <a name="credit-limit-adjustments-workflows"></a>Flujos de trabajo de ajustes de límite de crédito

Los flujos de trabajo de **Ajustes de límite de crédito** se pueden usar para enviar ajustes de límite de crédito mediante un proceso de aprobación de flujo de trabajo. Puede crear dos flujos de trabajo en la página **Flujo de trabajo de administración de crédito** (**Administración de crédito \> Configurar \> Flujo de trabajo de administración de crédito**):

- **Ajustes de límite de crédito**: este flujo de trabajo se puede usar para aprobar entradas a nivel de encabezado.
- **Línea de ajustes de límite de crédito**: este flujo de trabajo se puede usar para aprobar las entradas de ajuste de forma que las entradas puedan ser aprobadas por diferentes personas, según los criterios del flujo de trabajo.

> [!NOTE]
> Al crear el flujo de trabajo **Ajustes de límite de crédito** puede configurarlo para que los ajustes se publiquen automáticamente después de que se hayan aprobado las líneas. Incluya únicamente la tarea **Registrar diario automáticamente** en el flujo de trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
