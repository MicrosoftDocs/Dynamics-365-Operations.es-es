---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c18f4fb0db31a959647bb10d2b99d940646676e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976802"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de notificación de impuestos

[!include [banner](../../includes/banner.md)]

Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos. Se usan en diseños de informe específicos de país y en el pago de impuestos por informe de código para imprimir los importes de impuestos para un período de liquidación resumido por código de notificación. Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables- Configuración del informe de la página Código de impuestos. 

Esta grabación usa la empresa de demostración DEMF.

1. En el **Panel de navegación**, vaya a **Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos**.
2. Haga clic en **Nuevo**.
3. Seleccione el diseño del informe al que pertenece el código de notificación. Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos. Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal que usa un diseño de informe.  
4. En el campo **Código de notificación**, introduzca un número.
5. En el campo de **Texto del informe**, escriba una descripción para mostrar en los informes.
6. En el campo **Descripción breve**, escriba una descripción para fines internos.
7. Haga clic en **Guardar**.

