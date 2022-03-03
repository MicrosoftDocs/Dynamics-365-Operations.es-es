---
title: Información general de la facturación de suscripción
description: Este tema describe la facturación de suscripción en Microsoft Dynamics 365 Finance.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b94ac36e49d55ad42909877d77903cd40cb22cbe
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182691"
---
# <a name="subscription-billing-overview"></a>Información general de la facturación de suscripción

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La facturación de suscripción permite a las organizaciones administrar las oportunidades de ingresos por suscripción y la facturación recurrente a través de los calendarios de facturación. Los modelos complejos de fijación de precios y facturación y la asignación de ingresos se gestionan fácilmente y se facturan y reconocen a nivel de línea. La asignación de ingresos de elementos múltiples permite la asignación de ingresos para cumplir con las Normas Internacionales de Contabilidad (Norma Internacional de Financial Reporting 15 \[NIIF 15\]) y principios de contabilidad generalmente aceptados (US GAAP) (tema 606 de codificación de normas de contabilidad. \[ASC 606\]).

La solución cuenta con tres módulos que se pueden utilizar de forma independiente. Alternativamente, los tres módulos se pueden usar juntos.

- **Facturación de contratos recurrentes**: este módulo permite la facturación recurrente y la gestión de precios para proporcionar control sobre los parámetros de precios y facturación, la renovación de contratos y la facturación consolidada.
- **Aplazamientos de ingresos y gastos**: este módulo elimina los procesos manuales y la dependencia de sistemas externos al administrar los ingresos y permitir una visión en tiempo real de los ingresos recurrentes mensuales.
- **Asignación de ingresos de elementos múltiples**: este módulo ayuda con el cumplimiento de los ingresos mediante la gestión de precios y la asignación de ingresos en varios artículos.

La facturación de suscripción se habilita a través de **Administración de características**. Sin embargo, no se puede utilizar con la característica **Reconocimiento de ingresos**. Por lo tanto, debe deshabilitar esa característica antes de habilitar la facturación de la suscripción.

1. En el espacio de trabajo **Administración de características**, en la pestaña **Todos**, introduzca **Reconocimiento de ingresos** en el filtro y, a continuación, seleccione el nombre de la característica como filtro.
2. Seleccione la característica **Reconocimiento de ingresos** y luego seleccione el botón **Deshabilitar**.
3. En el filtro **Nombre de la característica**, introduzca **Facturación de suscripción** y, a continuación, seleccione el filtro de módulo.
4. Seleccione la característica **Facturación de suscripción** y, a continuación, seleccione **Habilitar**.
5. Seleccione uno de los tres módulos de la lista anterior y luego seleccione **Habilitar**. Repita este paso para los otros dos módulos.

    > [!IMPORTANT]
    > La característica **Facturación de suscripción** debe estar habilitada antes de poder habilitar cualquiera de los tres módulos.
