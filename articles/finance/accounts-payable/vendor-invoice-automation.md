---
title: Automatización de factura de proveedor
description: Este tema explica las funciones disponibles para la automatización completa de las facturas de proveedor, incluso las facturas que incluyen adjuntos.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba986afb5c17c7a317b47d1e9cf4ae57ac29da97
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179839"
---
# <a name="vendor-invoice-automation"></a>Automatización de factura de proveedor

[!include [banner](../includes/banner.md)]

Este tema explica las funciones disponibles para la automatización completa de las facturas de proveedor, incluso las facturas que incluyen adjuntos.

Las organizaciones que desean para agilizar los procesos de proveedores (AP) con frecuencia identifican el procesamiento de facturas como una de las principales áreas de proceso que deben aumentar su eficacia. En muchos casos, estas organizaciones delegan el procesamiento de las facturas de papel en un proveedor de servicios de reconocimiento de caracteres ópticos (OCR) de terceros. A continuación reciben metadatos de la factura que se pueden leer automáticamente junto con una imagen digitalizada de cada factura. Para contribuir a la automatización, se incorpora una solución de recta final para habilitar el consumo de estos artefactos en el sistema de facturación. Ahora esta automatización de "recta final" está habilitada desde el principio a través de una solución de automatización de facturas.

## <a name="solution-context"></a>Contexto de la solución

La solución de automatización de facturas ofrece una interfaz estándar que puede aceptar los metadatos de las facturas para el encabezado de la factura y las líneas de factura, así como los adjuntos aplicables a la factura. Cualquier sistema externo que pueda generar artefactos que cumplan con esta interfaz podrá enviar la información para el procesamiento automático de facturas y adjuntos.

La ilustración siguiente muestra un escenario de integración de ejemplo en el que Contoso colaboró con un proveedor de servicios de OCR para el procesamiento de facturas de proveedor. Los proveedores de Contoso envían las facturas al proveedor de servicios por correo electrónico. Con el procesamiento de OCR, el proveedor de servicios genera metadatos de facturas (encabezado y/o líneas) y una imagen digitalizada de la factura. A continuación, un nivel de integración transforma estas artefactos de modo que se puedan consumir.

![Escenario de integración de ejemplo](media/vendor_invoice_automation_01.png)

Se permiten varias variaciones del escenario ejemplo anterior si se necesita la integración de facturas. La migración de datos es otro caso de uso en el que esta interfaz se puede usar para crear facturas y adjuntos.

### <a name="solution-components"></a>Componentes de la solución

La superficie de la solución consiste en los siguientes componentes:

+ Entidades de datos del encabezado de factura, las líneas de factura y los adjuntos de la factura
+ Procesamiento de excepciones para las facturas
+ Visualizador de adjuntos en paralelo en las facturas

El resto de este tema proporciona descripciones detalladas de estos componentes de la solución.

## <a name="data-entities"></a>Entidades de datos

Un paquete de datos es la unidad de trabajo que debe enviarse para que se puedan crear encabezados de factura, líneas de factura y adjuntos de la factura. Se usarán las siguientes entidades de datos para los artefactos que componen el paquete de datos:

+ Encabezado de factura de proveedor
+ Línea de factura de proveedor
+ Datos adjuntos de documento de factura de proveedor

Los adjuntos del documento de la factura de proveedor son una nueva entidad de datos que se introduce como parte de esta función. Se ha modificado la entidad del encabezado de la factura de proveedor para que admita adjuntos. No se ha modificado la entidad de la línea de factura de proveedor para esta función.

Este tema no ofrece una definición detallada de un paquete de datos. Tampoco explica cómo crear los paquetes de los datos. Para obtener esta información, consulte [Marco de entidades y paquetes de datos](../../dev-itpro/data-entities/data-entities-data-packages.md).

Para generar rápidamente los datos de prueba que incluyen facturas y adjuntos, siga estos pasos.

1. Iniciar sesión en su instancia.
1. Vaya a **Proveedores** > **Facturas** > **Facturas de proveedor pendientes**.
1. Cree las facturas que tengan líneas y adjuntos.

    > [!NOTE]
    > Los adjuntos se deben ser adjuntos de encabezados. Actualmente, la entidad de adjuntos de documentos de facturas de proveedor no admite adjuntos de líneas.

1. Abra el espacio trabajo **Administración de datos** .
1. Cree un trabajo de exportación que incluya el encabezado de la factura de proveedor, la línea de la factura de proveedor y las entidades de adjuntos de documentos de la factura de proveedor.
1. Exporte los datos
1. Descargue los datos exportados como paquete. Ahora puede usar el paquete para importar datos en las instancias de destino con fines de prueba.

### <a name="determining-the-legal-entity-for-an-invoice"></a>Determinar la entidad jurídica de una factura

Las facturas que se importan mediante los paquetes de datos se pueden asociar a la entidad jurídica a la que pertenecen de dos maneras:

+ El trabajo de importación que procesa las facturas las importa en la misma empresa en la que se ha programado el trabajo en el espacio de trabajo **Administración de datos** . Es decir, la empresa del trabajo determina la empresa a la que pertenece la factura.
+ Cuando el paquete de datos que contiene las facturas se envía a Finance, el autor de llamada (es decir, la aplicación de integración que se ejecuta fuera de Finance) pueden explícitamente mencionar el identificador de empresa en la solicitud HTTP. En este caso, el contexto de la empresa en el que el trabajo de procesamiento ejecuta en Finance se anula, y las facturas se importan en la empresa transmitida con la solicitud HTTP.

> [!NOTE]
> Este comportamiento es el comportamiento estándar de gestión de datos. Aquí se explica, en el contexto de las facturas, solo para que sea más completo.

## <a name="exception-processing"></a>Procesamiento de excepciones

En las situaciones en las que las facturas de proveedor se introducen en Finance and Operations a través de la integración, debe haber una forma sencilla de que un miembro del equipo de los proveedores procese las excepciones o facturas que han fallado, y que cree facturas pendientes fuera de facturas que han fallado. Este procesamiento de excepciones para las facturas de proveedor es ahora parte de Finance and Operations.

### <a name="exceptions-list-page"></a>Página de lista de excepciones

La nueva página de lista para las excepciones de facturas está disponible en **Proveedores** > **Facturas** > **Errores de importación** > **Facturas de proveedor que no se han importado**. Esta página muestra todos los registros de encabezado de facturas de proveedor de la tabla de ensayo de la entidad de los datos de encabezado de facturas de proveedor. Tenga en cuenta que puede ver los mismos registros del espacio de trabajo **Administración de datos** , donde también puede efectuar las mismas acciones que se proporcionan en la función de control de excepciones. Sin embargo, la interfaz de usuario que ofrece la función de control de excepciones está optimizada para un usuario funcional.

![Página de lista de excepciones](media/vendor_invoice_automation_02.png)

Esta página de lista incluye los siguientes campos que se incluyen en la incorporación de la información:

+ **Empresa** – La empresa a la que pertenece la factura
+ **Mensaje de error** - El mensaje de error que el marco de gestión de datos emite para explicar por qué la factura no ha podido ser creada
+ **Número** – El número de la factura
+ **Cuenta de facturación**
+ **Nombre** – El nombre del proveedor
+ **Cuenta del proveedor**
+ **Pedido de compra** – El número de pedido de compra de la factura
+ **Fecha de registro**
+ **Fecha de la factura**
+ **Descripción de factura**
+ **Divisa**
+ **Registro**
+ **Referencia de la línea** El identificador que procede del sistema externo

    > [!NOTE]
    > La referencia de la línea no es el identificador de la factura.

Esta página de lista también tiene un panel de vista previa que se puede utilizar de las siguientes formas:

+ Permite ver el mensaje de error completo, de modo que no tiene que expandir la columna **Mensaje de error** en la cuadrícula.
+ Permite ver la lista completa de adjuntos de la factura, si factura tiene adjuntos.

La página de lista admite las siguientes acciones:

+ **Editar** - Abre el registro de excepciones en modo de edición, para que pueda corregir los problemas.
+ **Opciones** - Ofrece acceso a las opciones estándar que están disponibles en las páginas de lista. Puede usar la opción **Agregar al espacio de trabajo** para anclar la página de lista de excepciones en su espacio de trabajo como una lista o mosaico.

### <a name="exception-details-page"></a>Página de detalles de excepciones

Al iniciar el modo de edición, aparece la página de detalles de excepciones de la factura que tiene problemas. Si hay adjuntos, la factura y los adjuntos predeterminados aparecen de forma simultánea en la página de detalles de la excepción.

![Página de detalles de excepciones](media/vendor_invoice_automation_03.png)

En la ilustración anterior, no había ninguna línea para el encabezado de factura de proveedor entrante. Por lo tanto, la sección líneas está vacía.

La página de detalles de excepciones admite la operación siguiente:

+ **Crear factura pendiente** - Después de corregir los problemas en la factura como parte del procesamiento de excepciones, puede hacer clic en este botón para crear la factura pendiente. La creación de facturas pendientes se produce en segundo plano (como operación asincrónica).

### <a name="shared-service-vs-organization-based-exception-processing"></a>Procesamiento de servicio compartido versus procesamiento de excepciones basado en la organización

La página de lista de excepciones admite las construcciones estándar de seguridad que admite el área de trabajo **Administración de datos** para el procesamiento de los registros de ensayo. El trabajo de importación de la factura se puede asegurar de las siguientes formas:

+ Por rol de usuario
+ Por usuario
+ Por entidad jurídica

![Importe el trabajo que está asegurado por el de usuario y la entidad jurídica](media/vendor_invoice_automation_04.png)

Si la seguridad se ha configuro para el trabajo de importación de facturas, la página de lista de excepciones seguirá estos valores. Los usuarios podrán ver solo los registros de excepciones de factura que les permita ver esta configuración.

Por ejemplo, Contoso ha decidido procesar las excepciones de facturas por entidad jurídica. Por lo tanto, la seguridad está configura en el trabajo de importación de la factura de tal manera que un usuario de la entidad jurídica A puede ver solo las excepciones de factura en la entidad jurídica A, mientras que un usuario de la entidad jurídica B puede ver únicamente las excepciones de factura en la entidad jurídica B. Esta configuración permite la segregación de controles para administrar las excepciones de la factura.

Contoso también podría decidir no aplicar ninguna seguridad, de modo que los mismos usuarios puedan procesar las excepciones de factura para todas las entidades jurídicas. Esta configuración permite un escenario de servicios compartidos para la administración de excepciones de factura.

## <a name="side-by-side-attachment-viewer"></a>Visualizador de adjuntos en paralelo

Para ayudar a ver fácilmente los adjuntos de las facturas de proveedor, las siguientes páginas que se utilizan en el proceso de facturación proporcionan ahora un visualizador de adjuntos:

+ **Control de excepciones**
+ Página **Facturas de proveedor pendientes** (también disponibles en el proceso de revisión de facturas)
+ Página de consultas **Diario de facturas** (para las facturas registradas)

A continuación se indica la funcionalidad principal que proporciona el visualizador de adjuntos:

+ Ver todos los tipos de adjuntos que admite la administración de documentos (archivos, imágenes, direcciones URL y notas).
+ Ver los archivos TIFF de varias páginas.
+ Realizar las siguientes acciones en los archivos de imagen:
  + Resaltar partes de la imagen.
  + Bloquear partes de la imagen.
  + Agregar anotaciones a la imagen.
  + Aumentar o reducir la imagen.
  + Panorámica de imagen.
  + Deshacer y rehacer acciones.
  + Adaptar la imagen al tamaño.

> [!NOTE]
> Estas acciones están disponibles solo para los archivos de imagen (JPEG, TIFF, PNG, etc.). Los cambios que realice a una imagen mediante estas acciones se guardan en el archivo de imagen. Actualmente, el visualizador de adjuntos no incluye capacidades de versiones o de auditoría.

### <a name="default-attachment"></a>Adjunto predeterminado

Si una factura de proveedor tiene más de un adjunto, puede establecer uno de los documentos como adjunto predeterminado en la página **Adjuntos** . La opción **Adjuntos predeterminados** es una nueva opción que se ha agregado como parte de esta función. Esta opción también se expone en la entidad de datos de adjuntos de documentos de la factura de proveedor. Por lo tanto, los adjuntos predeterminados se pueden definir con integraciones.

Sólo un documento se puede definir como adjunto predeterminado. Una vez que define un documento como adjunto predeterminado, se muestran automáticamente en el visualizador de adjuntos cuando se abre la factura. Si no define ningún documento como adjunto predeterminado, el visualizador no muestra automáticamente ningún adjunto cuando se abre la factura.

### <a name="showhide-invoice-attachments"></a>Mostrar/ocultar adjuntos de la factura

Un nuevo botón que está disponible en las páginas de consulta **Procesamiento de excepciones**, **Factura pendiente** y **Diario de facturas** permite mostrar u ocultar el visualizador de adjuntos.

### <a name="security"></a>Seguridad

Las siguientes acciones en el visualizador de adjuntos se controlan mediante seguridad basada en roles:

+ Resaltar
+ Bloque
+ Anotación

### <a name="pending-vendor-invoices-page"></a>Página de facturas de proveedor pendientes

Los privilegios siguientes ofrecen acceso de solo lectura o lectura/escritura al visualizador de adjuntos para las acciones de resaltar, bloquear y anotar:

+ **Mantener la imagen de la factura de proveedor** - Este privilegio proporciona acceso de lectura/escritura.
+ **Ver la imagen de la factura de proveedor** - Este privilegio proporciona acceso de solo lectura.

Las siguientes tareas proporcionan acceso de solo lectura o acceso de lectura/escritura al visualizador de adjuntos para dichas acciones:

+ **Mantener facturas de proveedor** - El privilegio de mantener imagen de la factura de proveedor se asigna a este derecho.
+ **Consultar acerca del estado de las facturas de proveedor** - El privilegio de ver imagen de la factura de proveedor se asigna a este derecho.

Los siguientes roles proporcionan acceso de solo lectura o acceso de lectura/escritura al visualizador de adjuntos para dichas acciones:

+ **Funcionario de proveedores** y **Administrador de los proveedores** - El derecho de mantener las facturas de proveedor se asigna a estos roles.
+ **Funcionario de proveedores**, **Administrador de los proveedores**, **Funcionario de pagos centralizados de proveedores**, y **Funcionario de pagos de proveedores** - El derecho de consulta sobre el estado de la factura de proveedor se asigna a estos roles.

### <a name="invoice-exception-details-page"></a>Página de detalles de excepciones de factura

Los privilegios siguientes ofrecen acceso de solo lectura o lectura/escritura al visualizador de adjuntos para las acciones de resaltar, bloquear y anotar.

> [!NOTE]
> Desde el principio, los roles mencionados en esta sección proporcionan acceso de solo lectura a las imágenes de la factura en el visualizador de adjuntos. Si un rol también debe tener acceso de escritura a las imágenes, puede conceder acceso de escritura a dicho rol mediante el privilegio y el derecho que se describe aquí.

+ **Mantener imagen de entidad de encabezado de facturas de proveedor** - Este privilegio proporciona acceso de lectura/escritura a las imágenes de la factura en el visualizador de adjuntos.
+ **Ver imagen de entidad de encabezado de facturas de proveedor** - Este privilegio proporciona acceso de solo lectura a la imagen de la factura en el visualizador de adjuntos.

Los siguientes derechos proporcionan acceso de solo lectura al visualizador de adjuntos para dichas acciones:

+ **Mantener facturas de proveedor** - El privilegio de mantener imagen de entidad de encabezado de facturas de proveedor se asigna a este derecho.

Los siguientes roles proporcionan acceso de solo lectura al visualizador de adjuntos para dichas acciones:

+ **Funcionario de proveedores** y **Administrador de los proveedores** - El derecho de mantener las facturas de proveedor se asigna a estos roles.

De forma predeterminada, si el rol de usuario proporciona derechos de edición en cualquier página, el usuario también tendrá derechos de edición en el visualizador de datos adjuntos para las acciones de resaltar, bloquear y anotar. Sin embargo, si hay escenarios donde un rol específico debe tener derechos de edición en la página pero no en el visualizador de adjuntos, los privilegios necesarios la lista anterior se pueden utilizar para satisfacer este caso.
