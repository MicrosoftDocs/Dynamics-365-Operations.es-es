---
title: Aplicaciones conectadas
description: Este artículo explica cómo configurar aplicaciones en Facturación electrónica.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: aa6c80914301cc0403974a6acc5e95ff61c9c1a7
ms.sourcegitcommit: a5a4c45bb265758c6e5c3483c8552503b1799a89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "9524699"
---
# <a name="connected-applications"></a>Aplicaciones conectadas

[!include [banner](../includes/banner.md)]

Las aplicaciones conectadas son las instancias de Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management a las que quizás desee acceder a través de Regulatory Configuration Service (RCS). A través de las aplicaciones conectadas, puede configurar parte de la característica Globalización en Finance o Supply Chain Management para que funcione el escenario de Facturación electrónica.

Cuando implementa su característica Globalización, la información de configuración que se aplica a su aplicación Finance o Supply Chain Management se puede publicar directamente desde RCS a la aplicación conectada adecuada.

La disponibilidad de los parámetros de Finance o Supply Chain Management en RCS es útil cuando tiene varios entornos de aplicación, como pruebas de aceptación de usuarios (UAT) y entornos de producción, y desea mantener la configuración uniforme mediante la implementación de los mismos parámetros en diferentes entornos.

## <a name="create-a-connected-application"></a>Crear una aplicación conectada

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Característica de globalización**, en la sección **Enlaces relacionados**, seleccione **Configurar entorno**.
3. En la página **Configuración de entornos**, en el Panel de acciones, seleccione **Aplicaciones conectadas**.
4. Seleccione **Nuevo** para crear una aplicación conectada.
5. En el campo **Nombre**, especifique el nombre de la aplicación a conectar.
6. En el campo **Tipo**, seleccione **Dynamics 365 Finance**.
7. En el campo **Aplicación**, especifique la dirección URL del entorno que se conectará.
8. En el campo **Inquilino**, especifique el inquilino del entorno.
9. Seleccione **Guardar**.
10. En el panel de acciones, seleccione **Comprobar conexión** para probar la conexión con el entorno. A continuación, cierre la página.

## <a name="link-connected-applications-to-environments"></a>Vincular aplicaciones conectadas a entornos

1. En la página **Configuración de entornos**, seleccione **Nuevo** para asignar una aplicación conectada a un entorno.
2. En el campo **Aplicación conectada**, seleccione una aplicación conectada.
3. En el campo **Entorno de servicio**, seleccione un entorno de servicio.
4. Haga clic en **Guardar** y, a continuación, cierre la página.
