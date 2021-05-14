---
title: Inferior a clases de camión (LTL)
description: Este tema explica qué son las clases de carga inferior a un camión (LTL) y describe cómo configurarlas en Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941819"
---
# <a name="less-than-truckload-ltl-classes"></a>Inferior a clases de camión (LTL)

[!include [banner](../includes/banner.md)]

Una clase de carga inferior a un camión (LTL) es una clase de envío de carga que se utiliza para clasificar los artículos que se pueden enviar. Generalmente, cada tipo de producto o mercancía tiene un código de Clasificación Nacional de Transporte de Carga Motorizada (NMFC) que corresponde a un número de clase de carga específico para envíos LTL. Las clases de carga LTL representan categorías de artículos, mientras que los códigos NMFC están relacionados con productos específicos en cada una de las 18 clases de carga.

Esta característica le permite usar su sistema para realizar las tareas siguientes:

- Defina las clases de flete LTL que se utilizan en su empresa.
- Asigne cada clase LTL a un código NMFC en la página **Códigos NMFC**. Para más información, vea [Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)](nmfc-codes.md).
- Asigne un código NMFC (y por lo tanto su código LTL asociado) a cada producto en la página **Productos**.
- Evalúe con precisión la clase LTL de cada producto al que se le asigna un código NMFC.
- Determine los requisitos de embalaje para cada clase de LTL comprobando los estándares internacionales de LTL. De esta manera, se asegura de que sus productos estén bien protegidos y se envíen de forma segura.
- Obtenga estimaciones de envío precisas, basadas en la clase de carga LTL para cada producto.

En este tema se describe cómo crear clases LTL en Microsoft Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>Crear una clase LTL

Para crear una clase LTL, siga estos pasos.

1. Siga uno de estos pasos:

    - Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Clases LTL**.
    - Vaya a **Administración de transporte \> Configuración \> Estándares de transporte \> Clases LTL**.

2. En el panel de acciones, seleccione **Nueva** para crear una clase LTL. Entonces establezca los campos siguientes:

    - **Clase LTL**: introduzca el identificador (ID) de clase LTL interno de su empresa para el tipo de producto. La mayoría de las empresas utilizan el estándar internacional. En ese caso, el valor de este campo coincidirá con el valor del campo **Clase**. Sin embargo, si su empresa utiliza su propio estándar, introduzca un código que se ajuste a ese estándar.
    - **Nombre**: introduzca un nombre descriptivo que le ayudará a usted y a otros usuarios a seleccionar la clase LTL correcta para cada código NMFC.
    - **Clase**: introduzca el id. de clase LTL estándar internacional para el tipo de producto. El código que introduzca aquí debe cumplir con el estándar oficial.

## <a name="example-set-up-ltl-classes"></a>Ejemplo: configurar clases LTL

El siguiente ejemplo muestra cómo configurar dos clases LTL diferentes que puede utilizar con diferentes tipos de productos.

1. Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Clases LTL**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva línea, establezca los siguientes valores:

    - **Clase LTL:** *92.5*
    - **Nombre:** *Ordenadores, monitores, refrigeradores*
    - **Clase:** *92.5*

1. En el panel Acciones, seleccione **Guardar**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva línea, establezca los siguientes valores:

    - **Clase LTL:** *125*
    - **Nombre:** *Pequeños electrodomésticos*
    - **Clase:** *125*

1. En el panel Acciones, seleccione **Guardar**.

## <a name="additional-resources"></a>Recursos adicionales

- [Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)](nmfc-codes.md)
- [Crear un conocimiento de embarque](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
