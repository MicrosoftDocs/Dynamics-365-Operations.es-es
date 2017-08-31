--- 
title: Configurar precios basados en atributos para productos configurables
description: "Este procedimiento muestra cómo configurar unos precios en función del atributo."
author: BibiSp
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 473d01ecddfd58aa72a972ee901673534c9d7c9c
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Configurar precios basados en atributos para productos configurables

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar unos precios en función del atributo. Como requisito previo, debe tener un modelo de configuración de productos con uno o más componentes y atributos. Este ejemplo usa el modelo de producto Altavoz de gama alta en los datos de demostración de la empresa USMF. Normalmente, un responsable de productos utiliza este procedimiento.


## <a name="create-a-new-price-model"></a>Cree un nuevo modelo de precio
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Modelos de configuración del producto.
3. En la lista, seleccione la línea Altavoz de gama alta, pero no haga clic en el vínculo del nombre.
4. En el panel de acciones, haga clic en Modelo.
5. Haga clic en Modelos de precio.
6. Haga clic en Nuevo.
7. En el campo Nombre de modelo de precio, escriba un valor.
    * Use un nombre que permita identificar fácilmente el modelo.  
8. En el campo Descripción, escriba un valor.
9. Haga clic en Guardar.

## <a name="add-price-elements"></a>Agregue elementos de precio
1. Haga clic en Editar.
    * Cada componente de un modelo de producto puede tener un elemento de precio base y cualquier número de reglas de la expresión del precio. También puede agregar precios en divisas distintas.  
2. En el campo Expresión de precio base, escriba un valor.
    * Por ejemplo, escriba 100.   Una expresión del precio base puede ser un valor numérico, o puede estar compuesto por un cálculo aritmético que contenga uno o varios atributos.  
3. Haga clic en Agregar.
4. En el campo Nombre, escriba "Palo de rosa".
    * Las ayudas del nombre de la expresión del precio permiten identificar lo que representa el elemento de precio. En este ejemplo, estamos creando un elemento de precio para la opción de acabado de la caja del altavoz en madera de palo de rosa.  
5. Haga clic en Editar condición.
    * Una condición de precio permite garantizar que un elemento de la expresión del precio se incluya en el precio de venta únicamente si está presente una combinación específica de atributos.  
6. En el campo ConstraintBody, especifique "CabinetFinish=="Rosewood"".
7. Haga clic en Aceptar
8. En el campo Expresión, escriba un valor.
    * Por ejemplo, escriba 50.  
9. Cierre la página.
10. Cierre la página.


