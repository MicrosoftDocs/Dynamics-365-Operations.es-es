---
title: Crear una nueva jerarquía de productos
description: En este tema se describe cómo crear una nueva jerarquía de productos en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 724ec2e5af7837d574298d662911cd9c6ee9e9f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415460"
---
# <a name="create-a-new-product-hierarchy"></a>Crear una nueva jerarquía de productos


[!include [banner](includes/banner.md)]

En este tema se describe cómo crear una nueva jerarquía de productos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Dynamics 365 Commerce admite varios canales comerciales. Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas). Cada canal de tienda puede tener sus propios métodos de pago, grupos de precios, registros de puntos de venta (PDV), cuentas de ingresos y gastos, o personal. Debe configurar todos estos elementos antes de crear una canal de tienda. 

Se usa una jerarquía de productos de Commerce para definir la jerarquía de productos global para su organización. Puede usar este tipo de jerarquía de productos de Commerce para comercialización, precios y promociones, informes y planificación de selecciones. Solo se puede asignar una jerarquía de productos de Commerce por organización.

## <a name="create-and-configure-a-product-hierarchy"></a>Crear y configurar una jerarquía de productos

Para crear y configurar una jerarquía de productos de Commerce, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Jerarquía de productos de Commerce**.
1. Si aún no existe una jerarquía, en el **Panel de acciones**, seleccione **Nuevo** para crear la raíz de la jerarquía.
1. En **General**:
    1. Escriba un nombre en el cuadro **Nombre**.
    1. En el cuadro **Descripción**, escriba una descripción.
    1. En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.
    1. Establezca **Activo** en **Sí**.

## <a name="add-hierarchy-nodes"></a>Agregar nodos de jerarquía

Para agregar nodos de jerarquía, siga estos pasos.

1. En el Panel de acción, seleccione **Editar jerarquía de categoría**.
1. Seleccione el nodo principal al que desea agregar un nuevo nodo y, a continuación, seleccione **Nuevo nodo de categoría**.
1. En la sección **General**, especifique valores de **Nombre**, **Descripción**, **Nombre descriptivo** y **Palabras clave**.
1. En **General**:
    1. Escriba un nombre en el cuadro **Nombre**.
    1. En el cuadro **Descripción**, escriba una descripción.
    1. En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.
    1. En el cuadro **Palabras clave**, introduzca palabras clave pertinentes.
    1. En el cuadro **Orden de visualización**, escriba un número para el orden de visualización (opcional).
1. En el panel de acciones, seleccione **Guardar**.
1. Repita los pasos anteriores para agregar nodos adicionales.

La siguiente imagen muestra la creación de un nuevo nodo de jerarquía de productos.

![Crear jerarquía de productos](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Otras opciones de configuración

También se pueden asignar grupos de atributos de categoría a cada grupo según sea necesario.  

## <a name="additional-resources"></a>Recursos adicionales

[jerarquías comerciales](retail-hierarchies.md)

[Administrar las categorías de productos y los productos](category-management-product-creation.md)

[Cambiar el orden de clasificación de entidades de comercialización](custom-order-categories-nav-retail-prod-hierarchy.md)
