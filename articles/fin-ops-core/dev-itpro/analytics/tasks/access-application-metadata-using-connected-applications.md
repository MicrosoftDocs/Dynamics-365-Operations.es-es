---
title: Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas
description: Los pasos de este tema explican cómo un usuario de Regulatory Configuration Service puede diseñar una nueva asignación de modelo de informes electrónicos mediante el uso de metadatos.
author: NickSelin
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b113f0db1d44dc5fbda30e10d62ff939550f299
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748702"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario de Regulatory Configuration Service (RCS) con el rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos en Finance and Operations. Se accederá en línea a los metadatos de la aplicación mediante el uso de la aplicación conectada de RCS. La asignación del modelo de ER de ejemplo se configurará para acceder a transacciones de comercio exterior. Para completar estos pasos, en RCS primero debe completar los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). Si no ha completado los pasos del tema [Acceder a metadatos de la aplicación mediante el uso de la configuración de ER](access-application-metadata-er-configuration.md), vaya a la [Página de ejemplos de informes electrónicos](https://go.microsoft.com/fwlink/?linkid=862266) para descargar y guardar las siguientes configuraciones de ER: Metadatos de comercio exterior.xml; Modelo de comercio exterior.xml; Asignación de comercio exterior.xml y, a continuación, complete los pasos del procedimiento.

## <a name="prerequisites"></a>Requisitos previos
1. Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**. 
2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="get-required-er-configurations"></a>Obtener las configuraciones de ER necesarias
1. Haga clic en **Configuraciones de informes**. 
2. Si ya ha completado los pasos del procedimiento [Acceder a metadatos de la aplicación mediante el uso de la configuración de ER](access-application-metadata-er-configuration.md), ya tiene todas las configuraciones de ER necesarias (configuraciones de metadatos, modelo y asignación de comercio exterior) en la instancia de RCS actual. Puede omitir todos los pasos restantes de esta subtarea. 
3. Haga clic en **Intercambiar**. 
4. Haga clic en **Cargar desde un archivo XML**. 
5. Haga clic en **Examinar** y seleccione el archivo **Metadatos de comercio exterior.xml**. 
6. Haga clic en **Aceptar**. 
7. Haga clic en **Intercambiar**. 
8. Haga clic en **Cargar desde un archivo XML**. 
9. Haga clic en **Examinar** y seleccione el archivo **Modelo de comercio exterior.xml**. 
10. Haga clic en **Aceptar**. 
11. Haga clic en **Intercambiar**. 
12. Haga clic en **Cargar desde un archivo XML**. 
13. Haga clic en **Examinar** y seleccione el archivo **Asignación de comercio exterior.xml**. 
14. Haga clic en **Aceptar**. 

## <a name="register-a-connected-application"></a>Registrar una aplicación conectada
1. Cierre la página. 
2. Cierre la página. 
3. Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**. 
4. Haga clic en **Aplicaciones conectadas**. 
5. Asegúrese de que la aplicación configurada se basa en Azure y el usuario actual de RCS puede acceder a ella. También se requiere que el usuario actual de RCS tenga acceso a la aplicación seleccionada y se haya registrado como usuario de esta aplicación con un rol que le dé privilegios para acceder a los metadatos de la aplicación. 
6. Haga clic en **Nuevo**. 
7. En el campo **Nombre**, escriba 'MyConnectedApp'. 
8. En el campo **Aplicación**, escriba 'https:// mycompany.operations.dynamics.com'. 
9. En el campo **Inquilino**, escriba "mycompany.onmicrosoft.com". 
10. Haga clic en **Guardar**. 
11. Cuando compruebe la conexión a la aplicación configurada, en la página **Conectar con aplicación remota**, haga clic en el vínculo **Haga clic aquí para conectarse a la aplicación remota seleccionada**. 
12. Haga clic en **Comprobar conexión**. 
13. Haga clic en **Cerrar**. 
14. Cuando la validación de la conexión fue correcta, se actualizarán los detalles de la versión y del inquilino para la aplicación configurada en la cuadrícula actual. 

## <a name="review-existing-model-mapping-configuration"></a>Revisar configuración de asignación existente del modelo
1. Cierre la página. 
2. Haga clic en **Configuraciones de informes**. 
3. En el árbol, expanda **Modelo de comercio exterior**. 
4. En el árbol, seleccione **Modelo de comercio exterior\Asignación de comercio exterior**. 
5. Expanda la sección **Requisitos previos**. 

    > [!NOTE]
    > Actualmente, esta asignación hace referencia a la configuración de metadatos. Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo. 

6. Haga clic en **Diseñador**. 
7. Haga clic en **Diseñador**. 
8. En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**. 
9. Haga clic en **Agregar raíz**. 
10. En el campo **Tabla**, especifique o seleccione un valor. 

    > [!NOTE]
    > Actualmente, esta asignación hace referencia a la configuración de metadatos. Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo. 

11. Haga clic en **Cancelar**. 
12. Cierre la página. 
13. Cierre la página. 

## <a name="assign-connected-application-to-model-mapping"></a>Asignar aplicación conectada a asignación de modelo 
1. Haga clic en **Editar**. 
2. Seleccione la aplicacón **MyConnectedApp**. 

    > [!NOTE]
    > Actualmente, esta asignación hace referencia a los metadatos de la aplicación conectada seleccionada. Cuando la misma asignación hace referencia a la configuración de metadatos y a la aplicación conectada al mismo tiempo, se utilizarán los metadatos de la aplicación conectada. 

3. Haga clic en **Diseñador**. 
4. Haga clic en **Diseñador**. 
5. En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**. 
6. Haga clic en **Agregar raíz**. 
7. En el campo **Tabla**, especifique o seleccione un valor. 

    > [!NOTE]
    > Se ofrecieron más de dos tablas de la aplicación ya que esta asignación utiliza todos los metadatos de la aplicación conectada que se le ha asignado. 

8. Haga clic en **Cancelar**. 
9. Hacer clic en **Validar**. 

    > [!NOTE]
    > Enlazamos correctamente elementos del modelo de datos con artículos de orígenes de datos que se describen con detalles de metadatos de la aplicación conectada que se ha asignado para esta asignación. 

10. Cierre la página. 
11. Cierre la página. 

Cuando tenga que evaluar esta asignación de modelo mediante el uso de metadatos de una aplicación de versión diferente, registre otra aplicación conectada, asígnela a esta asignación de modelo y valídela con nuevos metadatos.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]