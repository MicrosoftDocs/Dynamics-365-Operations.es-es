---
title: Revisar información de cobros
description: Este tema explica cómo revisar la información de cobros junto con diferentes opciones de configuración y transacciones de cobros.
author: ShivamPandey-msft
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59fcaef39460761dbe68273aecb5cbff8850ef031d43393277a17d07dd92db3b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778395"
---
# <a name="review-collections-information"></a>Revisar información de cobros

[!include [banner](../../includes/banner.md)]

Este tema explica cómo revisar la información de cobros junto con diferentes opciones de configuración y transacciones de cobros. Este procedimiento usa la empresa de demostración USMF.

## <a name="create-customer-pools"></a>Crear grupos de clientes
1. En el panel de navegación, vaya a **Módulos > Crédito y cobros > Configuración > Secciones de clientes**.
- Use esta página para configurar secciones de clientes, que son consultas que definen un grupo de cuentas de clientes que pueden mostrarse y gestionarse para cobros o procesos de vencimiento. Use las secciones de clientes para filtrar información de la página de lista **Cobros** y de páginas de lista relacionadas. También se pueden usar las secciones de clientes para filtrar las cuentas de cliente que se incluyen al crear instantáneas de vencimientos.  
- También se pueden usar las secciones de clientes para filtrar las cuentas de cliente que se incluyen al crear instantáneas de vencimientos.  
2. Seleccione **Nuevo**.
3. En el campo **Id. de grupo**, escriba un valor.
4. En el campo **Descripción del grupo**, escriba un valor.
5. Haga clic en **Seleccionar criterios de grupo**.
6. En el campo **Criterios**, escriba un valor.
7. Seleccione **Aceptar**.
8. Seleccione **Vista previa de sección de clientes**.

## <a name="create-collections-agents"></a>Crear agentes de cobros
1. En el panel de navegación, vaya a **Módulos > Crédito y cobros > Configuración > Agentes de cobros**.  
- Use esta página para configurar los trabajadores como agentes de cobros y asignarles de manera opcional secciones de clientes. El *agente de cobros* es una persona que trabaja con clientes para asegurarse de que los pagos se cobran a tiempo.  
- Los agentes de cobros configurados en esta página se agregan automáticamente a un equipo de cobros. Si hay un equipo seleccionado en el campo **Equipo** de la página **Parámetros de clientes**, los agentes de cobros se agregarán a dicho equipo. Si no hay un equipo seleccionado, se creará un nuevo equipo automáticamente con el nombre Cobros y los agentes de cobros se agregarán a dicho equipo.  
2. Seleccione el agente desea y después **Agregar** en la página.
3. En el campo **Id. de grupo**, seleccione en el menú desplegable el registro que desee.
4. Active o desactive la casilla **Grupo predeterminado**.
- Active esta opción para incluir todas las secciones de clientes en las listas de filtros para el agente de cobros seleccionado. Si esta opción no está activada, solo las secciones de clientes asignadas al agente de cobros estarán disponibles en las listas de filtros.  

## <a name="create-aging-period-definition"></a>Crear definición período de vencimiento
1. En el panel de navegación, vaya a **Módulos > Crédito y cobros > Configuración > Definiciones de período de vencimiento**.
- Las definiciones de períodos de vencimiento se pueden usar para analizar el vencimiento de las cuentas de cliente y de proveedor, en función de la fecha que se especifique. Cada período de vencimiento que configure para la definición del período de vencimiento se corresponde con una columna de la página de lista, o del formulario o informe cuando se realiza el análisis.  
2. Seleccione **Nuevo**.
3. En el campo **Definición de período de vencimiento**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
- Permite especificar el nombre del período, la unidad y el intervalo para cada período de vencimiento que se va a incluir en la definición del período de vencimiento. La línea que tiene cero (0) en el campo Unidad representa la fecha en la que se ejecuta el análisis. Las líneas inferiores a cero tendrán -1, y las líneas superiores a cero tendrán 1 como entrada predeterminada en el campo Unidad, pero se pueden modificar. Seleccione **Arriba** y **Abajo** para reorganizar las líneas. La línea 0 (cero) no se puede mover.  
- Coloque el puntero donde desee insertar una nueva línea y, a continuación, haga clic en **Agregar**.  
- Seleccione un indicador para representar el período de vencimiento en el formulario y la página de lista **Cobros**. Por ejemplo, puede seleccionar un indicador verde para un período actual, un indicador amarillo para un período de pasados 30 días y un indicador rojo para un período de pasados 90 días.  
- Seleccione la dirección de impresión de la definición del período de vencimiento. Esta selección determina el orden en que aparecen las columnas en el informe de vencimientos del cliente o en el informe de vencimientos del proveedor.  
  - Hacia adelante: permite imprimir las columnas en el mismo orden en el que aparecen los encabezados en la tabla, comenzando por la fila superior.  
  - Hacia atrás: permite imprimir las columnas en el orden inverso al que aparecen los encabezados en la tabla, comenzando por la fila inferior.    

## <a name="setup-collections-parameters"></a>Configurar parámetros de cobros
1. En el panel de navegación, vaya a **Módulos > Crédito y cobros > Configuración > Parámetros de clientes**.
2. Seleccione la pestaña **Cobros**.
3. Expanda o contraiga la sección **Valores predeterminados de cobros**.
- Permite seleccionar una definición de período de vencimiento para la instantánea de vencimiento predeterminada que se va a usar en el formulario **Cobros**.  
- Permite seleccionar un equipo al que se asignan agentes de cobros en el formulario **Agente de cobros**. En la lista solo aparecen los equipos que tengan el tipo de equipo Cobros.  
4. Expanda o contraiga la sección **Cancelación**.
- Permite seleccionar el nombre del diario, que se configura para asientos contables diarios, que desea usar cuando se cancela una transacción mediante el formulario **Cobros** o las páginas de lista relacionadas.  
- Permite seleccionar el código de motivo predeterminado que se debe usar cuando se cancelan transacciones mediante el formulario **Cobros** o las páginas de lista relacionadas.  
- Active esta opción para crear una línea de diario independiente para los importes de impuestos si se crean transacciones de cancelación mediante la página **Cobros** o las páginas de lista relacionadas. Si activa esta opción, podrá realizar con facilidad un seguimiento de los importes de impuestos implicados en las transacciones de cancelación. Puede realizar un seguimiento de los importes de impuestos de manera independiente para ajustar con mayor facilidad la deuda tributaria para el período afectado.  
5. Expanda o contraiga la sección **Plantilla de correo electrónico**.
- Permite seleccionar la plantilla de correo electrónico que se debe usar al enviar un mensaje de correo electrónico mediante la acción **Correo electrónico > Transacciones** para contacto del formulario **Cobros**.  
- Permite seleccionar la plantilla de correo electrónico que se debe usar al enviar un informe de cliente como adjunto a un mensaje de correo electrónico mediante la acción **Correo electrónico > Extracto** para contacto del formulario **Cobros**.  
- Permite seleccionar la plantilla de correo electrónico que se debe usar al enviar un mensaje de correo electrónico mediante la acción **Correo electrónico > Transacciones** para vendedor del formulario **Cobros**.  

## <a name="age-customer-balance"></a>Calcular vencimientos de saldos de clientes
1. En el panel de navegación, vaya a **Módulos > Crédito y cobros > Tareas periódicas > Calcular vencimientos de saldos de clientes**.
- Seleccione una definición de período de vencimiento. El proceso de instantánea de vencimientos hace vencer las transacciones en función de los períodos de vencimiento que se definen en la definición del período de vencimiento seleccionado.  
- Seleccionar una sección de clientes o salir de este campo en blanco para crear una instantánea de vencimientos para todos los clientes. Si una sección de clientes está seleccionada, el proceso de la instantánea de vencimientos solo se aplica a las cuentas de cliente que forman parte de la sección de clientes. La sección de clientes seleccionada debe ser del tipo Instantánea de vencimientos.  
- Seleccionar el tipo de fecha en la que desea basar la instantánea de vencimientos.  
  - Fecha de la transacción: vence cada transacción en función de su fecha de transacción.    
  - Fecha de vencimiento: vence cada transacción en función de su fecha de vencimiento.    
  - Fecha de documento: vence cada transacción en función de la fecha de documento.  
- Seleccionar la fecha para usarla como la fecha actual de la instantánea de vencimientos. Los períodos de vencimiento se calculan en función de esta fecha.    
  - Fecha de hoy: use la fecha del sistema. Use esta opción si el procesamiento se configura para que se produzca en un trabajo por lotes periódico. Si usa esta fecha, el lote periódico se puede ejecutar periódicamente y se usará la fecha del sistema en ese momento.    
  - Fecha seleccionada: use una fecha especificada. Si selecciona esta opción, especifique una fecha de vencimiento.  
2. Seleccione **Aceptar**.

## <a name="view-aged-customer-balances"></a>Ver saldos del cliente vencidos
1. En el panel de navegación, vaya a **Módulos > Crédito y cobros > Cobros > Saldos vencidos**.
- Use esta página de lista para ver saldos de los clientes e importes vencidos por período de vencimiento. Esta información se almacena como una instantánea de vencimientos. Los períodos de vencimiento se determinan por la definición de período de vencimiento que se use. La definición del período de vencimiento se toma de la sección de clientes, si se ha especificado una para la consulta de secciones. Si el grupo de clientes no tiene definición de período de vencimiento, se usará la definición de período de vencimiento predeterminada que se haya especificado en el formulario Parámetros de clientes.  
2. Expanda el cuadro informativo **Contacto**. Aquí puede ver la información de contacto.
- Contacto de cobros del cliente.  
- Persona de ventas predeterminada para el cliente.  
3. Expanda el cuadro informativo **Límite de crédito**.
- Use el cuadro informativo **Información crediticia** para ver la información del saldo actual y del límite de crédito del cliente.  

## <a name="view-customer-collections-details"></a>Ver detalles de cobros de clientes
1. Asegúrese de que el registro deseado está seleccionado.
2. Expanda **Dirección**, **Contacto**, **Vencimiento** y **Límite de crédito** para ver la información especificada.
3. En el panel de acciones, seleccione **Cobrar**.
- Actualizar la instantánea de vencimientos para el cliente, usando la fecha actual como la fecha de antigüedad con la que se comparan las fechas de transacción. Si la instantánea de vencimientos contiene información para varias entidades jurídicas, la instantánea de vencimientos actualizada contiene información para el mismo conjunto de entidades jurídicas. Los importes se almacenan en la divisa de contabilidad de la entidad jurídica en la que ha iniciado sesión al actualizar la instantánea de vencimientos.  
- Seleccione una definición de período de vencimiento. De forma predeterminada, aparece la definición del período de vencimiento asociada con la instantánea de vencimientos para el cliente. La definición del período de vencimiento controla los importes y los períodos de vencimiento que se muestran en los cuadros informativos **Saldos vencidos** e **Información crediticia**.  
- Abre un menú que contiene los siguientes elementos:    
  - Empresa: muestra los importes en los cuadros informativos Saldos vencidos e Información crediticia en la divisa de contabilidad de la entidad jurídica.  
  - Cliente: muestra importes en los cuadros informativos Saldos vencidos e Información crediticia en la divisa del cliente.  
- Seleccionar una o varias entidades jurídicas en la instantánea de vencimientos del cliente para el que desea ver información. Las entidades jurídicas que aparecen en la lista se seleccionaron cuando se creó la instantánea de vencimientos.  
- Ver el extracto del cliente en formato Microsoft Excel. Puede seleccionar una fecha inicial para el intervalo de transacciones que se van a incluir en el informe y decidir si desea incluir solo las transacciones abiertas, o las transacciones abiertas y liquidadas. Si la instantánea de vencimientos contiene información para varias entidades jurídicas, las transacciones se incluyen para todas las entidades jurídicas.  
- Abre el formulario **Documentos**, en el que puede crear o editar documentos o notas.  
4. En el panel de acciones, haga clic en **Comunicar**.  
- Abre Outlook, donde puede enviar un mensaje de correo electrónico al contacto que se especifica en el campo Contacto. Si no se especifica un contacto de cobros, se usa la dirección principal del cliente. Si no se especifica un contacto principal, los mensajes de correo electrónico se enviarán a la primera dirección que aparezca en el formulario **Contactos**. Las transacciones seleccionadas se incluyen como adjunto. El adjunto se encuentra en formato Excel y contiene tres hojas de cálculo. Se puede especificar una plantilla de correo electrónico para los mensajes a los contactos del cliente en el formulario **Parámetros de clientes**.  
- Este botón no está disponible si el contacto seleccionado en este formulario no tiene una dirección de correo electrónico configurada.  
- Preparar un extracto y abrir Outlook, donde puede enviar un mensaje correo electrónico que tenga un extracto vinculado a la dirección especificada en el campo **Contacto**. Si no se especifica un contacto de cobros, se usa la dirección principal del cliente. Si no se especifica un contacto principal, los mensajes de correo electrónico se enviarán a la primera dirección que aparezca en el formulario **Contactos**.  
- Este botón no está disponible si el contacto seleccionado en este formulario no tiene una dirección de correo electrónico configurada.  
- Abre Outlook, donde puede enviar un mensaje de correo electrónico al empleado especificado como el representante de ventas para el grupo de ventas asignado al cliente. Si se seleccionan las transacciones, se incluyen como adjunto. El adjunto se encuentra en formato Excel y contiene dos hojas de cálculo. Se puede especificar una plantilla de correo electrónico para mensajes a los vendedores en el formulario **Parámetros de clientes**.  
- Este botón no está disponible si el vendedor que aparece en este formulario no tiene una dirección de correo electrónico configurada.  
- Permite ver y realizar acciones en las transacciones del cliente. Si usa pagos centralizados, se incluye la información de todas las entidades jurídicas incluidas en la instantánea de vencimientos del cliente. Puede limitar la información de la entidad jurídica seleccionando **Empresa** en el grupo **Seleccionar** del panel de acciones.  
- Cambiar el estado de los cobros para las transacciones seleccionadas.    
  - Sin conflicto: no se ha producido ninguna acción de cobros para la transacción.    
  - Con conflicto: el cliente le ha notificado que hay un problema con la transacción.    
  - Con compromiso de pago: el cliente ha acordado pagar el importe de la transacción.    
  - Resuelto: todos los problemas con la transacción se han solucionado y no es necesaria ninguna acción adicional de cobros.  
- Abra un menú y seleccione uno de los siguientes artículos para especificar qué transacciones desea visualizar en este formulario:    
  - Abrir: mostrar solo las transacciones que no se han liquidado.    
  - Abierto y cerrado: muestre todas las transacciones, las liquidadas y las no liquidadas.  
- Procesar el pago seleccionado como pago de fondos insuficientes (NSF).    
  - Este botón solo está disponible si la transacción seleccionada es un pago (un saldo de crédito sin una factura) especificado en un diario de pago, se asigna una cuenta bancaria a la transacción y el pago no se ha cancelado anteriormente.  
- Cancelar las transacciones seleccionadas.  
- Marcar las transacciones seleccionadas para liquidación entre sí.  
- Abra el formulario **Documento original**, en el que puede ver e imprimir el documento de la transacción seleccionada.  
- Abre un **menú** que contiene los siguientes elementos:    
  - Cobros: muestra únicamente las actividades creadas en el formulario de cobros.    
  - Todas: muestra las actividades para el cliente, independientemente del lugar en que se crearon las actividades.  
- Abre un **menú** que contiene los siguientes elementos:    
  - Abrir: muestra únicamente las actividades que no están cerradas.    
  - Abierto y cerrado: muestra todas las actividades, independientemente de su estado.  
- Seleccione un caso de cobros asignado al cliente o deje este campo en blanco. Si hay un caso seleccionado, solo aparecerán en este formulario las transacciones y las actividades asociadas al caso.  
5. Seleccione **Mostrar lista**.
- Seleccione una cuenta de cliente o acepte la entrada predeterminada. De forma predeterminada esta es la cuenta de cliente seleccionada en la página de lista o en el formulario desde el que abrió este formulario. Si ha abierto el formulario desde una página de lista, los clientes de la lista son los clientes incluidos en la sección de cobros que se usa en la página de lista.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]