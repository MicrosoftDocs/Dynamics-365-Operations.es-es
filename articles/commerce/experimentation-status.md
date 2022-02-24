---
title: Revisar el estado de un experimento
description: Este tema explica qué estado tiene un experimento en el ciclo de vida de la experimentación en Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 5ae29fe5ac49d92c261c59d115664b50e87880a0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965132"
---
# <a name="review-the-status-of-an-experiment"></a>Revisar el estado de un experimento
Hay muchos pasos involucrados en la configuración y ejecución de un experimento en Dynamics 365 Commerce. Para obtener información sobre el ciclo de vida de la experimentación, consulte [Experimentación en Dynamics 365 Commerce](experimentation-overview.md).

Para saber dónde se encuentra un experimento en el ciclo de vida, en el generador de sitios de Commerce vaya a la pestaña **Experimentos** del panel de navegación izquierdo. Se muestra una lista de experimentos con el estado de cada experimento tanto en Commerce como en el servicio de terceros que se está utilizando para permitir la creación de experimentos, asignar variaciones y analizar datos.

En la columna **Estado comercial**, se pueden mostrar los siguientes valores. 
- **Borrador** - El experimento está conectado a una página o fragmento en Commerce y se está editando.
- **Publicado** - Las variaciones del experimento están listas para mostrarse en su sitio web. Si el experimento se está ejecutando en el servicio de terceros, los usuarios del sitio web verán una variación de la página o el fragmento seleccionado por el servicio de terceros.
- **Inédito** - El experimento ya no está disponible en su sitio web. Los usuarios del sitio web solo verán la versión predeterminada de la página o el fragmento incluso si el experimento se está ejecutando en el servicio de terceros.
- **Terminado** - El experimento ha seguido su curso y se promovió una variación para que esté disponible para todos los usuarios del sitio web.

Del mismo modo, en la columna **estado de terceros**, los siguientes valores pueden mostrarse para indicar en qué estado se encuentran los experimentos en el servicio de terceros.
- **Borrador** - El experimento está configurado en el servicio de terceros, pero no se ha iniciado.
- **En ejecución** - El experimento se inició en el servicio de terceros y está recopilando datos.
- **Pausado** - El experimento está en pausa y no se recopilan datos. Debe reanudar el experimento para que vuelva a recopilar datos.
- **Archivado** - El experimento ha seguido su curso y se ha catalogado en el servicio de terceros para futuras referencias.

El siguiente diagrama muestra ambos conjuntos de estados y cómo se relacionan entre sí.

[ ![Estados de experimentación](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)
