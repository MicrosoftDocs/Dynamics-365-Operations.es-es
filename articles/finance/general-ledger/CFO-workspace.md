---
title: Agregar dimensiones financieras al espacio de trabajo del CFO
description: Este artículo explica cómo agregar dimensiones financieras al área de trabajo de CFO, para que se puedan usar en el libro mayor y los informes presupuestarios.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ea453eed826dec2e97371ec559e91b94933bdce6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853391"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Agregar dimensiones financieras al espacio de trabajo del CFO

[!include [banner](../includes/banner.md)]

Este artículo explica cómo agregar dimensiones financieras al área de trabajo de CFO (Director financiero), para que se puedan usar en el libro mayor y los informes presupuestarios. El área de trabajo del director financiero tiene una pestaña **Visión general** y una pestaña **Datos financieros**. Los informes de estas dos pestañas se basan en dos medidas: LedgerActivityMeasure y BudgetActivityMeasure. Existe una relación entre las dos medidas y la entidad DimensionCombinationEntity. Por lo tanto, puede seleccionar las dimensiones.

1. En Finance, en la página **Almacén de la entidad** , actualice las medidas **MedidasActividadContable** y **MedidasActividadPresupuestaria** .
2. En Microsoft Visual Studio, abra el Explorador de la aplicación, y busque **ContabilidadCFO**.
3. En **Recursos**, abra **ContabilidadCFOEspacioDeTrabajoPBIX**.
4. Cuando el recurso se abre en Microsoft Power BI Desktop, seleccione **Obtener datos**, seleccione **Base de datos de SQL Server** y después seleccione **Conectar**.
5. Especifique el nombre del servidor y seleccione **AxDW** como la base de datos. Haga clic en **DirectQuery** y, a continuación, en  **Aceptar**.
6. Busque y seleccione **MedidasDeActividadContable\_DimensiónCombinación**, y después seleccione **carga**.

    > [!TIP]
    > En el lista **Campos** , cambie el nombre de la tabla **Dimensiones financieras**, de modo que sea fácil identificar.

7. Seleccione **Gestionar las relaciones**, y después seleccione **Nuevo**.
8. En el primer campo, seleccione **Actividades de la contabilidad general**, y después seleccione **DimensiónContable**.
9. En el segundo campo, seleccione **LedgerActivityMeasure\_DimensionCombination** (o **Dimensiones financieras** si se retituló la tabla). Seleccione el encabezado **DimensiónCombinaciónRECID** .
10. En el campo **Cardinalidad** , seleccione **Muchos a uno**.
11. Cambie el valor de **Dirección del filtro cruzado** a **Individual**.
12. Seleccione **Hacer esta relación activa** y **Asumir la integridad referencial**, seleccione **Aceptar** y, a continuación seleccione **Cerrar**.

    [![Crear una relación.](./media/Create-relationship.png)](./media/Create-relationship.png)

13. En el lista **Campos** , debe ver la tabla y las dimensiones financieras disponibles. Arrastre las dimensiones financieras que desea a los filtros de informes nivel.
14. Guarde los cambios.
15. En el Árbol de objetos de aplicaciones (AOT), haga clic con el botón derecho en el proyecto y, a continuación seleccione **Sincronizar**.
16. Compile el proyecto, y después abra la aplicación para ver los resultados.

    [![Espacio de trabajo completado.](./media/workspace.png)](./media/workspace.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
