---
title: Aprobar proveedores para categorías de compras específicas
description: Este tema explica cómo aprobar proveedores para las categorías de compras específicas en Dynamics 365 for Finance and Operations.
author: mkirknel
manager: AnnBe
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1583a2eedc535f81b84e3094fee1574451f6f209
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867158"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Aprobar proveedores para categorías de compras específicas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tema explica cómo aprobar proveedores para las categorías de compras específicas en Dynamics 365 for Finance and Operations. Cuando se crea una solicitud de compra, puede haber un requisito para seleccionar un proveedor aprobado o preferido, en función de cómo se configuran las directivas de compras. Este procedimiento le muestra cómo especificar que un proveedor está aprobado o preferido para una categoría de compras específica. Esta tarea la lleva a cabo normalmente un profesional de compras. Puede utilizar este procedimiento en la empresa de datos de demostración USMF.

1. En el panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Proveedores > Todos los proveedores**.
2. Seleccione el proveedor que desea establecer como proveedor aprobado o preferido para una categoría.
3. En el panel de acciones, seleccione **Gneral**.
4. Seleccione **Categorías**.
5. Seleccione **Agregar categoría**.
6. En el campo **Categoría**, seleccione **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.
7. En el campo **Estado de categoría del proveedor**, seleccione **Preferido**. Es posible especificar más de un proveedor preferido para una categoría.  
8. Seleccione **Guardar**.
9. En el Panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Categorías de compras**.
10. En el árbol, seleccione **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.
11. Expanda la sección **Proveedores**. Compruebe si el proveedor que ha seleccionado aparece como proveedor preferido para la categoría de accesorios de la oficina y escritorio. Si está ejecutando este procedimiento como guía de tareas, es posible que tenga que hacer seleccionar en el botón **Desbloquear** para poder desplazarse hacia abajo en la lista de proveedores.  También es posible agregar proveedores preferidos y aprobados en esta página.  
12. En el árbol, expanda **OFFICE AND DESK ACCESSORIES** y seleccione **Tijeras**.
13. Seleccione **No** en el campo **Heredar proveedores de la categoría principal:**.
14. Seleccione **Sí** en el campo **Heredar proveedores de la categoría principal:**.

