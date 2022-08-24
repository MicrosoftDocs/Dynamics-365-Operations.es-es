---
title: Impuestos integrados
description: Este artículo describe la integración de datos de impuestos entre finanzas y operaciones y Dataverse.
author: josaw
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8f148b710e2294edf1e402b9b8b22cb24e60a1f2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288806"
---
# <a name="integrated-tax"></a>Impuestos integrados

[!include [banner](../../includes/banner.md)]



Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos. Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.

## <a name="templates"></a>Plantillas

Los datos de los impuestos incluyen una colección de mapas de tabla que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de finanzas y operaciones | Aplicaciones Customer Engagement | Description |
|-----------------------------|-----------------------------------|-------------|
[Grupo de impuestos de artículos](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Autoridades fiscales](mapping-reference.md#193) | msdyn_taxauthorities | |
[Entidad de código de exención de impuestos para CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Grupos de impuestos](mapping-reference.md#195) | msdyn_taxgroups | |
[Grupos de registro contable de impuestos de ventas V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Códigos de retenciones de impuestos](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Grupos de retenciones de impuestos](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

