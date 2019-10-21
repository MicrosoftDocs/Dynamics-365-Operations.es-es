---
title: Aplicación móvil de la hoja de horas del proyecto
description: Este tema proporciona información sobre la aplicación móvil Microsoft Dynamics 365 Project Timesheet. La aplicación Project Timesheet permite a los usuarios enviar y aprobar hojas de horas para los proyectos desde su dispositivo móvil.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 91ecccab58e4f1582a43eac62b42c7205b383bb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174498"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>Aplicación móvil Microsoft Dynamics 365 Project Timesheet

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Información general

La aplicación Microsoft Dynamics 365 Project Timesheet permite a los usuarios enviar y aprobar hojas de horas para los proyectos desde su dispositivo móvil (iPhone o Android). La aplicación móvil aprovecha la funcionalidad de la hoja de horas que reside en el área de Gestión de proyectos y contabilidad de Dynamics 365 Finance, mejorando la productividad y eficiencia del usuario, así como habilitando la entrada y aprobación de hojas de horas de proyecto a tiempo.

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil

Descargue e instalar la aplicación móvil Microsoft Dynamics 365 Project Timesheet para Android o iPhone desde la tienda móvil del dispositivo.

## <a name="enable-the-app"></a>Habilitar la aplicación 

En Finance, la aplicación móvil de Project Timesheet debe estar habilitada. Para habilitar la funcionalidad, vaya **Parámetros de gestión de proyectos y contabilidad \> Hoja de horas** y seleccione el parámetro **Habilitar Microsoft Dynamics 365 Project Timesheet**.

## <a name="sign-in-to-the-app"></a>Iniciar sesión en la aplicación

1.  Inicie la aplicación en su dispositivo móvil.

2.  Introduzca su URL de Finance.

3.  La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.

4.  Iniciará sesión en su empresa predeterminada.

## <a name="submit-a-project-timesheet"></a>Enviar una hoja de horas de proyecto

Puede crear y enviar una hoja de horas de proyecto en la aplicación. También puede basar una nueva hoja de horas en la información de una hoja de horas anterior, en las líneas guardadas del formulario o asignación de proyecto. Si se le designa como delegado, también puede introducir una hoja de horas para otro trabajador. Para crear una hoja de horas como delegado, seleccione el botón **Menú** y seleccione un nombre de recurso.

La página de la hoja de horas creará una nueva hoja de horas del período de hoja de horas, en función de la fecha actual. Se mostrará la semana laboral. Si el período de hoja de horas cubre varias semanas, puede seleccionar otra semana laboral en la pestaña de semana laboral.
Si existe una hoja de horas para la fecha actual, se mostrará. Si necesita crear una nueva hoja de horas en un período de hoja de horas diferente, seleccione el botón **Menú** y después **Nueva hoja de horas**.

Puede especificar información de proyecto haciendo clic en la acción **Agregar tiempo** o la acción **Copiar tiempo de**. La acción **Copiar tiempo de** copiará la información de la línea de proyecto, pero no las horas. El menú **Copiar tiempo de** incluye las opciones siguientes:

- **Copiar de hoja de horas ya existente**: permite copiar las líneas de hoja de horas de una hoja de horas existente.

- **Copiar de favoritos**: permite crear nuevas líneas de hoja de horas con la configuración de la hoja de horas que seleccionó como favoritas.

- **Copia de asignación**: crea nuevas líneas de hoja de horas a partir de proyectos asignados.

La información de proyecto que se muestra depende de los parámetros móviles que definió en la página **Parámetros de gestión de proyectos y contabilidad**.

En el campo **Entidad jurídica**, seleccione la entidad jurídica para la que realizó el trabajo de proyecto. El campo **Entidad jurídica** está disponible solo si se ha habilitado la compatibilidad de hoja de horas de empresas vinculadas en su entidad jurídica.

Seleccione el cliente asociado al proyecto de la hoja de horas. Para la versión inicial en Android, la entrada del cliente no se admite, ya que debe seleccionar el proyecto primero. Si ha seleccionado el proyecto primero, el campo **Cliente** se rellena automáticamente.

En el campo **Proyecto**, seleccione el proyecto para el que desee especificar horas. El campo **Cliente** se completa automáticamente.

Las búsquedas del cliente y de proyecto habilitan la búsqueda de clientes y de proyectos.

Seleccione la información en los campos **Categoría**, **Actividad**, **Propiedad de línea**, **Grupo de impuestos** y **Grupo de impuestos de artículos** como sea necesario. Estos campos se pueden sobrescribir.

El campo **Propiedad de línea** se establecerá en un valor predeterminado, en función de los parámetros de la gestión de proyectos y de contabilidad. Si se habilitan el proyecto/categoría y los parámetros de categoría/recurso, el valor **Propiedad de línea** se establecerá en valor predeterminado que haya definido para esta validación. Cuando el proyecto/categoría y los parámetros de categoría/recurso no se habiliten, el valor **Propiedad de línea** tendrá un valor predeterminado según el campo **Habilitar propiedad de línea predeterminada** en la página **Parámetros de gestión de proyectos y contabilidad**. El valor de la **Propiedad de línea** no puede ser anularse.

Seleccione un día para agregar tiempo. Especifique el número de horas que trabajó cada día.

Para agregar comentarios acerca de las horas que está introduciendo, haga clic en **Agregar comentarios** y, a continuación, escriba comentarios para un público interno, clientes, o ambos.
Los directores de proyecto pueden ver los comentarios internos. Los comentarios de clientes se incluyen en las facturas.

Para guardar la línea como favorita, active la casilla y, a continuación, haga clic en **Guardar como favorita**.

La compatibilidad de la dimensión financiera y los datos adjuntos no se proporciona en la aplicación móvil.

Continúe agregando las líneas de proyecto según sea necesario para completar la hoja de horas.

Haga clic en **Enviar** para enviar la hoja de horas al flujo de trabajo de aprobación.

## <a name="review-timesheets"></a>Revisar hojas de horas

Una lista de las hojas de horas que necesitan ser revisadas está disponible en el menú. Esta opción solo está disponible si se le ha designado como aprobador del flujo de trabajo. Se admiten el encabezado y la aprobación de la línea. La aprobación de nivel de línea proporciona la capacidad de marcar una o más líneas para su aprobación. Después de revisar la información de la hoja de horas, haga clic en **Aprobar**, **Delegado**, o **Devolución** para continuar el flujo de trabajo.
