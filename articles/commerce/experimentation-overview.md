---
title: Experimentación en Dynamics 365 Commerce
description: La experimentación permite la creación, edición y gestión del diseño de página y tratamientos de contenido en el creador de sitios. El soporte de experimentación de un extremo a otro está habilitado para las páginas y entidades de comercio electrónico dentro de una página.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d836f0e431c444c07186da123579f5cce9895be5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238615"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Experimentación en Dynamics 365 Commerce
Utilice la experimentación en Dynamics 365 Commerce para validar hipótesis sobre la eficacia de sus páginas de comercio electrónico y tomar decisiones con confianza basada en datos. Commerce admite pruebas A/B en páginas, módulos y fragmentos y le permite medir el impacto de los cambios propuestos en su sitio web.

Puede crear, editar y administrar tratamientos de contenido y página conocidos como **variaciones** en el generador de sitios de Commerce. Commerce se integra con servicios de terceros que puede utilizar para crear experimentos y asignaciones de tratamiento. Los flujos de eventos en tiempo real capturados en Commerce habilitan los análisis que definen los resultados del experimento en el servicio de terceros. Luego, puede aprovechar estos análisis para ayudar a respaldar o refutar su hipótesis.

## <a name="set-up-prerequisites"></a> Requisitos previos de configuración
1. **Obtener la versión correcta de Commerce**: actualice su biblioteca de módulos, el kit de desarrollo de software (SDK) de extensibilidad de canales en línea y Commerce Scale Unit a la versión 10.0.13 o posterior de Commerce.
1. **Configurar un conector de experimentación** - Un conector de experimentación permite a Comercio conectarse con servicios de terceros para recuperar la lista de experimentos y determinar cuándo mostrar un experimento a un usuario. Puede adquirir un conector de terceros en [AppSource](https://appsource.microsoft.com). Siga las instrucciones de configuración proporcionadas por el editor. Alternativamente, puede utilizar el conector de prueba de muestra de Commerce para probar el flujo de trabajo de experimentación sin necesidad de configurar un servicio externo. Para más información, vea [Configurar y habilitar conectores](e-commerce-extensibility/connectors.md). 
1. **Activar las banderas de funciones de experimentación en Commerce** - Puede habilitar la experimentación a nivel de inquilino yendo a **Configuración de inquilinos > Funciones** o en el nivel de sitio en **Configuración del sitio > Funciones**.
    - Habilite la marca **Experimentación** para crear variaciones experimentales de módulos dentro de una página sin afectar o copiar otro contenido que no es parte del experimento. Esto asegura que las actualizaciones de contenido en curso fuera del experimento permanezcan sincronizadas durante el ciclo de vida del experimento. La desactivación de esta marca impide que todos los experimentos se muestren a los usuarios y elimina todas las funciones de edición dentro del creador de sitios.
    - Habilite la marca **Experimente con páginas o fragmentos** para ejecutar experimentos en una página o fragmento. Esto crea una copia de instancia completa de toda la página o fragmento para todos los módulos dentro de la página o fragmento. Utilice este modo cuando desee probar cambios de contenido completos o cuando la sincronización de cambios de contenido en curso entre instancias no sea un problema. La desactivación de esta marca evita la creación y edición de nuevos experimentos en páginas y fragmentos.
    > [!NOTE]
    > La marca **Experimentación** también debe estar habilitada para que la funcionalidad **Experimente con páginas o fragmentos** funcione.
    
## <a name="experimentation-lifecycle"></a>Ciclo de vida de experimentación
Configurar un experimento, crear variaciones y ejecutar un experimento es un proceso iterativo. El siguiente diagrama ilustra el ciclo de vida de la experimentación en Commerce y el servicio de terceros. 

[ ![Ciclo de vida de experimentación](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Para obtener más información sobre cada paso del proceso de experimentación, consulte los siguientes temas.
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