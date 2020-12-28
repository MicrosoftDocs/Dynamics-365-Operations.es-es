---
title: Digitalizar códigos de barras mediante una cámara en la aplicación de almacén
description: Este tema explica cómo configurar la aplicación de almacén para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: fd4818ab936e1c93000793da756c97df6d05b2a9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436646"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a>Digitalizar códigos de barras mediante una cámara en la aplicación de almacén

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar la aplicación de almacén para digitalizar códigos de barras mediante una cámara en un dispositivo móvil. 

## <a name="prerequisites"></a>Requisitos previos
Para utilizar esta característica, debe tener instalada la versión 1.2.0.0 de la aplicación de almacén y su dispositivo debe tener una cámara. Cuando abra la aplicación después de actualizarla, se le solicitará que permita a la aplicación usar la cámara. Si su dispositivo no tiene cámara, no se mostrará ningún mensaje y no podrá utilizar una cámara como escáner. 

## <a name="setup"></a>Configurar
En la configuración de visualización de la aplicación de almacén, puede seleccionar si la cámara debe utilizarse para la digitalización de códigos de barras. Si habilita la opción **Usar la cámara como escáner**, puede usar la cámara en cada campo de entrada que tenga el modo de entrada preferido establecido en **Exploración**. 

Para controlar si un campo de entrada debe ser escaneable, en la página **Nombres de campo de aplicación Warehouse**, establezca **Modo de entrada preferido** en **Exploración**. Cuando se selecciona esta opción, se puede usar una cámara para escanear en la aplicación de almacén. Para obtener información sobre cómo configurar nombres de campo en Warehousing, consulte [Configurar nombres de campo de aplicación en la aplicación de almacén](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Formatos de códigos de barras admitidos
Se admiten los formatos de códigos de barras más comúnes, incluido el Código 128, el Código 39, el Código 93, EAN-8, EAN-13, UPC-E, UPC-A y códigos QR. 

## <a name="navigation"></a>Navegación
La página de la cámara se iniciará en cada página donde el campo de entrada tenga el modo de entrada preferido establecido en Exploración, cuando se encuentre en la página Cámara, use las siguientes opciones para navegar:
- Haga clic en el botón Atrás para volver a la página de tarea y detalles. 
- Haga clic en el lápiz en la página de tarea y detalles para pasar a la página donde puede escribir la entrada manualmente.
- Haga clic en la cámara en la página de tarea y detalles para volver a la página Cámara. 

| Página de tarea y detalles | Página de la cámara | 
| :---------------------: | :--------------------: |
| ![Página de detalles de tarea de ejemplo de escaneo de cámara](./media/camera-scanning-example-task-detail-page50.png)          | ![Ejemplo de escaneo de cámara, página de cámara más pequeña](./media/camera-scanning-example-camera-page50.png)          |

En la página de la cámara, al hacer clic en el botón Cámara, aparecerá atenuada mientras trata de identificar un código de barras. Si no se identifica un código de barras en menos de 5 segundos, el proceso se pondrá en tiempo de espera y el botón Cámara volverá a estar disponible. A continuación, podrá intentar escanear de nuevo un código de barras.

Cuando apunte la cámara a un código de barras, mantenga el código de barras alineado entre los corchetes para lograr un mejor resultado. Cuando un código de barras se digitaliza correctamente, el resultado se procesará y pasará al siguiente paso. Si el siguiente paso contiene otro campo de entrada con el modo de entrada preferido establecido en Exploración, la página de la cámara se volverá a iniciar. Si el paso siguiente no es un campo de exploración, la página de la cámara no se iniciará.

