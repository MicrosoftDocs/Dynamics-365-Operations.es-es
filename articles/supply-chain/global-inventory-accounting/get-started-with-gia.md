---
title: Introducción a la contabilidad de inventario global
description: Este artículo describe cómo comenzar con la Contabilidad de inventario global.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cbe6bff6fab96900b8bd4e112a8858363fff86d1
ms.sourcegitcommit: 9870b773a2ea8f5675651199fdbc63ca7a1b4453
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013566"
---
# <a name="get-started-with-global-inventory-accounting"></a>Introducción a la contabilidad de inventario global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

La contabilidad de inventario global permite realizar múltiples contabilidades de inventarios en los libros de contabilidad de inventario global que ha configurado. Debe asociar cada libro de contabilidad de inventario global a una *convención*. Una convención es una colección de los siguientes tipos de directivas contables:

- Objeto de coste
- Base de medida de entrada
- Suposición de flujo de costes
- Elemento de coste

> [!NOTE]
> Incluso después de haber activado la contabilidad de inventario global, aún puede hacer contabilidad de inventario en Microsoft Dynamics 365 Supply Chain Management como siempre.

La contabilidad de inventario global es un complemento. Para que sus funciones estén disponibles, debe instalarlo desde Microsoft Dynamics Lifecycle Services (LCS). Puede elegir evaluarlo en un entorno de prueba antes de activarlo para entornos de producción.

Actualmente, la contabilidad de inventario global no admite todas las funciones de administración de costos que están integradas en Supply Chain Management. Por lo tanto, es importante que evalúe si el conjunto de funciones que están disponibles actualmente cumplirá sus requisitos.

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a>Cómo obtener el complemento Contabilidad de inventario global

> [!IMPORTANT]
> Para utilizar la contabilidad de inventario global, debe tener un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox). Además, debe ejecutar Supply Chain Management versión 10.0.19 o posterior.

### <a name="supply-chain-management-version-10019-to-10026"></a>Supply Chain Management versión 10.0.19 a 10.0.26

Para instalar Contabilidad de inventario global para Supply Chain Management versión 10.0.19 a 10.0.26, comience [instalando el complemento](#install). A continuación, envíe su ID de entorno LCS y el nombre de la empresa por correo electrónico al [Equipo de contabilidad de inventario global](mailto:GlobalInvAccount@microsoft.com). El equipo le enviará un correo electrónico de seguimiento que contiene los puntos de conexión del servicio de Contabilidad de inventario global.

### <a name="supply-chain-management-version-10027-and-later"></a>Supply Chain Management versión 10.0.27 y posterior

Para instalar Contabilidad de inventario global para Supply Chain Management versión 10.0.27 y posterior, [instale el complemento](#install). Para estas versiones de Supply Chain Management, los puntos de conexión del servicio de Contabilidad de inventario global se configurarán automáticamente, por lo que no es necesario que los encuentre manualmente. Si experimenta algún problema al configurar el complemento, comuníquese con el [Equipo de contabilidad de inventario global](mailto:GlobalInvAccount@microsoft.com).

## <a name="licensing"></a>Licencias

La contabilidad de inventario global tiene licencia junto con las funciones estándar de la contabilidad de inventario que están disponibles para Supply Chain Management. No tiene que comprar una licencia adicional para usar la contabilidad de inventario global.

## <a name="prerequisites"></a>Requisitos previos

### <a name="set-up-microsoft-power-platform-integration"></a>Configurar la integración de Microsoft Power Platform

Antes de poder habilitar la funcionalidad de complemento, debe integrarse con Microsoft Power Platform siguiendo estos pasos.

1. Abra el entorno LCS donde desea agregar el servicio.
1. Vaya a **Detalles completos**.
1. En la sección **Integración de Power Platform**, seleccione **Configuración**.
1. En el cuadro de diálogo **Configuración del entorno de Power Platform**, seleccione la casilla de verificación y luego seleccione **Configuración**. Normalmente, la instalación tarda entre 60 y 90 minutos.
1. Después de la instalación del entrorno de Microsoft Power Platform se completa, la página muestra el nombre de su entorno. Además, la sección **Integración de Power Platform** muestra la declaración, "La configuración del entorno de Power Platform está completa". La contabilidad de inventario global no requiere una aplicación de escritura dual.

Para obtener más información, consulte [Habilitar después de la implementación del entorno](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="install-the-add-in"></a><a name="install"></a>Instalar el complemento

Siga estos pasos para instalar el complemento y poder utilizar la Contabilidad de inventario global.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index).
1. Abra el entorno LCS donde desea agregar el servicio.
1. Vaya a **Detalles completos**.
1. Vaya a **Integración de Power Platform** y seleccione **Configuración**.
1. En el cuadro de diálogo **Configuración del entorno de Power Platform**, seleccione la casilla de verificación y luego seleccione **Configuración**. Normalmente, la instalación tarda entre 60 y 90 minutos.
1. Cuando termine la configuración del entorno Microsoft Power Platform, inicie sesión en el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com) y luego instale el complemento Contabilidad de inventario global siguiendo los siguientes pasos:
   1. Seleccione el entorno donde desea instalar el complemento.
   1. Seleccione **Aplicaciones de Dynamics 365**.
   1. Seleccione **Instalar aplicación**.
   1. Seleccione **Contabilidad de inventario global de Dynamics 365**.
   1. Seleccione **Siguiente** para instalar.
1. Vuelva al entorno LCS. En la ficha desplegable **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
1. Seleccione **Contabilidad de inventario global**.
1. Siga la guía de instalación y acepte los términos y condiciones.
1. Seleccione **Instalar**.
1. En la ficha desplegable **Complementos de entorno**, debería ver que se está instalando la contabilidad de inventario global. Después de unos minutos, el estado debería cambiar de *Instalando* a *Instalado*. (Es posible que tenga que actualizar la página para ver este cambio). En ese momento, la contabilidad de inventario global está lista para usar.

Si el idioma predeterminado de su instalación de Dataverse no es en inglés, siga estos pasos:
1. Vaya a **Configuración avanzada \> Administración \> Idiomas**.
1. Seleccione *Inglés* (*LanguageCode = 1033*) y seleccione **Solicitar**.

## <a name="set-up-the-integration"></a>Configuración de la integración

Siga estos pasos para configurar la integración entre la contabilidad de inventario global y Supply Chain Management.

1. Inicie sesión en de Supply Chain Management.
1. Vaya a **Administración del sistema \> Administración de funciones**.
1. Seleccione **Buscar actualizaciones**.
1. En la pestaña **Todas**, busque la característica que se denomina *(Vista previa) Contabilidad global de inventarios*.
1. Seleccione **Habilitar ahora**.
1. Ir **Contabilidad global de inventarios \> Configuración \> Parámetros de contabilidad de inventario global \> Parámetros de integraciones**.
1. Según qué versión de Supply Chain Management esté ejecutando, realice uno de los siguientes pasos:
    - **Supply Chain Management versión 10.0.19 a 10.0.26**: En los campos **Extremo del servicio de datos** y **Punto de conexión de contabilidad de inventario global**, ingrese las URL que le fueron enviadas por correo electrónico desde el equipo de Contabilidad de inventario global (vea también [Cómo obtener el complemento Contabilidad de inventario global](#sign-up)).
    - **Supply Chain Management versión 10.0.27 y posteriores**: no necesita ingresar los puntos de conexión, por lo que puede omitir este paso.

La Contabilidad de inventario global ya está lista para usar.
