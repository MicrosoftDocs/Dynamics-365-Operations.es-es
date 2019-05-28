---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4543cf7eaa0b1ef8e32d3fdafa2c354cd3739256
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554234"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de notificación de impuestos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos. Se usan en diseños de informe específicos de país y en el pago de impuestos por informe de código para imprimir los importes de impuestos para un período de liquidación resumido por código de notificación. Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables- Configuración del informe de la página Código de impuestos. 

Esta grabación usa la empresa de demostración DEMF.



1. Vaya a Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos.
2. Haga clic en Nuevo.
3. Seleccione el diseño del informe al que pertenece el código de notificación.
    * Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos. Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal que usa un diseño de informe.  
4. Especifique un número que haga referencia a un campo del informe de impuestos.
5. En el campo de texto del informe, escriba una descripción para mostrar en los informes.
6. En el campo Descripción breve, escriba una descripción para fines internos.
7. Haga clic en Guardar.

