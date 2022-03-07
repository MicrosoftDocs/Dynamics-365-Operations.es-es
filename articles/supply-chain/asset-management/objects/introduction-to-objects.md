---
title: Introducción a los activos
description: Este tema proporciona una visión general de los activos en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetTimeline, EntAssetObjectTableLookup, EntAssetObjectTableParent, EntAssetObjectOverview, EntAssetObjectImage, EntAssetObjectTable, EntAssetLifecycleStateLog, EntAssetObjectWorkOrderActive, EntAssetObjectAttribute
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43a5646bc4a1301922781d8b083dfa709befe3dca0fad1074b5433c6e02f5c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767517"
---
# <a name="introduction-to-assets"></a>Introducción a los activos

[!include [banner](../../includes/banner.md)]

 

Este tema proporciona una visión general de los activos en Administración de activos. Un *activo* es cualquier tipo de equipo, como una máquina o una pieza de equipo, que requiere mantenimiento, servicio o reparación.

Un activo se actualiza automáticamente con la información relacionada. Por ejemplo, esta información puede tener que ver con órdenes de trabajo nuevas o actualizadas. Puede crear activos mediante el elemento de menú **Todos los activos** o el elemento de menú **Activos pendientes** . Este tema explica cómo crear activos mediante el elemento de menú **Todos los activos**. Para obtener información acerca de la creación de activos mediante el elemento de menú **Activos pendientes** , consulte [Crear activos basados en órdenes de compra](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Todos los activos

Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**. La página de lista **Todos los activos** muestra todos los activos y parte de la información relacionada con ellos. Para ver solo los activos activos, seleccione **Activos activos**. Para ver únicamente los activos que están instalados en las ubicaciones funcionales que están relacionadas con usted como trabajador de mantenimiento, seleccione **Mis activos activos**. (Esta relación se configura en la página **Trabajadores**. Para obtener más información, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md)).

En la vista de cuadrícula **Todos los activos**, seleccione un vínculo en la columna **Activo** para ver los detalles del registro seleccionado. Para editar el registro, seleccione el botón **Editar**. La vista de detalles muestra información detallada relacionada con el activo. El panel **Información relacionada** de la derecha contiene información adicional relacionada con el activo. Expanda el panel para mostrar la información relacionada del activo seleccionado.

Los botones del panel de acciones se organizan en fichas. La tabla siguiente describe brevemente los botones relacionados con Administración de activos.

| Nombre del botón          | Descripción                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Editar                 | Editar el activo seleccionado.                                                                                                                                         |
| Nueva                  | Crear un activo nuevo.                                                                                                                                                |
| Borrar               | Eliminar el activo seleccionado.                                                                                                                                       |
| Mover activo           | Mover el activo a otra estructura de activos o a otra ubicación de la misma estructura de activos.                                                                                         |
| Reemplazar activo        | Sustituir un activo secundario de una jerarquía de activos con otro activo.                                                                                                  |
| Instalar activo        | Instalar un activo en una ubicación funcional.                                                                                                                          |
| Copiar activo           | Copiar una jerarquía de activos para otro activo.                                                                                                                          |
| Solicitudes             | Abrir la página de lista **Solicitudes de activo**, donde puede ver las solicitudes de mantenimiento que se han creado para el activo seleccionado.                                                                         |
| Historial de eventos        | Obtener una visión general de varios registros realizados en el activo.                                                                                                         |
| L. MAT. de activos            | Ver una lista de todos los artículos (piezas de repuesto y otros elementos) que se utilicen en un activo.                                                                                  |
| Órdenes de trabajo          | Abrir la página de lista **Órdenes de trabajo activas** , donde puede ver las órdenes de trabajo para el activo.                                                                                        |
| Lista de comprobación            | Obtener una visión general de las listas de comprobación de mantenimiento y las medidas que se han registrado en el activo.                                                                                                 |
| Tiempo de inactividad por mantenimiento | Crear o ver registros de tiempo de inactividad de mantenimiento del activo.                                                                                                       |
| Transacciones de proyecto | Ver todas las transacciones registradas relacionadas con las órdenes de trabajo que se han creado para el activo.                                                                                       |
| Medidas de activo       | Crear o ver las medidas de activos en el activo.                                                                                                               |
| Programa de mantenimiento | Abrir la página de lista **Programación de mantenimiento abierta**, donde puede ver los planes de mantenimiento, las solicitudes de mantenimiento y las rondas de mantenimiento asociados al activo y que tengan el estado **Creado**. |
| Actualizar estado de activo   | Actualizar el estado de ciclo de vida del activo. Puede seleccionar varios activos en la página de lista **Todos los activos** y después actualizar al estado de ciclo de vida de activo para todos al mismo tiempo.              |
| Registro de estado de ciclo de vida  | Abrir un registro que muestre los estados de ciclo de vida del activo seleccionado.                                                                                                                 |
| Documentos de activos      | Ver una lista de los documentos adjuntos a un activo. Estos documentos se configuran en **Administración de activos** \> **Configuración** \> **Documentos del activo**.                 |
| Atributos           | Crear o ver los atributos del activo.                                                                                                                             |
| Imagen                | Seleccionar una imagen para el activo.                                                                                                                                   |
| Activos principales        | Ver el historial del activo principal del activo seleccionado.                                                                                                                |
| Ubicaciones funcionales | Ver el historial de la ubicación funcional del activo seleccionado.                                                                                                          |
| Evaluación de condiciones | Registrar las medidas de evaluación de condición del activo.                                                                                                         |
| Defectos               | Abrir la página de lista **Errores de activo**, donde puede ver los errores que se han registrado en el activo.                                                                                             |
| Control de costes         | Comparar los costes de presupuesto y los costes reales del activo.                                                                                                              |
| Control de horas         | Comparar las horas previstas y las horas reales en el activo.                                                                                                              |
| KPI de activo           | Calcular y ver los indicadores clave de rendimiento (KPI) para el activo.                                                                                              |
| Tipos de trabajo            | Obtener una visión general de los tipos de trabajo predeterminados actuales para el activo.                                                                                                            |
| Tipos de criticidad    | Ver o actualizar los tipos de importancia del activo.                                                                                                                              |
| Piezas de repuesto          | Ver una lista de repuestos aprobados y alternativos que se pueden utilizar en el activo.                                                                               |
| Consumo de activo    | Imprimir un informe que muestre los registros de consumo del activo.                                                                                                |
| Defecto de activo          | Imprimir un informe que muestre los registros de defectos del activo.                                                                                                      |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]