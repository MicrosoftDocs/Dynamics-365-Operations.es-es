---
title: Actualización de la entidad compuesta del diario del banco
description: Este artículo lista los pasos necesarios para poder agregar el campo adicional de BankTransactionType al compuesto BankJournalEntity.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1855f9680ba6bcf8eb46608882a128b4a21f0dac
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715300"
---
# <a name="update-the-bank-journal-composite-entity"></a>Actualización de la entidad compuesta del diario del banco

[!include [banner](../includes/banner.md)]

Este artículo lista los pasos necesarios para poder agregar el campo adicional de BankTransactionType al compuesto BankJournalEntity.

Siga estos pasos para agregar el campo adicional de BankTransactionType al compuesto BankJournalEntity.

1.  Recopilar y sincronizar las entidades compuestas del siguiente diario del banco, las partes y las tablas de montaje:
    -   Entidad compuesta\\BankJournalEntity
    -   Entidad\\BankJournalHeaderEntity
    -   Entidad\\BankJournalLineEntity
    -   Tabla\\BankJournalHeaderStaging
    -   Tabla\\BankJournalLineStaging

2.  Gestión de datos\\proyectos de datos
    -   Exponga el tipo de **Transacción bancaria** en el diseño de **Datos de origen**.
        -   Formato de datos de origen = Elemento XML
        -   Nombre de la entidad = Diario del banco
        -   Cargar archivo de datos = nueva versión SampleBankJournalCompositeEntity.xml
        -   Haga clic en **Sí** para sobrescribir el archivo existente.
        -   Haga clic en **Sí** para generar la asignación desde cero.
        -   Compruebe que se asigna el Tipo de transacción bancaria.
            -   Haga clic en **Ver mapa** en la Entidad de la línea.
            -   Compruebe que se asigna el Tipo de transacción bancaria del Origen a Montaje

3.  Importar el extracto nuevo.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
