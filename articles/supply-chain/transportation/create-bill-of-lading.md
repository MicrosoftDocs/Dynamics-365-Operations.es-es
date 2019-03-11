---
title: Crear un conocimiento de embarque
description: Este tema describe cómo crear un conocimiento de embarque al utilizar procesos de gestión de almacenes.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8d5caed5553ad1c7aec5db83591024129aab1264
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "352606"
---
# <a name="create-a-bill-of-lading"></a>Crear un conocimiento de embarque

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear un conocimiento de embarque al utilizar procesos de gestión de almacenes.  

Un conocimiento de embarque es un documento legal entre la empresa que envía los artículos y el transportista. El documento acompaña a los artículos enviados y sirve como recepción de envío cuando los artículos se entregan en el destino. Si utiliza la gestión de almacenes, hay dos maneras de generar un conocimiento de embarque:

  -   Cree el informe manualmente, mediante la página **Conocimiento de embarque**.
  -   Genere el informe desde el **Área de trabajo de planificación de la carga**.

Si genera el conocimiento de embarque desde el **Área de trabajo de planificación de la carga**, el estado de carga debe ser **Enviados**. Si hay más de un envío en la carga, se crea un conocimiento de embarque para cada envío. Una vez que se ha creado un conocimiento de embarque, puede realizar cambios en él en la página **Conocimiento de embarque**.

## <a name="master-bill-of-lading"></a>Conocimiento de embarque maestro
Si hay más de un envío en la carga, puede generar un conocimiento de embarque maestro. Esto tiene el mismo diseño e información que un conocimiento de embarque, pero contiene el contenido resumido para todos los envíos. Si la opción **Crear un conocimiento de embarque maestro cuando exista más de un envío en una carga** se establece en **Sí** en la página **Parámetros de administración de transporte**, se genera automáticamente un conocimiento de embarque maestro si crea un conocimiento de embarque en **Área de trabajo de planificación de la carga** y hay más de un envío. También puede obtener una lista de los conocimientos de embarque haciendo clic en **Información relacionada** &gt; **Conocimiento de embarque**. Si está creando conocimientos de embarque manualmente, puede crear un conocimiento de embarque maestro en la página **Conocimiento de embarque**.



