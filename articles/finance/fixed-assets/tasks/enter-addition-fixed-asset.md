---
title: Especificar una adición para un activo fijo
description: Este procedimiento muestra cómo agregar una adición a un activo fijo existente.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d23f60963466249b332b759ee72ebc8387aee4b
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713060"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
