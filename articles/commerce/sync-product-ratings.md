---
title: Sincronizar clasificaciones de producto en Dynamics 365 Retail
description: Este tema describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698174"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a>Sincronizar clasificaciones de producto en Dynamics 365 Retail

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Retail.

## <a name="overview"></a>Visión general

Para consumir clasificaciones de productos en omnicanales, como en punto de venta (PDV) y en centros de llamadas, las clasificaciones de productos del servicio de clasificaciones y revisiones deben importarse en la base de datos de canal de Retail. Cuando las clasificaciones de productos se vuelven disponibles en omnicanales, pueden ayudar a los clientes indirectamente durante sus interacciones con socios de ventas.

Este tema describe las siguientes tareas:

1. Configurar un trabajo por lotes de Retail para importar clasificaciones de productos.
1. Compruebe que el trabajo por lotes para la sincronización de clasificación de productos fue correcto.
1. Haga que las clasificaciones de productos estén disponibles en PDV.

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a>Configurar un trabajo por lotes de Retail para importar clasificaciones de productos

> [!IMPORTANT]
> Antes de comenzar, asegúrese de que la versión 10.0.6 o posterior de Retail está instalada.

### <a name="initialize-the-retail-scheduler"></a>Inicializar el Programador de tareas Retail

Para inicializar el Programador de tareas Retail, siga estos pasos.

1. Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Inicializar el Programador de tareas Retail**. Como alternativa, busque “Inicializar el Programador de tareas Retail”.
1. En el cuadro de diálogo **Inicializar el Programador de tareas Retail**, asegúrese de que la opción **Configuración de la existente Eliminar** está establecida en **No** y, a continuación, seleccione **Aceptar**.

### <a name="verify-the-retailproductrating-subjob"></a>Comprobar el trabajo subordinado de RetailProductRating

Para comprobar que existe el trabajo subordinado **RetailProductRating**, siga estos pasos.

1. Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Trabajos subordinados del programador**. Como alternativa, busque “Trabajos subordinados del programador”.
1. En la lista de trabajos subordinados, encuentre o busque el trabajo subordinado **RetailProductRating**.

La ilustración siguiente muestra un ejemplo de los detalles del trabajo subordinado en Retail.

![Detalles del trabajo subordinado de RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Si no encuentra el trabajo subordinado **RetailProductRating**, es posible que ya haya ejecutado el trabajo **Sincronizar clasificaciones de producto** y el trabajo **1040 CDX** antes de haber inicializado el Programador de tareas Retail. En este caso, siga estos pasos para ejecutar el trabajo **Sincronización de datos completa**.
>
> 1. Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Base de datos de canales**. Como alternativa, busque “Base de datos de canales”.
> 1. Seleccione la base de datos de canal que se sincronizará.
> 1. En el panel de acciones, seleccione **Sincronización de datos completa**.
> 1. En el cuadro de diálogo desplegable **Seleccionar una programación de distribución**, seleccione **1040 - productos** y, a continuación, **Aceptar**.
> 1. Repita los pasos del procedimiento anterior para comprobar que se ha creado el trabajo subordinado **RetailProductRating**.

### <a name="import-product-ratings"></a>Importar clasificaciones de productos

Para importar clasificaciones de productos en Retail desde el servicio de clasificaciones y revisiones, siga estos pasos.

1. Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Sincronizar trabajo de clasificaciones de productos**. Como alternativa, busque “Sincronizar trabajo de clasificaciones de productos”.
1. En el cuadro de diálogo **Extraer clasificaciones de productos**, en la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.
1. En el cuadro de diálogo **Definir periodicidad**, configure un patrón de periodicidad. (El valor sugerido es dos horas). No programe una periodicidad inferior a una hora.
1. Seleccione **Aceptar**.
1. Establezca la opción **Procesamiento por lotes** en **Sí**. Este valor ayuda a garantizar que podrá auditar los registros y comprobar el estado de las ejecuciones de trabajos por lotes.
1. Seleccione **Aceptar** para programar el trabajo por lotes.

La ilustración siguiente muestra un ejemplo de la configuración de trabajos por lotes en Retail.

![Configuración del trabajo por lotes de Sincronizar clasificaciones de productos](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Comprobar que el trabajo por lotes para la sincronización de la clasificación de productos fue correcto

Para comprobar que el trabajo por lotes **Sincronizar clasificaciones de productos** fue correcto, siga estos pasos.

1. Vaya a **Retail \> Administrador del sistema \> Consultas \> Trabajos por lotes** o, si usa una referencia de almacén (SKU) solo de Retail, **Retail \> Consultas e informes \> Trabajos por lotes** en su lugar. Como alternativa, busque “Trabajos por lotes”.
1. Para ver los detalles del trabajo por lotes, en la lista de trabajos por lotes, en la columna **Descripción del trabajo**, busque una descripción que contenga “Extraer clasificaciones de productos”.
1. Seleccione el id. de trabajo para ver los detalles del trabajo por lotes, como la fecha u hora inicial programada y el texto de periodicidad.

La ilustración siguiente se muestra un ejemplo de los detalles del trabajo por lotes en Retail cuando el trabajo por lotes se programa para que ejecutarse en intervalos de dos horas.

![Detalles del trabajo por lotes de Sincronizar clasificaciones de producto](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Hacer que las clasificaciones de productos estén disponibles en PDV

La solución de clasificaciones y revisiones en Dynamics 365 Commerce es una solución de omnicanal. Sin embargo, las clasificaciones de productos no se muestran en PDV de forma predeterminada. Para ayudar a los clientes de tiendas a ver las clasificaciones y las revisiones cuando les ayudan los socios de ventas, debe activar las clasificaciones de productos en el PDV.

Para activar clasificaciones de productos en el PDV, siga estos pasos.

1. Vaya a **Retail \> Configuración de Retail \> Parámetros \> Parámetros comerciales**. Como alternativa, busque "Parámetros comerciales”.
1. En la pestaña **Parámetros de configuración**, seleccione **Nuevo**.
1. Escriba un nombre como **RatingsAndReviews.EnableProductRatingsForRetailStores** y establezca el valor en **verdadero**.
1. Seleccione **Guardar**.
1. Vaya a **Retail \> TI de Retail \> Programación de distribución**. Como alternativa, busque “Programación de distribución”.
1. En la lista de trabajos, seleccione **1110** (**Configuración global**) y después seleccione **Ejecutar ahora**.
1. Una vez que el trabajo se haya ejecutado correctamente, compruebe que las clasificaciones de productos se mostrarán ahora en PDV.

La ilustración siguiente muestra un ejemplo de la configuración de los parámetros de Retail para activar las clasificaciones de productos en el PDV.

![Configuración de los parámetros de Retail para las clasificaciones de productos en PDV](media/rnr-hq-enable-ratings-in-pos.png)

En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en el PDV.

![Clasificaciones de productos en el PDV](media/rnr-pos-catalog-ratings.png)

En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en los canales del centro de llamadas.

![Clasificaciones de productos en un canal de centro de llamadas](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar clasificaciones y revisiones](manage-reviews.md)

[Configurar clasificaciones y revisiones](configure-ratings-reviews.md)
