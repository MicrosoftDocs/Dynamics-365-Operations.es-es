---
title: Configurar precios basados en atributos para productos configurables
description: En este artículo se explica cómo configurar unos precios en función del atributo.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec16a0a8078cddd433c99592aa4a7474cf923aec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849398"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Configurar precios basados en atributos para productos configurables

[!include [banner](../../includes/banner.md)]

En este artículo se explica cómo configurar unos precios en función del atributo. Como requisito previo, debe tener un modelo de configuración de productos con uno o más componentes y atributos. Este ejemplo usa el modelo de producto Altavoz de gama alta en los datos de demostración de la empresa USMF. Normalmente, un responsable de productos utiliza este procedimiento.


## <a name="create-a-new-price-model"></a>Cree un nuevo modelo de precio

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. En la lista, seleccione la línea **Altavoz de gama alta**, pero no seleccione el vínculo del nombre.
1. En el panel de acciones, haga clic en **Modelo**.
1. Seleccione **Modelos de precio**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre de modelo de precio**, escriba un valor. Use un nombre que permita identificar fácilmente el modelo.  
1. En el campo **Descripción**, escriba un valor.
1. Seleccione **Guardar**.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]