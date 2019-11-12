---
title: Introducción a las ubicaciones funcionales
description: Este tema proporciona una visión general de las ubicaciones funcionales en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 577c888393163bdb7e445e436c336f20381cc78f
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572161"
---
# <a name="introduction-to-functional-locations"></a>Introducción a las ubicaciones funcionales

[!include [banner](../../includes/banner.md)]

 

Este tema proporciona una visión general de las ubicaciones funcionales en Administración de activos. Las ubicaciones funcionales son elementos de una estructura técnica, como las unidades funcionales de un sistema. Las ubicaciones funcionales se crean jerárquicamente y en ellas se instalan activos. La configuración de las ubicaciones funcionales de la empresa depende de los requisitos de la misma.

A continuación se muestran algunos ejemplos de cómo se pueden usar las ubicaciones funcionales:

- **Funcional**: las ubicaciones funcionales pueden estar dirigidas al usuario y usarse para gestionar activos que tienen un comportamiento similar.
- **Relacionada con el proceso**: las ubicaciones funcionales pueden estar orientadas al flujo de trabajo.
- **Espacial**: las ubicaciones funcionales pueden representar ubicaciones geográficas o sitios.

Cada ubicación funcional se administra de forma independiente en Administración de activos. Estas son algunas de las características útiles de las ubicaciones funcionales:

- Configurar especificaciones de ubicaciones funcionales.
- Configurar requisitos de especificación de activos.
- Configurar secuencias de mantenimiento preventivo y reactivo.
- Gestionar activos instalados.
- Realizar un seguimiento de las solicitudes y las órdenes de trabajo activas relacionadas con los activos instalados.
- Realizar un seguimiento de los errores que se registran en los activos.
- Realizar un seguimiento de los costes de mantenimiento de los activos relacionados con una ubicación funcional en un momento dado.

Las ubicaciones funcionales ofrecen la trazabilidad de los activos en relación con solicitudes, órdenes de trabajo, registros de errores, evaluaciones de condición, registros de detención de producción y registros de contador de activos.

> [!NOTE]
> Incluso si un activo está instalado en varias ubicaciones funcionales durante su vida útil, los costes se pueden relacionar con cada ubicación. En otras palabras, los costes del activo siempre están relacionados con la ubicación funcional en la que se instaló el activo en un momento dado.

Las ubicaciones funcionales **no** son flexibles. Por lo tanto, después de configurar una jerarquía de ubicaciones funcionales, no puede mover las ubicaciones en ella. 

Después de crear una jerarquía de ubicaciones funcionales, el paso siguiente es instalar activos en ella. Para más información, consulte [Instalar activos en ubicaciones técnicas](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Todas las ubicaciones técnicas

Seleccione **Administración de activos** \> **Campo común** \> **Ubicaciones funcionales** \> **Todas las ubicaciones funcionales** para abrir la página lista **Todas las ubicaciones funcionales**. Esta página muestra todas las ubicaciones funcionales y alguna información relacionada con cada una. Para ver solamente las ubicaciones funcionales activas, seleccione **Ubicaciones funcionales activas**. Para ver únicamente las ubicaciones funcionales que están relacionadas con usted como trabajador, seleccione **Mis ubicaciones funcionales activa**. (Esta relación se configura en la página **Trabajadores**. Para obtener más información, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md)).

En la página de lista **Todas las ubicaciones funcionales**, seleccione un vínculo en la columna **Ubicación funcional** para ver los detalles del registro seleccionado. Para editar la ubicación funcional, seleccione el botón **Editar**. La vista de detalles muestra información detallada relacionada con la ubicación. También incluye un panel **Información relacionada** a la derecha. Este panel muestra la jerarquía de ubicaciones funcionales. Puede expandir y contraer el panel **Información relacionada**.

Los botones del panel de acciones se organizan en fichas. La tabla siguiente describe brevemente los botones relacionados con Administración de activos.

| Nombre del botón                         | Descripción                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Editar                                | Cambiar entre el modo de edición y el modo de vista de la página.                                                                                         |
| Nueva                                 | Crear una nueva ubicación funcional.                                                                                                            |
| Borrar                              | Eliminar la ubicación funcional seleccionada.                                                                                                     |
| Asignar un nuevo nombre                              | Cambiar de nombre la ubicación funcional seleccionada.                                                                                                     |
| Copiar estructura de ubicación técnica  | Copiar la jerarquía de ubicaciones funcionales.                                                                                                      |
| Instalar activo                       | Instalar un activo, incluidos los activos secundarios, en la ubicación funcional.                                                                        |
| Reemplazar activo                       | Sustituir la jerarquía de activos con otra jerarquía de activos en la ubicación funcional.                                                         |
| Control de costes                        | Abrir la página **Control de costes de la ubicación funcional**, donde puede hacer un cálculo de costes para la ubicación funcional seleccionada.                |
| Control de horas                        | Abrir la página **Control de horas de la ubicación funcional**, donde puede hacer un cálculo de costes para la ubicación funcional seleccionada.                |
| Activos                              | Abrir la página **Todos los activos**, donde puede ver una lista de activos relacionados con la ubicación funcional seleccionada.                      |
| Solicitudes                            | Abrir la página **Solicitudes activas**, donde puede ver una lista de las solicitudes relacionadas con la ubicación funcional seleccionada.               |
| Órdenes de trabajo                         | Abrir la página **Órdenes de trabajo activas**, donde puede ver una lista de las órdenes de trabajo relacionadas con la ubicación funcional seleccionada.         |
| Defectos                              | Abrir la página **Errores de activo**, donde puede ver una lista de los registros de errores de activos relacionados con la ubicación funcional seleccionada. |
| Actualizar estado de ubicación técnica    | Cambiar la etapa de la ubicación funcional seleccionada.                                                                                        |
| Registro de estado de ciclo de vida                 | Ver un registro que muestre las etapas de la ubicación funcional seleccionada.                                                                        |
