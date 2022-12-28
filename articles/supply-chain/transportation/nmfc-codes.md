---
title: Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)
description: Este artículo describe cómo trabajar con códigos de clasificación nacional de transporte de mercancías (NMFC) en Microsoft Dynamics 365 Supply Chain Management
author: Weijiesa
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: c173057b8e1357790e780469c5806afb857be62a
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838345"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)

[!include [banner](../includes/banner.md)]

Los códigos de Clasificación Nacional de Carga Motorizada (NMFC) le ayudan a clasificar los artículos que pueden enviarse. El código NMFC es una designación que se utiliza para agrupar productos. Permite a las empresas de transporte evaluar los productos para su envío clasificando los artículos en función de consideraciones como lo adecuado del camión, los problemas de carga, los problemas de manipulación y la perecibilidad. Los productos se agrupan en una de las 18 clases de transporte mediante un rango de números del 50 al 500. La clase en la que se agrupa una mercancía se basa en una evaluación de cuatro características de transporte: densidad, capacidad de almacenamiento, manipulación y responsabilidad. Juntas, estas características establecen la transportabilidad de la mercancía.

Un código NMFC está asociado con cada artículo de envío de carga inferior a un camión (LTL). Por ejemplo, a un portátil se le puede asignar un NMFC que se clasifica en 2.5, mientras que a los cables eléctricos se le puede asignar un NMFC que se clasifica en 65.

Esta función puede ayudar a los trabajadores a utilizar los códigos NMFC para clasificar los artículos de envío LTL. A continuación, encontrará algunos ejemplos:

- Si su empresa incluye una descripción de la carga en el conocimiento de embarque (BOL), el transportista tendrá una idea de cuál es la carga. El flete es una clasificación importante porque muchas empresas de transporte basan todo su modelo de negocio en los tipos de flete que envían.
- Esta clasificación puede ser esencial para su empresa porque se utiliza para determinar el coste de una carga determinada.
- Su empresa puede identificar la rentabilidad de una empresa de logística y transporte LTL.

En este artículo se describe cómo trabajar con códigos NMFC en Microsoft Dynamics 365 Supply Chain Management.

## <a name="prerequisites"></a>Requisitos previos

Antes de poder crear códigos NMFC, debe configurar todas las clases de carga LTL que deben asignarse a ellos. Las clases de carga LTL representan categorías de artículos, mientras que los códigos NMFC están relacionados con productos específicos en cada una de las 18 clases de carga. Para obtener más información sobre cómo trabajar con clases LTL, consulte [Clases de carga inferior al camión (LTL)](ltl-class.md).

## <a name="create-an-nmfc-code"></a>Crear un código NMFC

Para crear un código NMFC, siga estos pasos.

1. Siga uno de estos pasos:

    - Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Códigos NMFC**.
    - Vaya a **Administración de transporte \> Configuración \> Estándares de transporte \> Códigos NMFC**.

1. Seleccione **Nuevo** para crear un código NMFC. Entonces establezca los campos siguientes:

    - **Código NMFC**: especifique el código NMFC de tipo de mercancía.
    - **Nombre**: escriba un nombre para el código NMFC.
    - **Clase LTL**: seleccione la clase LTL que está asociada con el código NMFC.
    - **Unidad de manipulación BOL**: defina el tipo de manipulación predeterminado para el envío.

## <a name="example-set-up-nmfc-codes"></a>Ejemplo: configurar códigos NMFC

El siguiente ejemplo muestra cómo configurar dos códigos NMFC diferentes que puede utilizar con diferentes tipos de productos.

1. Vaya a **Warehouse management \> Configuración \> Inventario \> Códigos NMFC** o **Administración de transportes \> Configuración \> Estándares de transporte \> Códigos NMFC**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva línea, establezca los siguientes valores:

    - **Código NMFC:** *92.5*
    - **Nombre:** *Ordenadores*
    - **Clase LTL:** *92.5*
    - **Unidad de manipulación BOL:** *Unidad*

1. En el panel Acciones, seleccione **Guardar**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva línea, establezca los siguientes valores:

    - **Código NMFC:** *125*
    - **Nombre:** *Teléfonos*
    - **Clase LTL:** *125*
    - **Unidad de manipulación BOL:** *Unidad*

1. En el panel Acciones, seleccione **Guardar**.

## <a name="additional-resources"></a>Recursos adicionales

- [Inferior a clases de camión (LTL)](ltl-class.md)
- [Crear un conocimiento de embarque](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
