---
title: Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras
description: El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566820"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras

[!include [banner](../includes/banner.md)]

El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.

## <a name="registration-modes"></a>Modos de registro

En la ficha desplegable **Registro de escáner**, puede seleccionar el modo de registro, que controla la acción cuando se escanea un número de tarjeta kanban o se escribe manualmente el número en el campo de número de tarjeta kanban.

| Establecer modo de registro | Descripción                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Iniciar                 | Registra un trabajo de transferencia kanban como en curso.                                                 |
| Completada              | Registra un trabajo de transferencia kanban como completado.                                                   |
| Vacía                 | Registra la unidad de gestión de material a la que hace referencia una tarjeta kanban como vacía.              |
| Seleccionar                | Registra un número de tarjeta kanban y selecciona automáticamente el trabajo al que se hace referencia en la lista de trabajos kanban. |

 
## <a name="registration-mode-select"></a>Seleccionar el modo de registro

Cuando se usa un lector de códigos de barras para seleccionar un trabajo, el modo de visualización del tablero kanban cambia. De esta manera, se aplicarán las condiciones siguientes:

-   Solo se muestra el trabajo kanban escaneado.
-   Los detalles del trabajo seleccionado se muestran en la ficha desplegable **Detalles**.
-   La ficha desplegable **Mensajes** muestra mensajes solo para el trabajo seleccionado.
-   Puede cambiar el estado del trabajo mediante las funciones disponibles en el Panel de acciones. El tablero kanban de transferencia sigue mostrando un solo trabajo durante este tiempo.
-   Puede actualizar la información de la lista de trabajos manualmente haciendo clic en **Actualizar** (Mayús+F5) en el Panel de acciones. Tras actualizar la información, los resultados completos del filtro de trabajo se muestran de nuevo.

## <a name="job-status-and-possible-actions"></a>Estado del trabajo y acciones posibles
El estado del trabajo seleccionado y el estado de cualquier trabajo fijado para los kanban de evento determinan si puede seguir procesando el trabajo. La tabla siguiente muestra información acerca de estos estados y tareas:
-   Los estados disponibles para los trabajos o para las unidades de gestión de material a los que hacen referencia los trabajos.
-   Todas las tareas que puede realizar para el trabajo.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de trabajo</th>
<th>El estado del trabajo o el estado de la unidad de gestión de material</th>
<th>Actualizar lista de selección</th>
<th>Iniciar</th>
<th>Actualizar registro</th>
<th>Completada</th>
<th>Vacía</th>
<th>Crear kanbans de evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Transferir</td>
<td><ul>
<li>Sin planificar</li>
<li>No hay trabajos fijados o estos están completados</li>
</ul></td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>No</td>
<td>Sí</td>
</tr>
<tr class="even">
<td>Transferir</td>
<td><ul>
<li>Sin planificar</li>
<li>El trabajo fijado no está completado</li>
</ul></td>
<td>Sí</td>
<td>No</td>
<td>Sí</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Transferir</td>
<td>En curso</td>
<td>Sí</td>
<td>No</td>
<td>Sí</td>
<td>Sí</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="even">
<td>Transferir</td>
<td>Completada</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>Sí</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Transferir o procesar</td>
<td>Vacía</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="even">
<td>Transferir o procesar</td>
<td>No se encuentra una tarjeta kanban</td>
<td>Nº</td>
<td>Nº</td>
<td>Nº</td>
<td>Nº</td>
<td>Nº</td>
<td>Nº</td>
</tr>
<tr class="odd">
<td>Transferir o procesar</td>
<td>Se encuentra una tarjeta kanban, pero no está asignada a un kanban</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="even">
<td>Procesar</td>
<td><ul>
<li>Sin planificar</li>
<li>Preparado</li>
<li>En curso</li>
</ul></td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Procesar</td>
<td>Completada</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]