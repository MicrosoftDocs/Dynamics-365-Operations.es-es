---
title: Novedades y cambios en Dynamics 365 Human Resources (19 de noviembre de 2021)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources independiente para el 19 de noviembre de 2021.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f28057c370b27dbdad4bfe1104e9289f7df65621
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691957"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Novedades y cambios en Dynamics 365 Human Resources (19 de noviembre de 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este tema se describen las funciones que son nuevas, han cambiado o estarán disponibles próximamente en Microsoft Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

En esta versión se incluyen las siguientes correcciones de errores. Los cambios se aplican al número de compilación 8.1.4591.

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Problema | Description |
|---|---|---|
| 626178 | Falta la navegación en los iconos de trabajadores en **Autoservicio para directores** | Este problema ahora está solucionado. La navegación está disponible para ver los detalles del informe en **Autoservicio para directores**. |
| 632573 | No hay ningún error de validación al guardar un **Curso** | Este problema ahora está solucionado. Al crear un curso con el **Número mínimo de participantes** a mayor que 0 todavía se podía guardar incluso cuando el **Número máximo de participantes** es 0. |
| 615955 | Error "El campo **Objetivo** debe completarse" al crear una nueva ubicación de solicitud de contratación. | Al crear una dirección para una nueva ubicación de solicitud de contratación, aparece el error: "El campo 'Objetivo' debe completarse". Sin embargo, el campo **Objetivo** no está disponible en la página. |
| 620797 | El error del campo de **Género** vacío es confuso | Cuando no se introduce un género para un contacto personal, el informe muestra 'Haga clic o toque aquí para introducir texto': es confuso, ya que no se puede introducir nada en el campo. |
| 620800 | El vínculo de la declaración de prestaciones está oculto | La declaración de prestaciones no se puede ver de forma predeterminada en **Autoservicio para empleados**.  Se agregó un vínculo al lado derecho de **Autoservicio para empleados** en la sección **Vínculos** |
| 629778 | Problema de rendimiento con la integración de CDS. | La solicitud relacionada con la autorización provocó un problema de rendimiento. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información sobre activar las funciones, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
|---|---|---|
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Próximamente
Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Dynamics 365 y las nubes de la industria: lanzamiento de versiones 2 de 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
