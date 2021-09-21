---
title: No encuentra el cuadro de diálogo desplegable "Flujo de trabajo" para los diarios de inventario
description: No encuentra el cuadro de diálogo desplegable "Flujo de trabajo" en la página del diario, o las operaciones de flujo de trabajo relacionadas no están disponibles.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477506"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>No encuentra el cuadro de diálogo desplegable "Flujo de trabajo" para los diarios de inventario

## <a name="symptoms"></a>Síntomas

No encuentra el cuadro de diálogo desplegable **Flujo de trabajo** en la página del diario, o las operaciones de flujo de trabajo relacionadas no están disponibles.

Este problema puede producirse por tres motivos, como se describe en las siguientes secciones.

## <a name="resolution-1"></a>Resolución 1

Si el problema se aplica a todos los usuarios, es posible que se deba a que el flujo de trabajo de aprobación no se ha asignado al nombre del diario. Para arreglar el problema, siga estos pasos.

1. Vaya a **Gestión del inventario &gt; Configurar &gt; Nombres de diarios &gt; Inventario**.
1. En el panel de lista, seleccione un nombre de diario para abrir su configuración.
1. En la ficha desplegable **General**, establezca la opción **Flujo de trabajo de aprobación** en *Sí*. Seleccione **Sí** si se le solicita que confirme el cambio.
1. En el campo **Flujo de trabajo**, seleccione el flujo de trabajo que desee usar para el nombre de diario seleccionado.

## <a name="resolution-2"></a>Resolución 2

Si su flujo de trabajo utiliza código personalizado, pueden surgir problemas después de actualizar el sistema. Por ejemplo, en el flujo de trabajo del diario, el botón **Enviar** puede aparecer atenuado, por lo que no puede seleccionarlo para aprobar un envío.

Si el botón **Enviar** está atenuado, es posible que su flujo de trabajo se haya personalizado, lo que significa que el método del flujo de trabajo, `canSubmitToWorkflow()` en `FormDataUtil`, se ha extendido. Para solucionar este problema, cambie la forma en que amplía el método del `canSubmitToWorkflow()` para usar la estructura en el siguiente ejemplo.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>Resolución 3

Si el problema solo se aplica a algunos usuarios específicos, es posible que esos usuarios no tengan los privilegios de seguridad necesarios para ejecutar operaciones de flujo de trabajo en diarios de inventario. Compruebe que cada usuario afectado tenga el privilegio de seguridad *Mantener el flujo de trabajo del diario de inventario*. De forma predeterminada, este privilegio se asigna a un deber que tiene el mismo nombre, y ese deber se aplica a los roles *Trabajador de almacén* y *Responsable de almacén*.
