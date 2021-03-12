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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45ae7d6bb04dbf06b9b05d9f5610895fced650b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994449"
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

