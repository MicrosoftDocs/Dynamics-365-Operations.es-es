---
title: Tipos de atributos de mantenimiento
description: En este tema se explica cómo crear tipos de atributos en Administración de activos.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 283cff931ce665ae09152c8f3d3c976b7c8b66ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808529"
---
# <a name="maintenance-attribute-types"></a>Tipos de atributos de mantenimiento

[!include [banner](../../includes/banner.md)]

 

En este tema se explica cómo crear tipos de atributos en Administración de activos. Los atributos se utilizan para describir las propiedades de varios elementos. Puede configurar los atributos de los siguientes elementos:

- [Tipos de ubicaciones funcionales](../setup-for-functional-locations/functional-location-types.md)
- [Crear ubicaciones funcionales](../functional-locations/create-functional-locations.md)
- [Tipos de activos](../setup-for-objects/object-types.md)
- Activos

Los atributos que puede configurar varían, en función del elemento. Por ejemplo, para una ubicación funcional, puede configurar los atributos para la configuración y el tamaño físico de la ubicación. Para un tipo de activo o un activo, puede configurar los atributos por volumen del motor, el consumo energético y carga de capacidad máxima en diferentes condiciones.

## <a name="create-attribute-types"></a>Crear tipos de atributo

Puede crear sus propios tipos de atributos. Además, puede transferir dimensiones de producto a la página **Tipos de atributo**.

1. Seleccione **Administración de activos** \> **Configuración** \> **Tipos de atributo**.
2. La primera vez que configura tipos de atributos, seleccione **Crear dimensiones del producto** para transferir automáticamente las dimensiones de producto estándar.
3. Seleccione **Nuevo** para crear un nuevo tipo de atributo.
4. En el campo **Tipo de atributo**, especifique un nombre para el tipo de atributo.
5. En el campo **Descripción**, escriba una descripción.
6. En el campo **Unidad**, seleccione la unidad relevante del atributo, según convenga.
7. En el campo **Tipo de datos**, seleccione un tipo de datos para la unidad.
8. Si seleccionó **Cadena** como tipo de datos, siga estos pasos para crear valores para el tipo de atributo:

    1. Seleccione el tipo de atributo y después **Valores**.
    2. En el campo **Valores de atributo**, seleccione **Nuevo**.
    3. En el campo **Tipo de atributo**, seleccione un tipo de atributo (dimensión).
    4. En el campo **Valor**, especifique un valor relaciondo.
    5. En el campo **Descripción**, escriba una descripción.
    6. Guarde el registro.
    7. Vuelva a la página **Tipos de atributo**.

9. Guarde el registro.

    El campo **Tipos de ubicación funcionales** muestra el número de ubicaciones técnicas que estén utilizando el tipo de atributo. El campo **Tipos del activo** muestra el número de tipos de activos que lo estén utilizando.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]