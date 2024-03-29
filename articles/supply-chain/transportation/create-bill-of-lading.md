---
title: Crear un conocimiento de embarque
description: Este artículo describe cómo crear un conocimiento de embarque al utilizar procesos de gestión de almacenes (WMS).
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68a703475191255ff6ceaee25ef8e2bdf33ba0c2
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069708"
---
# <a name="create-a-bill-of-lading"></a>Crear un conocimiento de embarque

[!include [banner](../includes/banner.md)]

Este artículo describe cómo crear un conocimiento de embarque al utilizar procesos de gestión de almacenes (WMS).  

Un conocimiento de embarque es un documento legal entre la empresa que envía los artículos y el transportista. El documento acompaña a los artículos enviados y sirve como recepción de envío cuando los artículos se entregan en el destino. Si utiliza la gestión de almacenes, hay dos maneras de generar un conocimiento de embarque:

  -   Cree el informe manualmente, mediante la página **Conocimiento de embarque**.
  -   Genere el informe desde el **Área de trabajo de planificación de la carga**.

Si genera el conocimiento de embarque desde el **Área de trabajo de planificación de la carga**, el estado de carga debe ser **Enviados**. Si hay más de un envío en la carga, se crea un conocimiento de embarque para cada envío. Una vez que se ha creado un conocimiento de embarque, puede realizar cambios en él en la página **Conocimiento de embarque**.

## <a name="master-bill-of-lading"></a>Conocimiento de embarque maestro
Si hay más de un envío en la carga, puede generar un conocimiento de embarque maestro. Esto tiene el mismo diseño e información que un conocimiento de embarque, pero contiene el contenido resumido para todos los envíos. Si la opción **Crear un conocimiento de embarque maestro cuando exista más de un envío en una carga** se establece en **Sí** en la página **Parámetros de administración de transporte**, se genera automáticamente un conocimiento de embarque maestro si crea un conocimiento de embarque en **Área de trabajo de planificación de la carga** y hay más de un envío. También puede obtener una lista de los conocimientos de embarque haciendo clic en **Información relacionada** &gt; **Conocimiento de embarque**. Si está creando conocimientos de embarque manualmente, puede crear un conocimiento de embarque maestro en la página **Conocimiento de embarque**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]