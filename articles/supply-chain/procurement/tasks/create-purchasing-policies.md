--- 
title: Crear directivas de compra
description: "Este procedimiento le muestra cómo crear directivas de compra para alinearlas con sus procesos empresariales para compras."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b3a66443394f5bfbe51b6685513281025d68fd
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-purchasing-policies"></a>Crear directivas de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo crear directivas de compra para alinearlas con sus procesos empresariales para compras. Para crear directivas de compra, es necesario configurar los parámetros de directiva de compra. Es posible crear, modificar y retirar una directiva de compras, pero no puede eliminar una directiva de compras. Este procedimiento lo realizará normalmente un director de compras. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="set-up-policy-parameters"></a>Configuración de los parámetros de directivas
1. Vaya a Directivas de compra.
2. Haga clic en parámetros.
    * Las reglas de prioridad de directivas se aplican a diferentes niveles de su organización. Las unidades organizativas que se muestran dependen de su jerarquía organizativa y de a qué niveles de la jerarquía se ha asignado el propósito del Control interno de compras. Por ejemplo, su organización puede tener entidades jurídicas, centros de costes, regiones y departamentos, pero es posible que solo algunos de estos tengan un propósito de jerarquía del Control interno de compras. De forma predeterminada, la organización de tipo Empresa está disponible.  
3. Haga clic en la pestaña Parámetros de tipo de regla de directiva.
4. En el árbol, seleccione "Directiva de compra\Regla de control de la solicitud de compra".
    * El orden de prioridad para la resolución de directivas se define en el nivel de directiva. Sin embargo, para algunos tipos de directivas, puede anular el orden de prioridad para tipos de reglas de directivas individuales. Por ejemplo, puede definir la orden de prioridad para que las directivas de compra sean: centro de coste, departamento, empresa. Para la regla de directivas de catálogo, puede que desee que el orden de prioridad sea: departamento, centro de coste, empresa. Puede cambiar el orden de prioridad para la regla de directivas del catálogo. Cuando un trabajador cree una solicitud, el catálogo que se muestra está determinado por las directivas asociadas con el departamento del trabajador, su centro de coste y su empresa, por este orden.  
    * Si se muestra más de un nivel de organización, puede utilizar las flechas arriba/abajo para establecer la orden de prioridad para la Regla de control de la solicitud de compra.  
5. Cierre la página.

## <a name="create-a-new-policy"></a>Crear una nueva directiva
1. Haga clic en Nuevo.
2. En el campo Nombre, escriba un valor.
3. En el campo Descripción, escriba un valor.
    * Una única directiva de compra solo se puede aplicar a una jerarquía organizativa. Por ejemplo, podría tener una jerarquía llamada “Geográfica” y otra llamada “Departamento” y tener una directiva de compras diferente para cada una.  
    * Seleccione una organización a la que se debería aplicar la directiva.  
4. Haga clic en la flecha para agregar la organización.
    * Puede repetir este proceso para agregar más organizaciones.  

## <a name="add-a-policy-rule"></a>Agregar una regla de directivas
1. En la lista Tipo de regla de directivas, seleccione Regla de propósito de pedido.
    * Creará una regla que establezca el propósito de pedido predeterminado en el tipo Consumo pero que permita que se seleccione en su lugar el Tipo de reabastecimiento.  
2. Haga clic en Crear regla de directivas.
3. Seleccione Sí en el campo Permitir anulación manual.
4. Haga clic en Cerrar.
    * Ahora puede configurar otras reglas de directivas para la directiva de compras.   Observe que un tipo de la regla de directiva no puede tener reglas de superposición que estén activas al mismo tiempo dentro de una sola directiva de compras.  
5. Cierre la página.
6. Cierre la página.


