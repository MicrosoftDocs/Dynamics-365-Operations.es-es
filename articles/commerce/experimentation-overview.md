---
title: Experimentación en Dynamics 365 Commerce
description: La experimentación permite la creación, edición y gestión del diseño de página y tratamientos de contenido en el creador de sitios. El soporte de experimentación de un extremo a otro está habilitado para las páginas y entidades de comercio electrónico dentro de una página.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946223"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Experimentación en Dynamics 365 Commerce
Utilice la experimentación en Dynamics 365 Commerce para validar hipótesis sobre la eficacia de sus páginas de comercio electrónico y tomar decisiones con confianza basada en datos. Commerce admite pruebas A/B en páginas, módulos y fragmentos y le permite medir el impacto de los cambios propuestos en su sitio web.

Puede crear, editar y administrar tratamientos de contenido y página conocidos como **variaciones** en el generador de sitios de Commerce. Commerce se integra con servicios de terceros que puede utilizar para crear experimentos y asignaciones de tratamiento. Los flujos de eventos en tiempo real capturados en Commerce habilitan los análisis que definen los resultados del experimento en el servicio de terceros. Luego, puede aprovechar estos análisis para ayudar a respaldar o refutar su hipótesis.

## <a name="set-up-prerequisites"></a> Requisitos previos de configuración

1. **Obtener la versión correcta de Commerce**: actualice su biblioteca de módulos, el kit de desarrollo de software (SDK) de extensibilidad de canales en línea y Commerce Scale Unit a la versión 10.0.13 o posterior de Commerce.
1. **Configurar un conector de experimentación** - Un conector de experimentación permite a Comercio conectarse con servicios de terceros para recuperar la lista de experimentos y determinar cuándo mostrar un experimento a un usuario. Puede adquirir un conector de terceros en [AppSource](https://appsource.microsoft.com). Siga las instrucciones de configuración proporcionadas por el editor. Alternativamente, puede utilizar el conector de prueba de muestra de Commerce para probar el flujo de trabajo de experimentación sin necesidad de configurar un servicio externo. Para más información, vea [Configurar y habilitar conectores](e-commerce-extensibility/connectors.md). 
1. **Activar la bandera de funciones de experimentación en Commerce** - Puede habilitar la experimentación a nivel de inquilino yendo a **Configuración de inquilinos \> Funciones** o en el nivel de sitio yendo a **Configuración del sitio \> Funciones**. Active la bandera **Experimentación** para comenzar a crear variaciones de módulo. La desactivación de esta marca impide que todos los experimentos se muestren a los usuarios y elimina todas las funciones de edición dentro del creador de sitios.
    
## <a name="experimentation-lifecycle"></a>Ciclo de vida de experimentación

Configurar un experimento, crear variaciones y ejecutar un experimento es un proceso iterativo. El siguiente diagrama ilustra el ciclo de vida de la experimentación en Commerce y el servicio de terceros. 

[ ![Ciclo de vida de experimentación.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Para obtener más información sobre cada paso del proceso de experimentación, consulte los siguientes artículos.
- [Identificar una hipótesis y determinar métricas para un experimento](experimentation-identify.md)
- [Configurar un experimento](experimentation-setup.md)
- [Conectar y editar un experimento](experimentation-connect-edit.md)
- [Obtener una vista previa y publicar un experimento](experimentation-preview-publish.md)
- [Ejecutar y supervisar un experimento](experimentation-run-monitor.md)
- [Promover una variación y completar un experimento](experimentation-review-complete.md)

> [!NOTE]
> Para saber dónde se encuentra un experimento en el ciclo de vida, seleccione **Experimentos** en el panel de navegación izquierdo del generador de sitios de Commerce. Se muestra una lista de experimentos con el estado de cada experimento tanto en Commerce como en el servicio de terceros. Para más información, vea [Revisar el estado de un experimento](experimentation-status.md).

## <a name="next-step"></a>Paso siguiente
[Identificar una hipótesis y determinar métricas de éxito para un experimento](experimentation-identify.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
