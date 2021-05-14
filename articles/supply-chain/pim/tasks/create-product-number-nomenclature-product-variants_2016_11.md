---
title: Crear una nomenclatura de números de producto para las variantes de producto configuradas
description: Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921020"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Crear una nomenclatura de números de producto para las variantes de producto configuradas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable. Este procedimiento también demuestra la manera de crear una nomenclatura de la configuración para un componente del modelo de configuración de productos. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. La nueva nomenclatura del número de producto se asigna al producto maestro D0004. Esta tarea normalmente la realiza un diseñador de productos.

## <a name="create-a-product-number-nomenclature"></a>Crear una nomenclatura de número de producto

1. Vaya a **Gestión de información de productos \> Configuración \> Nomenclatura de productos**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Descripción**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Número de producto maestro**.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Configuración**.
1. Cierre la página.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Asignar la nomenclatura del número de producto a un producto maestro

1. Vaya a **Gestión de información de productos \> Productos \> Productos maestros**.
1. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo **Número de producto** con un valor de 'D'.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Seleccione **Editar**.
1. Seleccione *Sí* en el campo **Usar nomenclatura**.
1. En el campo **Nomenclatura del número de variante del producto**, especifique o seleccione un valor.
1. Cierre la página.
1. Cierre la página.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Crear una nomenclatura para un componente de modelo de configuración de productos

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. En la lista, busque y seleccione el registro deseado.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Seleccione **Editar**.
1. Seleccione *Sí* en el campo **Usar nomenclatura de configuración**.
1. Seleccione **Agregar**.
1. Seleccione **Valor de atributo**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Atributo**, especifique o seleccione un valor.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Valor de atributo**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Atributo**, especifique o seleccione un valor.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Valor de atributo**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Atributo**, especifique o seleccione un valor.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Valor de atributo**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Atributo**, especifique o seleccione un valor.
1. Seleccione **Agregar**.
1. Seleccione **Constante de texto**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Texto**, escriba un valor.
1. Seleccione **Agregar**.
1. Seleccione **Valor de secuencia numérica**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Secuencia numérica**, especifique o seleccione un valor.
1. Cierre la página.
1. Cierre la página.
1. Cierre la página.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]