---
title: Registrar artículos habilitados para procesos de gestión de almacenes mediante un diario de recepción de artículos
description: Este artículo presenta un escenario que muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa los procesos de gestión de almacenes (WMS).
author: Mirzaab
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66fc9e21b79d70ec14750440c74d354bb8ec0695
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219610"
---
# <a name="register-items-enabled-for-warehouse-management-processes-using-an-item-arrival-journal"></a>Registrar artículos habilitados para procesos de gestión de almacenes mediante un diario de recepción de artículos

[!include [banner](../../includes/banner.md)]

Este artículo presenta un escenario que muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa los procesos de gestión de almacenes (WMS). Esto lo realiza normalmente un empleado de recepción.

## <a name="enable-sample-data"></a>Habilitar datos de muestra

Para trabajar en este escenario utilizando los registros de muestra y los valores especificados en este artículo, debe utilizar un sistema en el que estén instalados los [datos de demostración](../../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar y debe seleccionar la entidad jurídica *USMF* antes de comenzar.

En su lugar, puede trabajar en este escenario sustituyendo valores de sus propios datos siempre que tenga los siguientes datos disponibles:

- Debe tener un pedido de compra confirmada con una línea de pedido de compra abierta.
- El artículo de la línea debe mantenerse en existencias. No debe utilizar variantes de producto y no debe tener dimensiones de seguimiento.
- El artículo debe estar asociado con un grupo de dimensiones de almacenamiento habilitado con proceso de gestión de almacenes.
- El almacén que se usa debe estar habilitado para WMS y la ubicación que usa para recepción debe controlada por matrículas de entidad de almacén.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Cree un encabezado de diario de llegada de artículos que utilice la gestión de almacén

El siguiente escenario muestra cómo crear un encabezado de diario de llegada de artículos que utiliza la gestión de almacén:

1. Asegúrese de que su sistema contenga un pedido de compra confirmada que cumpla con los requisitos descritos en la sección anterior. Este escenario utiliza una orden de compra para la empresa *USMF*, cuenta de proveedor *1001*, almacén *51*, con una línea de pedido para *10 PL* (10 palets) del número de artículo *M9200*.
1. Anote el número del pedido de compra que usará.
1. Vaya a **Gestión del inventario \> Movimientos de diario \> Recepción de artículos \> Recepción de artículos**.
1. En el panel Acciones, seleccione **Nuevo**.
1. El cuadro de diálogo **Crear diario de administración de almacén** se abre. Seleccione un nombre de diario en el campo **Nombre**.
    - Si va a utilizar los datos de demostración de la empresa *USMF*, seleccione *WHS*.
    - Si está utilizando sus propios datos, el diario que elija debe tener **Verificar ubicación de picking** establecido en *No* y **Gestión de cuarentena** establecido en *No*.
1. Establezca **Referencia** a *Pedido de compra*.
1. Establezca **Número de cuenta** en *1001*.
1. Establezca **Número** al número del pedido de compra que identificó para este ejercicio.

    ![Diario de recepción de artículos.](../media/item-arrival-journal-header.png "Diario de recepción de artículos")

1. Seleccione **Aceptar** para crear el encabezado del diario.
1. En la sección **Líneas de diario**, seleccione **Agregar línea** e introduzca los siguientes datos:
    - Establezca **Número de artículo** en *M9200*. El **Sitio**, **Almacén**, y **Cantidad** se configurarán en función de los datos de la transacción de inventario para los 10 palés (1000 c / u).
    - **Ubicación**: establecida en *001*. Esta ubicación específica no rastrea las matrículas.

    ![Línea de diario de recepción de artículos.](../media/item-arrival-journal-line.png "Línea de diario de recepción de artículos")

    > [!NOTE]
    > El campo **Fecha** determina la fecha en la que la cantidad disponible del artículo se registrará en el inventario.  
    >
    > El sistema rellenará el **Identificador de lote** si se puede identificar de forma exclusiva con la información proporcionada. De lo contrario, tendrá que introducir esto manualmente. Esto es un campo obligatorio, que vincula este registro a una línea de documento de origen específica.  

1. En el panel de acciones, seleccione **Validar**. Esto comprueba que el diario está listo para registrarse. Si se produce un error en la validación, tendrá que corregir los errores para poder registrar el diario.  
1. El cuadro de diálogo **Comprobar diario** se abre. Seleccione **Aceptar**.
1. Revisar la barra de mensajes. Debe haber un mensaje que indica que se ha completado la operación.  
1. En el panel de acciones, seleccione **Registrar**.
1. El cuadro de diálogo **Registrar diario** se abre. Seleccione **Aceptar**.
1. Revisar la barra de mensajes. Debe haber mensajes que indican que se ha completado la operación.
1. Seleccione **Funciones > Recibo de producto** en el Panel de acciones para actualizar la línea del pedido de compra y publicar un recibo de producto.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
