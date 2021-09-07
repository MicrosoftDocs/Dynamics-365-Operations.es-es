---
title: Administrar características en Human Resources
description: Este tema describe la función de Administración de características y cómo puede utilizarla.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61e40f7177a1c8cf3d60a9a991ecbb0ed4d93aa1
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414642"
---
# <a name="manage-features-in-human-resources"></a>Administrar características en Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Como parte de nuestro desarrollo continuo de nuevas capacidades de Microsoft Dynamics 365 Human Resources, deseamos que los clientes experimenten las nuevas características lo más rápidamente posible. Ofrecemos características en versión preliminar, que están casi preparadas para la disponibilidad general y han pasado por un amplio proceso de pruebas. Simplemente estamos buscando una ronda final de comentarios de clientes y de validación antes de estén disponibles de forma general.

Para obtener más información sobre características nuevas en Human Resources, consulte [Novedades en Human Resources](hr-admin-whats-new.md) y [Plan de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products).

El espacio de trabajo **Administración de características** proporciona una lista de características entregadas en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación. Para obtener más información acerca de la administración de características, consulte [Visión general de la Administración de características](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Todas las características nuevas siguen en versión preliminar durante al menos 30 días como mínimo, y normalmente 30-60 días. Las características más importantes están disponibles en octubre y abril de cada año tras el periodo de prueba preliminar. En cuanto vea características nuevas en el espacio de trabajo **Administración de características**, puede activarlas. Algunas características pueden estar activadas de forma predeterminada.

Cuando una característica esté disponible, se puede activar y desactivar en los entornos de producción. El espacio de trabajo **Administración de características** indica cuando una característica de versión preliminar pasará a ser obligatoria. Esta fecha es un el 1 de octubre o el 1 de abril para que se corresponda con los planes semestrales de publicación. No pueden desactivar características obligatorias. Hasta que llegue a ser obligatoria, se puede activar y desactivar una característica en todos los entornos.

## <a name="enable-or-disable-preview-features"></a>Habilitar o deshabilitar las funciones de vista previa

Para obtener acceso a características de vista previa, primero debe permitirlas en el entorno. Habilitar o deshabilitar las características de vista previa es específica del entorno.

> [!IMPORTANT]
> Las características de vista previa solo están disponibles en entornos de **Espacio aislado**. Cuando activa una característica en versión preliminar, lo hace para todos los usuarios de la organización que se encuentran en dicho entorno. Cuando desactiva una característica en versión preliminar, la deshabilita y hace que no sea accesible para los usuarios. Las funciones de vista previa tienen compatibilidad limitada en Human Resources. Es posible que apliquen menos medidas de privacidad y de seguridad, y no se incluyen en el contrato de nivel de servicio (SLA) de Human Resources. No debe utilizar características de vista preliminar para procesar datos personales (es decir, toda información que pueda identificarle), o para procesar otros datos sujetos a requisitos de conformidad legales o administrativos.

1. En Human Resources, seleccione **Administración del sistema**.

2. Seleccione la ventana **Gestión de funciones**.

3. Para habilitar una característica en versión preliminar, selecciónela de la lista y luego seleccione **Habilitar**. Para deshabilitar una característica en versión preliminar, selecciónela de la lista y luego seleccione **Deshabilitar**.

## <a name="enable-or-disable-benefits-management"></a>Habilitar o deshabilitar la administración de prestaciones

Para habilitar la gestión de prestaciones, utilice el mismo procedimiento en [Habilitar o deshabilitar funciones de vista previa](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> No puede deshabilitar la gestión de prestaciones en un entorno de **Producción** después de haberla habilitado. Sin embargo, puede deshabilitar la gestión de prestaciones en entornos **Espacio aislado**.

Para obtener más información sobre la configuración y el uso de la administración de beneficios, consulte [Resumen de gestión de beneficios](hr-benefits-management-overview.md).

La gestión de beneficios reemplaza la funcionalidad en el espacio de trabajo **Beneficios**. Cuando habilita la función de vista previa de administración de Beneficios, ya no puede acceder a los siguientes formularios en el espacio de trabajo **Beneficios**:

- **Prestaciones**
- **Elementos de beneficio**
- **Índices de cálculo de la contribución**
- **Resultados de la inscripción a beneficios**
- **Resultados de la expiración y la extensión de los beneficios**
- **Tipos de reglas de directiva de idoneidad de beneficio**
- **Directivas de idoneidad para prestaciones**
- **Eventos de idoneidad**

Puede ver la información en estas páginas en modo de solo lectura. Si desea editar la información, primero debe deshabilitar la administración de prestaciones (aplicable solo a entornos **Espacio aislado**).

## <a name="enable-or-disable-leave-and-absence"></a>Habilitar o deshabilitar Permiso y ausencia

Para habilitar Permiso y ausencia, utilice el mismo procedimiento que en [Habilitar o deshabilitar funciones de vista previa](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> No puedes deshabilitar la característica **Múltiples tipos de permiso** en Permiso y ausencia después de habilitarla. Esto se aplica tanto a los entornos **Espacio aislado** como **Producción**.

Características sobre la vista previa de características en permisos y ausencias, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

## <a name="send-us-feedback"></a>Envíenos sus comentarios

Queremos conocer su experiencia con las características en versión preliminar. Recomendamos que publique con regularidad sus comentarios en los sitios siguientes cuando use estas características u otras:

- [Comunidad](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Este sitio es un gran recurso en el que los usuarios pueden discutir los casos de uso, hacer preguntas, y obtener ayuda de la comunidad.
- Infórmenos sobre las características que desea ver en el producto, así como los cambios que crea que deberíamos realizar en las características existentes. Sugiera ideas de productos en [Ideas para Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
No incluya los datos personales (información que podría identificarle) en los envíos de comentarios o de revisión del producto. La información que se obtiene se puede analizar más, pero no se usará para responder a solicitudes, de acuerdo con las leyes aplicables de privacidad. La información personal obtenida por separado en estos programas está sujeta a la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Consulte también

- [Novedades de Human Resources](hr-admin-whats-new.md)
- [Plan de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
