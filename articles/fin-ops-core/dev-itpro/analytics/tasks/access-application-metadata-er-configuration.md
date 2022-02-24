---
title: Acceder a metadatos de la aplicación mediante el uso de una configuración de ER
description: Los pasos de este tema explican cómo un usuario de Regulatory Configuration Service (RCS) puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos en Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fa8e9ac4940bbc1252819ebcc3de2e21c9e0933f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682174"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Acceder a metadatos de la aplicación mediante el uso de una configuración de ER

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario de Regulatory Configuration Service (RCS) con el rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos de la aplicación. Se accederá a los metadatos de la aplicación mediante el uso de una configuración de metadatos de ER que contenga un conjunto de metadatos de ejemplo para acceder a transacciones de comercio exterior. Para completar estos pasos, en RCS primero debe completar los pasos del tema, el procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). A continuación, complete los pasos del tema, [Preparar metadatos de la aplicación para usarse en RCS](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Requisitos previos
1. Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**. 
2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="import-metadata-configuration"></a>Importar configuración de metadatos 
1. Haga clic en **Configuraciones de metadatos**. 
2. Importe la configuración de metadatos de ER que contenga metadatos que se han configurado para generar documentos electrónicos para el dominio empresarial de comercio exterior. Esta configuración de metadatos de ER se ha exportado como archivo XML mientras se han completado los pasos del procedimiento [Preparar metadatos de la aplicación para usarse en RCS](prepare-application-metadata-rcs.md). 
3. Haga clic en **Intercambiar**. 
4. Haga clic en **Cargar desde un archivo XML**. 
5. Haga clic en **Examinar** y seleccione el archivo "Metadatos de comercio exterior.xml". 
6. Haga clic en **Aceptar**. 
7. Cierre la página. 

## <a name="create-data-model-configuration"></a>Crear configuración de modelo de datos
1. Haga clic en **Configuraciones de informes**. 
2. Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable. 
3. En el campo **Nombre**, escriba 'Modelo de comercio exterior'. 
4. Haga clic en **Crear configuración**. 
5. Haga clic en **Diseñador**. 
6. Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable. 
7. Escriba 'Raíz' en el campo **Nombre**. 
8. Haga clic en **Agregar**. 
9. Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable. 
10.    En el campo **Nombre**, escriba 'Transacción'. 
11.    En el campo **Tipo de artículo**, seleccione **Lista de registros**. 
12.    Haga clic en **Agregar**. 
13.    Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable. 
14.    En el campo **Nombre**, escriba 'Código de mercancía'. 
15.    En el campo **Tipo de artículo**, seleccione **Cadena**. 
16.    Haga clic en **Agregar**. 
17.    Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable. 
18.    En el campo **Nombre**, introduzca 'Importe facturado'. 
19.    En el campo **Tipo de artículo**, seleccione **Real**. 
20.    Haga clic en **Agregar**. 
21.    Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable. 
22.    En el campo **Nombre**, escriba 'Fecha'. 
23.    En el campo **Tipo de artículo**, seleccione **Fecha**. 
24.    Haga clic en **Agregar**. 
25.    Haga clic en **Referencia raíz**. 
26.    Haga clic en **Aceptar**. 
27.    Haga clic en **Guardar**. 
28.    Cierre la página. 
29.    Haga clic en **Cambiar estado**. 
30.    Haga clic en **Completar**. 
31.    Haga clic en **Aceptar**. 

## <a name="create-model-mapping-configuration"></a>Crear configuración de asignación del modelo 
1. Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable. 
2. En el campo **Nuevo**, especifique 'Asignación de modelo basado en el modelo de datos del Modelo de comecio exterior'. 
3. En el campo **Nombre**, escriba 'Asignación de comercio exterior'. 
4. Haga clic en **Crear configuración**. 
5. Expanda la sección **Requisitos previos**. 
6. Haga clic en **Editar**. 
7. Haga clic en **Nuevo**. 
8. En la lista, marque la fila seleccionada. 
9. En el campo **Tipo de componente de requisito previo**, seleccione **Configuración**. 
10.    Seleccione la configuración **Metadatos de comercio exterior**. 
11.    Haga clic en **Guardar**. 
12.    Agregamos la referencia a la versión 1 de la configuración "Metadatos de comercio exterior". Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo. 
13.    Cierre la página. 
14.    Haga clic en **Diseñador**. 
15.    Haga clic en **Diseñador**. 
16.    En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**. 
17.    Haga clic en **Agregar raíz**. 
18.    En el campo **Nombre**, escriba 'Intrastat'. 
19.    Seleccione el registro de tabla de **Intrastat**. 
20.    Haga clic en **Aceptar**. 

> [!NOTE]
> Solo se ofrecieron 2 tablas, ya que solo se agregaron 2 tablas al conjunto de metadatos que se utiliza actualmente. 

21.    Haga clic en **Enlazar**. 
22.    En el árbol, expanda **Intrastat**. 
23.    En el árbol, seleccione **Intrastat\AmountMST**. 
24.    En el árbol, expanda **Transacción = Intrastat**. 
25.    En el árbol, seleccione **Transacción = Intrastat\Importe facturado**. 
26.    Haga clic en **Enlazar**. 
27.    En el árbol, seleccione **Intrastat\TransDate**. 
28.    En el árbol, seleccione **Transacción = Intrastat\Fecha**. 
29.    Haga clic en **Enlazar**. 
30.    En el árbol, expanda **Intrastat\>Relaciones**. 
31.    En el árbol, expanda **Intrastat\>Relaciones\IntrastatCommodity**. 
32.    En el árbol, seleccione **Intrastat\>Relaciones\IntrastatCommodity\Código**. 
33.    En el árbol, seleccione **Transacción = Intrastat\Código de mercancía**. 
34.    Haga clic en **Enlazar**. 
35.    Hacer clic en **Validar**. 

> [!NOTE]
> Hemos enlazada correctamente los elementos del modelo de datos con artículos de orígenes de datos que se describen con detalles de metadatos de la aplicación desde la configuración de metadatos de ER a la que se hace referencia. 
36.    Haga clic en **Guardar**. 
37.    Cierre la página. 
38.    Cierre la página. 
39.    Cuando se necesiten, puede ampliar el conjunto existente de metadatos y después exportar la nueva versión completada de la configuración de los metadatos de ER. A continuación puede importarla al RCS, y actualizar los requisitos previos de configuración de asignación de modelos configurados a una nueva versión de la configuración de metadatos importada. 

> [!NOTE]
> Esta forma de obtener información sobre metadatos de la aplicación es la única disponible para aplicaciones implementadas localmente (cuando se utiliza un modelo de implementación de datos empresariales locales (LBD), o en las instalaciones).
        
