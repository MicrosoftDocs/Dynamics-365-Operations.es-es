---
title: Importación de la configuración de domiciliación bancaria ISO20022
description: Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de cliente.
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
ms.openlocfilehash: e5d4256b155d3e06d63e425fab63b4025ef2577f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140027"
---
# <a name="import-iso20022-direct-debit-configuration"></a>Importación de la configuración de domiciliación bancaria ISO20022

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de cliente. Este procedimiento usa el formato de débito directo ISO 20022 como ejemplo. 



Este procedimiento se creó con la empresa de datos de demostración DEMF pero puede usar cualquier empresa de datos de demostración para este fin.



Este es el primero de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. En la lista de proveedores de configuración disponibles, seleccione Microsoft
3. Haga clic en Definir como activo.
4. Haga clic en Repositorios.
5. Haga clic en Abrir.
6. Haga clic en Mostrar filtros.
7. Aplique los siguientes filtros: especifique un valor de filtro de "Domiciliación bancaria ISO20022 (DE)" en el campo "Nombre de configuración" mediante el operador de filtro "empieza por".
    * Opcionalmente, puede encontrar la configuración en la lista, seleccionarla y omitir este paso.  
8. Haga clic en Importar.
    * Si el botón Importar no está disponible, es que la configuración ya se ha importado.  
9. Haga clic en Sí.

