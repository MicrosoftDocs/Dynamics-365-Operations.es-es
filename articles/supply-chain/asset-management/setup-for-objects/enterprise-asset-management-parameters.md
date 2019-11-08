---
title: Parámetros de administración de activos
description: En Gestión de activos, se deben configurar los parámetros generales relativos a los activos y los pedidos de trabajo, y la programación de órdenes de trabajo.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3ccbb7eed643abf613f8b75ae78854246d20f6d
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569892"
---
# <a name="asset-management-parameters"></a>Parámetros de administración de activos

[!include [banner](../../includes/banner.md)]

 

En Gestión de activos, se deben configurar los parámetros generales relativos a los activos y los pedidos de trabajo, y la programación de órdenes de trabajo. En este tema se explica cómo configurarlos. Seleccione **Administración de activos** > **Configuración** > **Parámetros de administración de activos** para abrir el formulario.

El botón del asistente **Crear datos** se puede usar para crear automáticamente los datos de configuración a modo de prueba o demostración en una empresa en Dynamics 365 Supply Chain Management. Consulte la documentación “Configurar datos de prueba en Administración de activos” para obtener información acerca de cómo utilizar el asistente.

Vínculo **Activos**

- **Ubicación funcional predeterminada** es la ubicación funcional estándar, que se selecciona automáticamente en los activos al crear nuevos activos.  
- En el campo **Calendario estándar**, seleccione un calendario que se utilizará para calcular los KPI de activos, en caso de que no se seleccione ningún recurso en un activo.  
- En el campo **Ver**, seleccione la vista estándar que se muestra al abrir el formulario **Vista de activo** (**Administración de activos** > **Común** > **Activos** > **Vista de activo**).
- **Tipo de solicitud predeterminado** es el tipo de solicitud de mantenimiento estándar, que se activa automáticamente al crear una nueva solicitud.  
- Si desea crear proyectos relacionados con activos, las relaciones de proyecto en relación con la selección de **Proyecto principal**, **Jerarquía de proyectos** y la opción para **Crear proyectos automáticamente** se configuran en **Parámetros de administración de activos**.  
- En el campo **Máscara de proyecto de orden de trabajo** se define el número de proyectos secundarios permitidos para las órdenes de trabajo y los subactivos. Una máscara de orden de trabajo se usa para definir cuántas órdenes de trabajo se pueden crear en un activo y usar en el proyecto de trabajo relacionado de la orden de trabajo. La máscara de orden de trabajo se configura en el campo **Máscara relacionada de orden de trabajo** en los **Parámetros de administración de activos** (**Administración de activos** > **Configuración** > **Parámetros de administración de activos** > **Órdenes de trabajo**).  
>[!NOTE]
>El formato de una máscara de orden de trabajo relacionada es de varios signos #, en función del número máximo de órdenes de trabajo que se espera crear en un activo. Ejemplo: ## permite crear hasta 99 subproyectos.  
- Las previsiones de tipos de trabajo se almacenan en el proyecto seleccionado en el campo **Proyecto de previsión**. Para cada tipo de trabajo, se crea una nueva actividad automáticamente en el proyecto de previsión. Las previsiones del tipo de trabajo se guardan en el proyecto de previsión.  
- En el campo **Modelo**, seleccione el modelo de previsión usado en previsiones de tipo de trabajo y orden de trabajo.  


Vínculo **Órdenes de trabajo**

- **Tipo de orden de trabajo predeterminado** define la configuración estándar al crear una orden de trabajo.  
- **Tipo de orden de trabajo preventivo** define el tipo de orden de trabajo usado al crear órdenes de trabajo a partir de planes de mantenimiento. Si este campo se deja en blanco, se usa el tipo de orden de trabajo en el campo **Tipo de orden de trabajo predeterminado** .  
- En el campo **Máscara de orden de trabajo relacionada**, deberá definir el máximo número de órdenes de trabajo que pueden estar relacionadas con una orden de trabajo. Ejemplo: ## permite tener hasta 99 órdenes de trabajo relacionadas. Si define una máscara como se describe aquí, las órdenes de trabajo relacionadas se numeran [identificador de la orden de trabajo con la que está relacionada una orden de trabajo] -01, -02, -03, y así sucesivamente. Si no define una máscara en este campo, una orden de trabajo relacionada obtendrá el identificador secuencial siguiente.  
- Seleccione "Sí" en el botón de alternar **Copiar errores** si desea copiar automáticamente los errores registrados en las órdenes de trabajo con solicitudes de mantenimiento relacionadas.  
- En el campo **Nivel**, defina el nivel de la ubicación técnica que se inserta automáticamente en una orden de trabajo si todos los trabajos relacionados de la orden de trabajo hacen referencia a la misma ubicación. Si no todos los trabajos de la orden de trabajo están relacionados con la misma ubicación técnica en el nivel definido, el campo **Ubicación funcional** se deja en blanco en la orden de trabajo. Ejemplo: Si especifica el número "1"en este campo, este es el nivel superior de una estructura de ubicación técnica. Si especifica el número "0" en este campo, no ha definido un nivel de ubicación funcional específico, solo que todos los trabajos de la orden de trabajo deben estar relacionados con la misma ubicación técnica para que dicha ubicación se agregue a la orden de trabajo.  
- Los diarios utilizados al registrar el consumo en una orden de trabajo se pueden seleccionar en el FastTab **General** de los campos **Hora**, **Artículo** y **Gasto**.  
- En el campo **Origen de idioma del producto**, seleccione el idioma que se va a usar para los nombres de producto en los informes de Administración de activos. Puede seleccionar la configuración de idioma en la cuenta de empresa, o la configuración de idioma para el usuario que haya iniciado sesión actualmente.  
- Seleccione "Sí" en el botón de alternar **Actualización en tiempo real** si desea actualizar automáticamente los cambios en los valores predeterminados del tipo de trabajo, los planes de mantenimiento y las rondas mantenimiento.
> - Si selecciona ”No”, los cambios en los valores predeterminados de tipo de trabajo, planes de mantenimiento y rondas de mantenimiento no se actualizan automáticamente en Administración de activos  
> - Seleccione ”No” en el botón de alternar si tiene una gran cantidad de datos que se sincronizan, por ejemplo, varios activos o ubicaciones funcionales en planes de mantenimiento o rondas de mantenimiento, o un gran número de planes o rondas de mantenimiento.  
> - Si realiza cambios en los valores predeterminados del tipo de trabajo o los planes de mantenimiento o las rondas de mantenimiento y ha activado ”No” para la actualización en tiempo real, puede que no se muestre una advertencia si los cambios afectan a:
>   - las ubicaciones funcionales configuradas en los planes o las rondas de mantenimiento  
>   - los objetos configurados en los planes o las rondas de mantenimiento  
>   - la configuración de los planes de mantenimiento  
>   - la configurcación de las rondas de mantenimiento  
- En el FastTab **Categoría** , se pueden definir las categorías predeterminadas relativas al consumo en las órdenes de trabajo.  


Vínculo **Programación de órdenes de trabajo**

- **Límite de tiempo de programación** define el período en días, calculado a partir de la fecha de inicio esperada de la orden de trabajo, durante el cual se planifican los trabajos de la orden de trabajo.  
- **Plan maestro** está relacionado con los recursos del módulo **Administración de la organización**. Si selecciona un plan maestro en este campo, puede ver las reservas de capacidades relacionadas con las órdenes de trabajo en **Reservas de capacidad** (**Administración de la organización** > **Recursos** > **Recursos** > seleccionar el recurso > pestaña **Recurso** > botón **Reservas de capacidad**). Si deja el campo en blanco, podrá ver la carga de capacidad relacionada con las órdenes de trabajo en **Carga de capacidad** (**Administración de la organización** \> **Recursos** \> **Recursos** \> seleccionar el recurso \> pestaña **Recurso** \> botón **Carga de capacidad**).  

>[!NOTE]
>La selección en relación con el uso de un plan maestro o no en el módulo **Administración de activos** y el formulario relacionado utilizado para obtener una visión general de las reservas de capacidad o de la carga de capacidad es la configuración estándar. En función de la configuración del campo **Plan maestro**, podrá tener acceso a la información de capacidad en **Reservas de capacidad** o **Carga de capacidad** en el módulo **Administración de la organización**. No es posible crear una configuración en la que las reservas de capacidad se muestren en ambas vistas.  

Los campos que se describen en la lista de abajo están relacionados con las puntuaciones que se usan para calcular la prioridad de la orden de trabajo durante la programación de órdenes de trabajo.

- **Prioridad**: puntuación calculada junto con la puntuación de los campos **Importancia** y **Fecha de inicio**. El número de este campo se divide entre el número del campo **Prioridad** en una orden de trabajo. Ejemplo: Si el valor "5.00 "se inserta en este campo y una orden de trabajo tiene prioridad "20", la puntuación de la calificación de prioridad es de 0.25.  
- **Importancia**: puntuación calculada junto con la puntuación de los campos **Prioridad** y **Fecha de inicio**. El número de este campo se multiplica por el número del campo **Importancia** en una orden de trabajo. Ejemplo: Si el valor "10.00 "se inserta en este campo y una orden de trabajo tiene importancia "5", la puntuación de la calificación de importancia es de 50.  
- **Fecha de inicio**: puntuación calculada junto con la puntuación de los campos **Prioridad** e **Importancia**. Este campo indica la puntuación diaria como valor negativo y se compara con el campo **Inicio esperado** en una orden de trabajo. Ejemplo: Si el valor "10.00"se inserta en este campo y la fecha de inicio esperada de una orden de trabajo es de tres días a partir de ahora, el resultado de la puntuación es menos 30.00. La suma de los resultados 0.25 y 50 de los ejemplos de los campos **Prioridad** e **Importancia** descritos antes proporciona un total de más 20.25. Ese número se compara con el resto de puntuaciones de órdenes de trabajo durante la programación de órdenes de trabajo y las puntuaciones más altas se planifican primero.  
- **Trabajador responsable**: puntuación que se calcula junto con los valores de **Grupo de trabajadores responsables**, **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**. Si el valor "50.00"se inserta en este campo y se ha seleccionado un trabajador responsable en una orden de trabajo, el trabajador obtiene 50 puntos en el cálculo total durante la programación de órdenes de trabajo.  
- **Grupo de trabajadores responsables**: puntuación que se calcula junto con los valores de **Trabajador responsable**, **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**. Si el valor "50.00"se inserta en este campo y se ha seleccionado un trabajador responsable en una orden de trabajo, el trabajador obtiene 50 puntos en el cálculo total durante la programación de órdenes de trabajo.  
- El botón de alternar Sí/No de **Límite de responsables** limita el número de trabajadores disponibles para la programación de la orden de trabajo. Seleccione “No” si no desea calcular una puntuación para todos los trabajadores, sin importar si se configuran como trabajadores responsables o como parte de un grupo de trabajadores responsables. Seleccione "Sí" si desea calcular una puntuación para los trabajadores que hayan sido configurados como trabajador responsable en la orden de trabajo y/o estén incluidos en un grupo de trabajadores responsables seleccionado en la orden de trabajo.  
- **Trabajador preferido**: puntuación que se calcula junto con los valores de **Trabajador responsable**, **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**. Las cuatro puntuaciones que calculan y suman para proporcionar la puntuación utilizada para seleccionar qué trabajador debe estar asignado a la orden de trabajo durante la programación de órdenes de trabajo. Si el valor "10.00"se inserta en este campo y se ha seleccionado un trabajador como preferido en una orden de trabajo, ese trabajador obtiene 10 puntos en el cálculo total durante la programación de órdenes de trabajo.  
- **Grupo de trabajadores preferidos**: puntuación que se calcula junto con los valores de **Trabajador responsable**, **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**. Si el valor "10.00"se inserta en este campo y se ha asignado un trabajador a un grupo de trabajadores preferidos en una orden de trabajo, ese trabajador obtiene 10 puntos en el cálculo total durante la programación de órdenes de trabajo.  
- El botón de alternar Sí/No de **Límite de preferidos** limita el número de trabajadores disponibles para la programación de la orden de trabajo. Seleccione “No” si no desea calcular una puntuación para todos los trabajadores, sin importar si se configuran como trabajadores preferidos o como parte de un grupo de trabajadores preferidos. Seleccione "Sí" si solo desea calcular una puntuación para los trabajadores configurados como trabajadores preferidos y/o incluidos en un grupo de trabajadores preferidos.  
- **Ubicación**: puntuación que se calcula junto con los valores de **Trabajador responsable**, **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**. Si el valor "3000.00 "se inserta en este campo, el trabajador obtiene 3000 puntos en el cálculo si el trabajador se encuentra en la fábrica o las instalaciones del activo para el que se va a programar un trabajo.  

  - Si su empresa usa ubicaciones funcionales, los trabajadores obtienen la puntuación completa si se encuentran en la ubicación funcional relacionada con el activo. Si la ubicación funcional del activo tiene un activo principal, los trabajadores en esa ubicación funcional obtienen media puntuación. Si dicha ubicación también tiene un elemento principal, los trabajadores de dicha ubicación obtienen un tercio de la puntuación. Si dicha ubicación también tiene un elemento principal, los trabajadores de dicha ubicación obtienen una cuarta parte de la puntuación y así sucesivamente.  
  - Si su empresa usa la ubicación del activo, que no es lo recomendable, la ubicación, el área, y la zona se utilizan para calcular las puntuaciones de la ubicación. Los trabajadores obtienen la puntuación completa si se encuentran en la ubicación y el área y la zona relacionados con el activo. Si la ubicación del trabajador solo coincide con la ubicación y el área, la puntuación para el trabajador es de 2/3 de la puntuación completa. Si la ubicación del trabajador solo coincide con la ubicación, la puntuación para el trabajador es de 1/3 de la puntuación completa.  

- El botón de alternar Sí/No de **Límite de ubicación** limita el número de trabajadores disponibles para la programación de la orden de trabajo. Seleccione “No” si no desea calcular una puntuación para todos los trabajadores en todas las ubicaciones funcionales. Seleccione “Sí” si solo desea calcular una puntuación para los trabajadores asociados a la ubicación funcional de la orden de trabajo.

>[!NOTE]
>Los tres botones “Límite de…” se han introducido para aumentar la velocidad de la programación de órdenes de trabajo limitando el número de puntuaciones calculadas para los trabajadores.

**Fecha inicial del trabajador**: puntuación que se calcula junto con los valores de **Trabajador responsable**, **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**. Este campo indica la puntuación diaria como valor negativo y se compara con el campo **Inicio esperado** en una orden de trabajo. Ejemplo: Si el valor "10.00"se inserta en este campo y la fecha inicial esperada de una orden de trabajo es mañana, el resultado de la puntuación es de menos 10.00.

  - Suponiendo que no se ha seleccionado ningún trabajador responsable y grupo de trabajadores responsables en una orden de trabajo por programar, se deben sumar y restar las puntuaciones de ejemplo de los campos **Trabajador preferido**, **Grupo de trabajadores preferidos**, **Ubicación del activo** y **Fecha inicial**, lo que resulta en un total de 3010.00. Esto significa una puntuación alta para el trabajador seleccionado como trabajador preferido en el grupo de trabajadores preferidos para la orden de trabajo si el trabajador también se encuentra en las mismas instalaciones que el activo para el que se debe programar el trabajo. Cosiderando todo esto, hay una alta probabilidad de que el trabajador en cuestión complete el trabajo durante la programación de la orden de trabajo.  
  - Si el valor "0.00" se inserta en uno de los ocho campos anteriores, esa puntuación no se usará durante la programación de la orden de trabajo.  


Vínculo **Tipos de documento**

Seleccione los tipos de documento que deben estar disponibles para imprimir los datos adjuntos relacionados con un informe de orden de trabajo. Para ello, haga clic en un tipo de documento en la sección **Disponible** y haga clic en el botón de la ![flecha atrás](media/15-setup-for-objects.png). Si desea quitar un tipo de documento seleccionado, seleccione el tipo de documento en la sección **Seleccionado** y haga clic en el botón de la ![flecha hacia delante](media/16-setup-for-objects.png) .



Vínculo **Secuencias numéricas**

Seleccione las secuencias numéricas necesarias en esta sección. Existen dos secuencias numéricas para los activos: una para activos creados manualmente y otra para activos creados a través de activos pendientes.
