---
title: Versión preliminar de Dynamics 365 Commerce 10.0.30 (noviembre de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Commerce 10.0.30.
author: josaw1
ms.date: 12/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: a449c7eff21c059555f9659ea932705858d26275
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831757"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>Versión preliminar de Dynamics 365 Commerce 10.0.30 (noviembre de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Commerce versión de vista previa 10.0.30. Esta versión tiene el número de compilación 10.0.1362 y está disponible con la siguiente programación:

- **Versión preliminar:** septiembre de 2022
- **Disponibilidad general de la versión (actualización automática):** octubre de 2022
- **Disponibilidad general de la versión (actualización automática):** noviembre de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---------|------------------|----------------|--------------| 
| Atención al cliente   | Converse en un sitio de comercio electrónico usando un bot de Power Virtual Agents. | Esta característica les dará a los usuarios del sitio de comercio electrónico la opción de usar un bot de chat de Power Virtual Agents para solicitudes de soporte. | Habilitado por administradores/fabricantes para usuarios finales |
| Información  |  Transmita eventos de operational insights del punto de venta (PDV) a su cuenta de Application Insights. | [Registros de acceso en Application Insights](../dev-itpro/operational-insights.md#enable-diagnostic-events-in-application-insights)   |  Participación de desarrolladores/profesionales de TI   |
|  Pagos  | Compatibilidad con pedidos de PayPal más allá del período de autorización de 29 días. | El período máximo de autorización para PayPal es de 29 días, periodo tras el cual se debe generar una nueva autorización e ID de pedido. Como alternativa, PayPal ofrece una opción en la que se puede hacer referencia a un pedido de PayPal como pedido general, lo que permite varias autorizaciones y capturas para el mismo ID de pedido, en lugar de generar una nueva autorización e ID de pedido a los 29 días). | Al configurar el conector de pago de PayPal en Commerce headquarters, el campo **OrderIntent** se ha agregado y puede tener dos valores:<p><p>- **Autorizar** - Esta configuración es la predeterminada (si el campo se deja en blanco, **Autorizar** actuará de forma predeterminada). La configuración de **OrderIntent** como **Autorizar** se correlaciona con el valor de **processing_instruction** de PayPal de **NO_INSTRUCTION**. El pedido será autorizado con PayPal y la autorización no podrá ser modificada cuando se utilice este valor.<p>- **Guardar** - Cuando el valor de **OrderIntent** se establece en **Guardar**, esto se correlaciona con el valor de **processing_instruction** de PayPal de **ORDER_SAVED_EXPLICITLY**. Las referencias de pedidos se guardarán en el servicio de PayPal cuando se utilice este valor.  |
| Inicio de sesión de PDV  | [Habilitar capacidades de diagnóstico de autoservicio para inicio de sesión de PDV](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Esta característica proporciona capacidades de diagnóstico de autoservicio en el punto de venta (PDV) y Commerce headquarters para ayudar a empleados y gerentes de la tienda a identificar y solucionar rápidamente las causas raíz de los problemas de inicio de sesión de PDV.<p><p>- Los mensajes de error que se muestran en la pantalla de inicio de sesión de PDV se mejoraron para proporcionar información concreta sobre la causa raíz que puede ayudar a los empleados de la tienda que usan PDV a comprender qué salió mal para que puedan realizar las acciones necesarias para resolver el problema.<p>- La función **Inicio de sesión de la prueba** está disponible en la página **Trabajadores** de Commerce headquarters para que los gerentes de tiendas que configuran dispositivos PDV puedan simular el inicio de sesión de PDV. En caso de error de inicio de sesión, esta función proporciona prácticas guías de solución de problemas para que los administradores puedan verificar las configuraciones relevantes, corregir problemas y validar las correcciones.  | Activado de forma predeterminada |


## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Dynamics 365 Finance 10.0.30 incluye actualizaciones de la plataforma. Para obtener más información, consulte [Platform updates para la versión 10.0.30 de aplicaciones de finanzas y operaciones](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.30, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022](/dynamics365-release-plan/2022wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-features"></a>Características quitadas y obsoletas

El artículo [Funciones eliminadas o obsoletas en Dynamics 365 Commerce](removed-deprecated-features-commerce.md) describe las características que se han eliminado o están obsoletas para Commerce.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
