---
title: Configurar precios basados en atributos para productos configurables
description: En este tema se explica cómo configurar unos precios en función del atributo.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7382cdfa11e89896bba9518f36eb6caab56b98f6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213064"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Configurar precios basados en atributos para productos configurables

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo configurar unos precios en función del atributo. Como requisito previo, debe tener un modelo de configuración de productos con uno o más componentes y atributos. Este ejemplo usa el modelo de producto Altavoz de gama alta en los datos de demostración de la empresa USMF. Normalmente, un responsable de productos utiliza este procedimiento.


## <a name="create-a-new-price-model"></a>Cree un nuevo modelo de precio
1. Seleccione **Definición de modelo de variante del producto** en la página de inicio.
2. Seleccione **Modelos de configuración del producto** en la sección **vínculos**.
3. En la lista, seleccione la línea **Altavoz de gama alta**, pero no seleccione el vínculo del nombre.
4. En el panel de acciones, haga clic en **Modelo**.
5. Seleccione **Modelos de precio**.
6. Seleccione **Nuevo**.
7. En el campo **Nombre de modelo de precio**, escriba un valor. Use un nombre que permita identificar fácilmente el modelo.  
8. En el campo **Descripción**, escriba un valor.
9. Seleccione **Guardar**.

## <a name="add-price-elements"></a>Agregue elementos de precio
1. Seleccione **Editar**. Cada componente de un modelo de producto puede tener un elemento de precio base y cualquier número de reglas de la expresión del precio. También puede agregar precios en divisas distintas.  
2. En el campo **Expresión de precio base**, escriba un valor. Por ejemplo, escriba 100. Una expresión del precio base puede ser un valor numérico, o puede estar compuesto por un cálculo aritmético que contenga uno o varios atributos.  
3. Seleccione **Agregar**.
4. En el campo **Nombre**, escriba `Rosewood`. Las ayudas del nombre de la expresión del precio permiten identificar lo que representa el elemento de precio. En este ejemplo, estamos creando un elemento de precio para la opción de acabado de la caja del altavoz en madera de palo de rosa.  
5. Seleccione **Editar condición**. Una condición de precio permite garantizar que un elemento de la expresión del precio se incluya en el precio de venta únicamente si está presente una combinación específica de atributos.  
6. En el campo **ConstraintBody**, introduzca `CabinetFinish=="Rosewood"`.
7. Seleccione **Aceptar**.
8. En el campo **Expresión**, escriba un valor. Por ejemplo, escriba `50`. 
9. Cierre la página.

