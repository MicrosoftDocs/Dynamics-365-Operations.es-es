---
title: "Visión general de conciliación bancaria avanzada"
description: "Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Visión general de conciliación bancaria avanzada

Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias.

La característica avanzada de conciliación bancaria le permite importar extractos bancarios. El extracto bancario importado se podrá conciliar automáticamente desde dentro de las transacciones bancarias. Estos son los pasos del flujo de conciliación bancaria avanzada.

1.  Configure una importación de extracto bancario.
    -   Importe extractos bancarios a través del marco de entidad de datos.
    -   Se integran tres formatos de extracto bancario típicos: ISO20022, BAI2 y MT940.
    -   Las funciones se pueden ampliar a cualquier formato.

2.  Configure una secuencia numérica para usarla para conciliación bancaria avanzada y defina las reglas de coincidencia de conciliación bancaria.
    -   Regla coincidente de conciliación es un conjunto de criterios que se usa para filtrar las líneas de extracto bancario y Microsoft Dynamics 365 para las líneas de las transacciones bancarias de las operaciones durante el proceso de conciliación. En función de la práctica empresarial, puede configurar más de una regla coincidente para automatizar y optimizar el proceso de conciliación.

3.  Concilie los extractos bancarios con las Dynamics 365 para las transacciones bancarias de las operaciones.
    -   Realice la creación y la conciliación automáticas de diarios de conciliación.
    -   Ver los extractos bancarios e Dynamics 365 para las transacciones bancarias de las operaciones de forma simultánea.
    -   Registrar Dynamics 365 para las transacciones bancarias de las operaciones si lo aparece en un extracto bancario pero no aparece en Dynamics 365 para las operaciones.
    -   Genere un extracto de conciliación.




