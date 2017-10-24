--- 
title: "Importación de la configuración de transferencia de crédito ISO20022"
description: "Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de proveedor."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 71c0175178203006e297466c4a37cd3e6319b6ea
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importación de la configuración de transferencia de crédito ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de proveedor. El formato alemán de transferencia de crédito ISO 20022 se usa como ejemplo. Este procedimiento se puede utilizar para otro formato de informes electrónicos disponibles. 

Esta tarea se creó con la empresa de datos de demostración DEMF pero puede usar cualquier empresa de datos de demostración para completar esta tarea.

Esta es la primera de cinco tareas que conjuntamente muestran el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.

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


