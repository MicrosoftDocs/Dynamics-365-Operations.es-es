---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo enumerado en un informe de impuestos.
author: twheeloc
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e040bac6ef9e950e8d7f97e3c136636acf1fe43
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813540"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de notificación de impuestos

[!include [banner](../../includes/banner.md)]

Los códigos de notificación de impuestos hacen referencia a un número de campo enumerado en un informe de impuestos. Se utilizan en diseños de informes específicos de cada país. También se utilizan en el informe Pago de impuestos por código. Ese informe muestra los importes de los impuestos para un período de liquidación, resumido para cada código de informe. Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables de configuración de informes, a las que puede acceder desde la página **Código de impuestos**. 

Esta grabación usa la empresa de demostración DEMF.

1. En el **Panel de navegación**, vaya a **Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos**.
2. Haga clic en **Nuevo**.
3. Seleccione el diseño del informe al que pertenece el código de notificación. Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos. Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal, que utiliza un diseño de informe.  
4. En el campo **Código de notificación**, introduzca un número.
5. En el campo de **Texto del informe**, escriba una descripción para mostrar en los informes.
6. En el campo **Descripción breve**, escriba una descripción para fines internos.
7. Haga clic en **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]