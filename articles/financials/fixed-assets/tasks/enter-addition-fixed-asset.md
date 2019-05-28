---
title: Especificar una adición para un activo fijo
description: Este procedimiento muestra cómo agregar una adición a un activo fijo existente.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c9733f07f995dd37669f3c33fd0f082daa34dd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566947"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Especificar una adición para un activo fijo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo agregar una adición a un activo fijo existente. El propósito de las adiciones de activos fijos es el seguimiento de las adiciones, el mantenimiento o las mejoras de artículo para un activo y es únicamente informativo. Cualquier cambio en el valor o el tiempo de vida del activo fijo debe llevarse a cabo de forma independiente.   



El procedimiento usa el rol de contable y los datos de prueba de la entidad jurídica USMF.

1. Vaya a Activos fijos > Activos fijos > Activos fijos.
2. En la lista, busque y seleccione el activo fijo para el accesorio.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en Activo fijo.
5. Haga clic en Accesorios de activo fijo.
6. Haga clic en Nuevo.
7. En el campo Nombre, escriba un valor.
8. Defina la fecha de la compra o servicio del accesorio.
9. Escriba el coste del artículo, mantenimiento u otra mejora del activo.
10. En el campo Cantidad, especifique un número.
    * El coste total no sufrirá ningún impacto en el valor del activo fijo y solo sirve para realizar el seguimiento y para fines informativos. Si el coste se capitalizará, debe registrarse una transacción de ajuste de revalorización por separado.  
11. Haga clic en la pestaña General.
    * Establezca Aumenta el tiempo de vida si la adición incrementa el tiempo de vida del activo.  
    * Este campo es únicamente informativo. Para aumentar el tiempo de vida, modifíquelo en los modelos de valor y/o en los libros de amortización del activo.  

