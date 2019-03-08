---
title: 'MX-00008: Id. de registro de proveedores'
description: Este procedimiento le muestra cómo crear el proveedor para México de modo que se admita una declaración DIOT y otros informes legales.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c24a532be1a14f31fe0fa9369ae6dbad73d6757b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "370497"
---
# <a name="mx-00008-vendor-registration-ids"></a>MX-00008: Id. de registro de proveedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo crear el proveedor para México de modo que se admita una declaración DIOT y otros informes legales. Este procedimiento usa los datos de la empresa de demostración MXMF.

1. Vaya a Proveedores > Proveedores > Todos los proveedores.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba el nombre del proveedor.
4. En el campo Grupo, seleccione un grupo para el proveedor.
5. Expanda o contraiga la sección Factura y entrega.
6. En el campo Tipo de empresa, seleccione una opción.
7. En el campo Número de RFC, escriba el número de RFC de 12 o 13 caracteres del proveedor.
    * El número de Registro Federal del Contribuyentes (RFC) es el número de identificación fiscal asignado por las autoridades fiscales a una persona o una corporación. Los identificadores de registro de impuestos se validan según el formato especificado por las autoridades fiscales de México.  
8. En el campo Número de CURP, escriba el número de CURP de 18 caracteres del proveedor.
    * Si el tipo de empresa para este proveedor es una persona jurídica, este campo es obligatorio.  
9. En el campo Inscripción estatal, escriba un valor.
10. En el campo Tipo de proveedor, seleccione una opción.
11. En el campo Tipo de operación, seleccione una opción.
    * La opción que seleccione se convierte en la selección predeterminada al crear transacciones de compras del proveedor.  
    * Para los proveedores extranjeros, especifique el id. de registro de impuestos, el código de país o región y la nacionalidad.  
12. Haga clic en Guardar.

