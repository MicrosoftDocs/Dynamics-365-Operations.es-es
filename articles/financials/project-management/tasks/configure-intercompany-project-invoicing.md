---
title: Configurar la facturación de proyectos de empresas vinculadas
description: Este tema muestra cómo configurar un proyecto facturando entre dos empresas de su organización.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867328"
---
# <a name="configure-intercompany-project-invoicing"></a>Configurar la facturación de proyectos de empresas vinculadas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tema muestra cómo configurar un proyecto facturando entre dos empresas de su organización. Esta tarea usa el conjunto de datos USSI.

1. En el panel de exploración, vaya a **Módulos > Proveedores > Proveedores > Todos los proveedores**.
2. En la lista **Todos los proveedores** busque y seleccione el registro deseado.
3. En el panel de acciones, seleccione **Gneral**.
4. Seleccione **Empresas vinculadas**.
5. Establezca el campo **Activo** en **Sí** para habilitar el comercio entre empresas.
6. En el campo **Empresa del cliente**, especifique o seleccione un valor.
7. En el campo **Mi cuenta**, especifique o seleccione un valor.
8. Seleccione **Guardar**.
9. Cierre las páginas para regresar a la página principal.
10. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Administración de proyectos y parámetros de contabilidad**.
11. Seleccione la pestaña **Empresas vinculadas**.
12. Desplace el control deslizante a la opción **Sí** para activar la programación de recursos y las hojas de horas de empresas vinculadas.
13. En la lista, marque la fila seleccionada.
14. Seleccione **Nuevo**.
15. En el campo **Entidad jurídica a la que se presta el trabajador**, especifique o seleccione un valor.
16. Seleccione la casilla **Acumular ingresos**.
17. En el campo **Hoja de horas predeterminada**, especifique o seleccione un valor.
18. En el campo **Categoría de gastos predeterminada**, especifique o seleccione un valor.
19. Seleccione **Guardar**.
20. Cierre la página.
21. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Registrar > Configuración de registro**.
22. En el campo de **Tipos de cuenta contable**, seleccione una opción.
23. Seleccione **Nuevo**.
24. En el campo **Cuenta principal** de la nueva fila, especifique los valores deseados.
25. Seleccione **Guardar**.
26. Cierre la página.
27. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Transferir precio**.
28. Seleccione **Nuevo**.
29. En el campo **Fecha de vigencia**, especifique una fecha.
30. En el campo **Entidad jurídica a la que se presta el trabajador**, especifique o seleccione un valor.
31. En el campo de **Modelo de precio de transferencia**, seleccione una opción.
32. Escriba un número en el campo **Precio**.
33. Seleccione **Guardar**.

