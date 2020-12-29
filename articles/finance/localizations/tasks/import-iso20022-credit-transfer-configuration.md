---
title: Importación de la configuración de transferencia de crédito ISO20022
description: Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de proveedor.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 01f44c49b6623cbcc2f08cfd6e4978c9a1676b83
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447650"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importación de la configuración de transferencia de crédito ISO20022

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de proveedor. El formato alemán de transferencia de crédito ISO 20022 se usa como ejemplo. Este procedimiento se puede utilizar para otro formato de informes electrónicos disponibles. 

Esta tarea se creó con la empresa de datos de demostración DEMF pero puede usar cualquier empresa de datos de demostración para completar esta tarea.

Esta es la primera de cinco tareas que conjuntamente muestran el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. En la lista de proveedores de configuración disponibles, seleccione Microsoft
3. Haga clic en Definir como activo.
4. Haga clic en Repositorios.
5. Haga clic en Abrir.
6. Haga clic en Mostrar filtros.
7. Aplique los siguientes filtros: especifique un valor de filtro de "Transferencia de crédito ISO20022 (DE)" en el campo "Nombre de configuración" mediante el operador de filtro "empieza por".
    * De forma alternativa, puede buscar la configuración en la lista, seleccionarla y trasladarla a la tarea de importación.  
8. Haga clic en Importar.
    * Si el botón Importar no está disponible, es que la configuración ya se ha importado.  
9. Haga clic en Sí.

