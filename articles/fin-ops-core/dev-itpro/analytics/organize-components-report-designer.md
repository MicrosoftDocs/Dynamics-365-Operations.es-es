---
title: Organizar los componentes del informe en el diseñador de informes
description: Una vez ha diseñado los bloques de creación y los informes generados, resulta útil organizar estos objetos para que los usuarios los encuentren más fácilmente. En este artículo se explica cómo organizar los informes existentes, los bloques de creación y los objetos en el diseñador de informes.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 58525da35eb9e9376cb5793ad6c6fa45b9de42e6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685820"
---
# <a name="organize-report-components-in-report-designer"></a>Organizar los componentes del informe en el diseñador de informes

[!include [banner](../includes/banner.md)]

Una vez ha diseñado los bloques de creación y los informes generados, resulta útil organizar estos objetos para que los usuarios los encuentren más fácilmente. En este artículo se explica cómo organizar los informes existentes, los bloques de creación y los objetos en el diseñador de informes.

Puede cambiar el nombre de carpetas, informes, bloques de creación y otros objetos en el diseñador de informes para ayudar a organizar sus archivos. En función del tipo de objeto al que quiere cambiar el nombre, puede que tenga que actualizar las asociaciones con ese objeto.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Cambiar el nombre de una carpeta o un bloque de creación en el diseñador de informes
En el Diseñador de informes, puede cambiar el nombre de carpetas y de definiciones de informe, de fila, de columna y de organigrama.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Cambiar el nombre de una carpeta o un bloque de creación en el Diseñador de informes

1. En el Diseñador de informes, use el panel de navegación para localizar la carpeta o el objeto cuyo nombre desee cambiar.
2. Haga clic con el botón secundario en la carpeta o en el informe y, a continuación, haga clic en **Cambiar nombre**. El campo **Nombre** en el panel de navegación pasa a estar activo.
3. Escriba un nuevo nombre y luego presione Intro.
4. Si el bloque de creación es una definición de fila, definición de columna o definición de organigrama, debe actualizar otros bloques de creación asociados a él. Haga clic con el botón secundario en el bloque de creación al que le cambió el nombre en el paso 3, seleccione **Asociaciones** y, a continuación seleccione un elemento en la lista para actualizarlo.
5. Repita el paso 4 hasta que todos los elementos asociados se actualizan.

## <a name="create-and-manage-report-groups"></a>Crear y gestionar grupos de informes
Puede agrupar definiciones de informes para generar varios informes al mismo tiempo. Para crear, modificar, eliminar y generar los grupos de informes, debe tener el rol de diseñador o de administrador. Los usuarios que tienen el rol de generador pueden generar grupos de informes y también pueden modificar la configuración de definiciones de informes del usuario para los grupos de informes.

### <a name="create-a-report-group"></a>Crear un grupo de informes

1. En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.
2. En el menú **Archivo**, haga clic en **Nuevo** &gt; **Definición de grupo de informes** para abrir un nuevo grupo de informe en la ventana del visor. De forma alternativa, haga clic en el botón **Grupo de informes** ![Grupo de informes](media/report-group.gif "Grupo de informes") de la barra de herramientas.
3. Haga clic en la pestaña **Grupo de informes**. Para reemplazar la información sobre las definiciones de informes individuales para la generación de este informe, active la casilla **Eliminar la configuración de empresa, detalles y fecha de las definiciones de informes individuales**. La información sobre el nombre de la empresa, el nivel de detalle, la configuración provisional y la fecha se especifica automáticamente, pero puede realizar actualizaciones.
4. Para generar varios informes que muestren las divisas de notificación, active la casilla **Incluir todas las divisas de notificación**. A continuación, para obtener acceso a varias vistas, haga clic en el botón **Divisa** en el visor de la web al ver el informe.
5. En el campo **Informes en grupo**, haga clic en **Agregar** para seleccionar los informes que se incluirán en el grupo de informes. Para seleccionar varios informes en el cuadro de diálogo **Agregar**, mantenga presionada la tecla Ctrl mientras selecciona los informes. Cuando haya finalizado de seleccionar informes, haga clic en **Aceptar**.
6. Haga clic en **Archivo** &gt; **Guardar** para guardar el nuevo grupo de informes.

### <a name="modify-a-report-group"></a>Modificar un grupo de informes

1. En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.
2. Haga doble clic en el grupo de informes para modificarlo.
3. En la pestaña **Grupo de informes**, realice los cambios que desee.
4. En el menú **Archivo**, haga clic en **Guardar** para guardar el grupo de informes modificado. De forma alternativa, haga clic en el botón **Guardar** ![Guardar](media/save.gif "Guardar") de la barra de herramientas.

> [NOTA] si ha programado informes para que se generen en intervalos definidos, puede anular esos ajustes y generar un informe inmediatamente.

### <a name="generate-a-report-group-report"></a>Generar un informe del grupo de informes

1. En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.
2. Abra el grupo de informes que desea generar.
3. Haga clic en el botón **Generar informe** ![Generar informe](media/generate-report.gif "Generar informe") para generar informes.

### <a name="delete-a-report-group"></a>Eliminar un grupo de informes

1. En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.
2. Haga clic con el botón secundario en el grupo de informes para eliminarlo y, a continuación, seleccione **Eliminar**.
3. Cuando aparezca un mensaje de confirmación, haga clic en **Sí**.

## <a name="report-group-tab-controls"></a>Controles de la pestaña Grupo de informes
En la tabla siguiente se describen los controles de la pestaña **Grupo de informes**.

<table>
<thead>
<tr>
<th>Control</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>Anular las configuraciones de la empresa, detalles y fecha de definiciones de informes individuales</td>
<td>Active esta casilla para anular las definiciones de informes individuales de los informes de este grupo de informes para la generación de estos informes solo.</td>
</tr>
<tr>
<td>Nombre de empresa</td>
<td>Seleccione la empresa que desee usar para los informes.</td>
</tr>
<tr>
<td>Nivel de detalle</td>
<td>Especifique el nivel de detalle que incluyen los informes.
<ul>
<li><strong>Financiero</strong>: informe de resumen de alto nivel. No puede explorar en profundidad las cuentas y dimensiones, salvo las cuentas y dimensiones que se han agregado a través de un organigrama.</li>
<li><strong>Financiero y contable</strong>: un informe que contiene un resumen de alto nivel y detalles de la cuenta.</li>
<li><strong>Financiero, contable y de transacciones</strong>: un informe que contiene un resumen de alto nivel y detalles de transacciones.</li>
</ul></td>
</tr>
<tr>
<td>Provisional</td>
<td>Especifique los tipos de actividad que incluyen los informes.
<ul>
<li><strong>Solo actividad registrada:</strong> incluye solo las transacciones y los saldos registrados en los datos financieros.</li>
<li><strong>Actividad registrada y sin registrar:</strong> incluye todas las transacciones y saldos especificados y registrados en sus datos financieros.</li>
<li><strong>Solo actividad no registrada:</strong> incluye solo las transacciones especificadas, pero todavía no registradas, en los datos financieros.</li>
</ul></td>
</tr>
<tr>
<td>Incluir todas las divisas de notificación</td>
<td>Las divisas de notificación adicionales que se configuran en el sistema de Microsoft Dynamics ERP, aparecen aquí. Active esta casilla para generar informes adicionales en las divisas que se indican. Para ver estos informes en el Visor web, haga clic en el botón <strong>Divisa</strong> y, a continuación, seleccione una divisa.</td>
</tr>
<tr>
<td>Información sobre fechas que no ha sido guardada con la definición del informe</td>
<td><ul>
<li>Periodo base</li>
<li>Año base</li>
<li>Período de cobertura</li>
</ul>
Solo la configuración del período de base predeterminado se guarda con la definición del informe.</td>
</tr>
<tr>
<td>Información sobre fechas que ha sido guardada con la definición del informe</td>
<td><ul>
<li>Fecha del informe</li>
<li>Período base predeterminado</li>
</ul></td>
</tr>
<tr>
<td>Informes en grupo</td>
<td>Agregar, eliminar y reordenar informes en el grupo de informes.
<ul>
<li>Para agregar definiciones de informe al grupo de informes, haga doble clic en el grupo de informes para abrirlo y luego haga clic en <strong>Agregar</strong>. Seleccione los informes que se deben incluir en el grupo de informes y haga clic en <strong>Aceptar</strong>.</li>
<li>Para quitar un informe del grupo de informes, seleccione el informe deseado y haga clic en <strong>Quitar</strong>.</li>
<li>Para modificar el orden en que se generan los informes, seleccione un informe en la lista y, a continuación, haga clic en <strong>Mover hacia arriba</strong> o <strong>Mover hacia abajo</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)
