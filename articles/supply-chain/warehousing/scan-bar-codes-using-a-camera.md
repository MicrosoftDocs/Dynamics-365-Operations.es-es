---
title: Digitalizar códigos de barras mediante una cámara en la aplicación Gestión de almacenes
description: Este tema explica cómo configurar la aplicación móvil Warehouse Management para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: cc58d88865fea17e0e27463b25e2ba815ee1a5b1
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901996"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Digitalizar códigos de barras mediante una cámara en la aplicación Gestión de almacenes

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar la aplicación móvil Warehouse Management para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.

## <a name="setup"></a>Configurar

En la configuración de visualización de la aplicación móvil Warehouse Management, puede seleccionar si la cámara debe utilizarse para la digitalización de códigos de barras. Si habilita la opción **Usar la cámara como escáner**, puede usar la cámara en cada campo de entrada que tenga el modo de entrada preferido establecido en **Exploración**.

Para controlar si un campo de entrada debe ser escaneable, en la página **Nombres de campo de aplicación Warehouse**, establezca **Modo de entrada preferido** en **Exploración**. Cuando se selecciona esta opción, se puede usar una cámara para escanear en la aplicación móvil Warehouse Management. Para más información, consulte [Configurar campos para la aplicación](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Formatos de códigos de barras admitidos

Se admiten los formatos de códigos de barras más comúnes, incluido el Código 128, el Código 39, el Código 93, EAN-8, EAN-13, UPC-E, UPC-A y códigos QR.

## <a name="navigation"></a>Navegación

La página de la cámara se iniciará en cada página donde el campo de entrada tenga el **Modo de entrada preferido** establecido en *Exploración*, cuando se encuentre en la página Cámara, use las siguientes opciones para navegar:

- Seleccione el botón Atrás para volver a la página de **Tarea y detalles**.
- Seleccione el lápiz en la página de **Tarea y detalles** para pasar a la página donde puede escribir la entrada manualmente.
- Seleccione la cámara en la página de **Tarea y detalles** para volver a la página Cámara.

En la página de la cámara, al seleccionar el botón Cámara, aparecerá atenuada mientras trata de identificar un código de barras. Si no se identifica un código de barras en menos de 5 segundos, el proceso se pondrá en tiempo de espera y el botón cámara volverá a estar disponible. A continuación, podrá intentar escanear de nuevo un código de barras.

Cuando apunte la cámara a un código de barras, mantenga el código de barras alineado entre los corchetes para lograr un mejor resultado. Cuando un código de barras se digitaliza correctamente, el resultado se procesará y pasará al siguiente paso. Si el siguiente paso contiene otro campo de entrada con el modo de entrada preferido establecido en Exploración, la página de la cámara se volverá a iniciar. Si el paso siguiente no es un campo de exploración, la página de la cámara no se iniciará.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]