---
title: "Sustitución material en la fabricación"
description: "Este tema describe cómo sustituir materiales durante el proceso de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b3e70a6ad074911438ef45b6aac2523a4a9fccf8
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="material-substitution-in-manufacturing"></a>Sustitución material en la fabricación

[!include [banner](../includes/banner.md)]

Este tema describe cómo sustituir materiales durante el proceso de producción. 

Hay tres métodos para sustituir materiales durante el proceso de producción:

-   Por fecha, cuando un material se reemplaza por otro después de una fecha específica.
-   Durante la planificación maestra, cuando se sustituye material en una fórmula con otro material por no quedar existencias.
-   Durante la producción, cuando un material se agota de forma inesperada y se reemplaza con otro material.

## <a name="substituting-material-by-date"></a>Sustitución de material por fecha
Imagine el siguiente caso: una máquina que una empresa está fabricando contiene un componente que dejará de estar en el catálogo del proveedor en dos meses. A partir de la fecha en la que dejará de incluirse en el catálogo, el proveedor ofrecerá un nuevo componente que pueda reemplazar al antiguo componente. Las fechas de inicio y fin de validez se pueden configurar en las líneas de la lista de materiales. Por ejemplo, puede configurar que el antiguo componente deje de existir especificando la fecha de vencimiento en el campo **Fecha final**. A continuación, en la lista de materiales puede configurar el nuevo componente de sustitución de forma que sea válido a partir del día después de que venza el componente antiguo. Para ello, especifique la fecha de inicio en el campo **fecha inicial**.

## <a name="substituting-material-by-planning"></a>Sustitución de material por planificación
Puede sustituir materiales durante la planificación únicamente cuando se están usando fórmulas, no cuando se está usando una lista de materiales. Imagine el siguiente caso: una empresa de fabricación de alimentos hace una salsa de una fórmula que tiene 20 ingredientes. Un ingrediente en la fórmula se puede reemplazar por uno de otros dos ingredientes. Sin embargo, dado que estos dos ingredientes son más costosos que el ingrediente preferido, solo se sustituye si no queda el ingrediente preferido. El material que puede ser sustituido se denomina A, mientras que los dos materiales que lo pueden substituir se llaman B y C. La sustitución de material mediante planificación se controla en los campos **Grupo de planificación** y **Prioridad** de las líneas de la fórmula. Por ejemplo, puede crear líneas de fórmula para los tres materiales y asociar las líneas de fórmula con el mismo grupo de planificación. En la configuración, la línea de fórmula para el material A tiene la máxima prioridad (el número más bajo), la línea de fórmula para el material C tiene la prioridad más baja, y la línea de fórmula para el material B tiene una prioridad que se encuentre entre la prioridad de las otras dos líneas. Si tiene demanda para el artículo terminado, la planificación maestra primero determina si se puede cubrir la demanda para el material A. Si la demanda no se puede cubrir, la planificación maestra busca los materiales B y C en orden de prioridad. Si el material B está disponible, se utilizará después de firmar un pedido planificado de lote para la fórmula. Si ninguno de los materiales está disponible, la planificación maestra crea un pedido planificado para el material A. **Nota:** al configurar líneas de fórmula en un grupo de planificación, debe especificar una cantidad solo en el material que tiene la máxima prioridad. Esta cantidad se usará para calcular la demanda de todos los materiales en el plan, incluso los materiales que tienen prioridad más baja. No puede especificar diferentes cantidades de artículos de más baja prioridad en el grupo de planificación.

## <a name="substituting-material-during-production"></a>Sustitución de material durante la producción
Imagine el caso siguiente: se necesita una placa de metal para una operación de soldadura. Al realizar esta tarea, un trabajador de almacén informa al operador de la máquina de que no quedan placas. Sin embargo, se ha decidido que la placa se puede reemplazar por una placa ligeramente más gruesa. De esta manera, el trabajo se puede terminar. El material se puede agregar a la lista de materiales para un pedido de producción abierto. Si el pedido de producción tiene estado **Iniciado**, se solicita a los usuarios que vuelvan a estimar el pedido cuando agreguen un nuevo artículo a la lista de materiales de producción. Después de agregar el material, se puede crear una nueva lista de selección para el artículo nuevo. No es necesario agregar el nuevo material a la lista de materiales de producción. En su lugar, podrá agregarlo directamente a la lista de selección de producción. Posteriormente, cuando se registre la lista de selección, el sistema agregará el material a la lista de materiales de producción.




