---
title: Intervalos de servicio
description: Este tema proporciona información sobre cómo trabajar con intervalos de servicio. El intervalo de contrato de servicio indica la frecuencia con la que se crean líneas de pedido de servicio para líneas de contrato de servicio cuando se crean pedidos de servicio automáticamente.
author: kamaybac
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08ec58037657f7d04e50c31aec0f343a09b9fa4e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580321"
---
# <a name="service-intervals"></a>Intervalos de servicio

[!include [banner](../includes/banner.md)]

El intervalo de contrato de servicio indica la frecuencia con la que se crean líneas de pedido de servicio para líneas de contrato de servicio cuando se crean pedidos de servicio automáticamente.

Al crear pedidos de servicio automáticamente, se crean líneas de pedido de servicio en función del intervalo especificado para la línea de contrato de servicio, a partir de la fecha inicial de la línea de contrato.

Si el campo **Intervalo** de una línea de contrato de servicio del formulario **Contratos de servicio** se deja en blanco, la línea es un evento único y no se utiliza para crear pedidos de servicio repetidamente.

## <a name="example"></a>Ejemplo

Este ejemplo muestra cómo un intervalo de servicio afectará a las líneas de contrato de servicio y las líneas de pedido de servicio en un pedido de servicio.

### <a name="create-a-service-agreement"></a>Cree un contrato de servicio

En primer lugar, cree un contrato de servicio y establezca la opción **Combinar pedidos de servicio** en **Por contrato de servicio**.

1. Haga clic en **Contratos de servicio**
2. En el **Panel de acciones**, en la pestaña **Contrato de servicio**, en el grupo **Nuevo**, haga clic en **Contrato de servicio** para crear un nuevo contrato de servicio.
3. Introduzca una descripción, seleccione un proyecto en el campo **Id. de proyecto** y especifique una fecha en el campo **Fecha de inicio**.
4. En el campo **Combinar pedidos de servicio**, seleccione **Por contrato de servicio**.

Acaba de crear el siguiente acuerdo de servicio:

| Project      | Fecha inicial                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Su proyecto | La fecha especificada para el proyecto. En este ejemplo, se utiliza la fecha actual. |

### <a name="create-a-service-agreement-line"></a>Crear una línea de contrato de servicio

A continuación, cree una línea de contrato de servicio con el tipo de transacción **Hora**.

Para realizar esta parte del ejemplo, debe crear un intervalo de servicio de 10 días en la página **Intervalos de servicio**. 

1. Seleccione el acuerdo de servicio que acaba de crear. 
2. En la ficha desplegable **Líneas**, haga clic en el botón **Añadir** para crear una nueva línea en el panel inferior de la página **Contratos de servicio**.
3. Seleccione **Hora** en el campo **Tipo de transacción**.
4. En el campo **Trabajador**, seleccione el trabajador que prestará el servicio.
5. En el campo **Intervalo de servicio**, seleccione el intervalo de 10 días.

Ya ha creado una línea de contrato de servicio con el siguiente tipo de transacción:

| Tipo de transacción | Fecha de inicio                               | Intervalo de servicio |
|------------------|------------------------------------------|------------------|
| Hora             | La fecha actual.                        | Cada 10 días    |
| Trabajador           | El trabajador que llevará a cabo el servicio. |                  |

No hay ninguna ventana de tiempo especificada para la línea. 

### <a name="create-planned-service-orders"></a>Crear pedidos de servicio planificados

Ahora puede crear pedidos de servicio planificados y líneas de pedido de servicio para el mes siguiente.

1. En la página **Contratos de servicio**, en el **Panel de acciones**, en la pestaña **Entregar**, haga clicc en **Pedidos de servicio planificados**.
2. En la página **Crear pedidos de servicio**, especifique la fecha actual en el campo **Fecha inicial** y una fecha que sea un mes a partir de la fecha actual en el campo **Fecha final**.
3. Establezca el control deslizante **Hora** en **Sí**. 
4. Haga clic en **Aceptar**.

Puesto que no existe ninguna agrupación en el pedido de servicio (definida mediante la opción **Por contrato de servicio** en el campo **Combinar pedidos de servicio**), se crea una línea de pedido de servicio por cada pedido de servicio.

### <a name="service-orders-created"></a>Pedidos de servicio creados

Las tres líneas de pedido de servicio creadas en esta instancia se encuentran en la franja temporal especificada en el cuadro de diálogo **Crear pedidos de servicio**. Puede ver las líneas de pedido de servicio en el formulario **Contratos de servicio** (**Panel de acciones**\> pestaña **Entregar** \> botón **Ver**).

## <a name="related-topics"></a>Temas relacionados

[Configurar intervalos de servicio](set-up-service-intervals.md)  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]