---
title: Ajustes de Retail
description: Este procedimiento le guiará por la creación de un ajuste de precios de Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7443f69473c0aad478d47f80f284b1156bad9c24
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962994"
---
# <a name="retail-price-adjustments"></a>Ajustes de Retail

[!include [banner](../includes/banner.md)]

Este procedimiento le guiará por la creación de un ajuste de precios de Commerce. Un ajuste de precios puede definir el precio de venta de un artículo directamente, o modificar su precio de venta de la base o precio de venta de contrato comercial. Este procedimiento usa la empresa de datos de demostración USRT.

1. Haga clic en Administración de precios y descuentos.
2. Haga clic en la ficha Ajustes de precio.
3. Haga clic en Nuevo.
    * Desde aquí puede crear todas las reglas de precios y descuentos más usadas, incluidos descuentos, ajustes de precios, diarios de acuerdos comerciales y reglas de precios de categoría.  
4. Haga clic en Ajuste de precios.
5. En el campo Nombre, escriba un valor.
6. Expanda la sección Líneas.
7. Haga clic en Agregar.
    * Para este ejemplo, especifique "81126" en el campo Producto. A continuación, escriba "10,0" en el campo Porcentaje de descuento.  
    * Un ajuste de precios de tipo de porcentaje de descuento reducirá un precio de ventas base o precio de ventas de contrato comercial.  
8. Haga clic en Agregar.
    * Para este ejemplo, especifique "81125" en el campo Producto. A continuación, seleccione el "Importe de descuento por pronto pago" en el campo Método de descuento.    Por último, escriba "5.0" en el campo Importe de descuento por pronto pago.  
    * Un tipo de descuento de importe de descuento por pronto pago es un importe restado de un precio base o un precio de contrato comercial.  
9. Haga clic en Grupos de precios.
    * Seleccione "RP-Houston" en el campo Grupo de precios.  
    * Esto asociará el ajuste de precios a la tienda Houston.  
10. Haga clic en Guardar.
11. Cierre la página.
12. En el campo Estado, seleccione "Habilitado".
13. Haga clic en Guardar.
14. Cierre la página.
15. Actualice la página.

