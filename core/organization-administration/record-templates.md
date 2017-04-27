---
title: Crear plantillas de registro
description: "Este artículo presenta el concepto de las plantillas de registro y explica cómo se pueden usar para crear registros que comparten información."
author: pvillads
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 209e4fb346b8c5a02390996cb1fc8fdbd41ba241
ms.lasthandoff: 03/31/2017


---

# <a name="create-record-templates"></a>Crear plantillas de registro

[!include[banner](../includes/banner.md)]


Este artículo presenta el concepto de las plantillas de registro y explica cómo se pueden usar para crear registros que comparten información.

Las plantillas de registro pueden ayudarle a crear registros más rápidamente en Microsoft Dynamics 365 for Operations. Puede crear plantillas de registro solo para parte de los tipos de registro de Microsoft Dynamics 365 for Operations. Por ejemplo, **** imagínese que está introduciendo información de alquiler para un negocio de alquiler de coches ubicado en Valladolid. Dado que es probable que la mayoría de los clientes sean de la zona de Valladolid, estaría bien que se rellenasen automáticamente los valores para los campos de **Provincia**, **País** y **Ciudad** en el formulario de alquiler. **Nota:** solo se pueden aplicar plantillas para las áreas de Dynamics 365 for Operations a las que se tiene acceso. Sin embargo, todos los títulos de plantilla están visibles para el usuario actual cuando se crea un registro nuevo, así como a los demás usuarios si se crean plantillas que estarán disponibles a todos los usuarios. Asegúrese de tener esto en cuenta al asignar nombres a las plantillas. Por ejemplo, evite usar nombres que incluyan palabras como "comisión" en caso de que sea confidencial que algunos empleados de la empresa tengan salarios basados en comisiones. Cuando una o varias plantillas a las que tiene acceso se han creado para un formulario específico e intenta crear un nuevo registro en el formulario, se mostrará la página **Seleccionar una plantilla para...** . Al seleccionar una plantilla de la lista, se crea un registro nuevo que contiene la información predeterminada que se basa en la plantilla que ha seleccionado. Si no desea utilizar plantillas al crear registros nuevos, active la casilla de verificación **No volver a hacer esta pregunta** en la página **Seleccionar una plantilla para**. Para volver a mostrar el cuadro de diálogo de selección de plantilla, haga clic en **Información de registro** y después en **Mostrar la selección de plantilla**.




