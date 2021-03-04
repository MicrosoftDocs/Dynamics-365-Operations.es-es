---
title: Grabador de tareas y ayuda para Retail Modern POS (MPOS) y Cloud POS
description: Este tema describe cómo utilizar el Grabador de tareas en Retail Modern POS y Cloud POS.
author: mugunthanm
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, SystemParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0ab8456d81fbe2dca495b65b932395572242a25c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415596"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a>Grabador de tareas y ayuda para Retail Modern POS (MPOS) y Cloud POS

[!include [banner](includes/banner.md)]

Este tema describe cómo utilizar el Grabador de tareas en Retail Modern POS y Cloud POS.

## <a name="overview"></a>Información general

El Grabador de tareas en Retail Modern POS o Cloud POS en la nube de venta minorista es una nueva solución centrada en la alta capacidad de respuesta. Ofrece una interfaz de programación de aplicaciones (API) flexible para la extensibilidad y la integración sin problemas con los consumidores de grabaciones de procesos empresariales. Además, se ha presentado la integración del Grabador de tareas con la herramienta del Modelador de procesos empresariales (BPM) de Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)). Por lo tanto, los usuarios pueden seguir generando diagramas de procesos empresariales enriquecidos a partir de grabaciones para analizar y diseñar sus aplicaciones.

## <a name="architecture"></a>Arquitectura

El Grabador de tareas puede registrar las acciones del usuario en el cliente con fidelidad exacta. Cada control está instrumentado para notificar al Grabador de tareas la ejecución de una acción de usuario. El control notifica el Grabador de tareas que se ha producido un evento y le pasa toda la información pertinente sobre la acción de usuario en tiempo real. A partir de esta información, el Grabador de tareas puede determinar el tipo de acción de usuario (como un clic en un botón, la especificación de un valor o una acción de navegación) y de los datos relacionados con la acción del usuario (como el valor y el tipo de los datos especificados, el contexto del formulario o el contexto de grabación). El Grabador de tareas conserva la información con suficiente detalle para garantizar que una reproducción de la grabación puede realizar las acciones grabadas exactamente igual que las realizadas por el usuario. (La función de reproducción aún no está implementada para Retail Modern POS o el Cloud POS)

## <a name="basic-configuration"></a>Configuración básica

Para habilitar la grabación de tareas en el PDV, siga estos pasos.

1. Haga clic en **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Registros**.
2. Haga clic en el registro para habilitar en él la grabación de tareas.
3. En la pestaña **Registro**, en la ficha desplegable **General**, establezca la opción **Habilitar grabación de tareas** en **Sí**.
4. Haga clic en **Guardar**.
5. Vaya a **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programación de distribución**.
6. Seleccione el trabajo **Registros (1090)** y haga clic en el botón **Ejecutar ahora**.

## <a name="create-a-recording"></a>Crear una grabación

Siga estos pasos para crear una nueva grabación con el Grabador de tareas.

1. Inicie Retail Modern POS o Cloud POS e inicie sesión.
2. En la página **Configuración** , en la sección **Grabador de tareas** , haga click en **Abrir grabador de tareas**. Aparece el panel **Grabador de tareas**. Puede hacer clic en el botón **Cerrar** (**X**) en la esquina superior derecha para cerrar el panel **Grabador de tareas** antes de iniciar una nueva grabación. Para volver a abrir el panel, repita el paso 2.

    [![Panel Gabrador de tareas](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)

3. Escriba un nombre y una descripción para la grabación y, a continuación, haga clic en **Iniciar**. La sesión de grabación comenzará en cuanto haga clic en **Iniciar**.

    > [!NOTE]
    > Si hace clic en el botón **Cerrar** (**X**) en la esquina superior derecha mientras hay una grabación en curso, se cerrará el panel **Grabador de tareas**, pero la sesión de grabación no finaliza. Para volver a abrir el panel Grabador de tareas, haga clic en el botón de **Ayuda** (signo de interrogación) situado en la parte superior de la pantalla.
    >
    > [![Signo de interrogación](./media/help.jpg)](./media/help.jpg)

4. Tras hacer clic en **Iniciar**, el Grabador de tareas pasa a modo de grabación. El panel **Grabador de tareas** muestra la información y los controles relacionados con el proceso de grabación.
5. Realice acciones que desea realizar a través de la interfaz de usuario (IU) de Retail Modern POS o Cloud POS.
6. Para finalizar la sesión de grabación, haga clic en **Detener**.

## <a name="download-options"></a>Opciones de descarga

Cuando finalice una sesión de grabación verá varias opciones que le permitirán descargar la grabación.

[![Opciones de descarga](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)

### <a name="save-to-this-pc"></a>Descargar el paquete de grabación de tareas

Puede usar el paquete de grabación para reproducir una Guía de tareas, mantener la grabación o editar las anotaciones de la grabación. (Esta función aún no está implementada en Retail Modern POS y Cloud POS).

### <a name="export-as-word-document"></a>Descargar el documento Word de la grabación

Puede guardar la grabación como un documento de Microsoft Word. El documento contendrá los pasos grabados y las capturas de pantalla realizadas.

### <a name="save-as-developer-recording"></a>Descargar archivo de grabación sin procesar

El archivo de grabación sin procesar es útil para escenarios de desarrollo, como la generación de código de prueba. (Esta característica aún no se ha implementado).

## <a name="recording-controls"></a>Controles de grabación

[![Controles de grabación](./media/controls.jpg)](./media/controls.jpg)

### <a name="stop"></a>Detener

Haga clic en **Detener** para finalizar la sesión de grabación. Tenga en cuenta que no puede reiniciar una sesión finalizada. Por lo tanto, debe asegurarse de haber completado la grabación antes de finalizarla.

### <a name="pause"></a>Pausa

Haga click en **Pausa** para detener (pausar) temporalmente la sesión de grabación y continuar con la operación. Los pasos que realice tras hacer clic en **Pausa** no se graban.

### <a name="continue"></a>Continuar

Para reanudar la sesión de grabación tras una pausa, haga clic en **Continuar**.

### <a name="capture-screenshots"></a>Capturar pantallas

El Grabador de tareas puede realizar capturas de pantalla de la interfaz de usuario de Retail Modern POS durante la grabación de un proceso empresarial. Para activar la característica de captura de pantalla, establezca la opción **Capturar pantalla** en **Sí** y a continuación realice el registro. Una vez que el registro se complete, haga click en **Detener** y descargue el documento de Word. El documento contendrá los pasos con capturas de pantalla relevantes.

> [!NOTE]
> La funcionalidad de captura de pantalla no se ofrece en Cloud POS.

### <a name="start-task-and-end-task"></a>Iniciar tarea y finalizar tarea

Puede especificar el principio y el final de un conjunto de pasos agrupados mediante los botones **Iniciar tarea** y **Finalizar** **tarea** . Haga clic en **Iniciar tarea** “para agregar un paso de "Iniciar tarea" y después siga los pasos que se deben incluir en el grupo. Una vez que haya terminado de realizar los pasos para el grupo, haga clic en **Finalizar tarea**. Las tareas le ayudan a organizar sus procedimientos. Puede anidar tareas dentro de otras tareas. De esta manera, puede organizar mejor los procesos empresariales largos y complejos.

## <a name="adding-annotations"></a>Agregar anotaciones

Una anotación es texto adicional que se agrega a un paso de una grabación. Por ejemplo, puede usar anotaciones para proporcionar al usuario más contexto o instrucciones. Puede agregar anotaciones antes o después de un paso. Puede agregar una anotación a cualquier paso haciendo clic en el botón **Editar** (símbolo de lápiz) situado a la derecha del paso.

[![Botón Editar para un paso](./media/annotate.jpg)](./media/annotate.jpg)

### <a name="texts-and-notes"></a>Textos y notas

Puede utilizar los campos **Textos** y **Notas** para agregar texto que se debe asociar a un paso de una Guía de tareas.

[![Campos Textos y Notas](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)

#### <a name="text"></a>Texto

El texto que especifica en el campo **Texto** aparecerá *por encima* el texto del paso en la Guía de tareas. Esta ubicación es adecuada para el texto que desea que el usuario lea antes de completar el paso.

#### <a name="notes"></a>Notas

El texto que especifique en el campo **Notas** aparecerá *por debajo* del texto del paso en la Guía de tareas. Para leer el texto de la nota, el usuario debe expandir el texto del paso en la ventana emergente. Esta ubicación es adecuada para el material de lectura opcional u otra información que puede ser útil para el usuario, pero que el usuario no necesita para completar la acción.

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a>Ayuda en Retail Modern POS y Cloud POS

Para mostrar sus propias grabaciones de tareas personalizadas en el panel de la Ayuda de Retail Modern POS y Cloud POS para que se puedan reproducir como guías de tareas o ver como texto, debe guardar sus grabaciones de tareas en su propia biblioteca de BPM y después actualizar los parámetros del sistema de Ayuda para que señalen a la biblioteca de BPM. Para obtener más información, consulte [Conexión con el sistema de Ayuda](../fin-and-ops/get-started/help-connect.md). La Ayuda de Retail Modern POS y Cloud POS realiza búsquedas en tiempo real en LCS. Busca en todas las bibliotecas de BPM seleccionadas en los parámetros del sistema de Ayuda de Commerce y muestra los resultados relevantes. Para acceder al menú **Ayuda**, haga clic en el botón **Ayuda** (signo de interrogación) en la parte superior de la pantalla. A continuación, escriba en el cuadro de búsqueda el nombre del proceso y haga clic en el botón de búsqueda.

[![Botón Ayuda](./media/help.jpg)](./media/help.jpg)

Al hacer clic en una Guía de tareas en los resultados de la búsqueda verá los pasos como un tema de Ayuda. También puede exportar los pasos a un documento de Word.

> [!NOTE]
> La Ayuda en Retail Modern POS y Cloud POS no mostrará las guías de tareas según el formulario en el que se encuentre o la operación que esté haciendo. Tiene que escribir el nombre del proceso en el cuadro de búsqueda y después hacer click en **Buscar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]