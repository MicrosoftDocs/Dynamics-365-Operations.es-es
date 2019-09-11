---
title: Introducción a las órdenes de trabajo
description: Este tema proporciona una visión general de las órdenes de trabajo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875890"
---
# <a name="introduction-to-work-orders"></a>Introducción a las órdenes de trabajo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Se usan órdenes de trabajo para gestionar, proporcionar la información necesaria y registrar el consumo sobre trabajos mantenimiento. La orden de trabajo puede tener uno o más trabajos de orden de trabajo y uno o más activos que se pueden conectar a una orden de trabajo. Cada línea de orden de trabajo define un trabajo de mantenimiento programado en el activo.

Las órdenes de trabajo se pueden crear de forma manual o automática.

- Se crean automáticamente mediante el formulario **Programar planes de mantenimiento**, para planes de mantenimiento basados en calendario establecidos en "Crear automáticamente".  

- Se crean automáticamente mediante el formulario **Programar rondas de mantenimiento**, para rondas de mantenimiento basados en calendario establecidas en "Crear automáticamente".  

- Se pueden crear a partir del programa de mantenimiento, que pueden ser trabajos de mantenimiento preventivo o solicitudes de mantenimiento.  

- Cree una orden de trabajo manualmente.  

- Cree una orden de trabajo desde **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de la ubicación técnica**.

>[!NOTE]
>Las órdenes de trabajo relacionadas con el mismo activo están relacionadas con el mismo identificador del proyecto.

## <a name="all-work-orders"></a>Todas las órdenes de trabajo

Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** para abrir la lista. **Todas las órdenes de trabajo** contienen una lista de todas las órdenes de trabajo y muestra parte de la información relacionada con la orden de trabajo.

![Figura 1](media/01-work-orders.png)

- Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Órdenes de trabajo activas** para ver una lista de todas las órdenes de trabajo.

- Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Mis trabajos de mantenimiento de órdenes de trabajo de la ubicación técnica** para ver una lista de trabajos de orden de trabajo que contienen los activos instalados en ubicaciones técnicas, con les que está relacionada en calidad de trabajador (configurado en [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md)).

- En la lista **Todas las órdenes de trabajo** (vista de cuadrícula), haga clic en un vínculo en la columna **Orden de trabajo** para mostrar la vista Detalles del registro seleccionado. Haga clic en el botón **Editar** para editar.  

- La vista Detalles, verá información detallada relacionada con la orden de trabajo.  

- En la vista Detalles, seleccione el vínculo **Líneas** para ver los detalles de trabajo de la orden de trabajo o seleccione el vínculo **Encabezado** para ver los detalles de la orden de trabajo.  

- El panel **Información relacionada** vertical a la derecha de la pantalla contiene información adicional relacionada con la orden de trabajo. Expanda el panel para ver la información relacionada para la orden de trabajo seleccionada.  


![Figura 2](media/02-work-orders.png)


Los botones del panel de acciones se organizan en fichas en el panel de acción. A continuación, se indica una breve descripción de los botones relacionados con la administración de activos de la empresa:



| Nombre del botón                     | Descripción                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Editar                            | Editar la orden de trabajo seleccionada.                                                                                                                                                                                                                                           |
| Nuevos                             | Cree una nueva orden de trabajo.                                                                                                                                                                                                                                                  |
| Borrar                          | Eliminar la orden de trabajo seleccionada.                                                                                                                                                                                                                                         |
| Grupo de órdenes de trabajo                 | Agregue una orden de trabajo seleccionad a un grupo de órdenes de trabajo o quítela del grupo de órdenes de trabajo.                                                                                                                                                                                           |
| Ajustar                          | Ajuste la información sobre el inicio y final esperados, el nivel de servicio, el trabajador responsable de mantenimiento o el grupo de trabajadores de mantenimiento responsable en órdenes de trabajo seleccionadas.                                                                                                                                     |
| Orden de trabajo relacionada              | Crear una orden de trabajo nueva relacionada con el trabajo de órdenes de trabajo. Esto resulta útil si se desea registrar órdenes de trabajo principales y secundarios.                                                                                                                              |
| Copiar orden de trabajo                 | Crear una orden de trabajo basada en una orden de trabajo existente.                                                                                                                                                                                                                |
| Historial de eventos                   | Consulte el historial de registro en la orden de trabajo.                                                                                                                                                                                                                |
| Notas de trabajo de mantenimiento de orden de trabajo                           | Cree una descripción o inserte notas o comentarios en una orden de trabajo. Comience haciendo clic en el botón **Agregar marca de tiempo** para agregar el nombre de usuario y una marca de tiempo a la nota. Las notas se muestran en el formulario **Orden de trabajo** > ficha desplegable **Detalles de línea** > pestaña **Descripción** . |
| Herramientas                           | Cree una lista de herramientas necesarias en una orden de trabajo. Las herramientas se configuran como recursos en **Administración de la organización** > **Común** > **Recursos** > **Recursos**.                                                                                                      |
| Lista de comprobación de mantenimiento           | Ver la lista de comprobación para el activo conectado a la orden de trabajo.                                                                                                                                                                                                              |
| Defecto de activo                     | Vea o registre la información del defecto en un activo que se utilizará para la administración de defectos.                                                                                                                                                                                        |
| Tiempo de inactividad por mantenimiento            | Especifique el tiempo de inactividad de mantenimiento para una orden de trabajo.                                                                                                                                                                                                                               |
| Evaluación de condiciones            | Registre las medidas de evaluación de condición en una orden de trabajo.                                                                                                                                                                                                             |
| Contadores de activos                 | Cree o vea registros de contador en el activo.                                                                                                                                                                                                                     |
| Previsión                        | Vea o cree previsiones en una orden de trabajo.                                                                                                                                                                                                                               |
| Diarios                        | Vea o cree diarios de orden de trabajo. Las líneas del diario se pueden copiar desde las previsiones.                                                                                                                                                                                         |
| Transacciones de proyecto            | Vea todas las transacciones registradas relacionadas con las órdenes de trabajo creadas para el activo.                                                                                                                                                                                             |
| Actualizar el estado de la orden de trabajo                | Actualice el estados de ciclo de vida de la orden de trabajo.                                                                                                                                                                                                                                                |
| Registro de estado de ciclo de vida                       | Registro que muestra los estados del ciclo de vida de la orden de trabajo seleccionada.                                                                                                                                                                                                                   |
| Documentos de activos                | La lista de documentos vinculada a los activos relacionados con una orden de trabajo. Estos documentos se configuran en **Administración de activos** > **Configuración** > **Documentos del activo**.                                                                                                 |
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


Los botones en la pestaña **Orden de trabajo** > grupo **Proyecto** tienen que ver con la funcionalidad en el módulo **Administración de proyectos y contabilidad** con respecto a las previsiones, los diarios y la facturación.

>[!NOTE]
>Las previsiones creadas en una orden de trabajo se pueden incluir al ejecutar la programación maestra con el modelo de previsión seleccionado en el formulario **Parámetros de administración de activos**.

