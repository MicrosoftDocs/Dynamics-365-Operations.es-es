---
title: Instalar el complemento para microservicios en Lifecycle Services
description: Este artículo explica cómo instalar el complemento Facturación electrónica en Microsoft Dynamics Lifecycle Services (LCS).
author: gionoder
ms.date: 07/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 849d450ddb538e83a4aa6375fc99c705af154c61
ms.sourcegitcommit: 7a03b336d3c1c90770cc9913668c476e34ebf24a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2022
ms.locfileid: "9208999"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Instalar el complemento para microservicios en Lifecycle Services

[!include [banner](../includes/banner.md)]

La autenticación en el servicio de Facturación electrónica requiere que registre su entorno de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management en la plataforma de servicios instalando el complemento para su entorno en Microsoft Dynamics Lifecycle Services (LCS).

Para registrar un entorno, siga estos pasos.

1. Inicie sesión en su cuenta de LCS.
2. En el panel del proyecto, seleccione un proyecto de LCS.
2. En el proyecto, en el panel **Entornos**, seleccione su entorno implementado. El entorno que seleccione debe estar ejecutándose.
3. En la pestaña **Integración de Power Platform**, en la sección **Complementos del entorno**, seleccione **Instalar un nuevo complemento**.
4. Seleccione **Facturacion electrónica**.
5. En el campo **Id. de la aplicación AAD**, introduzca **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Este valor es un valor fijo. Asegúrese de introducir solo un identificador único global (GUID). No incluya ningún otro símbolo, como espacios, comas, puntos o comillas.
6. En el campo **Id. de inquilino de AAD**, introduzca el id. de su cuenta de suscripción de Azure. El inquilino de Azure Active Directory (Azure AD) que especifique debe ser el mismo inquilino que se utiliza para Regulatory Configuration Service (RCS).
7. Revise los términos y condiciones, y luego seleccione la casilla.
8. Seleccione **Instalar**. Después de unos minutos, el estado debería cambiar de **Instalando** a **Instalado**. Es posible que deba actualizar la página para ver este cambio.

La facturación electrónica ya está lista para usarse.

> [!NOTE]
> Las empresas suelen tener varios entornos de Finance o Supply Chain Management. Estos entornos incluyen entornos de producción, entornos de prueba de aceptación de usuarios (UAT) y entornos de desarrollo (espacio aislado). Debe completar el procedimiento anterior para todos los entornos que desea conectar a la facturación electrónica.
