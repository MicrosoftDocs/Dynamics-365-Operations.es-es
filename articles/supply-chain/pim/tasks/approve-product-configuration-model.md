---
title: Aprobar un modelo de configuración de producto
description: La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920516"
---
# <a name="approve-a-product-configuration-model"></a>Aprobar un modelo de configuración de producto

[!include [banner](../../includes/banner.md)]

La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible. Este procedimiento usa el modelo Altavoz superior de la empresa de demostración de datos USMF. Tenga en cuenta que ya se ha aprobado este modelo, pero el procedimiento le guía por todo el proceso.

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. En la lista, busque y seleccione el registro deseado.
    * Seleccione el modelo Altavoz superior para este procedimiento.  
1. Seleccione **Versiones**.
1. Seleccione **Nuevo**.
1. En el campo **Número de producto**, especifique o seleccione un valor.
    * La referencia a un producto representa una versión de un modelo de configuración de productos. Solo los productos maestros con la tecnología de configuración basada en restricciones aparecerán en esta lista.  
1. En el campo **Fecha inicial**, escriba una fecha.
    * Seleccione si la versión del modelo de producto estará disponible.  
1. En el campo **Fecha final**, especifique una fecha.
    * Seleccione una fecha final para cuándo expirará esta versión del modelo de producto o seleccione Nunca.  
1. Seleccione **Aprobar** para abrir el cuadro de diálogo desplegable.
1. En el campo **Aprobado por**, especifique o seleccione un valor.
    * Seleccione la persona responsable de aprobar los modelos de productos para usarlos en operaciones.  
1. Seleccione **Aceptar**.
1. En el campo **Método de cálculo de precios**, seleccione una opción.
    * Active la versión del modelo de producto. Solo es posible tener un producto activo para un modelo de producto cada vez.  
1. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]