---
title: Configurar y ejecutar un procesamiento para llamar a un formato ER de exportación simple para generar un informe de Excel
description: Este tema proporciona un ejemplo que muestra cómo configurar y usar mensajes electrónicos.
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c2735df09ecf029503ae96a88a523ea40197da8f
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735010"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Configurar y ejecutar un procesamiento para llamar a un formato ER de exportación simple para generar un informe de Excel

[!include [banner](../includes/banner.md)]

Una vez que haya creado el formato de ER, lo haya asignado a orígenes de datos, y lo haya completado, puede ejecutarlo desde el espacio de trabajo **Informes electrónicos**. Después de que se genera un informe, se puede guardar localmente.

Para controlar los siguientes aspectos del proceso de informes, configure el procesamiento de mensajes electrónicos:

- Registrar información sobre la persona que generó el informe.
- Registrar información sobre cuándo se generó el informe.
- Guardar los informes generados para períodos anteriores.

El ejemplo siguiente muestra cómo puede configurar mensajes electrónicos para generar un informe basado en un formato de ER de exportación para Microsoft Excel. Si quiere seguir este ejemplo, el formato ER de exportación para Excel debe haberse creado, asignado a orígenes de datos, y completado ya. Además, una secuencia numérica se debe haber configurado para los mensajes electrónicos.

Al compilar el procesamiento, resulta útil definir primero las acciones y los estados del proceso que se configurarán. La ilustración siguiente muestra el procesamiento para este ejemplo.

![Esquema de procesamiento](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Crear estados de mensajes

1. Vaya a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Estados de mensaje**.
2. Cree los estados del mensaje siguientes:

    - Nueva
    - Preparado
    - Generadas

    ![Estados de mensaje](media/message-statuses.png)

3. En la línea del estado **Nuevo** , seleccione la casilla de verificación **Permitir la cancelación** para permitir a los usuarios borrar los mensajes que tengan este estado.

## <a name="create-additional-fields"></a>Crear campos adicionales

1. Vaya a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Campos adicionales**.
2. Agregue un campo adicional y sus valores.
3. Establezca la opción **Edición del usuario** en **Sí** para permitir a los usuarios editar el campo.

![Campos adicionales](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Crear acciones de procesamiento de mensajes

Para este ejemplo, creará las siguientes acciones de procesamiento de mensajes:

- **Crear mensaje**
- **Actualizar a preparado**
- **Generar informe**
- **Actualización al estado inicial** (opcional)

Para crear las acciones, siga estos pasos.

1. Vaya a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Acciones de procesamiento de mensajes**.
2. Crear una acción que se llama **Crear el mensaje**. En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Crear el mensaje**.
3. Cree una acción que se llama **Actualizar a preparado**, y establezca los siguientes campos:

    - En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Procesamiento de usuario de nivel de mensaje**.
    - En la ficha desplegable **Estados iniciales** , en el campo **Estado del mensaje** , seleccione **Nuevo**.
    - En la ficha desplegable **Estados de resultado** , en el campo **Estado del mensaje** , seleccione **Preparado**. En el campo **Tipo de respuesta** , especifique **Ejecutado correctamente**.

4. Cree una acción que se llama **Generar informe**, y establezca los siguientes campos:

    - En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Exportación de informes electrónicos**. En el campo **Asignación de formato** , seleccione el formato de ER de exportación. Las opciones son **Excel**, **XML**, **JSON**, **Text**, y **Otros**.
    - En la ficha desplegable **Estados iniciales** , en el campo **Estado del mensaje** , seleccione **Preparado**.
    - En la ficha desplegable **Estados de resultado** , en el campo **Estado del mensaje** , seleccione **Generado**. En el campo **Tipo de respuesta** , especifique **Ejecutado correctamente**.

    ![Generar acción de informe](media/generate-report-action.png)

5. Opcional: Para que los usuarios puedan volver a generar un informe varias veces, puede crear una acción llamada **Actualización a estado inicial** y establecer los campos siguientes:

    - En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Procesamiento de usuario de nivel de mensaje**.
    - En la ficha desplegable **Estados iniciales** , en el campo **Estado del mensaje** , seleccione **Generado**.
    - En la ficha desplegable **Estados de resultado**, agregue una línea independiente para cada uno de los dos estados del mensaje (**Preparado** y **Nuevo**). Para las dos líneas, establezca el campo **Tipo de respuesta** en **Ejecutado correctamente**.

## <a name="electronic-message-processing"></a>Procesamiento de mensaje electrónico

En este ejemplo, todas las acciones deben configurarse para que ejecuten por separado. Se presupone que cada acción será inicializada por el usuario.

1. Vaya a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Procesamiento de mensaje electrónico**.
2. Agregue un registro para su procesamiento, y agregue todas las acciones definidas previamente y un campo adicional.
3. Opcional: en la ficha desplegable **Roles de seguridad** , defina los roles de seguridad para que su procesamiento limite el acceso al informe específico.
4. Vaya a **Impuestos** \> **Consultas e informes** \> **Mensajes electrónicos** \> **Mensajes electrónicos**.
5. Seleccione **Nuevo** para crear un mensaje. En este punto, puede agregar fechas y una descripción. También puede actualizar el valor del campo adicional como sea necesario.

    ![Crear un mensaje electrónico](media/create-electronic-message.png)

    La cuadrícula de la ficha desplegable **Registro de acción** se completa automáticamente con un registro de todas las acciones que se realizan en el mensaje.

    Ahora puede eliminar o actualizar el estado del mensaje. 

6. Para actualizar el estado del mensaje, seleccione **Actualizar estado**. En el campo **Nuevo estado** , seleccione **Preparado**, y después seleccione **Aceptar**.

    ![Actualizar el estado del mensaje](media/update-status.png)

    El estado del mensaje se actualiza a **Preparado**.

7. Genere el informe seleccionando **Generar informe**.

    Se genera el informe, y el estado del mensaje y el registro de acción se actualizan.

8. Para ver el informe generado, seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
