---
title: Aprobar un modelo de configuración de producto
description: La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 317aa9ad5bc5953b7148846622b893e5b525c637
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150203"
---
# <a name="approve-a-product-configuration-model"></a>Aprobar un modelo de configuración de producto

[!include [banner](../../includes/banner.md)]

La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible. Este procedimiento usa el modelo Altavoz superior de la empresa de demostración de datos USMF. Tenga en cuenta que ya se ha aprobado este modelo, pero el procedimiento le guía por todo el proceso.

1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Modelos de configuración del producto.
3. En la lista, busque y seleccione el registro deseado.
    * Seleccione el modelo Altavoz superior para este procedimiento.  
4. Haga clic en Versiones.
5. Haga clic en Nuevo.
6. En el campo Número de producto, especifique o seleccione un valor.
    * La referencia a un producto representa una versión de un modelo de configuración de productos. Solo los productos maestros con la tecnología de configuración basada en restricciones aparecerán en esta lista.  
7. En el campo Fecha inicial, escriba una fecha.
    * Seleccione si la versión del modelo de producto estará disponible.  
8. Especifique una fecha en el campo Fecha final.
    * Seleccione una fecha final para cuándo expirará esta versión del modelo de producto o seleccione Nunca.  
9. Haga clic en Aprobar para abrir el cuadro de diálogo desplegable.
10. En el campo Aprobado por, especifique o seleccione un valor.
    * Seleccione la persona responsable de aprobar los modelos de productos para usarlos en operaciones.  
11. Haga clic en Aceptar
12. En el campo Método de cálculo de precios, seleccione una opción.
    * Active la versión del modelo de producto. Solo es posible tener un producto activo para un modelo de producto cada vez.  
13. Cierre la página.

