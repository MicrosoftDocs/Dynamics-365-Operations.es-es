---
title: Habilitar Power BI para Contabilidad de inventario global
description: Este tema describe cómo habilitar Microsoft Power BI para la Contabilidad de inventario global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 562b56a85ad2f40cb673f8f2101bf92c39853d1f1a087d0498b6f7d19d1cca01
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773354"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Habilitar Power BI para Contabilidad de inventario global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Puede anclar mosaicos, paneles e informes desde su cuenta de [PowerBI.com](https://powerbi.com/) a su area de trabajo de la aplicación de Microsoft Dynamics 365.

## <a name="prerequisites"></a>Requisitos previos

Deben cumplirse los siguientes requisitos previos antes de poder habilitar informes de Power BI:

- Debe ser administrador del sistema en la aplicación Dynamics 365.
- Debe tener una cuenta de [PowerBI.com](https://powerbi.com/).
- Debe tener al menos un panel y un informe en su cuenta de Power BI.
- Debe ser administrador de su cuenta de Azure Active Directory (Azure AD).
- El dominio de Azure AD debe ser el mismo que usó para su cuenta de [PowerBI.com](https://powerbi.com/).

## <a name="setup"></a>Configurar

Para configurar la integración de Power BI, siga estos pasos.

1. Inicie sesión en [Microsoft Dynamics LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Vaya a **Biblioteca de activos compartidos**, seleccione **Modelo de informe de Power BI** como tipo de activo y descargue el paquete **Contabilidad global de inventarios**. 
1. Inicie sesión en [PowerBI.com](https://app.powerbi.com/) y suba el archivo de informe de Power BI de **Contabilidad global de inventarios** siguiendo estos pasos:

    1. Seleccione **Nuevo**.
    1. Seleccione **Cargar un archivo**.
    1. Seleccione el archivo de informe de Power BI **Contabilidad global de inventarios**.

1. Configure el informe de Power BI **Contabilidad global de inventarios** siguiendo estos pasos:

    1. Vaya a **Mi espacio de trabajo**, busque el conjunto de datos de Contabilidad de inventario global y, a continuación, en el menú **Opciones**, seleccione **Ajustes**.
    1. En **Configuración de la contabilidad de inventario global**, expanda **Parámetros** y actualice todos los parámetros según sea necesario.

1. Registre la aplicación como se describe en [Configurar la integración PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).
1. Integre el archivo de informe de Power BI **Contabilidad global de inventarios** en Dynamics 365 Supply Chain Management siguiendo estos pasos:

    1. Vaya a **Administración del sistema \> Configuración \> Configuración de PowerBI.com**.
    1. Seleccione **Editar**.
    1. Seleccione **Habilita la integración PowerBI.Com**.
    1. En el campo **ID de aplicación**, introduzca el id. de aplicación.
    1. En el campo **Clave de aplicación**, introduzca la clave de aplicación.
    1. Seleccione **Guardar**.

1. Actualice la página para que aparezca el cuadro de diálogo de inicio de sesión de Power BI.
1. En la pestaña **Opciones**, seleccione **Abrir catálogo de informes** y luego seleccione el archivo de informe de Power BI **Contabilidad global de inventarios** que cargó anteriormente.
1. Actualice la página. Debería ver que se ha agregado su informe.
1. En **Informes de Power BI**, seleccione el vínculo **Contabilidad global de inventarios**.

Para obtener más información, consulte [Configurar la integración de PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
