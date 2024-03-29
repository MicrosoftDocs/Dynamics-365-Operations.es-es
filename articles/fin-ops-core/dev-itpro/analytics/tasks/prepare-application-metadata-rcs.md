---
title: Preparar metadatos de la aplicación para usarse en RCS
description: Este artículo describe cómo crear una nueva configuración de informes que contenga metadatos de la aplicación.
author: kfend
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: a9ccbb120be43eaf7a8ae8b5bf8eaafb4850b199
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289986"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Preparar metadatos de la aplicación para usarse en RCS
[!include [banner](../../includes/banner.md)]

Los siguiente pasos explican cómo un usuario en el rol de Administrador del sistema o Desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos (ER) que contiene metadatos de la aplicación para diseñar configuraciones de asignación del modelo de ER en Regulatory Configuration Service (RCS). Esta configuración se utilizará para diseñar una configuración de asignación del modelo de ER de ejemplo para acceder a transacciones de comercio exterior. En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa. Para completar estos pasos, primero debe completar los pasos del artículo [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="prerequisites"></a>Requisitos previos
1.    Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**. 
2.    Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). 
3.    Haga clic en **Configuraciones de metadatos**. 
4.    Supongamos que RCS se utilizará para diseñar una solución de ER para una aplicación de Finance and Operations que generará documentos electrónicos que contienen información de dominio empresarial de comercio exterior. Para especificar la asignación entre el modelo de datos de ER y los orígenes de datos requeridos, en RCS necesitamos tener acceso a los metadatos de la aplicación de Finance and Operations. Por lo tanto, como parte del diseño de la solución de ER, configuramos una nueva configuración de metadatos de ER que contiene todos los metadatos que se requieren actualmente para generar informes de ER para el dominio empresarial seleccionado. 

## <a name="add-metadata-configuration"></a>Agregar configuración de metadatos 
1.    Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable. 
2.    En el campo **Nombre**, escriba 'Metadatos de comercio exterior'. 
3.    Haga clic en **Crear configuración**. 
4.    Haga clic en **Diseñador**. 
5.    Haga clic en **Agregar**. 
  
> [!NOTE]
> Puede seleccionar todos los metadatos para toda la aplicación o modelos o módulos seleccionados. Tenga en cuenta que, en este caso, los siguientes metadatos se agregarán automáticamente: tablas de registros, enumeraciones y tipos de datos extendidos. Cuando se necesitan tipos adicionales de metadatos, deben agregarse manualmente. 
 
Disponemos de algunos metadatos relacionados con transacciones de comercio exterior seleccionando elementos de metadatos manualmente. 
  
6.    Haga clic en **Agregar origen de datos**. 
7.    Haga clic en **Registros de tabla**. 
8.    Use el filtro rápido para filtrar el campo **Nombre** con un valor de 'Intrastat'. 
9.    Seleccione el registro de tabla de **Intrastat** . 
10.    Haga clic en **Aceptar**.
  
Agregamos información de metadatos sobre la tabla de registros de Intrastat. 
  
11.    En el árbol, expanda **Registros de tabla de Intrastat**\>**Relaciones**. 
12.    En el árbol, seleccione **Registros de tabla de Intrastat**\>**Relations\IntrastatCommodity (Registros de tabla EcoResCategory)**.     
13.    Haga clic en **Agregar metadatos**. 
  
> [!NOTE]
> Los metadatos sobre las relaciones necesarias para la tabla de registros seleccionada se deben agregar manualmente. 
  
16.    Haga clic en **Agregar origen de datos**. 
17.    Haga clic en **Enumeración**. 
18.    Use el filtro rápido para filtrar el campo **Nombre** con un valor de 'IntrastatDirection'. 
19.    Seleccione el registro **Enumeración de IntrastatDirection**. 
20.    Haga clic en **Aceptar**. 
21.    Haga clic en **Guardar**.  
22.    Cierre la página. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>Completar la versión de borrador de la configuración de metadatos
1.    Haga clic en **Cambiar estado**. 
2.    Haga clic en **Completar**. 
3.    Haga clic en **Aceptar**. 
4.    Seleccione la versión completada **1**. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>Exportar la versión completada de la configuración de metadatos desde la aplicación como archivo XML
1.    Haga clic en **Intercambiar**. 
2.    Haga clic en **Exportar como archivo XML**. 
3.    Haga clic en **Aceptar**. 
    
La configuración de metadatos de ER creada se ha guardado como archivo XML que se puede importar a RCS y utilizar como la fuente de información sobre metadatos para el dominio empresarial de comercio exterior. Según esta información, podemos especificar la asignación entre los metadatos de la aplicación y el modelo de datos de ER.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
