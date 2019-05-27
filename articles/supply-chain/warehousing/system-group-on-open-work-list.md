---
title: Agrupamiento del sistema en una lista de trabajo abierta
description: Este tema describe cómo filtrar la lista de trabajos abierta en un dispositivo móvil.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 73e1da37c354eecf1ef5d44e68d814664fe2be99
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564815"
---
# <a name="system-grouping-on-an-open-work-list"></a>Agrupamiento del sistema en una lista de trabajo abierta

[!include [banner](../includes/banner.md)]

Usando un campo de agrupamiento del sistema puede filtrar una lista de trabajos abierta sin tener que editar el elemento de menú del dispositivo móvil.
Donde corresponda, el agrupamiento del sistema funciona para filtrar una lista de trabajos en un solo campo de encabezados de trabajos. No puede usar el agrupamiento del sistema para filtrar campos en el nivel de línea.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Configuración del agrupamiento del sistema en una lista de trabajos abierta
Siga estos pasos para configurar el agrupamiento del sistema en una lista de trabajos abierta.

-   Desde un elemento de menú del dispositivo móvil, seleccione **Modo: Indirecto** y **Código de actividad: Mostrar lista de trabajo abierta**. Están disponibles las siguientes opciones. Estas opciones son obligatorias para el agrupamiento del sistema en una lista de trabajo abierta. 

|        Opción         |                                                                                                                                                                                                                                                                         Descripción                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Permitir agrupamientos del sistema |                                                                                                                                                                                                                                                 Habilita los agrupamientos del sistema para un elemento de menú seleccionado de la lista de trabajo.                                                                                                                                                                                                                                                  |
| Campo de agrupamiento del sistema | Disponible solo si <strong>Permitir trabajos del sistema</strong> está configurado en <strong>Sí</strong>. Seleccione el campo que determina cómo se agrupará el trabajo de selección para los trabajadores. Por ejemplo, si selecciona el campo <strong>ShipmentId</strong>, el trabajador explorará la identificación del envío para agrupar el trabajo de picking. Todo el trabajo para el envío se asigna al trabajador. Este campo requiere que cree un elemento de menú para usar el trabajo existente que el sistema ha agrupado. Use el campo <strong>Etiqueta de agrupamiento del sistema</strong> para informar al trabajador de qué debe escanear. |
| Etiqueta de agrupamiento del sistema |                       Disponible solo si <strong>Permitir trabajos del sistema</strong> está configurado en <strong>Sí</strong>. Especifique la información para el trabajador sobre qué escanear cuando el trabajo de selección se agrupe. Por ejemplo, si usa el campo <strong>ShipmentId</strong> para agrupar el trabajo de selección por envíos, puede especificar el Id. del envío en el campo. Este campo requiere que cree un elemento de menú para usar el trabajo existente que el sistema ha agrupado. También debe seleccionar el campo por el que desea agrupar en el campo <strong>Agrupamiento del sistema</strong>.                       |

