---
title: "Visión general de conciliación bancaria avanzada"
description: "Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: deba55d5e1e376f3f4063f372bfe853fcaf20498
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Visión general de conciliación bancaria avanzada

[!include[banner](../includes/banner.md)]


Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias.

La característica avanzada de conciliación bancaria le permite importar extractos bancarios. El extracto bancario importado se podrá conciliar automáticamente desde dentro de las transacciones bancarias. Estos son los pasos del flujo de conciliación bancaria avanzada.

1.  Configure una importación de extracto bancario.
    -   Importe extractos bancarios a través del marco de entidad de datos.
    -   Se integran tres formatos de extracto bancario típicos: ISO20022, BAI2 y MT940.
    -   Las funciones se pueden ampliar a cualquier formato.

2.  Configure una secuencia numérica para usarla para conciliación bancaria avanzada y defina las reglas de coincidencia de conciliación bancaria.
    -   Una regla de coincidencia de conciliación es un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de transacción bancaria de Microsoft Dynamics 365 for Operations durante el proceso de conciliación. En función de la práctica empresarial, puede configurar más de una regla coincidente para automatizar y optimizar el proceso de conciliación.

3.  Concilie extractos bancarios con las transacciones bancarias de Microsoft Dynamics 365 for Operations.
    -   Realice la creación y la conciliación automáticas de diarios de conciliación.
    -   Vea extractos bancarios y las transacciones bancarias de Microsoft Dynamics 365 for Operations en paralelo.
    -   Registre automáticamente transacciones bancarias de Microsoft Dynamics 365 for Operations si aparecen en un extracto bancario pero no aparecen en Microsoft Dynamics 365 for Operations.
    -   Genere un extracto de conciliación.





