---
title: Características quitadas u obsoletas en Lifecycle Services (LCS)
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen, de Microsoft Dynamics Lifecycle Services (LCS).
author: sericks007
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c792d06e9b0aa42919de924bdcc9118358779b72
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885464"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>Características quitadas u obsoletas en Lifecycle Services (LCS)

[!include[banner](../includes/banner.md)]

En este tema se describen las características que se han eliminado, o que están en desuso, en Microsoft Dynamics Lifecycle Services (LCS).

- Una característica *quitada* deja de estar disponible en el servicio.
- Una característica *en desuso* no está en desarrollo activo y se podría quitar en una actualización futura.

Esta lista se proporciona para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.

## <a name="october-2019-announcements"></a>Anuncios de octubre de 2019

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Diagramas de flujo en el Modelador de procesos empresariales

<table>
<tbody>
<tr>
<td><strong>Motivo de la depreciación/eliminación</strong></td>
<td>Vamos a dejar de usar el componente de diagramas de flujo en el Modelador de procesos empresariales (BPM), ya que el diseño heredado hizo que se usara poco.</td>
</tr>
<tr>
<td><strong>¿Reemplazado por otra característica?</strong></td>
<td>No</td>
</tr>
<tr>
<td><strong>Áreas afectadas</strong></td>
<td>Modelador de procesos empresariales</td>
</tr>
<tr>
<td><strong>Estado</strong></td>
<td>En desuso: se prevé la eliminación del componente de diagramas de flujo en BPM a principios de febrero de 2020. Se quitará la siguiente funcionalidad:
<ul>
<li>Los diagramas de flujo existentes no se podrán ver ni editar. Las propiedades de forma asociadas a las actividades del diagrama de flujo tampoco estarán disponibles, ya que se quitará la pestaña <strong>Diagrama de flujo</strong> completa. Estos diagramas de flujo incluyen diagramas de flujo predeterminados que se generan automáticamente y diagramas de flujo personalizados que se modifican en función de esos diagramas de flujo predeterminados.</li>
<li>La característica de análisis de idoneidad/lagunas heredado no estará disponible. Por lo tanto, no se creará automáticamente una lista de lagunas ni estará disponible para la exportación.
<p><strong>Nota:</strong> esta característica quedó en desuso anteriormente y fue reemplazada por las integraciones de Microsoft Azure DevOps.</p>
</li>
<li>El historial de versiones del diagrama de flujo no estará disponible.</li>
</ul>
</td>
</tr>
</tbody>
</table>
