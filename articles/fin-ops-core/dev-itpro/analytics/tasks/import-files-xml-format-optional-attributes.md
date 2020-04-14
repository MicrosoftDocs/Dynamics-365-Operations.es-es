---
title: (RCS) Importar archivos en formato XML con atributos opcionales
description: En este tema se proporciona información acerca de cómo un usuario puede diseñar la configuración del formato de ER para importar archivos en formato XML que contenga atributos opcionales.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc28e9a2170929c6cd8daafd7eae54713cec36ff
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143209"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) Importar archivos en formato XML con atributos opcionales

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una configuración de formato de ER para importar archivos en formato XML que contengan atributos opcionales. Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones". Antes de empezar, descargue y guarde localmente el archivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

1.    Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.
2.    Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).
3.    Haga clic en **Configuraciones de informes**.

## <a name="create-a-new-data-model-configuration"></a>Creación de un nuevo modelo de configuración de datos
1.    Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.
2.    En el campo **Nombre**, escriba 'Modelo para importar el archivo xml'.
3.    Haga clic en **Crear configuración**.
4.    Haga clic en **Diseñador**.
5.    Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.
6.    Escriba 'Raíz' en el campo **Nombre**.
7.    Haga clic en **Agregar**.
8.    Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.
9.    Escriba 'Lista' en el campo **Nombre**.
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
1.    Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.
2.    En el campo **Nuevo**, introduzca 'Formato basado en el modelo de datos del archivo Modelo para importar.xml'.
3.    En el campo **Nombre**, escriba 'Formato para importar el archivo xml'.
4.    Seleccione **Sí** en el campo **Admite la importación de datos**.
5.    Haga clic en **Crear configuración**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Diseñar un formato para analizar el archivo de entrada en formato xml
1.    Haga clic en **Diseñador**.
2.    Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.
3.    En el árbol, seleccione **XML\Elemento**.
4.    Escriba 'raíz' en el campo **Nombre**.
5.    Haga clic en **Aceptar**.
6.    Haga clic en **Agregar** para abrir el cuadro desplegable.
7.    En el árbol, seleccione **XML\Elemento**.
8.    En el campo **Nombre**, introduzca 'documento'.
9.    En el campo de **Multiplicidad**, seleccione **Uno o varios**.
10.    Haga clic en **Aceptar**.
11.    En el árbol, seleccione **root\document**.
12.    Haga clic en **Agregar** para abrir el cuadro desplegable.
13.    En el árbol, seleccione **XML\Atributo**.
14.    En el campo **Nombre**, escriba 'ID'.
15.    Haga clic en **Aceptar**.
16.    Haga clic en **Guardar**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Diseñar una asignación de formato para guardar la información analizada al modelo de datos
1. Haga clic en **Asignar formato a modelo**.
2. Haga clic en **Nuevo**.
3. En el campo **Definición**, especifique o seleccione un valor.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo **Nombre**, introduzca 'Asignación'.
6. Haga clic en **Guardar**.
7. Haga clic en **Diseñador**.
8. En el árbol, expanda **format**.
9. En el árbol, expanda **format\root: XML Element(root)**.
10.    En el árbol, seleccione **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
11.    Haga clic en **Enlazar**.
12.    En el árbol, expanda **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
13.    En el árbol, seleccione **format\root: XML Element(root)\document: XML Element 1..* (documento)\id**.
14.    En el árbol, expanda **List = format.root.document**.
15.    En el árbol, seleccione **List = format.root.document\Code**.
16.    Haga clic en **Enlazar**.
17.    Haga clic en **Guardar**.
18.    Cierre la página.
 
## <a name="run-format-mapping"></a>Ejecutar asignación de formato
1. Haga clic en **Ejecutar**.
2. Haga clic en **Examinar** y seleccione **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Haga clic en **Aceptar**.

> [!NOTE]
> El archivo seleccionado no se ha importado ya que el diseño de formato asume la existencia de atributo ‘id’ para el elemento ‘document’, pero el archivo importado no contiene tal atributo.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modificar la estructura del formato para gestionar el atributo xml como opcional
1. Cierre la página.
2. En el árbol, expanda **root\document**.
3. En el árbol, seleccione **root\document\id**.
4. Seleccione **Sí** en el campo **Cadena vacía para el atributo que falta** .
5. Haga clic en **Guardar**.
 
## <a name="run-format-mapping-to-test-changes"></a>Ejecutar asignación de formato para cambios de prueba
1. Haga clic en **Asignar formato a modelo**.
2. Haga clic en **Ejecutar**.
3. Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Haga clic en **Aceptar**.
5. Revise el archivo generado. 

> [!NOTE]
> Se ha importado el mismo archivo ya que el diseño de formato ahora considera el atributo "id" para el elemento "documento" como opcional.
