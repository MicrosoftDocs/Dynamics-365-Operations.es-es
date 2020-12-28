---
title: Introducción a las órdenes de trabajo
description: Este tema proporciona una visión general de las órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7997b4b9521b43e1e00cfa22f9df12a29582455a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436674"
---
# <a name="introduction-to-work-orders"></a>Introducción a las órdenes de trabajo

[!include [banner](../../includes/banner.md)]



Se usan órdenes de trabajo para gestionar trabajos de mantenimiento, proporcionar la información necesaria para ellos y registrar su consumo. Cada orden de trabajo puede tener uno o más trabajos de orden de trabajo y uno o más activos que se pueden conectar a cada orden de trabajo. Cada trabajo de orden de trabajo define un trabajo de mantenimiento programado en el activo.

Las órdenes de trabajo pueden crearse de las siguientes formas:

- Para planes de mantenimiento basados en calendario establecidos en "Crear automáticamente", se crean automáticamente usando [Programar planes de mantenimiento](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md).

- Para rondas de mantenimiento establecidos en "Crear automáticamente", se crean automáticamente usando [Programar rondas de mantenimiento](../preventive-and-reactive-maintenance/maintenance-rounds.md).

- Para trabajos de mantenimiento preventivo o solicitudes de mantenimiento, desde [Programa de mantenimiento](../preventive-and-reactive-maintenance/maintenance-schedule.md).

- Manualmente

- Desde **Todas las solicitudes de mantenimiento**, **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de la ubicación técnica**.

>[!NOTE]
>Las órdenes de trabajo que están relacionadas con el mismo activo están relacionadas con el mismo identificador del proyecto.

## <a name="all-work-orders"></a>Todas las órdenes de trabajo

Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** para abrir la página con la lista **Todas las órdenes de trabajo**. Esta página muestra todas las órdenes de trabajo y alguna información relacionada con cada una.

La ilustración siguiente muestra un ejemplo de la página de lista **Todas las órdenes de trabajo**.

![Figura 1](media/01-work-orders.png)

Para ver una lista de todas las órdenes de trabajo, seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Órdenes de trabajo activas**. 

Para ver una lista de trabajos de órdenes de trabajo que contienen activos instalados en las ubicaciones técnicas con las que está relacionado como trabajador, seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Mis trabajos de mantenimiento de órdenes de trabajo de la ubicación técnica**. (La relación entre los trabajadores y ubicaciones funcionales se configura en la página **Trabajadores**. Para obtener más información, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md)).

Aquí hay algunas maneras que puede usar la página **Todos los pedidos de trabajo**:

- En la vista de cuadrícula Todos los activos, seleccione un vínculo en la columna **Orden de trabajo** para ver los detalles del registro seleccionado. A continuación seleccionar **Editar** para abrir el registro para editar.

- En la vista Detalles, verá información detallada relacionada con la orden de trabajo.  

- En la vista Detalles, seleccione la pestaña **Líneas** para ver los detalles de trabajo de la orden de trabajo o seleccione la pestaña **Encabezado** para ver los detalles de la orden de trabajo.  

- Expanda el panel **Información relacionada** a la derecha de la página para ver información adicional relacionada con el pedido de trabajo seleccionado.

La ilustración siguiente muestra un ejemplo de vista detalles de **Todas las órdenes de trabajo**.

![Figura 2](media/02-work-orders.png)


Los botones del panel de acciones se organizan en fichas. La tabla siguiente describe brevemente los botones relacionados con Administración de activos:



| Nombre del botón                     | Descripción                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Editar                            | Editar la orden de trabajo seleccionada.                                                                                                                                                                                                                                           |
| Nuevos                             | Cree una nueva orden de trabajo.                                                                                                                                                                                                                                                  |
| Borrar                          | Eliminar la orden de trabajo seleccionada.                                                                                                                                                                                                                                         |
| Grupo de órdenes de trabajo                 | Agregue la orden de trabajo seleccionad a un grupo de órdenes de trabajo o quítela del grupo de órdenes de trabajo.                                                                                                                                                                                           |
| Ajustar                          | Ajuste la información sobre el inicio y final esperados, el nivel de servicio, el trabajador responsable de mantenimiento o el grupo de trabajadores de mantenimiento responsable en órdenes de trabajo seleccionadas.                                                                                                                                     |
| Orden de trabajo relacionada              | Crear una orden de trabajo nueva relacionada con el trabajo de órdenes de trabajo. Esto resulta útil si se desea registrar órdenes de trabajo principales y secundarios.                                                                                                                              |
| Copiar orden de trabajo                 | Crear una orden de trabajo basada en una orden de trabajo existente.                                                                                                                                                                                                               |
| Historial de eventos                   | Ver el historial de registro de la orden de trabajo.                                                                                                                                                                                                                |
| Notas de trabajo de mantenimiento de orden de trabajo                           | Cree una descripción en una orden de trabajo o inserte notas o comentarios sobre ella. Primero seleccione **Agregar marca de tiempo** para agregar el nombre de usuario y una marca de tiempo a la nota. Las notas se muestran en la pestaña **Descripción** en la ficha desplegable **Detalles de línea** de la página **Orden de trabajo**.         |
| Herramientas                           | Cree una lista de herramientas necesarias en una orden de trabajo. Las herramientas se configuran como recursos en **Administración de la organización** > **Recursos** > **Recursos**.                                                                                                      |
| Lista de comprobación de mantenimiento           | Ver la lista de comprobación para el activo conectado a la orden de trabajo.                                                                                                                                                                                                              |
| Defecto de activo                     | Vea o registre la información del error de un activo. Esta información se usa para administración de errores.                                                                                                                                                                                      |
| Tiempo de inactividad por mantenimiento            | Especifique el tiempo de inactividad de mantenimiento para una orden de trabajo.                                                                                                                                                                                                                               |
| Evaluación de condiciones            | Registre las medidas de evaluación de condición en una orden de trabajo.                                                                                                                                                                                                             |
| Contadores de activos                 | Cree o vea registros de contador en el activo.                                                                                                                                                                                                                     |
| Previsión                        | Vea o cree previsiones en una orden de trabajo.                                                                                                                                                                                                                               |
| Diarios                        | Vea o cree diarios de orden de trabajo. Las líneas del diario se pueden copiar desde las previsiones.                                                                                                                                                                                         |
| Transacciones de proyecto            | Vea todas las transacciones registradas que están relacionadas con las órdenes de trabajo creadas para el activo.                                                                                                                                                                                             |
| Actualizar el estado de la orden de trabajo           | Actualice el estados de ciclo de vida de la orden de trabajo.                                                                                                                                                                                                                                                |
| Registro de estado de ciclo de vida                      | Ver un registro que muestre los estados de ciclo de vida de la orden de trabajo seleccionada.                                                                                                                                                                                                                   |
| Documentos de activos                | Ver la lista de documentos vinculada a los activos relacionados con una orden de trabajo. Estos documentos se configuran en **Administración de activos** > **Configuración** > **Documentos del activo**.                                                                                                 |
| Programación                        | Programe las órdenes de trabajo seleccionadas.                                                                                                                                                                                                                                      |
| Distribuir            | Programe la orden de trabajo seleccionada para un trabajador.                                                                                                                                                                                                                        |
| Eliminar programación                 | Elimine la programación para la orden de trabajo seleccionada.                                                                                                                                                                                                                          |
| Trabajos de mantenimiento de órdenes de trabajo programados             | Abra la página de la lista **Trabajos de mantenimiento de órdenes de trabajo programadas**.                                                                                                                                                                                                                             |
| Solicitud de compra de orden de trabajo | Abra la página de la lista **Solicitud de compra de orden de trabajo**.                                                                                                                                                                                                                 |
| Compra de orden de trabajo             | Abra la página de la lista **Compra de orden de trabajo**.                                                                                                                                                                                                                             |
| Control de costes                    | Comparar los costes de presupuesto y los costes reales en la orden de trabajo.                                                                                                                                                                                                                |
| Control de horas                    | Compare las horas previstas y las horas reales en la orden de trabajo.                                                                                                                                                                                                                |
| Informe de orden de trabajo               | Imprima un informe de orden de trabajo.                                                                                                                                                                                                                                                |
| Consumo de orden de trabajo          | Imprima un informe de consumo.                                                                                                                                                                                                                                               |


Los botones en el grupo **Proyecto** en la ficha **Orden de trabajo** del panel de acción están relacionados con la funcionalidad para previsiones, diarios y facturación del módulo **Administración de proyectos y contabilidad**.

>[!NOTE]
>Para incluir las previsiones creadas en una orden de trabajo cuando ejecuta la programación maestra, use el modelo de previsión seleccionado en la página **Parámetros de administración de activos**.

