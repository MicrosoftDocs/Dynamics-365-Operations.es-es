---
title: Introducción a planificación maestra
description: Este artículo explica cómo empezar a usar la función de planificación maestra en Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 958de3f9ae6ead6cb6914bd3b7a4560e768013ab
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740339"
---
# <a name="get-started-with-master-planning"></a>Introducción a planificación maestra

[!include [banner](../../includes/banner.md)]

La planificación maestra en Supply Chain Management la proporciona un servicio externo denominado Complemento de optimización de planificación para Dynamics 365 Supply Chain Management. En este tema se explica cómo obtener y configurar ese servicio.

## <a name="availability"></a>Disponibilidad

Optimización de planificación está disponible actualmente en las siguientes geografías de Azure: Estados Unidos, Canadá, Brasil, Europa, Francia, Reino Unido, Australia, Asia Pacífico, Japón e India. Si intenta instalar el complemento desde otra región geográfica, LCS mostrará un mensaje que indica que esta ubicación geográfica no es compatible. Para obtener más información sobre las geografías de Azure y las regiones relacionadas, consulte [Geografías de Azure](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Tenga en cuenta que Optimización de planificación no admite implementaciones locales de Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Licencias

Si puede ejecutar con la planificación maestra con su licencia actual, no es necesario comprar una licencia adicional de empezar a usar la optimización de la planificación.

## <a name="install-and-enable-planning-optimization"></a>Instalar y habilitar Optimización de planificación

Para usar Optimización de planificación, debe asegurarse de que su sistema tenga todos los requisitos previos en su lugar y luego habilitar su clave de licencia e instalar el complemento de Optimización de planificación para Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Requisitos previos

Antes de instalar el complemento de Optimización de planificación, debe tener preparados los siguientes requisitos previos:

- Debe ejecutar Supply Chain Management en un entorno de alta disponibilidad habilitado para LCS, nivel 2 o superior (no un entorno OneBox), con Dynamics 365 Supply Chain Management, versión 10.0.7 o posterior. Si intenta instalar el complemento en un entorno OneBox, la instalación no se completará y deberá cancelarla.

- Su sistema debe estar configurado para la integración con Power Platform. Para obtener más información, consulte Integración de [Microsoft Power Platform con las aplicaciones de finanzas y operaciones](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Habilitar la licencia de Optimización de planificación

Para utilizar la Optimización de planificación, debe habilitar su clave de configuración. Para hacerlo:

1. Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
1. En la pestaña **Claves de configuración**, seleccione la casilla de verificación para **Optimización de planificación**.
1. Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Instalar el complemento de Optimización de planificación

Debe instalar el complemento desde su proyecto de LCS y a continuación activar la funcionalidad de optimización de la planificación desde la interfaz de usuario (IU) de Supply Chain Management.

Para instalar el complemento de Optimización de planificación:

1. Inicie sesión en LCS y abra el entorno deseado.
1. Vaya a **Detalles completos**.
1. Desplácese hacia abajo hasta la ficha desplegable **Complementos del entorno**.
1. Seleccione **Instalar un nuevo complemento**.
1. Seleccione **optimización de la planificación**.
1. Siga la guía de instalación y acepte los términos y condiciones.
1. Seleccione **Instalar**.
1. En la ficha desplegable **Complementos del entorno** debería ver que se está instalando Optimización de planificación.
1. Después de unos minutos, **Instalando** debería cambiar a **Instalado** (es posible que deba actualizar la página). Cuando está instalado, está listo para activar la Optimización de planificación en Dynamics 365 Supply Chain Management.

El objetivo principal de instalar el complemento de Optimización de planificación es conectar el servicio y el entorno. Por lo tanto, debe instalar el complemento por separado en cada entorno en el que utilizará Planning Optimization, independientemente de cualquier código movido entre los entornos.

## <a name="integrate-planning-optimization-with-your-system"></a>Integre la Optimización de la planificación con su sistema

Para configurar si el complemento de optimización de la planificación se debe usar para la planificación maestra, vaya **Planificación maestra** \> **Configuración** \> **Parámetros de optimización de la planificación**.

### <a name="connection-status"></a>Estado de conexión

El estado de la conexión indica el estado actual de la conexión entre Supply Chain Management y el servicio de optimización de la planificación. La tabla siguiente muestra los posibles valores.

| Estado de conexión | Descripción | ¿Se puede usar optimización de la planificación? |
|---|---|---|
| Conectada | Una conexión se ha establecido entre el servicio de optimización de la planificación y Supply Chain Management. | Sí |
| Habilitando conexión | Una petición para activar la conexión al servicio de optimización de la planificación está actualmente en curso. | No |
| Desconectado | No hay conexión al servicio de optimización de la planificación. La conexión se puede cambiar desde LCS, según lo descrito antes en este artículo. | No |
| Deshabilitando conexión | Una petición para desactivar la conexión al servicio de optimización de la planificación está actualmente en curso. | No |
| Obteniendo estado | El sistema está esperando por la información del estado del servicio de optimización de la planificación. | No |

### <a name="the-use-planning-optimization-option"></a>La opción de optimización de la planificación de uso

Si se establece la opción **optimización de la planificación de uso** se determina el motor de planificación que se usa para la planificación maestra:

- **Sí**: la optimización de la planificación se utiliza para la planificación maestra.
- **No**: el motor de planificación maestra en desuso se utiliza para la planificación maestra.

Esta configuración se aplica a todas las entidades legales (empresas). No es posible utilizar Optimización de planificación en algunas entidades legales y el motor de planificación maestra en desuso en otras entidades legales.

> [!NOTE]
> Si se activan los trabajos por lotes existentes de planificación creados para el motor de planificación maestra en desuso se activan mientras que la opción **optimización de la planificación de uso** está establecida en **Sí**, estos trabajos fallarán.

### <a name="integration-with-the-setup"></a>Integración con la configuración

Si la vista previa de Optimización de la planificación está activada, la planificación maestra se realiza mediante el complemento de optimización de la planificación. En este caso, se ven afectados los resultados y las características de la planificación maestra.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
