---
title: "Aprobaciones de factura móvil"
description: "Este tema está pensando para proporcionar un método práctico de diseñar escenarios móviles en Dynamics 365 for Finance and Operations con las aprobaciones de facturas de proveedores para aplicaciones móviles como un caso de uso."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c579db5a922d81a2781ec2011e148db54fac288d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="mobile-invoice-approvals"></a>Aprobaciones de factura móvil

[!include[banner](../includes/banner.md)]


Las capacidades móviles de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, permiten a un usuario empresarial diseñar experiencias móviles. Para situaciones avanzadas, la plataforma también permite a los desarrolladores ampliar las capacidades como desean. La forma más eficaz de aprender algunos de los conceptos nuevos sobre capacidades móviles es pasar por el proceso de diseño de algunos escenarios. Este tema está pensando para proporcionar un método práctico de diseñar escenarios móviles con las aprobaciones de facturas de proveedores para aplicaciones móviles como un caso de uso. Este tema le ayudará a diseñar otras variaciones de los escenarios y se puede aplicar a otros escenarios que no están relacionados con las facturas de proveedores.

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                                                            | Descripción                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Manual sobre capacidades móviles de lectura previa                                                                                |[Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 for Finance and Operations                                                                             | Un entorno que tiene la versión 1611 de Microsoft Dynamics 365 for Operations y la actualización 3 de la plataforma de Microsoft Dynamics for Operations (noviembre de 2016).                   |
| Instalar revisión KB 3204341.                                                                              | El grabador de tareas puede registrar de forma errónea dos comandos Close para diálogos desplegables incluidos en la actualización 3 de Dynamics 365 for Operations (noviembre de 2016) |
| Instalar revisión KB 3207800.                                                                              | Esta revisión habilita los datos adjuntos que se verán en el cliente móvil, lo cual se incluye en la actualización 3 de Dynamics 365 for Operation (noviembre de 2016).           |
| Instalar revisión KB 3208224.                                                                              | El código de la aplicación para la aplicación de aprobación de facturas de proveedores móviles se incluye en la aplicación 7.0.1 de Microsoft Dynamics AX (mayo de 2016).                          |
| Un dispositivo Android, iOS o Windows que tengan la aplicación móvil instalada para Finance and Operations | Busque la aplicación en la tienda de aplicaciones apropiada.                                                                                                                     |

## <a name="introduction"></a>Introducción
Las aprobaciones móviles para las facturas de proveedor requieren la tres revisiones mencionadas en la sección de los requisititos previos. Estas revisiones no proporcionan un espacio de trabajo para las aprobaciones de facturas. Para saber qué es un espacio de trabajo en el contexto de las aplicaciones móviles, lea el manual referido en la sección de los requisitos previos. Se debe diseñar un espacio de trabajo para aprobaciones de facturas. 

Cada organización articula y define su proceso empresarial para las facturas de proveedores de forma diferente. Antes de diseñar una experiencia móvil para las aprobaciones de la facturas de proveedores, debe tener en cuenta los siguientes aspectos del proceso empresarial. La idea es usar estos puntos de datos tanto como sea posible para optimizar la experiencia del usuario en el dispositivo.

-   ¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?
-   ¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?
-   ¿Cuántas líneas de factura hay en una factura? Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.
-   ¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones? Si la respuesta a esta pregunta es afirmativa, tenga en cuenta las preguntas siguientes:
    -   ¿Cuántas distribuciones contables (precio total, impuestos, cargos, divisiones, etc.) hay para una línea de factura? Una vez más, aplique la regla 80-20.
    -   ¿Las facturas también tienen distribuciones contables en el encabezado de factura? En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?

> [!NOTE]
> Este tema no explica cómo editar distribuciones contables, porque esta funcionalidad no se admite actualmente para los escenarios móviles.

-   ¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?

El diseño de la experiencia móvil de las aprobaciones de facturas variará, en función de las respuestas a estas preguntas. El objetivo es optimizar la experiencia del usuario para el proceso empresarial en las plataformas móviles de una organización. En el resto de este tema, revisaremos dos variaciones del escenario que se basan en diferentes respuestas a las preguntas anteriores. 

Como orientación general, al trabajar con el diseñador para aplicaciones móviles, asegúrese de “publicar” los cambios para evitar perder las actualizaciones.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Diseñar una situación de ejemplo sencillo de aprobación de facturas para Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de escenario</th>
<th>Respuesta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</td>
<td><ol>
<li>Nombre del proveedor</li>
<li>Total de la factura</li>
<li>Cuenta de facturación</li>
<li>Número de factura</li>
<li>Fecha de la factura</li>
<li>Descripción de factura</li>
<li>Fecha de vencimiento</li>
<li>Divisa de la factura</li>
</ol></td>
</tr>
<tr class="even">
<td>¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</td>
<td><ol>
<li>Categoría de compras</li>
<li>Cantidad</li>
<li>Precio unitario</li>
<li>Importe neto de línea</li>
<li>Importe de la declaración de IRPF</li>
</ol></td>
</tr>
<tr class="odd">
<td>¿Cuántas líneas de factura hay en una factura? Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</td>
<td>1</td>
</tr>
<tr class="even">
<td>¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</td>
<td>Sí</td>
</tr>
<tr class="odd">
<td>¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura? Una vez más, aplique la regla 80-20.</td>
<td>Precio total: 2 Impuestos: 0 Cargos: 0</td>
</tr>
<tr class="even">
<td>¿Las facturas también tienen distribuciones contables en el encabezado de factura? En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</td>
<td>No utilizado</td>
</tr>
<tr class="odd">
<td>¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</td>
<td>Sí</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Crear el espacio de trabajo

1.  En un explorador, abra Finance and Operations e inicie sesión.
2.  Una vez que haya iniciado sesión, agregue **&mode=mobile** a la dirección URL como se muestra en el siguiente ejemplo, y actualice la página: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**
3.  Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**. El diseñador para aplicaciones móviles de la aplicación debe aparecer igual que lo hace el Grabador de tareas.
4.  Haga clic en **Agregar** para crear un nuevo espacio de trabajo. Para este ejemplo, asigne un nombre al espacio de trabajo **Mis aprobaciones**.
5.  Escribir una descripción.
6.  Seleccione un color para el espacio de trabajo. El color del espacio de trabajo se usará para el estilo global de la experiencia móvil de este espacio de trabajo.
7.  Seleccione un icono para el espacio de trabajo.
8.  Haga clic en **Listo**
9.  Haga clic en **Publicar espacio de trabajo** para guardar los cambios

### <a name="vendor-invoices-assigned-to-me"></a>Facturas de proveedor asignadas al usuario

La primera página para aplicaciones móviles que debe diseñar es la lista de facturas que se asignan al usuario para revisión. Para diseñar esta página para aplicaciones móviles, use la página **VendMobileInvoiceAssignedToMeListPage** en Finance and Operations. Para completar este procedimiento, asegúrese de que al menos se le asigna una factura de proveedores para revisión, y que la línea de factura tiene dos distribuciones. Esta configuración cumple los requisitos para este supuesto.

1.  En la dirección URL de Finance and Operations, reemplace el nombre del elemento de menú con **VendMobileInvoiceAssignedToMeListPage** para abrir la versión móvil de la página con la lista **Facturas de proveedor pendientes asignadas a mí** en el módulo **Proveedores**. En función del número de facturas que tiene en el sistema asignadas a usted, esta página mostrará dichas facturas. Para buscar una factura específica, utilice el filtro a la izquierda. Sin embargo, no se requiere una factura concreta para este ejemplo. Simplemente se requiere que tenga asignada alguna factura, lo que le permitirá diseñar la página para aplicaciones móviles. Las nuevas páginas disponibles se diseñaron específicamente para desarrollar los escenarios móviles para la factura de proveedor. Por lo tanto, debe usar estas páginas. La dirección debe URL ser similar a la URL siguiente y, después de especificarla, la página que se muestra en la ilustración debe aparecer:https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Página de Facturas de proveedor pendientes asignadas a mí](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
2.  Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**
3.  Seleccione su espacio de trabajo y haga clic en **Editar**
4.  Haga clic en **Agregar página** para crear la primera página para aplicaciones móviles.
5.  Escriba un nombre, por ejemplo **Mis facturas de proveedor** y una descripción, por ejemplo **Facturas de proveedor que se me asignaron para revisión**.
6.  Haga clic en **Listo**.
7.  En el diseñador para aplicaciones móviles, en la ficha **Campos**, haga clic en **Seleccionar campos**. Las columnas de la página de lista deben ser semejantes a la siguiente ilustración. [![Columnas en la página Facturas de proveedor pendientes asignadas a mí](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
8.  Agregue las columnas necesarias de la página con la lista que se deben mostrar a los usuarios en la página para aplicaciones móviles. El orden en que se agrega es el orden en que los campos se mostrarán al usuario final. La única forma de cambiar orden de los campos es volviendo a seleccionar todos los campos. Según los requisitos para esta situación, son necesarias los ocho campos siguientes. Sin embargo, algunos usuarios pueden considerar que ocho campos son demasiada información para tener en un dispositivo móvil. Por lo tanto, mostraremos solamente los campos más importantes en la vista de lista del móvil. Los campos restantes aparecerán en la vista de detalles que diseñaremos posteriormente. Por ahora, agregaremos los campos siguientes. Haga clic en el signo más (**+**) en estas columnas para agregar a la página para aplicaciones móviles.
    - Nombre del proveedor
    - Total de la factura
    - Cuenta de facturación
    - Número de factura
    - Fecha de la factura

    Después de que se agreguen los campos, la página para aplicaciones móviles debe asemejarse a la siguiente ilustración. 
    [![Página después de haber agregado campos](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)
9.  También debe agregar las siguientes columnas ahora, de modo que podamos habilitar acciones de flujo de trabajo posteriormente.
    - Mostrar tarea completa
    - Muestra tarea de delegado
    - Mostar la tarea de recuperación
    - Mostrar tarea de rechazo
    - Mostrar tarea de finalización de solicitud
    - Mostrar tarea de reenvío

10. Haga clic en **Listo** para salir del modo de edición.
11. Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
12. Haga clic en **Publicar espacio de trabajo** para guardar el trabajo.
13. Habilite **Mostrar total factura en lista de facturas de proveedor pendiente** en los parámetros de proveedores desde **Factura**. Tenga en cuenta que, al habilitar este parámetro, los totales de las facturas se calcularán para mostrarse en la página de la lista de facturas de proveedor pendientes. Esta es una nueva capacidad que forma parte de la revisión 3208224 del requisito previo.

### <a name="vendor-invoice-details"></a>Detalles de la factura de proveedor

Para diseñar la página de detalles de la factura para móvil, use la página **VendMobileInvoiceHeaderDetails** en Finance and Operations. Tenga en cuenta que, en función del número de facturas que tiene en el sistema, esta página muestra la factura más antigua (la factura que se creó primero). Para buscar una factura específica, utilice el filtro a la izquierda. Sin embargo, no se requiere una factura concreta para este ejemplo. Simplemente requerimos algunos datos de la factura para que podamos diseñar la página para dispositivos móviles. [![Página del flujo de trabajo](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1.  En la dirección URL de Finance and Operations, sustituya el nombre del elemento de menú con **VendMobileInvoiceHeaderDetails** para abrir el formulario
2.  Abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).
3.  Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.
4.  Seleccione la página **Mis facturas de proveedor** que ha creado antes y haga clic en **Editar**.
5.  En los la ficha **Campos**, haga clic en el encabezado de columna **Cuadrícula**.
6.  Haga clic en **Propiedades** &gt; **Agregar página**. **Nota:** Al hacer clic en el encabezado de **Cuadrícula** y agregar una página, la relación con la página de detalles se establece automáticamente.
7.  Especifique un título de la página, por ejemplo **Detalles de la factura** y una descripción como **Ver detalles de línea y encabezado de la factura**.
8.  Haga clic en **Seleccionar campos**. Tenga en cuenta que el orden en que se agrega es el orden en que los campos se mostrarán al usuario final. La única forma de cambiar orden de los campos es volviendo a seleccionar todos los campos. 
9.  Agregue los siguientes campos desde el encabezado, según los requisitos para esta situación:
    - Nombre del proveedor
    - Total de la factura
    - Cuenta de facturación
    - Número de factura
    - Fecha de la factura
    - Descripción de factura
    - Fecha de vencimiento
    - Divisa de la factura

10. Agregue los siguientes campos en la cuadrícula de las líneas en la página:
    - Categoría de compras
    - Cantidad
    - Precio unitario
    - Importe neto de línea
    - Importe de la declaración de IRPF

11. Después de agregar todos los campos de los dos pasos anteriores, haga clic en **Listo**. La página deben asemejarse a la siguiente ilustración.
[![Página después de haber agregado campos](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Haga clic en **Listo** para salir del modo de edición.
13. Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
14. Haga clic en **Publicar espacio de trabajo** para guardar el trabajo

### <a name="workflow-actions"></a>Acciones de flujo de trabajo

Para agregar acciones de flujo, use la página **VendMobileInvoiceHeaderDetails** en Finance and Operations. Para abrir esta página, reemplace el nombre del elemento de menú de la dirección URL, como lo hizo anteriormente. Después, abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje). Siga estos pasos para agregar acciones de flujo de trabajo en la página de detalles. Debe tener facturas asignadas y que tengan un estado apropiado para que las acciones del flujo de trabajo para las que va a realizar el diseño estén disponibles.

#### <a name="record-workflow-actions"></a>Registrar acciones de flujo de trabajo
1.  Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.
2.  Seleccione la página **Mis facturas de proveedor** que ha creado antes y haga clic en **Editar**.
3.  En la ficha **Acciones**, haga clic en **Agregar acción**.
4.  Especifique un título de acción, como **Aprobar** y una descripción como **Aprobar factura**. Tenga en cuenta que el título de la acción que escriba aquí se convierte en el nombre de la acción que se muestra al usuario en la aplicación móvil.
5.  Haga clic en **Listo**.
6.  Haga clic en **Seleccionar campos**.
7.  Realice el proceso del flujo de trabajo en la página **VendMobileInvoiceHeaderDetails** y complete la acción que se quería registrar. Asegúrese de especificar los comentarios del flujo de trabajo durante este proceso, de forma que se incluya un campo de comentarios en la experiencia móvil.
8.  Una vez que se ejecute la acción del flujo de trabajo, haga clic en **Listo** para completar la tarea Seleccionar campos.
9.  Haga clic en **Listo** para salir del modo de edición.
10. Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
11. Haga clic en **Publicar espacio de trabajo** para guardar el trabajo
12. Repita los pasos anteriores para registrar todas las acciones del flujo de trabajo necesarias. 

#### <a name="create-a-js-file"></a>Crear un archivo .js
1. Abra el Bloc de notas o Microsoft Visual Studio, y pegue el código siguiente. Guarde el archivo como archivo .js. Este código hace lo siguiente:
    - Oculta las columnas adicionales relacionadas con el flujo de trabajo adicionales que agregamos anteriormente en la página de la lista para dispositivos móviles. Agregamos estas columnas de modo que la aplicación tenga información en contexto y se pueda ir al paso siguiente.
    - Según el paso del flujo de trabajo que está activo, aplica la lógica para mostrar solo esas acciones.

> [!NOTE]
> El nombre de las páginas y otros controles del código de JS deberían ser los mismos que los nombres en el espacio de trabajo.

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  Cargar el archivo del código en el espacio de trabajo seleccionando la ficha **Lógica**
3.  Haga clic en **Listo** para salir del modo de edición.
4.  Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
5.  Haga clic en **Publicar espacio de trabajo** para guardar el trabajo

### <a name="vendor-invoice-attachments"></a>Datos adjuntos de la factura de proveedor

1.  Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**
2.  Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.
3.  Seleccione la página **Detalles de la factura** que ha creado antes y haga clic en **Editar**.
4.  Establezca la opción **Administración de documentos** en **Sí** como se indica a continuación. **Nota:** Si no hay requisitos para mostrar los datos adjuntos en el dispositivo móvil, puede dejar esta opción establecida en **No**, que es la configuración predeterminada.
![Administración de documentos](./media/docmanagement-216x300.png)
6.  Haga clic en **Listo** para salir del modo de edición.
7.  Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
8.  Haga clic en **Publicar espacio de trabajo** para guardar el trabajo

### <a name="vendor-invoice-line-distributions"></a>Distribuciones de línea de la factura de proveedor

Los requisitos para este escenario confirman que solo habrá distribuciones a nivel de línea y que las facturas serán siempre de una línea. Puesto que este escenario es sencillo, la experiencia del usuario en el dispositivo móvil también debe ser lo suficientemente sencilla para que el usuario no tenga que buscar en profundidad para ver las distribuciones. Las facturas de proveedor de Finance and Operations incluyen la opción para mostrar todas las distribuciones del encabezado de la factura. Esta experiencia es lo que necesitamos para el escenario de dispositivos móviles. Por lo tanto, utilizaremos la página **VendMobileInvoiceAllDistributionTree** para diseñar esta parte del escenario móvil. 

> [!NOTE] 
> Conocer los requisitos nos ayuda a decidir qué página determinada se va utilizar y exactamente cómo optimizar la experiencia móvil del usuario cuando diseñamos el escenario. En el segundo escenario, utilizaremos una página diferente para mostrar las distribuciones, ya los requisitos para esa situación son diferentes.

1.  En la dirección URL, reemplace el nombre del elemento de menú tal como hizo antes. La página que aparece debe asemejarse a la siguiente ilustración.
[![Página de todas las distribuciones](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)
2.  Abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).
3.  Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo. **Nota:** Verá dos nuevas páginas que se han creado automáticamente. El sistema crea estas páginas porque ha activado la gestión de documentos en la sección anterior. Puede omitir estas páginas nuevas.
4.  Haga clic en **Agregar página**.
5.  Especifique un título para la página como **Ver contabilidad** y una descripción como **Ver contabilidad para la factura**.
6.  Haga clic en **Listo**.
7.  En la ficha **Campos**, haga clic en **Seleccionar campos**, seleccione los siguientes campos de la página de las distribuciones, y haga clic en **Listo**:
    1.  Importe
    2.  Divisa
    3.  Cuenta contable

    > [!NOTE] 
    > No seleccionamos la columna **Descripción** en la cuadrícula de las distribuciones debido a que los requisitos para este escenario confirmaron que el precio total es el único importe para el que habrá distribuciones. Por tanto, el usuario no necesitará otro campo para determinar el tipo de importe para el que es la distribución. Sin embargo, en el escenario siguiente, **utilizaremos** esta información porque los requisitos para esa situación especifican que otros tipos de importe tienen distribuciones (por ejemplo, impuestos).
8.  Haga clic en **Listo** para salir del modo de edición.
9.  Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
10. Haga clic en **Publicar espacio de trabajo** para guardar el trabajo

> [!NOTE] 
> Nota: La página para dispositivos móviles **Ver contabilidad** no está vinculada actualmente a ninguna página para dispositivos móviles que hemos diseñado hasta el momento. Dado que el usuario debe poder navegar a la página **Ver contabilidad** desde la página **Detalles de la factura** en el dispositivo móvil, debemos proporcionar navegación desde la página **Detalles de la factura** hasta la página **Ver contabilidad**. Establecemos esta navegación mediante el uso de lógica JavaScript adicional.

1.  Abre el archivo .js que ha creado anteriormente y agregue las líneas que se resaltan en el código siguiente. Este código hace dos cosas:
    1.  Ayuda a garantizar que los usuarios no pueden navegar directamente desde el espacio de trabajo a la página **Ver contabilidad**.
    2.  Establece un control de navegación desde la página **Detalles de la factura** hasta la página **Ver contabilidad**.

> [!NOTE] 
> El nombre de las páginas y otros controles del código de JS deberían ser los mismos que los nombres en el espacio de trabajo.

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  Cargar el archivo del código en el espacio de trabajo seleccionando la ficha **Lógica** para sobrescribir el código anterior
3.  Haga clic en **Listo** para salir del modo de edición.
4.  Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo
5.  Haga clic en **Publicar espacio de trabajo** para guardar el trabajo

### <a name="validation"></a>Validación

Desde el dispositivo móvil, abra la aplicación y conéctese a la instancia de su instancia de Finance and Operations. Asegúrese de tener haber iniciado sesión en la empresa donde tenga asignadas las facturas de proveedores para revisión. Debería poder realizar las acciones siguientes:

-   Ver el espacio de trabajo **Mis aprobaciones**.
-   Explorar en profundidad el espacio de trabajo **Mis aprobaciones** y ver la página **Mis facturas de proveedor**.
-   Explorar en profundidad la página **Mis facturas de proveedores** y ver la lista de facturas que se le han asignado.
-   Explorar en profundidad una de las facturas y ver los detalles del encabezado y la línea de la factura.
-   En la página de detalles, ver un vínculo a los datos adjuntos y utilizarlo para navegar a la lista de datos adjuntos y verlos.
-   En la página de detalles, ver un vínculo a la página **Ver contabilidad** y utilizarlo para navegar a la página de distribuciones y ver las distribuciones.
-   En la página de detalles, haga clic en el menú **Acciones** de la parte inferior y realice las acciones del flujo de trabajo aplicables al paso del flujo de trabajo.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Diseñar un escenario de aprobación de factoras complejo para Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de escenario</th>
<th>Respuesta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</td>
<td><ol>
<li>Nombre del proveedor</li>
<li>Importe de la factura</li>
<li>Cuenta de facturación</li>
<li>Número de factura</li>
<li>Fecha de la factura</li>
<li>Descripción de factura</li>
<li>Fecha de vencimiento</li>
<li>Divisa de la factura</li>
</ol></td>
</tr>
<tr class="even">
<td>¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</td>
<td><ol>
<li>Categoría de compras</li>
<li>Cantidad</li>
<li>Precio unitario</li>
<li>Importe neto de línea</li>
<li>Importe de la declaración de IRPF</li>
</ol></td>
</tr>
<tr class="odd">
<td>¿Cuántas líneas de factura hay en una factura? Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</td>
<td>5</td>
</tr>
<tr class="even">
<td>¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</td>
<td>Sí</td>
</tr>
<tr class="odd">
<td>¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura? Una vez más, aplique la regla 80-20.</td>
<td>Precio total: 2 Impuestos: 2 Cargos: 2</td>
</tr>
<tr class="even">
<td>¿Las facturas también tienen distribuciones contables en el encabezado de factura? En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</td>
<td>No utilizado</td>
</tr>
<tr class="odd">
<td>¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</td>
<td>Sí</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>Pasos siguientes

Las variaciones siguientes se pueden realizar para el escenario 1, en función de los requisitos para el escenario 2. Puede usar esta sección para mejorar la experiencia móvil de la aplicación.

1.  Dado que habrá más líneas de factura en el escenario 2, los cambios siguientes en el diseño ayudarán a optimizar la experiencia del usuario en el dispositivo móvil:
    1.  En lugar de ver las líneas de la factura en la página de detalles (como en el escenario 1), los usuarios pueden elegir ver las líneas en una página independiente para dispositivos móviles.
    2.  Dado que habrá más de una línea de factura este escenario, si la página **VendMobileInvoiceAllDistributionTree** se utiliza para diseñar la página de distribuciones para dispositivos móviles (como en el escenario 1), puede que resulte confuso para que el usuario correlacionar líneas con distribuciones. Por lo tanto, use la página **VendMobileInvoiceLineDistributionTree** para diseñar la página de distribuciones.
    3.  Por ello, las distribuciones se deben mostrar en el contexto de una línea de factura en este escenario. Por lo tanto, asegúrese de que el usuario puede explorar en una línea para ver la página de las distribuciones. Use la capacidad del vínculo de la página para establecer una búsqueda detallada, tal como hizo para el encabezado y las páginas de detalles en el escenario 1.

2.  Dado que habrá más de un tipo de importe en las distribuciones en el escenario 2 (los impuestos, los gastos, etc.), será útil mostrar la descripción del tipo de importe. (Omitimos esta información en el escenario 1).





