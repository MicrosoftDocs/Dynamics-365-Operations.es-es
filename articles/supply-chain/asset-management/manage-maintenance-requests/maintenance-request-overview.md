---
title: Solicitudes de mantenimiento
description: Este artículo proporciona una visión general de la gestión de solicitudes de mantenimiento en Administración de activos
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 488b6505aba246aa3a6ea69436514a274403bf49
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015649"
---
# <a name="maintenance-requests"></a>Solicitudes de mantenimiento

[!include [banner](../../includes/banner.md)]

Las solicitudes de mantenimiento son las notas o declaraciones que se crean para notificar a un administrador o planificador sobre un activo que requiere un trabajo de mantenimiento o de reparación, sin crear una orden de trabajo. Si el contenido de una solicitud de mantenimiento se considera válido, se puede crear una orden de trabajo a partir de la solicitud de mantenimiento.

Las solicitudes de mantenimiento se pueden crear para cualquier activo en Administración de activos. Se pueden crear distintos tipos de solicitudes de mantenimiento, en función de cómo las utilice la empresa. A continuación se incluyen algunos ejemplos:

- Solicitudes de mantenimiento
- Notas
- Correcciones o mejoras
- Inversiones
- Reparación interna (este tipo se usa cuando se reciben activos de otra ubicación para poder realizar un trabajo de mantenimiento o reparación y después se devuelve el activo cuando el trabajo se ha completado).

## <a name="view-maintenance-requests"></a>Ver solicitudes de mantenimiento

Para ver las solicitudes de mantenimiento, seleccione **Administración de activos** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento**, **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de ubicación funcional**. Cada página de lista muestra la información relacionada con una solicitud de mantenimiento.

![Ver solicitudes de mantenimiento.](media/01-manage-maintenance-requests.png)

> [!NOTE]
> Use la página de lista **Mis solicitudes de mantenimiento de ubicación funcional** para ver una lista de las solicitudes de mantenimiento que contienen ubicaciones funcionales con las que está relacionado como trabajador o los activos que están instalados en ubicaciones funcionales con las que está relacionado como trabajador. (Para obtener información sobre cómo configurar ubicaciones funcionales en trabajadores de mantenimiento, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md)).
> 
> Aunque hay información de cuenta de cliente disponible en Administración de servicios de activos (mantenimiento externo), no está disponible en Administración de activos (mantenimiento interno).

Para abrir la vista de detalles de un registro, en la página de lista **Todas las solicitudes de mantenimiento** , en la vista de cuadrícula, seleccione un vínculo en la columna **Solicitud de mantenimiento**.

![Ver detalles de la solicitud de mantenimiento.](media/02-manage-maintenance-requests.png)

Los botones del panel de acciones se organizan en fichas. La tabla siguiente describe brevemente los botones relacionados con Administración de activos.

| Nombre del botón                      | Descripción |
|----------------------------------|-------------|
| Editar                             | Editar la solicitud de mantenimiento seleccionada. |
| Nueva                              | Crear una nueva solicitud de mantenimiento. |
| Borrar                           | Eliminar la solicitud de mantenimiento seleccionada. |
| Grupo de órdenes de trabajo                  | Conectar la solicitud de mantenimiento seleccionada a un grupo de órdenes de trabajo. |
| Orden de trabajo                       | Crear una orden de trabajo a partir de la solicitud de mantenimiento seleccionada. |
| Defecto de activo                      | Haga click en **Defectos de activo**, donde puede crear un registro de defectos para la solicitud de mantenimiento seleccionada. |
| Órdenes de trabajo                      | Muestra una lista de todas las órdenes de trabajo que están conectadas a la solicitud de mantenimiento seleccionada. |
| Actualizar estado de solicitud de mantenimiento | Actualizar el estado de la solicitud de mantenimiento. |
| Registro de estado de ciclo de vida              | Ver un registro que muestre los estados de ciclo de vida de la solicitud de mantenimiento seleccionada. |
| Detalles de solicitud de mantenimiento      | Imprimir un informe que muestre los detalles de la solicitud de mantenimiento seleccionada. |
| Enviar activo en préstamo                  | Seleccione un activo en préstamo que debe ser una sustitución temporal del activo seleccionado en la solicitud de mantenimiento seleccionada. |
| Devolver activo en préstamo                | Registrar el activo en préstamo como devuelto. |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]