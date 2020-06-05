---
title: Funciones quitadas u obsoletas en Lifecycle Services (LCS)
description: En este tema se describen las funciones que se han eliminado, o que está previsto que se eliminen, de Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5c5c525b403715ba8dfd3c1bc2dfac4dd69f4a3d
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367277"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>Funciones quitadas u obsoletas en Lifecycle Services (LCS)

[!include[banner](../includes/banner.md)]

En este tema se describen las funciones que se han eliminado, o que están en desuso, en Microsoft Dynamics Lifecycle Services (LCS).

- Una función *quitada* deja de estar disponible en el servicio.
- Una función *en desuso* no está en desarrollo activo y se podría quitar en una actualización futura.

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
<td><strong>¿Reemplazado por otra función?</strong></td>
<td>No</td>
</tr>
<tr>
<td><strong>Áreas afectadas</strong></td>
<td>Modelador de procesos empresariales</td>
</tr>
<tr>
<td><strong>Estado</strong></td>
<td>En desuso: se prevé la eliminación del componente de diagramas de flujo en BPM en 2020. La siguiente funcionalidad no estará disponible:
<ul>
<li>Todos los diagramas de flujo serán de solo lectura y no estarán disponibles para edición. Las propiedades de forma asociadas con las actividades del diagrama de flujo tampoco estarán disponibles. Estos diagramas de flujo incluyen diagramas de flujo predeterminados que se generan automáticamente y diagramas de flujo personalizados que se modifican en función de esos diagramas de flujo predeterminados.</li>
<li>La función de análisis de idoneidad/lagunas heredado no estará disponible. Por lo tanto, no se creará automáticamente una lista de lagunas ni estará disponible para la exportación.
<p><strong>Nota:</strong> esta función quedó en desuso anteriormente y fue reemplazada por las integraciones de Microsoft Azure DevOps.</p>
</li>
<li>El historial de versiones del diagrama de flujo no estará disponible.</li>
</ul>
</td>
</tr>
</tbody>
</table>
