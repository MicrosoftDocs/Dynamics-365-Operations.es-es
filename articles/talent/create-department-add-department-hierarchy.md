---
title: "Crear un departamento y asociarlo a la jerarquía de departamento"
description: "Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización. Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos. Puede usar departamentos para informar sobre las áreas funcionales. Los departamentos pueden tener responsabilidad de pérdidas y ganancias."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adf3dbf8b7ffa906c872a6b66d9cb43eb8e02805
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a>Crear un departamento y asociarlo a la jerarquía de departamento

[!include[banner](includes/banner.md)]


Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización. Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos. Puede usar departamentos para informar sobre las áreas funcionales. Los departamentos pueden tener responsabilidad de pérdidas y ganancias.

Un departamento puede incluir un grupo de centros de coste. Se pueden asignar puestos a los departamentos. Para crear un departamento, haga clic en **Recursos humanos** &gt; **Departamentos** &gt; **Departamento**. En la tabla siguiente se describen los campos disponibles.

| Campo               | Descripción                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                | Escriba un nombre para el departamento.                                                                                                                                                                                  |
| Número del departamento   | e puede generar automáticamente un valor predeterminado si se asigna un código de secuencia numérica a la referencia **Número de organización** en la página **Numerar secuencias**.                                                 |
| Nombre de búsqueda         | Escribir un nombre o un acrónimo que se pueda utilizar en una búsqueda de departamento.                                                                                                                                            |
| Observaciones                | Especificar información adicional aquí.                                                                                                                                                                            |
| En jerarquía        | Una casilla de verificación activada indica que el departamento se incluye en la jerarquía de departamento. Para obtener información acerca de cómo agregar un departamento a la jerarquía de departamentos, consulte información más adelante en este artículo. |
| Número DUNS         | DUNS representa el sistema de numeración universal de datos. Esto es un número de nueve dígitos que emite Dun & Bradstreet.                                                                                                     |
| Encargado             | Especifique la persona que administra el departamento                                                                                                                                                                    |
| Direcciones           | Agregue la información de dirección del departamento. Por ejemplo, agregue la dirección postal del edificio en el que se encuentra el departamento.                                                                          |
| Información de contacto | Agregue la información de contacto del departamento. Por ejemplo, agregue un número de teléfono para el servicio de recepción del departamento.                                                                                           |

Para agregar un departamento a la jerarquía de departamentos, siga estos pasos.

1.  Haga clic en **Recursos humanos** &gt; **Departamentos** &gt; **Jerarquía de departamentos**.
2.  Haga clic en **Editar** y luego seleccione la organización en la que debe estar el departamento.
3.  Haga clic en **Insertar** y seleccione **Departamento** en la lista.
4.  En la lista de departamentos que aparece, seleccione el departamento que desea agregar a la jerarquía.
5.  Guarde los cambios. Recibirá un mensaje en el que se ha creado un borrador de la versión de la jerarquía.
6.  Cuando esté preparado, haga clic en **Publicar** en el diseñador de jerarquías. Puede especificar una fecha de vigencia que indica cuándo la jerarquía se debe publicar. Por ejemplo, para agregar un nuevo departamento al inicio del año natural siguiente, defina la fecha de vigencia a 1 de enero del nuevo año natural. Los cambios en la jerarquía surtirán efecto en esa fecha.





