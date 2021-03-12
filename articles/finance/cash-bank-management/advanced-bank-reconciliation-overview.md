---
title: Visión general de conciliación bancaria avanzada
description: Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09128f33d4208bc5c987683bb881aa1129b0dc8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985445"
---
# <a name="advanced-bank-reconciliation-overview"></a>Visión general de conciliación bancaria avanzada

[!include [banner](../includes/banner.md)]

Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias.

La característica avanzada de conciliación bancaria le permite importar extractos bancarios. El extracto bancario importado se podrá conciliar automáticamente desde dentro de las transacciones bancarias. Estos son los pasos del flujo de conciliación bancaria avanzada.

1.  Configure una importación de extracto bancario.
    -   Importe extractos bancarios a través del marco de entidad de datos.
    -   Se integran tres formatos de extracto bancario típicos: ISO20022, BAI2 y MT940.
    -   Las funciones se pueden ampliar a cualquier formato.

2.  Configure una secuencia numérica para usarla para conciliación bancaria avanzada y defina las reglas de coincidencia de conciliación bancaria.
    -   Una regla de coincidencia de conciliación es un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de transacción bancaria de Microsoft Dynamics 365 Finance durante el proceso de conciliación. En función de la práctica empresarial, puede configurar más de una regla coincidente para automatizar y optimizar el proceso de conciliación.

3.  Concilie extractos bancarios con las transacciones bancarias de Finance.
    -   Realice la creación y la conciliación automáticas de diarios de conciliación.
    -   Vea extractos bancarios y las transacciones bancarias de Finance en paralelo.
    -   Registre automáticamente transacciones bancarias de Finance si aparecen en un extracto bancario pero no aparecen en la aplicación Finance.
    -   Genere un extracto de conciliación.





