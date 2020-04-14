---
title: Especificar una adición para un activo fijo
description: Este procedimiento muestra cómo agregar una adición a un activo fijo existente.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc1e13863ae13daaa641f52f7a55e01fc1353dc1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142763"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Especificar una adición para un activo fijo

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo agregar una adición a un activo fijo existente. El propósito de las adiciones de activos fijos es el seguimiento de las adiciones, el mantenimiento o las mejoras de artículo para un activo y es únicamente informativo. Cualquier cambio en el valor o el tiempo de vida del activo fijo debe llevarse a cabo de forma independiente.   

El procedimiento usa el rol de contable y los datos de prueba de la entidad jurídica USMF.

1. En el panel de navegación, vaya a **Módulos > activos fijos > activos fijos > activos fijos**.
2. En la lista, busque y seleccione el activo fijo para el accesorio.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en **Activo fijo.**
5. Haga clic en **Accesorios de activo fijo**.
6. Haga clic en **Nuevo**.
7. En el campo **Nombre**, escriba un valor.
8. En el campo **Fecha de adquisición** , defina la fecha de la compra o el servicio de adición.
9. En el campo **Coste unitario**, escriba el coste del artículo, mantenimiento u otra mejora del activo.
10. En el campo **Cantidad**, especifique un número. El coste total no sufrirá ningún impacto en el valor del activo fijo y solo sirve para realizar el seguimiento y para fines informativos. Si el coste se capitalizará, debe registrarse una transacción de ajuste de revalorización por separado.  
11. Haga clic en la pestaña **General**.

    * Establezca **Aumenta el tiempo de vida** en **Sí** si la adición incrementa el tiempo de vida del activo.  
    * Este campo es únicamente informativo. Para aumentar el tiempo de vida, modifíquelo en los modelos de valor y/o en los libros de amortización del activo.  

