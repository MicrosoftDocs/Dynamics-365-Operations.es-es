---
title: Importar archivos en formato XML con atributos opcionales
description: En este tema se proporciona información sobre el diseño de formatos de ER que especifican atributos XML para analizar documentos electrónicos entrantes en formato XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 10795c90cb90961c17a4326b71ed43dc72039f2b
ms.sourcegitcommit: 66eae22cd99e53fe8e4c6c94945ad8061b69a442
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "3117434"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a>Importar archivos en formato XML con atributos opcionales

[!include [banner](../includes/banner.md)]

Puede diseñar formatos de informes electrónicos (ER) para analizar documentos electrónicos entrantes en formato XML. Algunos atributos de elementos XML se pueden especificar en formato de ER diseñados como opcionales. Le permitirá gestionar correctamente archivos entrantes con y sin estos atributos XML. Puede usar el contenido de estos archivos para actualizar datos de la aplicación.

Para obtener más información acerca de esta característica, complete los pasos del tema [(RCS) Importar archivos en formato XML con atributos opcionales](tasks/import-files-xml-format-optional-attributes.md), que forma parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de soluciones/servicios de TI (10677). Puede descargar esta guía de tareas y los archivos de ejemplo asociados desde el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).


| Descripción del contenido       | Archivo                                                         |
|---------------------------|--------------------------------------------------------------|
| Archivo de ejemplo en formato XML | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml     |
| Guía de tareas                | RCS Importar archivos en formato XML con atributos opcionales.axtr |


En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una configuración de formato de ER para importar archivos en formato XML que contengan atributos opcionales. Para completar estos pasos, primero debe completar los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md). Antes de empezar, descargue y guarde localmente el archivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml del Centro de descarga de Microsoft (https://go.microsoft.com/fwlink/?linkid=874684).

1. Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**.
2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete los pasos del tema [Crear proveedores de configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Haga clic en **Configuraciones de informes**.

## <a name="create-a-new-data-model-configuration"></a>Creación de un nuevo modelo de configuración de datos
1. Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.
2. En el campo **Nombre**, escriba 'Modelo para importar el archivo xml'.
3. Haga clic en **Crear configuración**.
4. Haga clic en **Diseñador**.
5. Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.
6. Escriba 'Raíz' en el campo **Nombre**.
7. Haga clic en **Agregar**.
8. Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.
9. Escriba 'Lista' en el campo **Nombre**.
10.    En el campo **Tipo de artículo**, seleccione **Lista de registros**.
11.    Haga clic en **Agregar**.
12.    Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.
13.    En el campo **Nombre**, escriba 'Código'.
14.    En el campo **Tipo de artículo**, seleccione **Cadena**.
15.    Haga clic en **Agregar**.
16.    Haga clic en **Guardar**.
17.    Cierre la página.
18.    Haga clic en **Cambiar estado**.
19.    Haga clic en **Completar**.
20.    Haga clic en **Aceptar**.

## <a name="create-a-format-for-data-import"></a>Crear un formato para la importación de datos
1. Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.
2. En el campo **Nuevo**, introduzca 'Formato basado en el modelo de datos del archivo Modelo para importar.xml'.
3. En el campo **Nombre**, escriba 'Formato para importar el archivo xml'. 
4. Seleccione **Sí** en el campo **Admite la importación de datos**.
5. Haga clic en **Crear configuración**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Diseñar un formato para analizar el archivo de entrada en formato xml
1. Haga clic en **Diseñador**.
2. Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.
3. En el árbol, seleccione **XML\Elemento**.
4. Escriba 'raíz' en el campo **Nombre**.
5. Haga clic en **Aceptar**.
6. Haga clic en **Agregar** para abrir el cuadro desplegable.
7. En el árbol, seleccione **XML\Elemento**.
8. En el campo **Nombre**, introduzca 'documento'.
9. En el campo de **Multiplicidad**, seleccione **Uno o varios**.
10.    Haga clic en **Aceptar**.
11.    En el árbol, seleccione **root\document**.
12.    Haga clic en **Agregar** para abrir el cuadro desplegable.
13.    En el árbol, seleccione **XML\Atributo**.
14.    En el campo **Nombre**, escriba 'id'.
15.    Haga clic en **Aceptar**.
16.    Haga clic en **Guardar**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Diseñar una asignación de formato para guardar la información analizada al modelo de datos
1.    Haga clic en **Asignar formato a modelo**.
2.    Haga clic en **Nuevo**.
3.    En el campo **Definición**, especifique o seleccione un valor.
4.    En el campo **Nombre**, introduzca 'Asignación'.
5.    Haga clic en **Guardar**.
6.    Haga clic en **Diseñador**.
7.    En el árbol, expanda **format**.
8.    En el árbol, expanda **format\root: XML Element(root)**.
9.    En el árbol, seleccione **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
10.    Haga clic en **Enlazar**.
11.    En el árbol, expanda **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
12.    En el árbol, seleccione **format\root: XML Element(root)\document: XML Element 1..* (documento)\id**.
13.    En el árbol, expanda **List = format.root.document**.
14.    En el árbol, seleccione **List = format.root.document\Code**.
15.    Haga clic en **Enlazar**.
16.    Haga clic en **Guardar**.
17.    Cierre la página.

## <a name="run-format-mapping"></a>Ejecutar asignación de formato
1. Haga clic en **Ejecutar**.
2. Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Haga clic en **Aceptar**.

> [!NOTE]
> El archivo seleccionado no se ha importado ya que el diseño de formato asume la existencia de atributo ‘id’ para el elemento ‘document’, pero el archivo importado no contiene tal atributo.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modificar la estructura del formato para gestionar el atributo xml como opcional
1. Cierre la página.
2. En el árbol, expanda **root\document**.
3. En el árbol, seleccione **root\document\id**.
4. En el campo **Cadena vacía para el atributo que falta**, selección **Sí**.
5. Haga clic en **Guardar**.

## <a name="run-format-mapping-to-test-changes"></a>Ejecutar asignación de formato para cambios de prueba
1. Haga clic en **Asignar formato a modelo**.
2. Haga clic en **Ejecutar**.
3. Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Haga clic en **Aceptar**.
5. Revise el archivo generado. Tenga en cuenta que se ha importado el mismo archivo ya que el diseño de formato ahora considera el atributo ‘id’ para el elemento ‘documento‘ como opcional.
