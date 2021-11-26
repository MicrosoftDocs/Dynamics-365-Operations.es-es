---
title: Impuestos integrados
description: Este tema describe la integración de datos de impuestos entre Finance and Operations y Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d1e74bbbeba019ca48dd823b58251643e96edd0c
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782219"
---
# <a name="integrated-tax"></a>Impuestos integrados

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos. Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.

## <a name="templates"></a>Plantillas

Los datos de los impuestos incluyen una colección de mapas de tabla que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de Finance and Operations | Aplicaciones Customer Engagement | Descripción |
|-----------------------------|-----------------------------------|-------------|
[Grupo de impuestos de artículos](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Autoridades fiscales](mapping-reference.md#193) | msdyn_taxauthorities | |
[Entidad de código de exención de impuestos para CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Grupos de impuestos](mapping-reference.md#195) | msdyn_taxgroups | |
[Grupos de registro contable de impuestos de ventas V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Códigos de retenciones de impuestos](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Grupos de retenciones de impuestos](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
