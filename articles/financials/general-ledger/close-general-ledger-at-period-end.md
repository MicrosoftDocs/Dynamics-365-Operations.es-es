---
title: Cerrar la contabilidad general al final del período
description: En este tema se describen las tareas que se completan normalmente al realizar un cierre de período para la contabilidad general.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eca533ed1621ec3507d8510f75842c0f0165275
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839554"
---
# <a name="close-the-general-ledger-at-period-end"></a>Cerrar la contabilidad general al final del período

[!include [banner](../includes/banner.md)]

En este tema se describen las tareas que se completan normalmente al realizar un cierre de período para la contabilidad general. 

En Contabilidad general, puede completar los procedimientos de cierre de un período o un año. El cierre de procesos prepara al sistema para un período nuevo. Para preparar el sistema para un año nuevo, debe ejecutar el proceso de cierre de ejercicio. Cada organización tiene diferentes procesos y pasos que realiza para el final de un período. A continuación se indican algunos pasos opcionales para finales de períodos:

-   Completar todas las tareas para todos los demás módulos, como Clientes, Proveedores e Inventario.
-   Comprobar que se registran todos los diarios.
-   Ejecutar la revalorización de divisa extranjera para generar beneficios no realizados o importes de pérdidas.
-   Liquidar transacciones para cuenta contable.
-   Procesar cualquier asignación obligatoria.
-   Registrar manualmente ajustes de fin de período.
-   Registrar transacciones en el diario y revisar el informe del **Diario contable**.
-   Realizar una consolidación mediante una empresa de consolidación o informes financieros.
-   Generar resultados financieros de final de período con Informes financieros.
-   Definir períodos contables en **En espera**, de modo que no se produzca ningún otro registro. También puede restringir un período a un grupo de usuarios específico mientras se estén produciendo actividades de final de período, para un mayor control. No es buena idea establecer períodos en **Cerrado de forma permanente** porque no se puede volver a abrir un período que se ha cerrado.

El espacio de trabajo de cierre del período financiero se puede usar para organizar y seguir las tareas necesarias para varios procesos de cierre del ejercicio. 


Para obtener más información, vea los siguientes temas:
- [Espacio de trabajo de cierre del período financiero](financial-period-close-workspace.md) 
- [Cierre de fin de año](Year-end-close.md)  
- [Cierre masivo de período financiero](tasks/mass-financial-period-close.md)




