---
title: Crear reglas avanzadas para diarios
description: Este procedimiento le guía por la creación de reglas avanzadas para los diarios.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5cc41f19928fd415fb54073fd733f97a3e7aa01
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717429"
---
# <a name="create-advanced-rules-for-journals"></a>Crear reglas avanzadas para diarios

[!include [banner](../../includes/banner.md)]

Este procedimiento le guía por la creación de reglas avanzadas para los diarios. Esto incluye la configuración de restricciones de registro de usuario y de control de diarios. Este procedimiento usa la empresa de datos de demostración USMF.


## <a name="set-up-journal-control"></a>Configurar el control del diario
1. En el **Panel de exploración**, vaya a **Módulos > Contabilidad general > Configuración del diario > Nombres del diario**.
2. En la lista, busque y seleccione el registro deseado.
3. En el **panel de acciones**, haga clic en **Control del diario**.
4. En la ficha desplegable, **¿Qué tipos de cuentas se pueden registrar?**, haga clic en **Agregar**.
5. En el campo **Cuentas de la empresa**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En la ficha desplegable **¿Qué valores del segmento son válidos para este diario?**, haga clic en **Agregar**.
9. En el campo **Estructura contable**, haga clic en el botón desplegable para abrir la búsqueda.
10. En la lista, busque y seleccione el registro deseado.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
12. En el campo **Segmento**, haga clic en el botón desplegable para abrir la búsqueda.
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. En el campo **Valor inicial**, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, busque y seleccione el registro deseado.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. En el campo **Valor final**, haga clic en el botón desplegable para abrir la búsqueda.
18. En la lista, busque y seleccione el registro deseado.
19. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="set-up-posting-restrictions"></a>Configuración de restricciones de registro
1. Cierre la página.
2. Haga clic en **Restricciones de registro**.
3. En **¿Cómo desea configurar las restricciones de registro?**, seleccione "Por grupo de usuarios".
4. En el árbol, active "el grupo al que desea permitir el registro para este nombre de diario”.
5. Haga clic en **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
