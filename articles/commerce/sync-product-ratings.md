---
title: Sincronizar clasificaciones de producto en Dynamics 365 Commerce
description: Este artículo describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 7946bcaa9c6f318115640c6b20b00554a117dd38
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282033"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a>Sincronizar clasificaciones de producto en Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artículo describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Commerce.

Para consumir clasificaciones de productos en omnicanales, como en punto de venta (PDV) y en centros de llamadas, las clasificaciones de productos del servicio de clasificaciones y revisiones deben importarse en la base de datos de canal de Commerce. Cuando las clasificaciones de productos se vuelven disponibles en omnicanales, pueden ayudar a los clientes indirectamente durante sus interacciones con socios de ventas.

Este artículo describe las siguientes tareas:

1. Configure **Trabajo de sincronización de clasificaciones de productos** como un trabajo por lotes para sincronizar clasificaciones de productos desde el **servicio de clasificaciones y revisiones**.
1. Compruebe que el trabajo por lotes para la sincronización de clasificación de productos fue correcto.
1. Haga que las clasificaciones de productos estén disponibles en PDV.

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a>Configurar un trabajo por lotes para sincronizar clasificaciones de productos

> [!IMPORTANT]
> Antes de comenzar, asegúrese de que la versión 10.0.6 o posterior de Dynamics 365 Commerce está instalada.

### <a name="initialize-the-commerce-scheduler"></a>Inicializar el programador de Commerce

Para inicializar el programador de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Inicializar programador de Commerce**. Como alternativa, busque “Inicializar programador de Commerce”.
1. En el cuadro de diálogo **Inicializar el programador de Commerce**, asegúrese de que la opción **Configuración de la existente Eliminar** está establecida en **No** y, a continuación, seleccione **Aceptar**.

### <a name="verify-the-retailproductrating-subjob"></a>Comprobar el trabajo subordinado de RetailProductRating

Para comprobar que existe el trabajo subordinado **RetailProductRating**, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Trabajos subordinados del programador**. Como alternativa, busque “Trabajos subordinados del programador”.
1. En la lista de trabajos subordinados, encuentre o busque el trabajo subordinado **RetailProductRating**.

La ilustración siguiente muestra un ejemplo de los detalles del trabajo subordinado en Commerce.

![Detalles del trabajo subordinado de RetailProductRating.](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Si no encuentra el trabajo subordinado **RetailProductRating**, es posible que ya haya ejecutado el trabajo **Sincronizar clasificaciones de producto** y el trabajo **1040 CDX** antes de haber inicializado el programador Commerce. En este caso, siga estos pasos para ejecutar el trabajo **Sincronización de datos completa**.

> 1. Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Base de datos de canales**. Como alternativa, busque “Base de datos de canales”.
> 1. Seleccione la base de datos de canal que se sincronizará.
> 1. En el panel de acciones, seleccione **Sincronización de datos completa**.
> 1. En el cuadro de diálogo desplegable **Seleccionar una programación de distribución**, seleccione **1040 - productos** y, a continuación, **Aceptar**.
> 1. Repita los pasos del procedimiento anterior para comprobar que se ha creado el trabajo subordinado **RetailProductRating**.

### <a name="import-product-ratings"></a>Importar clasificaciones de productos

Para importar clasificaciones de productos en Commerce desde el servicio de clasificaciones y revisiones, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de tareas Retail \> Sincronizar trabajo de clasificaciones de productos**. Como alternativa, busque “Sincronizar trabajo de clasificaciones de productos”.
1. En el cuadro de diálogo **Extraer clasificaciones de productos**, en la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.
1. En el cuadro de diálogo **Definir periodicidad**, configure un patrón de periodicidad. (El valor sugerido es dos horas). No programe una periodicidad inferior a una hora.
1. Seleccione **Aceptar**.
1. Establezca la opción **Procesamiento por lotes** en **Sí**. Este valor ayuda a garantizar que podrá auditar los registros y comprobar el estado de las ejecuciones de trabajos por lotes.
1. Seleccione **Aceptar** para programar el trabajo por lotes.

La ilustración siguiente muestra un ejemplo de la configuración de trabajos por lotes en Commerce.

![Configuración del trabajo por lotes de Sincronizar clasificaciones de productos.](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Comprobar que el trabajo por lotes para la sincronización de la clasificación de productos fue correcto

Para comprobar que el trabajo por lotes **Sincronizar clasificaciones de productos** fue correcto, siga estos pasos.

1. Vaya a **Retail y Commerce \> Administrador del sistema \> Consultas \> Trabajos por lotes** o, si usa una referencia de almacén (SKU) solo de Commerce, **Retail y Commerce \> Consultas e informes \> Trabajos por lotes** en su lugar. Como alternativa, busque “Trabajos por lotes”.
1. Para ver los detalles del trabajo por lotes, en la lista de trabajos por lotes, en la columna **Descripción del trabajo**, busque una descripción que contenga “Extraer clasificaciones de productos”.
1. Seleccione el id. de trabajo para ver los detalles del trabajo por lotes, como la fecha u hora inicial programada y el texto de periodicidad.

La ilustración siguiente se muestra un ejemplo de los detalles del trabajo por lotes en Commerce cuando el trabajo por lotes se programa para que ejecutarse en intervalos de dos horas.

![Detalles del trabajo por lotes de Sincronizar clasificaciones de producto.](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Hacer que las clasificaciones de productos estén disponibles en PDV

La solución de clasificaciones y revisiones en Dynamics 365 Commerce es una solución de omnicanal. Sin embargo, las clasificaciones de productos no se muestran en PDV de forma predeterminada. Para ayudar a los clientes de tiendas a ver las clasificaciones y las revisiones cuando les ayudan los socios de ventas, debe activar las clasificaciones de productos en el PDV.

Para activar clasificaciones de productos en el PDV, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de Commerce \> Parámetros \> Parámetros de Commerce**. Como alternativa, busque "Parámetros de Commerce”.
1. En la pestaña **Parámetros de configuración**, seleccione **Nuevo**.
1. Escriba un nombre como **RatingsAndReviews.EnableProductRatingsForRetailStores** y establezca el valor en **verdadero**.
1. Seleccione **Guardar**.
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**. Como alternativa, busque “Programación de distribución”.
1. En la lista de trabajos, seleccione **1110** (**Configuración global**) y después seleccione **Ejecutar ahora**.
1. Una vez que el trabajo se haya ejecutado correctamente, compruebe que las clasificaciones de productos se mostrarán ahora en PDV.

La ilustración siguiente muestra un ejemplo de la configuración de los parámetros de Commerce para activar las clasificaciones de productos en el PDV.

![Configuración de los parámetros de Commerce para las clasificaciones de productos en PDV.](media/rnr-hq-enable-ratings-in-pos.png)

En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en el PDV.

![Clasificaciones de productos en el PDV.](media/rnr-pos-catalog-ratings.png)

En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en los canales del centro de llamadas.

![Clasificaciones de productos en un canal de centro de llamadas.](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar calificaciones y opiniones](manage-reviews.md)

[Configurar calificaciones y opiniones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de producto](sync-product-ratings.md)

[Habilitar la publicación manual de calificaciones y reseñas por parte de un moderador](manual-publish-rating-reviews.md)

[Importación y exportación de calificaciones y opiniones](import-export-reviews.md)

[Configurar autenticación de servicio a servicio](service-to-service-auth.md)

[P+F de clasificaciones y revisiones](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
