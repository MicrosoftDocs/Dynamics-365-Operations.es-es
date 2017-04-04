---
title: "Aprobaciones de facturas móviles"
description: "Las capacidades en móviles Microsoft Dynamics 365 para las operaciones permiten un usuario empresarial diseñar experiencias móviles. Para las situaciones avanzado, la plataforma también permite los desarrolladores extender las capacidades como desean. La mayoría de forma más eficaz de obtener algunos de los conceptos nuevos en móvil es pasar el proceso de diseño de algunas escenarios. Este tema sólo está pensando para proporcionar un método a práctico diseñar escenarios móviles tomando las aprobaciones de la factura de proveedor para el móvil como un caso de uso. Este tema debe diseñar otras variaciones de los escenarios y se puede aplicar a otros escenarios que no están relacionados con las facturas de proveedor."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Aprobaciones de facturas móviles

Las capacidades en móviles Microsoft Dynamics 365 para las operaciones permiten un usuario empresarial diseñar experiencias móviles. Para las situaciones avanzado, la plataforma también permite los desarrolladores extender las capacidades como desean. La mayoría de forma más eficaz de obtener algunos de los conceptos nuevos en móvil es pasar el proceso de diseño de algunas escenarios. Este tema sólo está pensando para proporcionar un método a práctico diseñar escenarios móviles tomando las aprobaciones de la factura de proveedor para el móvil como un caso de uso. Este tema debe diseñar otras variaciones de los escenarios y se puede aplicar a otros escenarios que no están relacionados con las facturas de proveedor.

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                                                            | Descripción                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Manual móvil previos leído                                                                                |(/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform.md)                                                                                                  |
| Dinámica 365 para las operaciones                                                                             | Un entorno con Microsoft Dynamics 365 para la versión 1611 de las operaciones y Microsoft Dynamics para la plataforma de las operaciones actualiza 3 (noviembre de 2016)                   |
| Sustitución de 3204341 KB la instalación.                                                                              | El Grabador de tareas puede registrar dos erróneamente cercanos comandos para los de diálogos desplegable que esto se incluye en Dynamics 365 para la plataforma de actualiza la operación 3 (noviembre de 2016 la actualización) |
| Sustitución de 3207800 KB la instalación.                                                                              | Este sustitución habilita los datos adjuntos que se verán en el cliente móvil que esto se incluye en Dynamics 365 para la plataforma de actualiza la operación 3 (noviembre de 2016 actualización).           |
| Sustitución de 3208224 KB la instalación.                                                                              | El código de aplicación para la aplicación móvil de la aprobación de la factura de proveedor se incluye en la aplicación 7.0.1 de Microsoft Dynamics AX (mayo de 2016).                          |
| Android o un IOS o un dispositivo de Windows que tiene la aplicación móvil instalaron para Dynamics 365 para las operaciones | Busque la aplicación en el almacén apropiado de la aplicación.                                                                                                                     |

## <a name="introduction"></a>Introducción
Aprobaciones móviles para las facturas de proveedor requiere la sustituciones tres mencionados en la sección “de los requisitos previos”. Estos sustituciones no proporcionan un área de trabajo para aprobaciones de facturas. Para obtener la cual es un área de trabajo en el contexto de móvil, lea el manual móvil que se ha mencionado en la sección “de los requisitos previos”. El área de trabajo de aprobaciones de facturas debe ser la tarea. 

Cada organización orquestra y define su proceso empresarial para las facturas de proveedor de forma diferente. Antes de diseñar una experiencia móvil de las aprobaciones de la factura de proveedor, debe tener en cuenta los siguientes aspectos del proceso empresarial. La idea es usar estos puntos de datos tanto como sea posible para optimizar la experiencia del usuario en el dispositivo.

-   ¿Qué campos del encabezado de factura el usuario deseará para ver en la experiencia móvil, y en qué pedidos?
-   ¿Qué campos de las líneas de factura el usuario deseará para ver en la experiencia móvil, y en qué pedidos?
-   ¿Cuántas líneas de factura hay en una factura? Aplica la regla 80-20 aquí, y optimiza para el 80 por ciento.
-   ¿Los usuarios desearán para ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante estudios? Si la respuesta a esta pregunta se afirmativo, tenga en cuenta las preguntas siguientes:
    -   ¿Cuántas distribuciones contables (precio total, impuestos, cargos, divisiones, etc.) hay para una línea de factura? Una vez más aplica la regla 80-20.
    -   ¿Las facturas también tienen distribuciones contables en el encabezado de factura? ¿En dicho caso estas deben distribuciones contables estar disponible en el dispositivo?

> [!NOTE]
> Este tema no se explica cómo editar distribuciones contables, porque esta funcionalidad no se admite actualmente para los escenarios móviles.

-   ¿Los usuarios desearán para ver los datos adjuntos de la factura en el dispositivo?

El diseño de la experiencia móvil de las aprobaciones de facturas variará, en función de las respuestas a estas preguntas. El objetivo es optimizar la experiencia del usuario para el proceso empresarial de móvil de una organización. En el resto de este tema, miraremos dos variaciones del escenario que se basen en varias las respuestas a las preguntas anteriores. 

Como orientación general, al trabajar con el diseñador móvil, asegúrese de “publicar” los cambios para evitar perder las actualizaciones.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Diseño de una situación de ejemplo sencillo de aprobación de facturas para Contoso
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
<td>¿Qué campos del encabezado de factura el usuario deseará para ver en la experiencia móvil, y en qué pedidos?</td>
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
<td>¿Qué campos de las líneas de factura el usuario deseará para ver en la experiencia móvil, y en qué pedidos?</td>
<td><ol>
<li>Categoría de compras</li>
<li>Cantidad</li>
<li>Precio unitario</li>
<li>Importe neto de línea</li>
<li>Importe de la declaración de IRPF</li>
</ol></td>
</tr>
<tr class="odd">
<td>¿Cuántas líneas de factura hay en una factura? Aplica la regla 80-20 aquí, y optimiza para el 80 por ciento.</td>
<td>1</td>
</tr>
<tr class="even">
<td>¿Los usuarios desearán para ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante estudios?</td>
<td>Sí</td>
</tr>
<tr class="odd">
<td>¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura? Una vez más aplica la regla 80-20.</td>
<td>Precio total: Impuestos: 2 Cargos 0: 0</td>
</tr>
<tr class="even">
<td>¿Las facturas también tienen distribuciones contables en el encabezado de factura? ¿En dicho caso estas deben distribuciones contables estar disponible en el dispositivo?</td>
<td>No utilizado</td>
</tr>
<tr class="odd">
<td>¿Los usuarios desearán para ver los datos adjuntos de la factura en el dispositivo?</td>
<td>Sí</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Cree el área de trabajo

1.  En un explorador, las Dynamics 365 abierto para operaciones, y firman en.
2.  Una vez que haya firmado en, Anexar ** &mode=mobile ** la dirección URL como se muestra en el siguiente ejemplo, y actualice la página: https://yoururl/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**&lt;&gt;
3.  Haga clic en ** los valores ** (engranaje) abotone en la parte superior derecha de la página y, a continuación haga clic en ** aplicación móvil **. El diseñador móvil de la aplicación debe aparecer igual que el Grabador de tareas aparece.
4.  Haga clic en ** agregue ** para crear un nuevo espacio de trabajo. Para este ejemplo, asigne un nombre al área de trabajo ** mis ** aprobaciones.
5.  Escribir una descripción.
6.  Seleccione un área de trabajo color. El área de trabajo color se usará para el estilo total de la experiencia móvil de esta área de trabajo.
7.  Seleccione un icono para el espacio de trabajo.
8.  Haga clic en ** hecho **
9.  Haga clic en ** publique el área de trabajo ** para guardar los cambios

### <a name="vendor-invoices-assigned-to-me"></a>Facturas de proveedor asignadas al usuario

La primera página móvil que debe diseñar es la lista de facturas que se asignan al usuario para revisión. Para diseñar esta página móvil, use VendMobileInvoiceAssignedToMeListPage ** ** paginan en Dynamics 365 para las operaciones. Para completar este procedimiento, asegúrese de que al menos una factura de proveedor le se le asigne a revisión, y que la línea de factura tiene dos distribuciones. Esta configuración cumple los requisitos para esta situación.

1.  En Dynamics 365 para la dirección URL de operaciones, reemplace el nombre del elemento de menú con VendMobileInvoiceAssignedToMeListPage ** ** para abrir la versión móvil ** pendientes las facturas de proveedor asignadas a mí ** de la página de lista de los proveedores ** ** el módulo. En función del número de facturas que tiene en el sistema ha asignado a esta página, mostrará dichas facturas. Para encontrar una factura concreta, puede usar el filtro en la parte izquierda. Sin embargo, no requerimos una factura concreta en este ejemplo. Simplemente requerimos cierta factura asignada a las que se van a permitir que se diseñan la página móvil. Las nuevas páginas disponibles se diseñaron específicamente para desarrollar los escenarios móviles para la factura de proveedor. Por lo tanto, debe usar estas páginas. La dirección URL debe como la dirección URL siguiente y, tras la, especifique la página que se muestra en la ilustración debe aparecer: https://yourURL/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile&lt;&gt;[facturas de proveedor pendientes![asignadas a mí página (]. /media/mobile-invoice-approvals01-1024x281.png])(. /media/mobile-invoice-approvals01.png)
2.  Hace clic en ** los valores ** el botón (de engranaje) en la parte superior derecha de la página, haga clic en ** la aplicación móvil **
3.  Seleccione su área de trabajo y clic ** la edición **
4.  Haga clic en ** agregue la página ** para crear la primera página móvil.
5.  Escriba un nombre, por ejemplo ** mis facturas de proveedor **, y descripción, por ejemplo ** las facturas de proveedor asignadas a mí para revisión **.
6.  Click **Done**.
7.  En el diseñador móvil, en ** campos ** la ficha, haga clic en Seleccionar campos ** **. Las columnas de la página de lista deben organismo a la siguiente ilustración. [columnas![en las facturas de proveedor pendientes asignadas a mí página (]. /media/mobile-invoice-approvals02-1024x117.png])(. /media/mobile-invoice-approvals02.png)
8.  Agregar columnas necesarias de la página de lista que se debe mostrar los usuarios en la página móvil. La orden en que se agrega es el orden en que los campos se mostrarán al usuario final. La única forma de cambiar orden de los campos estará reeligiendo todos los campos. Según los requisitos para esta situación, son necesarias los ocho campos siguientes. Sin embargo, algunos usuarios pueden considerar ocho campos demasiada información para tener en un dispositivo móvil. Por lo tanto, mostraremos solamente los campos críticos en el list views móvil. Los campos restantes aparecerán en la vista de detalles que diseñan posteriormente. Por agregaremos ahora, los campos siguientes. Haga clic en el signo más (**+**) en estas columnas de agregar a la página móvil.
    1.  Nombre del proveedor
    2.  Total de la factura
    3.  Cuenta de facturación
    4.  Número de factura
    5.  Fecha de la factura

    Después de que se agreguen los campos, la página móvil debe organismo a la siguiente ilustración. [la página![siguientes campos se agrega] (. /media/mobile-invoice-approvals03.png])(. /media/mobile-invoice-approvals03.png)
9.  También debe agregar ahora las siguientes columnas, de modo que podamos habilitar acciones de flujo posteriormente.
    1.  Muestra la tarea se
    2.  Muestra la tarea de delegado
    3.  Muestra la tarea de memoria
    4.  Muestra la tarea de rechazo
    5.  Muestra la tarea de finalización de la solicitud
    6.  La presentación envía tarea

10. Haga clic en ** hecho ** a salir modo de edición.
11. Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
12. Haga clic en ** publique el área de trabajo ** para guardar el trabajo.
13. ** El permiso total de factura de las facturas de proveedor pendientes ** que aparecen en los parámetros de los proveedores en forma ** ** factura. Tenga en cuenta que, sólo habilitando este parámetro, los totales de factura se calcularán para mostrarse en la página de lista pendiente de las facturas de proveedor. Ésta es una nueva capacidad como parte de la revisión 3208224 del requisito previo.

### <a name="vendor-invoice-details"></a>Detalles de la factura de proveedor

Para diseñar la página de detalles de la factura para el móvil, use VendMobileInvoiceHeaderDetails ** ** paginan en Dynamics 365 para las operaciones. Tenga en cuenta que, en función del número de facturas que tiene en el sistema, las presentaciones de esta página troqueladora antigua la factura (la factura que se creó primero). Para encontrar una factura concreta, puede usar el filtro en la parte izquierda. Sin embargo, no requerimos una factura concreta en este ejemplo. Simplemente requerimos algunos datos de la factura del contenido para que podamos diseñar la página móvil. [página del flujo de trabajo![] (. /media/mobile-invoice-approvals04-1024x425.png])(. /media/mobile-invoice-approvals04.png)

1.  En Dynamics 365 para la dirección URL de las operaciones, sustituyen el nombre del elemento de menú con VendMobileInvoiceHeaderDetails ** ** para abrir el formulario
2.  Abrir el diseñador de móvil ** los valores ** botón de engranaje ().
3.  Haga clic en ** edición ** botón para iniciar el modo de edición en el área de trabajo.
4.  Seleccione ** mis facturas de proveedor ** paginan que ha creado anteriormente, y haga clic en ** ** edición.
5.  ** En los campos ** la ficha, haga clic en ** cuadrícula ** el encabezado de columna.
6.  Haga clic en ** propiedades ** &gt; ** agregue la página **. ** Nota: ** Al hacer clic en ** cuadrícula ** el encabezado y agrega una página, la relación con la página de detalles se establece automáticamente.
7.  Especifique un título de la página, por ejemplo ** los detalles de la factura **, y descripción, por ejemplo ** encabezado de factura de la vista y los detalles de línea **.
8.  Haga clic en ** campos seleccionar **. Tenga en cuenta que, el orden en que se agrega es el orden en que los campos se mostrarán al usuario final. La única forma de cambiar orden de los campos estará reeligiendo todos los campos.
9.  Agregue los siguientes campos de cabecera, en función de los requisitos de este escenario:
    1.  Nombre del proveedor
    2.  Total de la factura
    3.  Cuenta de facturación
    4.  Número de factura
    5.  Fecha de la factura
    6.  Descripción de factura
    7.  Fecha de vencimiento
    8.  Divisa de la factura

10. Agregue los siguientes campos en la cuadrícula de las líneas en la página:
    1.  Categoría de compras
    2.  Cantidad
    3.  Precio unitario
    4.  Importe neto de línea
    5.  Importe de la declaración de IRPF

11. Después de todos los campos de los dos pasos anteriores se han agregado, hace clic ** **. La página debe organismo a la siguiente ilustración. [![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Haga clic en ** hecho ** a salir modo de edición.
13. Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
14. Haga clic en ** publique el área de trabajo ** para guardar el trabajo

### <a name="workflow-actions"></a>Acciones de flujo de trabajo

Para agregar acciones de flujo, use VendMobileInvoiceHeaderDetails ** ** paginan en Dynamics 365 para las operaciones. Para abrir esta página, reemplace el nombre del elemento de menú de la dirección URL, como hizo anterior. A continuación abre el diseñador de móvil ** los valores ** botón de engranaje (). Siga estos pasos para agregar acciones de flujo en la página de detalles.

1.  Haga clic en ** edición ** botón para iniciar el modo de edición en el área de trabajo.
2.  ** Seleccione los detalles de la factura ** paginan que ha creado anteriormente, y haga clic en ** ** edición.
3.  En ** acciones ** la ficha, haga clic en ** agregue la acción **.
4.  Especifique un título de la acción, por ejemplo ** apruebe **, y descripción, por ejemplo ** apruebe la factura **. Tenga en cuenta que el título de la acción que escriba aquí se convierte en el nombre de la acción que se muestra al usuario en la aplicación móvil.
5.  Click **Done**.
6.  Haga clic en ** campos seleccionar **.
7.  Pase con el proceso de flujo de trabajo en VendMobileInvoiceHeaderDetails ** ** la página, y complete la acción que se quiere registrar. Asegúrese de especificar comentarios del flujo de trabajo durante este proceso, para incluir un campo de comentarios en la experiencia móvil.
8.  Una vez que se ejecute la acción del flujo de trabajo, haga clic en ** hecho ** para completar la tarea Seleccionar campos.
9.  Haga clic en ** hecho ** a salir modo de edición.
10. Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
11. Haga clic en ** publique el área de trabajo ** para guardar el trabajo
12. Repita los pasos 3 a 11 para registrar todas las acciones del flujo de trabajo necesarias. Tenga en cuenta que, es un requisito tener facturas asignadas al que se incluyan en una estado para configurar las acciones de flujo a disposición que se va a para diseñar.
13. Abre el Bloc de notas o Microsoft Visual Studio, y pega el código siguiente. Guarde el archivo como un archivo de .js. Este código hacer dos cosas:
    1.  Oculta las columnas relacionadas con el flujo de trabajo adicionales que agregue anterior en la página de lista móvil. Agregamos estas columnas de modo que la aplicación que tenga información de contexto y ponga al paso siguiente.
    2.  Según el paso de flujo que está activa, se aplica lógica para mostrar sólo dichas acciones.

Tenga en cuenta que, el nombre de las páginas y otros controles del código de JS deberían coincidir del espacio de trabajo.

1.  principal de la función (metadataService, dataService, cacheService, $q) {devolución {appInit: función appMetadata) ({controles de la Ocultar de //que necesiten presentes, sólo metadataService.configureControl no visible (“Mi-proveedor- facturas “, “,” ShowAccept ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowApprove ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowReject ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowDelegate ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowRequestChange ocultado: { verdadera});              metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowRecall ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowComplete ocultado: { verdadera});            metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowResubmit ocultado: { verdadera});            }, pageInit: (función pageMetadata, params) ({si facturas detalles de ") == de pageMetadata.Name “{acciones de flujo de presentación o la Ocultar de //basadas en el paso de flujo metadataService.configureAction (acepte “,” {visible: verdadera});                    metadataService.configureAction (“Aprobar,” {visible: verdadera});                    metadataService.configureAction (rechazo “,” {visible: verdadera});                    metadataService.configureAction delegado (“,” {visible: verdadera});                    metadataService.configureAction (“Petición- cambio,” {visible: verdadera});                    metadataService.configureAction (“,” la {visible: verdadera});                    metadataService.configureAction completado (“,” {visible: verdadera});                    metadataService.configureAction (volver a “,” {visible: verdadera});

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

2.  Cargar el archivo del código al área de trabajo seleccionando ** lógica ** la ficha
3.  Haga clic en ** hecho ** a salir modo de edición.
4.  Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
5.  Haga clic en ** publique el área de trabajo ** para guardar el trabajo

### <a name="vendor-invoice-attachments"></a>Datos adjuntos de la factura de proveedor

1.  Hace clic en ** los valores ** el botón (de engranaje) en la parte superior derecha de la página, haga clic en ** la aplicación móvil **
2.  Haga clic en ** edición ** botón para iniciar el modo de edición en el área de trabajo.
3.  ** Seleccione los detalles de la factura ** paginan que ha creado anteriormente, y haga clic en ** ** edición.
4.  Establezca Sí ** gestión de documentos ** de la opción ** ** como se muestra a continuación. ** Nota: ** Si no hay requisitos para mostrar los datos adjuntos del dispositivo móvil, puede dejar esta opción establecida ** ninguna **, que es la configuración predeterminada.
5.  [docmanagement de![] (. /media/docmanagement-216x300.png])(. /media/docmanagement.png)
6.  Haga clic en ** hecho ** a salir modo de edición.
7.  Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
8.  Haga clic en ** publique el área de trabajo ** para guardar el trabajo

### <a name="vendor-invoice-line-distributions"></a>Distribuciones de la línea de factura de proveedor

Los requisitos para este confirmar el escenario habrá que sólo distribuciones de nivel de línea, y que tendrá una factura siempre una única línea. Puesto que esta escenario es simple, la experiencia del usuario en el dispositivo móvil también debe estar en lugar sencillo que el usuario no tienen que explorar en profundidad desde varios niveles para ver distribuciones. Las facturas de proveedor de Dynamics 365 para las operaciones incluyen la opción para mostrar todas las distribuciones del encabezado de factura. Esta es la experiencia que necesitamos para el escenario móvil. Por lo tanto, utilizaremos ** VendMobileInvoiceAllDistributionTree ** paginamos para diseñar esta parte del escenario móvil. 

> [!NOTE] 
> Conocer los requisitos nos ayuda a decida qué página determinada a utilizar y exactamente cómo optimizar la experiencia móvil del usuario cuando diseñar el escenario. En la segunda escenario, utilizaremos una página diferente para mostrar las distribuciones, ya que difieren los requisitos para esa situación.

1.  En la dirección URL, reemplace el nombre del elemento de menú, como hizo antes. La página que aparece como debe a la siguiente ilustración. [![toda la página de distribuciones] (. /media/mobile-invoice-approvals06.png])(. /media/mobile-invoice-approvals06.png)
2.  Abrir el diseñador de móvil ** los valores ** botón de engranaje ().
3.  Haga clic en ** edición ** botón para iniciar el modo de edición en el área de trabajo. ** Nota: ** Se que verá dos nuevas páginas se han creado automáticamente. El sistema crea estas páginas, ya que activado la gestión de documentos en la sección anterior. Puede omitir estas páginas nuevas.
4.  Haga clic en ** agregue la página **.
5.  Especifique un título de la página, por ejemplo ** las estadísticas de la vista **, y descripción, por ejemplo ** las transacciones para la factura **.
6.  Click **Done**.
7.  ** En los campos ** la ficha, haga clic en ** seleccionar los campos **, seleccione los siguientes campos de la página de las distribuciones, y haga clic en ** hecho **:
    1.  Importe
    2.  Divisa
    3.  Cuenta contable

> [!NOTE] 
> No seleccione ** descripción ** la columna de la cuadrícula de las distribuciones, debido a que los requisitos para esta situación confirmaron que el precio total es el único importe que habrá distribuciones por. Por tanto, el usuario no necesitará otro campo determinar el tipo de importe que la distribución es para. Sin embargo, en el escenario siguiente, ** ** usamos esta información, debido a que los requisitos para esa situación especifican qué otros tipos de importe tienen distribuciones (por ejemplo, impuestos).
8.  Haga clic en ** hecho ** a salir modo de edición.
9.  Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
10. Haga clic en ** publique el área de trabajo ** para guardar el trabajo

** Nota: ** ** Al visualizar las estadísticas de la página ** móvil no está vinculada actualmente a las páginas móviles cualquiera de las que hemos diseñado hasta el momento. Dado que el usuario debe poder navegar ** las estadísticas de la vista ** a la página ** los detalles de la factura ** de la página del dispositivo móvil, debemos proporcionar navegación ** los detalles de la factura ** de la página ** las estadísticas de la vista ** a la página. Establecemos esta exploración mediante lógica mediante JavaScript adicional.

1.  Abre el archivo de .js que ha creado anteriormente, y agregar las líneas que se destacan en el código siguiente. Este código hacer dos cosas:
    1.  Ayuda garantía que los usuarios no pueden acceder directamente desde el área de trabajo ** las estadísticas de la vista ** a la página.
    2.  Establece un control de navegación ** los detalles de la factura ** de la página ** las estadísticas de la vista ** a la página.

> [!NOTE] 
> El nombre de las páginas y otros controles del código de JS debe ser igual del espacio de trabajo.

1.  principal de la función (metadataService, dataService, cacheService, $q) {devolución {appInit: función appMetadata) ({controles de la Ocultar de //que necesiten presentes, sólo metadataService.configureControl no visible (“Mi-proveedor- facturas “, “,” ShowAccept ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowApprove ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowReject ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowDelegate ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowRequestChange ocultado: { verdadera});              metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowRecall ocultado: { verdadera});                metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowComplete ocultado: { verdadera});            metadataService.configureControl (“Mi-proveedor- facturas “, “,” ShowResubmit ocultado: { verdadera});                La Ocultar de páginas correspondientes //no aplicable para la metadataService.hideNavigation exploración (“Vista- estadísticas de "); la raíz                //Link para ver metadataService.addLink que ha registrado (“facturas detalles “, “Vista- estadísticas “, “Vista-estadística-NAV- CONTROL “, “visualizar las estadísticas de”, cumplen;)            }, pageInit: (función pageMetadata, params) ({si facturas detalles de ") == de pageMetadata.Name “{acciones de flujo de presentación o la Ocultar de //basadas en el paso de flujo metadataService.configureAction (acepte “,” {visible: verdadera});                    metadataService.configureAction (“Aprobar,” {visible: verdadera});                    metadataService.configureAction (rechazo “,” {visible: verdadera});                    metadataService.configureAction delegado (“,” {visible: verdadera});                    metadataService.configureAction (“Petición- cambio,” {visible: verdadera});                    metadataService.configureAction (“,” la {visible: verdadera});                    metadataService.configureAction completado (“,” {visible: verdadera});                    metadataService.configureAction (volver a “,” {visible: verdadera});

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

2.  Cargar el archivo del código al área de trabajo seleccionando ** lógica ** la ficha sobrescribir el código anterior
3.  Haga clic en ** hecho ** a salir modo de edición.
4.  Haga clic en ** ** y a continuación ** hecho ** salir del área de trabajo
5.  Haga clic en ** publique el área de trabajo ** para guardar el trabajo

### <a name="validation"></a>Validación

Del dispositivo móvil, abra la aplicación, y conectar el Dynamics 365 para la instancia de las operaciones. Asegúrese de tener en firme en la empresa en las facturas de proveedor tenga asignados para revisión. Debería poder realizar las acciones siguientes:

-   Consulte ** mis aprobaciones ** el área de trabajo.
-   Explorar en ** mis aprobaciones ** el área de trabajo y consulte ** mis facturas de proveedor ** la página.
-   Explorar en ** mis facturas de proveedor ** paginan y consulte la lista de facturas que tiene asignados.
-   Explorar en una de las facturas, y ver los detalles y los detalles de línea del encabezado de factura.
-   En la página de detalles, consulte un vínculo al elemento adjunto, y utilice este vínculo para navegar a los datos adjuntos enumerados y para ver los datos adjuntos.
-   En la página de detalles, consulte el vínculo ** las estadísticas de la vista ** en la página, y utilice este vínculo para navegar a la página de las distribuciones y ver distribuciones.
-   En la página de detalles, haga clic en ** las acciones ** el menú en el, y realizar las acciones de flujo aplicables al paso de flujo de trabajo.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Diseño de un escenario compleja de aprobación de facturas para Fabrikam
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
<td>¿Qué campos del encabezado de factura el usuario deseará para ver en la experiencia móvil, y en qué pedidos?</td>
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
<td>¿Qué campos de las líneas de factura el usuario deseará para ver en la experiencia móvil, y en qué pedidos?</td>
<td><ol>
<li>Categoría de compras</li>
<li>Cantidad</li>
<li>Precio unitario</li>
<li>Importe neto de línea</li>
<li>Importe de la declaración de IRPF</li>
</ol></td>
</tr>
<tr class="odd">
<td>¿Cuántas líneas de factura hay en una factura? Aplica la regla 80-20 aquí, y optimiza para el 80 por ciento.</td>
<td>5</td>
</tr>
<tr class="even">
<td>¿Los usuarios desearán para ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante estudios?</td>
<td>Sí</td>
</tr>
<tr class="odd">
<td>¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura? Una vez más aplica la regla 80-20.</td>
<td>Precio total: Impuestos: 2 2 Cargos: 2</td>
</tr>
<tr class="even">
<td>¿Las facturas también tienen distribuciones contables en el encabezado de factura? ¿En dicho caso estas deben distribuciones contables estar disponible en el dispositivo?</td>
<td>No utilizado</td>
</tr>
<tr class="odd">
<td>¿Los usuarios desearán para ver los datos adjuntos de la factura en el dispositivo?</td>
<td>Sí</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Ejercicio

Las variaciones siguientes se pueden realizar para el escenario 1, en función de los requisitos para el escenario 2. Utilice esta sección como ejercicio poder completar para obtener propósitos.

1.  Dado que más líneas de factura se esperan en el escenario 2, los cambios en el diseño siguientes ayudarán a optimizar la experiencia del usuario en el dispositivo móvil:
    1.  En lugar de las líneas de factura de la página de detalles (como en escenario 1), los usuarios pueden elegir para ver las líneas en una página independiente móvil.
    2.  Dado que más de una línea de factura se espera en este escenario, si VendMobileInvoiceAllDistributionTree ** ** la página se utiliza para diseñar la página de distribuciones para el móvil (como en el escenario 1), puede que se confusa para que el usuario correlacione líneas a las distribuciones. Por lo tanto, use VendMobileInvoiceLineDistributionTree ** ** paginan para diseñar la página de distribuciones.
    3.  Por ello, las distribuciones se deben mostrar en el contexto de una línea de factura en esta situación. Por lo tanto, asegúrese de que el usuario puede explorar en una línea para ver la página de las distribuciones. Use la capacidad del vínculo de la página de establecer taladro- por, tal como hizo para la cabecera y las páginas de detalles en el escenario 1.

2.  Dado que esperan más de un tipo de importe en las distribuciones en el escenario 2 (los impuestos, los gastos, etc.), se útil mostrar la descripción del tipo de importe. (Omitimos esta información en el escenario 1).

## <a name="conclusion"></a>Conclusión
La plataforma móvil y las capacidades de la aplicación le permiten diseñar las situaciones móviles que se optimizan para una base de los usuarios de una organización. Según los ejemplos que se proporcionan en este tema, pruebe otras variaciones y crear distintas experiencias que cubran una necesidad específica.


