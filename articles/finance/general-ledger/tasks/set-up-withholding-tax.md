---
title: Configurar retención de impuestos
description: Este tema explica cómo configurar la retención de impuestos.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfa1b9e43a5745eb5b5c442998597319f196f23f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447514"
---
# <a name="set-up-withholding-tax"></a>Configurar retención de impuestos

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar la retención de impuestos. La *retención de impuestos* es un impuesto sobre los proveedores que no crea transacciones de impuestos. La retención de impuestos calculada sobre los pagos de proveedor es un pasivo. Por lo tanto, tan solo las cuentas de balance de situación o las cuentas de pasivos son cuentas validas para el registro de la retención de impuestos. Esta guía de la tarea demuestra cómo configurar la retención de impuestos.

1. Vaya al **panel de navegación > Módulos > Impuestos > Impuestos indirectos > Retención de impuestos > Códigos de retención de impuestos**.
2. Seleccione **Nuevo**.
3. En el campo **Código de retención de impuestos**, escriba un valor.
4. En el campo **Nombre de la retención de impuestos**, especifique el nombre del código de retención de impuestos.
5. En el campo **Cuenta principal**, seleccione la cuenta principal para registrar el pasivo de la retención de impuestos.
6. Seleccione **Guardar**.
7. Seleccione **Valores** y marque el registro deseado en la lisat.
8. En el campo **Valor**, especifique un porcentaje usado para el cálculo de la retención de impuestos.
9. Seleccione **Guardar**.
10. Cierre la página.
11. Seleccione **Guardar**.
12. Cierre la página.
13. Vaya a **Panel de navegación > Módulos > Impuestos > Impuestos indirectos > Retención de impuestos > Grupos de retenciones de impuestos**.
14. Seleccione **Nuevo**.
15. En el campo **Grupo de retenciones de impuestos**, especifique el identificador del grupo de retenciones de impuestos.
16. En el campo **Descripción**, especifique el nombre del grupo de retenciones de impuestos.
17. En el campo **Código de retención de impuestos**, seleccione el código de retención de impuestos.
18. Seleccione **Guardar**.
19. Cierre la página.

