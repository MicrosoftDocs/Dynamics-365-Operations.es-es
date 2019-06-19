---
title: EUR-00015 Registro de ID de IVA del proveedor
description: Este procedimiento muestra cómo agregar identificadores de registro de IVA y un impuesto salvo el número en una cuenta de proveedor.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9788a35e768a4a289742e9cd864b3ca185a0407
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566880"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a>EUR-00015 Registro de ID de IVA del proveedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo agregar identificadores de registro de IVA y un impuesto salvo el número en una cuenta de proveedor. Este proceso es similar para las entidades jurídicas y clientes. 

Para completar este procedimiento, debe configurar identificadores de IVA. Este procedimiento se aplica a todos los países o regiones europeos. Este procedimiento se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal en Alemania. Este procedimiento se ha creado para un administrador de gestión de datos, un administrador de proveedores o un administrador de clientes. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Proveedores > Proveedores > Todos los proveedores.
2. En la lista, busque y seleccione el proveedor DE-01001
3. Haga clic en Id. de registro.
4. Haga clic en Agregar.
5. Seleccione el Id. de IVA.
6. En el campo Número de registro, escriba un valor.
    * Especifique un identificador de IVA en Alemania para el proveedor seleccionado. El identificador debe coincidir el formato especificado del tipo de registro.  
7. Haga clic en la pestaña General.
8. En el campo Vigente, especifique una fecha.
9. Haga clic en Guardar.
10. Haga clic en Nuevo.
11. En el campo Nombre o descripción, escriba un valor.
    * Por ejemplo, escriba ITA.  
12. En el campo País o región, especifique o seleccione un valor.
    * Por ejemplo, seleccione ITA.  
13. Seleccione Sí en el campo Principal para país.
14. Haga clic en Guardar.
15. Haga clic en la ficha Visión general.
16. Haga clic en Agregar.
17. En el campo Tipo de registro, especifique o seleccione un valor.
    * Por ejemplo, seleccione Id. de IVA.  
18. En el campo Número de registro, escriba un valor.
    * Por ejemplo, especifique un identificador de IVA en Italia.  El identificador debe tener el mismo formato que el tipo de registro.  
19. Haga clic en Guardar.
20. Cierre la página.
21. En la lista, busque y seleccione el registro deseado.
    * Por ejemplo, seleccione DE-01001.  
22. En la lista, haga clic en el vínculo de la fila seleccionada.
23. Expanda la sección Factura y entrega.
24. Haga clic en Editar.
25. En el campo NIF, especifique o seleccione un valor.
26. Haga clic en Guardar.

