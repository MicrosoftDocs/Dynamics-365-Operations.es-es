---
title: "Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos"
description: "Es necesario añadir un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 672697254c1bf06e193a51c5c7c83c467a220ce8
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importación avanzada de conciliación bancaria MT940 - Actualización de la entidad de datos compuestos

[!include[banner](../includes/banner.md)]


Es necesario añadir un número de secuencia a la entidad de importación del extracto bancario para admitir el formato MT940. 

Siga estos pasos para agregar la entidad de importación del extracto bancario para admitir el formato MT940.

1.  Recopilar y sincronizar lo siguiente:
    -   Entidad compuesta\\BankStatementImportEntity
    -   Entidad\\BankStatementBalanceEntity
    -   Entidad\\BankStatementDocumentEntity
    -   Entidad\\BankStatementEntity
    -   Entidad\\BankStatementLineEntity
    -   Tablas\\BankStatementStaging

2.  Gestión de datos\\proyectos de datos.
    1.  Cargar proyecto(s) de importación MT940
        1.  Cambiar XSLT.
            -   Haga clic en **Ver mapa**.
            -   Haga clic en **Ver mapa** en el documento del extracto bancario.
            -   Haga clic en **Transformaciones**
            -   Eliminar el archivo de BankReconiliation-to-Composite.xslt.
            -   Añadir la nueva versión de BankReconiliation-to-Composite.xsl.

        2.  Exponer el **Número de secuencia** en el diseño de **Datos de origen**.
            1.  Formato de datos de origen = Elemento XML.
            2.  Nombre de la entidad = Extractos bancarios.
            3.  Cargar archivo de datos = nueva versión SampleBankCompositeEntity.xml.
            4.  Haga clic en **Sí** para sobrescribir el archivo existente.
            5.  Haga clic en **Sí** para generar una nueva asignación.
            6.  Comprobar que se ha asignado S**equenceNumber**.
                -   Haga clic en **Ver mapa** en la entidad del extracto.
                -   Comprobar que **SequenceNumber** se asigna desde Origen a Montaje.

3.  Importar el extracto nuevo.





