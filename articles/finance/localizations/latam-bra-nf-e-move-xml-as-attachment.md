---
title: Mover archivos NF-e XML como archivos adjuntos
description: Este artículo explica cómo mover archivos NF-e XML fuera de su base de datos de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management y ponerlos a disposición como archivos adjuntos.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 7bb0fb975c6d73cc4e990b39ea9b5a0c0455db74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270636"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>Mover archivos NF-e XML como archivos adjuntos

[!include [banner](../includes/banner.md)] 


Cuando se emiten documentos electrónicos fiscales (NF-e), los archivos XML se crean y almacenan en bases de datos de Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management. En la localización brasileña, puede utilizar la característica **Mover archivos NF-e XML como archivos adjuntos** para liberar el espacio de la base de datos que consumen esos archivos XML.

Para un intervalo de fechas y un establecimiento fiscal específicos, la función mueve los archivos NF-e XML desde su base de datos de Finance o Supply Chain Management al almacenamiento de blobs desde su suscripción de Azure. Este movimiento hace que los archivos estén disponibles solo como archivos adjuntos. Una vez que los archivos XML se han movido correctamente al almacenamiento de blobs, los archivos originales se eliminan de la base de datos de Finance o Supply Chain Management. Por lo tanto, se libera el espacio de la base de datos que utilizaron esos archivos.

Para habilitar la característica **Mover archivos NF-e XML como archivos adjuntos**, siga estos pasos.

1. En Finance o Supply Chain Management, abra el espacio de trabajo **Administración de características**.
2. En la pestaña **Todos**, busque y seleccione la característica **Mover archivos NF-e XML como archivos adjuntos**.
3. Seleccione **Habilitar ahora**.

Siga estos pasos para mover archivos NF-e XML como archivos adjuntos.

1. Vaya a **Clientes** \> **Documentos fiscales** \> **Documentos fiscales electrónicos** \> **Mover archivos NF-e XML como archivos adjuntos**.
2. En los campos **Desde fecha** y **Hasta fecha**, seleccione las fechas de inicio y final.
3. En el campo **Id. de establecimiento fiscal**, seleccione un valor.
4. Seleccione **Aceptar**.

> [!IMPORTANT]
> Este proceso no es reversible. Después de mover los archivos NF-e XML, los usuarios solo pueden verlos seleccionando **Archivos adjuntos** en la parte superior de la página **Documento fiscal**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
