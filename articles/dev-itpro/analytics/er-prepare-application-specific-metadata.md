---
title: Preparar metadatos específicos de la aplicación para RCS y ER
description: En este tema se explica cómo preparar metadatos específicos de la aplicación para Regulatory configuration service (RCS) e informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3a540676ba11bc3c0fb7855a2fdaff998819dfbe
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849694"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a>Preparar metadatos específicos de la aplicación para RCS

[!include[banner](../includes/banner.md)]

Este tema le guía por ejemplos de las siguientes tareas:

- [Preparar metadatos de la aplicación que pueden usarse en RCS](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Acceder a metadatos de la aplicación mediante el uso de una configuración de ER](#access-application-metadata-by-using-an-er-configuration)
- [Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>Preparar metadatos de la aplicación que pueden usarse en RCS

El siguiente procedimiento muestra cómo un usuario de Finance and Operations que tiene en el rol de **Administrador del sistema** o **Desarrollador de informes electrónicos** puede crear una configuración de informes electrónicos (ER) que contenga metadatos para la aplicación de Microsoft Dynamics 365 for Finance and Operations y que se utiliza para diseñar configuraciones de asignación del modelo de ER en Regulatory Configuration Service (RCS). La configuración de asignación del modelo de ER de ejemplo que se crea en este ejemplo se utilizará para acceder a transacciones de comercio exterior.

Para este ejemplo, desea utilizar RCS para diseñar una solución de ER para Finance and Operations que se utilizará para generar documentos electrónicos que contienen información del dominio empresarial de comercio exterior. Para especificar la asignación entre el modelo de datos de ER y los orígenes de datos requeridos, debe tener acceso a los metadatos de la aplicación para Finance and Operations en RCS. Por lo tanto, como parte del proceso de diseñar la solución de ER, debe configurar una nueva configuración de metadatos de ER que contenga todos los metadatos que se requieren actualmente para generar informes de ER para el dominio empresarial seleccionado.

> [!NOTE]
> En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa.

1. Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.
2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete el procedimiento [Creación de un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Seleccione **Configuraciones de metadatos**.
4. Seleccionar **Crear configuración**.
5. En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca un nombre. Para este ejemplo, introduzca **Metadatos de comercio exterior**.
6. Seleccionar **Crear configuración**.
7. Seleccione **Diseñador**.
8. Seleccione **Agregar**.

    > [!NOTE]
    > Puede seleccionar todos los metadatos para toda la aplicación o para modelos o módulos seleccionados. En ambos casos, tenga en cuenta que los siguientes metadatos se agregarán automáticamente: tablas de registros, enumeraciones y tipos de datos extendidos (EDT). Cuando se requieren tipos adicionales de metadatos, deben agregarse manualmente.

Debe agregar algunos metadatos que están relacionados con transacciones de comercio exterior y seleccionar elementos de metadatos manualmente.

9. Seleccione **Agregar origen de datos \> Registros de tabla**.
10. Filtre según un valor de **Intrastat** en el campo **Nombre**.
11. Seleccione el registro de tabla de **Intrastat** .
12. Seleccione **Aceptar**.

Debe agregar información de metadatos sobre la tabla de registros de Intrastat.

13. En el árbol, seleccione **Registros de tabla de Intrastat \> \>Relations \> IntrastatCommodity (Registros de tabla EcoResCategory)**.
14. Seleccione **Agregar metadatos**.

    > [!NOTE]
    > Los metadatos sobre las relaciones necesarias para la tabla de registros seleccionada se deben agregar manualmente.

15. Seleccione **Agregar origen de datos**.
16. Seleccione **Enumeración**.
17. Filtre según un valor de **IntrastatDirection** en el campo **Nombre**.
18. Seleccione el registro de enumeración de **IntrastatDirection**.
19. Seleccione **Aceptar**.
20. Seleccione **Guardar**.
21. Cierre la página.
22. Completar la versión de borrador de la configuración de metadatos:

    1. Seleccione **Cambiar estado\> Completada**.
    2. Seleccione **Aceptar**.
    3. Seleccione la versión completada 1.

23. Exporte la versión completada de la configuración de metadatos desde la aplicación como archivo XML:

    1. Seleccione **Intercambiar \> Exportar como archivo XML**.
    2. Seleccione **Aceptar**.

La configuración de metadatos de ER que creó se guarda como el archivo **Metadatos de comercio exterior.xml** . Ahora puede importarla en RCS para que pueda utilizarse como origen de metadatos para el dominio empresarial de comercio exterior en Finance and Operations. Según esta información, puede especificar la asignación entre los metadatos de la aplicación y el modelo de datos de ER.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Acceder a metadatos de la aplicación mediante el uso de una configuración de ER

El siguiente procedimiento muestra cómo un usuario de RCS que tiene el rol **Administrador del sistema** o de **Desarrollador de informes electrónicos** puede diseñar una nueva asignación del modelo de ER mediante el uso de metadatos desde la aplicación Finance and Operations. Se accederá a los metadatos de la aplicación mediante el uso de una configuración de metadatos de ER que contenga un conjunto de metadatos de ejemplo para acceder a transacciones de comercio exterior.

Para poder completar este procedimiento, primero debe completar los siguientes procedimientos:

- [Creación y activación de un proveedor de configuraciones](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [Preparar metadatos de la aplicación que pueden usarse en RCS](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.
2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete el procedimiento [Creación de un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Importe la configuración de metadatos de ER que contenga metadatos para la aplicación de Finance and Operations, y que esté configurada para generar documentos electrónicos para el dominio empresarial de comercio exterior. Creó esta configuración de metadatos de ER y la exportó como archivo XML en el procedimiento [Preparar metadatos de la aplicación que pueden usarse en RCS](#prepare-application-metadata-that-can-be-used-in-rcs) descrito anteriormente en este tema.

    1. Seleccione **Configuraciones de metadatos**.
    2. Seleccione **Intercambiar**.
    3. Seleccione **Cargar desde un archivo XML**.
    4. Examine para seleccionar el archivo **Metadatos de comercio exterior.xml**.
    5. Seleccione **Aceptar**.
    6. Cierre la página.

4. Cree una configuración de modelo de datos:

    1. Seleccione **Configuraciones de informes**.
    2. Seleccionar **Crear configuración**.
    3. En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Modelo de comercio exterior**.
    4. Seleccionar **Crear configuración**.
    5. Seleccione **Diseñador**.
    6. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.

        1. Escriba **Raíz** en el campo **Nombre**.
        2. Seleccione **Agregar**.
    
    7. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.

        1. En el campo **Nombre**, escriba **Transacción**.
        2. En el campo **Tipo de artículo**, seleccione **Lista de registros**.
        3. Seleccione **Agregar**.
 
    8. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.

        1. En el campo **Nombre**, escriba **Código de mercancía**.
        2. En el campo **Tipo de artículo**, seleccione **Cadena**.
        3. Seleccione **Agregar**.

    9. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.

        1. En el campo Nombre, introduzca **Importe facturado**.
        2. En el campo **Tipo de artículo**, seleccione **Real**.
        3. Seleccione **Agregar**.

    10. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.

        1. En el campo **Nombre**, escriba **Fecha**.
        2. En el campo **Tipo de artículo**, seleccione **Fecha**.
        3. Seleccione **Agregar**.
 
    11. Seleccione **Agregar \> Referencia raíz**.
    12. Seleccione **Aceptar**.
    13. Seleccione **Guardar**.
    14. Cierre la página.
    15. Seleccione **Cambiar estado\> Completada**.
    16. Seleccione **Aceptar**.

5. Cree una configuración de asignación del modelo:

    1. Seleccionar **Crear configuración**.
    2. En el cuadro de diálogo desplegable, en el campo **Nuevo**, introduzca **Asignación de modelo basado en el modelo de datos Modelo de comercio exterior**.
    3. En el campo **Nombre**, introduzca **Asignación de comercio exterior**.
    4. Seleccionar **Crear configuración**.
    5. En la ficha desplegable **Requisitos previos**, seleccione **Editar**.
    6. Seleccione **Nuevo**.
    7. En el campo **Tipo de componente de requisito previo**, seleccione **Configuración**.
    8. Seleccione la configuración **Metadatos de comercio exterior**.
    9. Seleccione **Guardar**. Tenga en cuenta que la referencia se agrega a la versión 1 de la configuración **Metadatos de comercio exterior**. Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña la asignación del modelo.
    10. Cierre la página.
    11. Seleccione **Diseñador**.
    12. Seleccione **Diseñador**.
    13. En el árbol, seleccione **Dynamics 365 for Operations \> Registros de tabla**.
    14. Seleccione **Agregar raíz**.
    15. En el campo **Nombre**, especifique **Intrastat**.
    16. Seleccione el registro de tabla de **Intrastat**.
    17. Seleccione **Aceptar**.

        > [!NOTE]
        > Solo se ofrecen dos tablas, ya que solo se agregaron dos tablas al conjunto de metadatos que se utiliza actualmente.

    18. Seleccione **Enlazar**.
    19. En el árbol, seleccione **Intrastat \> AmountMST**.
    20. En el árbol, seleccione **Transacción = Intrastat \> Importe facturado**.
    21. Seleccione **Enlazar**.
    22. En el árbol, seleccione **Intrastat \> TransDate**.
    23. En el árbol, seleccione **Transacción = Intrastat \> Fecha**.
    24. Seleccione **Enlazar**.
    25. En el árbol, seleccione **Intrastat \> \>Relaciones \> IntrastatCommodity \> Código**.
    26. En el árbol, seleccione **Transacción = Intrastat \> Código de mercancía**.
    27. Seleccione **Enlazar**.
    28. Seleccione **Validar**.

        > [!NOTE]
        > Una vez que se complete la validación, habrá enlazado correctamente los elementos del modelo de datos a los artículos de los orígenes de datos que se describen con detalles de metadatos de la aplicación desde la configuración de metadatos de ER a la que se hace referencia.

    29. Seleccione **Guardar**.

Según necesite, puede ampliar el conjunto de metadatos existente en Finance and Operations. A continuación, puede exportar la nueva versión completada de la configuración de metadatos de ER desde Finance and Operations, importarla en RCS y actualizar los requisitos previos de la configuración de asignación del modelo configurado para hacer referencia a una nueva versión de la configuración de los metadatos importados.

> [!NOTE]
> Este método para obtener información sobre metadatos de la aplicación es el único método disponible para las aplicaciones que se implementan localmente (es decir, cuando se utiliza un modelo de implementación de datos empresariales locales \[LBD\], o en las instalaciones, para Finance and Operations).

## <a name="access-application-metadata-by-using-connected-applications"></a>Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas

El siguiente procedimiento muestra cómo un usuario de RCS que tiene el rol **Administrador del sistema** o de **Desarrollador de informes electrónicos** puede diseñar una nueva asignación del modelo de ER mediante el uso de metadatos de la aplicación Finance and Operations. Se accederá en línea a los metadatos de la aplicación mediante el uso de la aplicación conectada de RCS. Una asignación del modelo de ER de ejemplo se configurará para acceder a transacciones de comercio exterior.

Para completar este procedimiennto, primero debe completar el procedimiento [Creación de un proveedor de configuraciones y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md) en RCS. Si todavía no ha completado el procedimiento [Acceder a metadatos de la aplicación mediante el uso de una configuración de ER](#access-application-metadata-by-using-an-er-configuration) descrito anteriormente en este tema, vaya a la página [Guías de tareas de informes electrónicos para Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) para descargar los siguientes archivos de configuración de ER por adelantado y guardarlos localmente: **Metadatos de comercial exterior.xml**, **Modelo de comercio exterior.xml** y **Asignación de comercio exterior.xml**.


### <a name="get-required-er-configurations"></a>Obtener las configuraciones de ER necesarias

Si ya ha completado el procedimiento [Acceder a metadatos de la aplicación mediante el uso de una configuración de ER](#access-application-metadata-by-using-an-er-configuration) descrito anteriormente en este tema, ya tiene todas las configuraciones de ER necesarias (las configuraciones de metadatos, modelo y asignación de comercio exterior) en la instancia de RCS actual. En ese caso, puede omitir este procedimiento.

1. Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. Cargue los archivos de configuración **Metadatos de comercio exterior.xml**, **Modelo de comercio exterior.xml** y **Asignación de comercio exterior.xml** repitiendo la siguiente cadena de pasos para cada uno de ellos:

    1. Seleccione **Intercambiar**.
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Examinar** y seleccionar un archivo.
    4. Seleccione **Aceptar**.

### <a name="register-the-connection-with-finance-and-operations"></a>Registrar la conexión con Finance and Operations

1. Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.
2. Seleccione **Aplicaciones conectadas**.
3. Asegúrese de que la aplicación configurada se basa en Microsoft Azure y de que los usuarios de RCS pueden acceder a ella. El usuario de RCS actual debe tener acceso a la aplicación configurada registrándose como usuario de esta aplicación en un rol que dé privilegios para acceder a los metadatos de la aplicación.
4. Seleccione **Nuevo**.
5. En el campo **Nombre**, introduzca **MyConnectedApp** como el nombre de la aplicación conectada.
6. En el campo **Aplicación**, especifique la dirección URL de la aplicación.
7. En el campo **Inquilino**, especifique el proveedor de la aplicación.
8. Seleccione **Guardar**. 
9. Cuando compruebe la conexión a la aplicación configurada, en la página **Conectar con aplicación remota**, seleccione el vínculo **Seleccione aquí para conectarse a la aplicación remota seleccionada**. 
10. Seleccione **Comprobar conexión** para validar el acceso a la aplicación configurada.
11. Seleccione **Cerrar**.

Tras completar este procedimiento y la validación de la conexión correctamente, se actualizarán los detalles de la versión y del inquilino para la aplicación configurada en la cuadrícula actual.

### <a name="review-the-existing-model-mapping-configuration"></a>Revisar la configuración de asignación existente del modelo

1. Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. En el árbol, seleccione **Modelo de comercio exterior \> Asignación de comercio exterior**.
4. Seleccione la ficha desplegable **Requisitos previos**.

    > [!NOTE]
    > Actualmente, esta asignación hace referencia a la configuración de metadatos. Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.

4. Seleccione **Diseñador**.
5. Seleccione **Diseñador**.
6. En el árbol, seleccione **Dynamics 365 for Operations \> Registros de tabla**.
7. Seleccione **Agregar raíz**.
8. En el campo **Tabla**, especifique o seleccione un valor.

    > [!NOTE]
    > Actualmente, esta asignación hace referencia a la configuración de metadatos. Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.

9. Seleccione **Cancelar**.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Asignar la aplicación conectada a una asignación de modelo

1. Seleccione **Editar**.
2. En el **campo Aplicación conectada**, seleccione la aplicación **MyConnectedApp** .

    > [!NOTE]
    > Esta asignación hace referencia a los metadatos de la aplicación conectada seleccionada. Si una asignación hace referencia a la configuración de metadatos y a la aplicación conectada al mismo tiempo, se utilizarán los metadatos de la aplicación conectada.

3. Seleccione **Diseñador**.
4. Seleccione **Diseñador**.
5. En el árbol, seleccione **Dynamics 365 for Operations \> Registros de tabla**.
6. Seleccione **Agregar raíz**.
7. En el campo **Tabla**, especifique o seleccione un valor.

    > [!NOTE]
    > En este punto, se ofrecen más de dos tablas de la aplicación ya que esta asignación utiliza todos los metadatos de la aplicación conectada que se le ha asignado.

8. Seleccione **Cancelar**.
9. Seleccione **Validar**.

Ya ha enlazado elementos del modelo de datos con artículos de los orígenes de datos que se describen con detalles de los metadatos de la aplicación conectada que se ha asignado para esta asignación.

Cuando deba evaluar esta asignación de modelo mediante el uso de metadatos de una versión diferente de la aplicación, registre otra aplicación conectada, asígnela a esta asignación de modelo y valídela con los nuevos metadatos.

## <a name="additional-resources"></a>Recursos adicionales

Como alternativa, puede reproducir la guía de tareas **Preparar metadatos de la aplicación que pueden usarse en RCS** en Finance and Operations, así como las guías de tareas **Acceder a metadatos de la aplicación mediante el uso de una configuración de ER** y **Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas** en RCS. Estas guías de tareas se pueden descargar en la página [Guías de tareas de informes electrónicos para Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).
