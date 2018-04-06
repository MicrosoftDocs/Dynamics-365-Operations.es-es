---
title: "Integración con el cliente de Microsoft Project"
description: "Planificar y mantener la programación de un proyecto puede ser complejo, por lo que los gestores de proyectos deben utilizar herramientas que los ayuden a gestionar esta tarea. La integración con el cliente de Microsoft Project proporciona soporte para abrir y gestionar una estructura de descomposición del trabajo del proyecto."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a3445417d5ae88e2ff3676962a82921a7ab475d
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="microsoft-project-client-integration"></a>Integración con el cliente de Microsoft Project

[!include[banner](../includes/banner.md)]

Planificar y mantener la programación de un proyecto puede ser complejo, por lo que los gestores de proyectos deben utilizar herramientas que los ayuden a gestionar esta tarea. La integración con el cliente de Microsoft Project proporciona soporte para abrir y gestionar una estructura de descomposición del trabajo del proyecto. El gestor de proyectos puede volver publicar cualquier cambio en la estructura de descomposición del trabajo del proyecto de Finance and Operations.

> [!NOTE]
> Si utiliza Microsoft Dynamics 365 for Finance and Operations, actualización de julio, debe instalar KB 4054797 y 4055884.

## <a name="configure-the-microsoft-project-client-add-in"></a>Configurar el complemento del cliente de Microsoft Project
Para habilitar la integración con el cliente de Microsoft Project, se requiere la instalación de un complemento de Microsoft Dynamics 365 en la aplicación del cliente de Microsoft Project del usuario. Para ello, abra el **Espacio de trabajo de gestión de proyectos**.

•   Haga click en **Configurar el complemento de cliente del proyecto** de la sección **Vínculos** > **Configuración** del espacio de trabajo.

•   Haga clic en **Abrir** y, a continuación, haga clic en **Ejecutar** cuando se le solicite.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Abra y edite una estructura de descomposición del trabajo existente de borrador en el cliente de Microsoft Project
Si un proyecto en Finance and Operations ya tiene creada una estructura de descomposición del trabajo, la estructura de descomposición del trabajo se puede abrir en la aplicación del cliente de Microsoft Project si la estructura de descomposición del trabajo está en estado de borrador. Para abrirla desde la página **Proyecto**, haga clic en el vínculo **Abrir en Microsoft Project** de la pestaña **Plan**. Esta página también se puede abrir desde dentro de la aplicación del cliente de Microsoft Project haciendo clic en **Abrir** en la pestaña **Microsoft Dynamics 365**. Seleccione **Entidad jurídica** y **Proyecto** de la lista.

> [!NOTE]
> Si utiliza Internet Explorer como su explorador, deberá hacer clic en **Guardar** para abrir manualmente la ubicación en la que se ha descargado ese archivo. O bien, haga clic en **Guardar y abrir** para abrir el archivo en el cliente de Microsoft Project. No cambiar el nombre de archivo al guardar.

Antes de realizar cualquier edición en el archivo mediante el cliente de Microsoft Project, necesita comprobarlo. Haga clic en **Comprobar** en la pestaña **Microsoft Dynamics 365**. Esto impedirá que otros usuarios editen la estructura de descomposición del trabajo dentro de Finance and Operations al mismo tiempo. Para publicar la estructura de descomposición del trabajo después de completar las ediciones, haga clic en **Comprobar** en la pestaña **Microsoft Dynamics 365** .

Si ya ha agregado un equipo de proyecto al proyecto en Finance and Operations, la lista de recursos se rellenará con los miembros del equipo. Si todavía no ha agregado un equipo de proyecto al proyecto, puede seleccionar recursos y crear al equipo desde el cliente de Microsoft Project haciendo clic en el botón **Recursos** en la pestaña **Microsoft Dynamics 365**. 

Los siguientes datos se volverán a sincronizar en Finance and Operations como parte del proceso de registro de entrada:

•   Nombre de la tarea

•   Fecha de inicio

•   Fecha final

•   Predecesores

•   Nombres de recurso

•   Categoría

•   Categoría de recurso

•   Horas laborables

•   Notas

•   Prioridad

> [!NOTE]
> Si agrega cualquier otra columna a su archivo del cliente de Microsoft Project, no se guardará en el archivo y no se mostrará cuando se vuelva a abrir el archivo.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Crear la estructura de descomposición del trabajo para un proyecto existente mediante el cliente de Microsoft Project
Para crear una nueva estructura de descomposición del trabajo mediante el cliente de Microsoft Project, siga estos pasos:


1.  Abra el cliente de Microsoft Project.

2.  En la pestaña **Microsoft Dynamics 365**, haga clic en **Abrir**.

3.  Seleccionar la **Entidad jurídica** para el proyecto.

4.  Seleccione el **Proyecto**.

5.  En la pestaña **Microsoft Dynamics 365**, haga clic en **Desproteger**.

6.  Cuando esté listo para publicar en Finance and Operations, haga clic en **Proteger** en la pestaña **Microsoft Dynamics 365**.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Sustituir la estructura de descomposición del trabajo existente para un proyecto existente mediante el cliente de Microsoft Project
Para crear una estructura de descomposición del trabajo mediante el cliente de Microsoft Project y reemplazar una estructura de descomposición del trabajo existente por un proyecto existente, siga estos pasos:

1.  Abra el cliente de Microsoft Project.

2.  Cree la programación en el cliente de Microsoft Project.

3.  En la pestaña **Microsoft Dynamics 365**, haga clic en **Guardar cambios** > **Reemplazar proyecto existente**.

4.  Seleccionar la **Entidad jurídica** para el proyecto.

5.  Seleccione el **Proyecto**.

6.  Haga clic en **Aceptar**.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Cree un nuevo proyecto desde dentro del cliente de Microsoft Project


1.  Abra el cliente de Microsoft Project.

2.  Cree la programación en el cliente de Microsoft Project.

3.  En la pestaña **Microsoft Dynamics 365**, haga clic en **Guardar cambios** > **Guardar en nuevo proyecto**.

4.  Seleccionar la **Entidad jurídica** para el proyecto.

5.  Especifique el **Id. de proyecto** si es necesario.

6.  Especifique el **Nombre del proyecto**.

7.  Seleccione el **Tipo de proyecto**, el **Grupo de proyectos** y el **Id. de contrato de proyecto**. De forma alternativa, puede crear un nuevo contrato de proyecto haciendo clic en **Nuevo**.

8.  Seleccione el **Calendario** que se utilizará para los recursos.

11. Haga clic en **Aceptar**.

