---
title: Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.6 (noviembre de 2019)
description: Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Supply Chain Management 10.0.6.
author: kamaybac
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 8c97e4e5544c49d2e6a13b34061abfbf50e2932a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844449"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.6 (noviembre de 2019)

[!include [banner](../includes/banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Supply Chain Management 10.0.6. El número de compilación de esta versión es 10.0.234. Aunque la fecha de disponibilidad general cae en noviembre, las nuevas características están disponibles para un lanzamiento anticipado en octubre. Para obtener más información sobre la versión 10.0.6, consulte [Recursos adicionales](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Entidad de datos "modelos de configuración de producto V2"

Se lanza una segunda versión de la entidad de datos "modelos de configuración de producto" (llamada "modelos de configuración de producto V2"). La plantilla predeterminada "418-modelos de configuración de producto" también debe ser así para que use la nueva entidad de datos "modelos de configuración de producto V2" en las plantillas de marco de importación/exportación. La plantilla no se actualizará automáticamente, por lo que tendrá que cargarla desde la predeterminada manualmente. La entidad V2 exporta una fila como un archivo independiente en un archivo adjunto en lugar de en línea, solucionando así las limitaciones de tamaño de la entidad V1. 
 
¿Qué tengo que hacer para incorporar este cambio?
-    Como la entidad V1 ha quedado en desuso, debe iniciar la migración de V1 a V2. Si utiliza la plantilla "418-modelos de configuración de producto", puede hacer clic en el botón "cargar plantillas predeterminadas" y volver a cargar la plantilla "418-modelos de configuración de producto"
-    Si necesita mantener la compatibilidad con los sistemas existentes, puede seguir utilizando la plantilla existente y la entidad V1 (en desuso) hasta que migre sus integraciones a la nueva plantilla. 

## <a name="feature-management-enhancements"></a>Mejoras de la administración de características
Ahora la administración de características le permite habilitar todas las características de manera predeterminada, solicitar confirmación para habilitar una característica y habilitar todas las características que aún no se han habilitado. 


## <a name="purchase-agreement-responsible-party"></a>Parte responsable del acuerdo de compra
Ahora tiene la capacidad de definir las partes responsables principal y secundarias en el formulario de clasificación del acuerdo de compra y los acuerdos de compra derivados.  Esto proporciona al usuario acceso a quién supervisa los acuerdos.

## <a name="rfq-link-on-the-purchase-order-line"></a>Vínculo de solicitud de presupuesto en la línea de pedido de compra
Puede agregar un vínculo de referencia desde las líneas de pedido de compra a las líneas de solicitud de presupuesto correspondientes de las que se originaron, lo que permite al usuario recibir fácilmente el documento de solicitud de presupuesto correspondiente.

## <a name="additional-resources"></a>Recursos adicionales

### <a name="bug-fixes"></a>Correcciones de errores
Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.6, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Platform update 30
Microsoft Dynamics 365 Supply Chain Management 10.0.6 incluye la Platform update 30. Para obtener más información sobre la Platform update 30, consulte [Novedades y cambios en la Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: segunda oleada de lanzamiento de versiones de 2019
¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365: plan de la segunda oleada de lanzamiento de versiones de 2019](/dynamics365-release-plan/2019wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]