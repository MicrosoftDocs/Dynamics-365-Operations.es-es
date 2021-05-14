---
title: Agregar campos de datos en configuraciones de impuestos
description: Este tema explica cómo personalizar las configuraciones de impuestos agregando campos de datos.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 197a2d1605dd39188841aba02a71d228c7138c54
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921198"
---
# <a name="add-data-fields-in-tax-configurations"></a>Agregar campos de datos en configuraciones de impuestos

[!include [banner](../includes/banner.md)]

Este tema explica cómo personalizar las configuraciones de impuestos mediante el uso de [campos de datos que se agregan en la integración de impuestos](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Personalizar el modelo de datos de impuestos

1. En Microsoft Dynamics 365 Finance, vaya a **Informes electrónicos** \> **Configuraciones de impuestos**.
2. En el árbol de configuración, seleccione **Modelo de datos fiscales: Europa**. Luego, en el panel de acciones, seleccione **Crear configuración**.
3. En el cuadro de diálogo desplegable, seleccione la opción **Modelo de documento imponible derivado de Nombre: Modelo de datos fiscales - Europa, Microsoft**, introduzca un nombre para el nuevo modelo de datos de impuestos y luego seleccione **Crear configuración**.
4. Seleccione el modelo de datos de impuestos que acaba de crear y luego, en el panel de acciones, seleccione **Diseñador**.
5. Expanda el árbol del modelo de datos, seleccione **Líneas** y luego seleccione **Nueva**.
6. En el cuadro de diálogo **Crear nodo**, introduzca un nombre, especifique el tipo de artículo y luego seleccione **Agregar**.
7. Agregue las columnas requeridas.
8. En el panel de acciones, seleccione **Guardar** y luego seleccione **Completo**.
9. Cierre la página y vea la versión completa de su modelo de datos fiscales.

## <a name="customize-the-tax-configuration"></a>Personalizar la configuración de impuestos

1. En Finance, vaya a **Informes electrónicos** \> **Configuraciones de impuestos**.
2. En el árbol de configuración, seleccione **Configuración de impuestos: Europa**. Luego, en el panel de acciones, seleccione **Crear configuración**.
3. En el cuadro de diálogo desplegable, seleccione la opción **Configuración de servicio de impuestos derivada de Nombre: Configuración de impuestos, Europa, Microsoft**, introduzca un nombre para la nueva configuración de impuestos y luego seleccione **Crear configuración**.
4. Seleccione la configuración de impuestos que acaba de crear y luego, en el panel de acciones, seleccione **Diseñador**.
5. En la sección **Propiedades**, en el campo **Modelo de datos**, seleccione el modelo de datos de impuestos personalizado que creó anteriormente.
6. En el campo **Versión del modelo de datos**, seleccione la versión completa del modelo de datos de impuestos.
7. Seleccione **Agregar** y agregue las medidas tributarias requeridas.
8. En el panel de acciones, seleccione **Guardar** y luego seleccione **Completo**.
9. Cierre la página y vea la versión completa de su configuración de impuestos.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implementar funciones de impuestos en la configuración de impuestos personalizada

1. En el servicio de configuración regulatoria (RCS), vaya a **Características de globalización** \> **Impuesto**.
2. Seleccione **Agregar**, introduzca información sobre la nueva función y luego seleccione **Crear característica**.
3. En la pestaña **Versiones**, seleccione la característica y luego elija **Editar**.
4. En la pestaña **General**, en el campo **Versión de configuración**, seleccione la configuración y la versión de impuestos personalizadas.
5. En el cuadro de diálogo **Administrar columnas**, seleccione el encabezado y las columnas de línea que desea incluir en su medida de impuestos personalizada, y luego seleccione el botón de flecha hacia la derecha para agregarlos a la lista **Columnas seleccionadas**.
