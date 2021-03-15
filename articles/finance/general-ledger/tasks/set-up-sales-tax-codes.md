---
title: Configurar códigos de impuestos
description: Este tema explica cómo configurar códigos de impuestos en Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f6df5ed3fc49b537845e7d418d4953c0faee5f3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994549"
---
# <a name="set-up-sales-tax-codes"></a>Configurar códigos de impuestos

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar códigos de impuestos. Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.

Esta tarea usa la empresa de demostración USMF.

1. Vaya al **panel de navegación > Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos**.
2. Seleccione **Nuevo**.
3. En el campo de **código de impuestos**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. Seleccione un **período de liquidación** abriendo la lista desplegable para especificar qué autoridad fiscal y en qué intervalos tienen que notificarse y pagarse estos impuestos.
6. Seleccione un **grupo de registro** para especificar las cuentas principales para registrar los impuestos en contabilidad general.
7. Expanda la ficha desplegable **Cálculo**. Tiene varios campos que controlan cómo se calcularán los importes de impuestos. Complete estos campos según convenga.  
8. En el **Panel de acciones** en la parte superior de la interfaz, seleccione **Código de impuestos**.
9. Seleccione **Valores**.
10. Escriba el valor para este código de impuestos en la columna **valor** .
    - En la ficha desplegable **Cálculo**, en el campo Origen, si está seleccionado el importe por unidad, el valor se multiplicará por la cantidad de la transacción para calcular el importe de impuestos.  Si el código de impuesto no es un impuesto basado en la unidad, el valor es un porcentaje que se aplica en el origen de este código de impuesto para calcular el importe de impuestos.     
11. Seleccione **Guardar**.
12. Cierre la página.
13. Seleccione **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]