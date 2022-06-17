---
title: Abrir plantillas de diario financiero en Office
description: Este artículo describe los problemas que pueden surgir al crear diarios financieros personalizados mediante una plantilla de Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896358"
---
# <a name="open-financial-journal-templates-in-office"></a>Abrir plantillas de diario financiero en Office

[!include [banner](../includes/banner.md)]

Este artículo describe los problemas que pueden surgir al crear diarios financieros personalizados mediante una plantilla de Microsoft Excel.

## <a name="symptom"></a>Síntoma

Ha creado una plantilla de Excel personalizada para diarios financieros, pero no aparece en el menú **Abrir líneas en Excel**. Alternativamente, aparece en el menú, se abre una plantilla diferente cuando la selecciona.

## <a name="resolution"></a>Resolución

La funcionalidad predeterminada Abrir en Excel utiliza el origen de datos raíz (tabla) de la página actual para determinar qué plantillas de Office o entidades de datos aparecen como opciones en el menú **Abrir en Excel**. Este comportamiento no es una experiencia ideal para los diarios financieros, porque estos utilizan las mismas tablas (LedgerJournalTable y LedgerJournalTrans) como orígenes de datos raíz de muchos otros tipos de diarios.

Para los diarios financieros, la funcionalidad Abrir líneas en Excel tiene como objetivo mostrar plantillas diseñadas para el diario en el que está trabajando actualmente, como el diario general o un diario de pagos. Por ejemplo, una plantilla destinada a utilizarse con un diario de pagos de proveedor se diseñará para hacer cumplir su cuenta principal como cuenta de proveedor.

Si desea promocionar una plantilla para que esté disponible en los menús **Abrir líneas en Excel** y **Abrir en Excel**, una experiencia fácil para el desarrollador es implementar la interfaz **LedgerIJournalExcelTemplate** y extender la clase **DocuTemplateRegistrationBase**. Muchos ejemplos de este enfoque se implementan en el sistema. Un ejemplo que se puede utilizar como referencia es la interfaz **LedgerDailyJournalExcelTemplate** que se creó para el diario general (o diario).

Cuando se implementa la interfaz **LedgerIJournalExcelTemplate** para la plantilla, el menú **Abrir líneas en Excel** filtrará las plantillas por el tipo de diario y mostrará solo las plantillas que están disponibles para el mismo. La interfaz también proporciona un método de validación que garantiza que no se pueda abrir una plantilla para un diario si no cumple con los requisitos del tipo de cuenta. Por ejemplo, puede especificar que el tipo de cuenta debe ser del tipo **Proveedor** o **Libro mayor**.

Para obtener más información sobre esta funcionalidad, consulte [Agregar plantillas al menú Abrir líneas en Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
