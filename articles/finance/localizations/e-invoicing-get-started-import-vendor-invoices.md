---
title: Utilizar el servicio de facturación electrónica para importar facturas de proveedores
description: Este tema proporciona información sobre cómo importar facturas de proveedores mediante el servicio de facturación electrónica.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f3b3a27436d32cf25d09f368e4a32018d7559bf6
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983832"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Utilizar el servicio de facturación electrónica para importar facturas de proveedores

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema proporciona información que le ayudará a comenzar con la importación de facturas del proveedor usando el servicio de facturación electrónica. Lo guía a través de los pasos de configuración en Regulatory Configuration Services (RCS), Dynamics 365 Finance y Dynamics 365 Supply Chain Management que debe seguir para recibir facturas electrónicas de proveedor de los proveedores.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Configurar importación de factura de proveedor en RCS
Para configurar la importación de facturas de proveedor en RCS, siga estos pasos:

1. Consulte la lista de [Características de facturación electrónica generalmente disponibles](e-invoicing-configuration-rcs.md#generally-available-features).
2. Seleccione e importe la característica de facturación electrónica. Para obtener más información, consulte [Importar una característica de facturación electrónica desde cualquier proveedor de configuración](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Cree una característica de facturación electrónica para su organización. Para obtener más información, consulte [Crear una característica de facturación electrónica en el proveedor de su organización](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Configurar un canal de cuenta de correo electrónico

Configure un canal de cuenta de correo electrónico si la característica de facturación electrónica que creó importa facturas electrónicas de proveedores de archivos adjuntos que se reciben por correo electrónico.

1. En RCS, seleccione la característica de facturación electrónica que creó. Asegúrese de seleccionar la versión con un estado de **Borrador**.
2. En la pestaña **Configuraciones**, en la cuadrícula, seleccione una configuración de característica y después **Editar**.
3. Sobre la pestaña **Canal de datos** en el grupo de campos **Parámetros**, en el campo **Canal de datos**, ingrese el nombre del canal. El nombre del canal no debe tener más de diez caracteres.
4. A continuación, en el campo **Dirección de servidor**, escriba el proveedor de la cuenta de correo electrónico. Por ejemplo, la dirección del servidor para **https://outlook.live.com/** es **imap-mail.outlook.com**.
5. En el campo **Puerto del servidor**, introduzca el puerto utilizado por el proveedor de la cuenta de correo electrónico. Por ejemplo, el puerto del servidor para **https://outlook.live.com/** es **993**.
6. En el campo **Secreto del nombre de usuario**, introduzca el nombre del secreto de Key Vault que contiene el id. de la cuenta de usuario de correo electrónico. Este secreto debe crearse en el almacén de claves de Azure y configurarse en su entorno de servicio. 
7. En el campo **Secreto de contraseña de usuario**, introduzca el nombre del secreto de Key Vault que contiene la contraseña de la cuenta de usuario de correo electrónico.
8. Opcional: ingrese valores en los campos **Desde filtro**, **Filtro de asunto** y **Filtro de fecha**.
9. Ingrese los nombres de las carpetas del buzón de correo donde estarán los correos:

    - Importado de: **Carpeta principal**
    - Guardado después de un procesamiento exitoso: **Carpeta de archivo**
    - Guardado después de un procesamiento fallido: **Carpeta de errores** No es necesario que cree estas carpetas en el buzón de correo. Las carpetas se crean automáticamente después de la primera importación y procesamiento de la factura electrónica. 
   
10. En el grupo de campos **Filtro de archivos adjuntos**, agregue la información de filtrado de archivos. Solo se procesan los adjuntos que satisfacen el filtro definido. Por ejemplo, puede configurar "\* .xml" para archivos adjuntos con extensión xml. El nombre del archivo adjunto se utiliza en Dynamics 365 Finance o Dynamics 365 Supply Chain Management durante la instalación. 
11. En la pestaña **Reglas de aplicabilidad**, revise y actualice los criterios según sea necesario. El campo **Canal** debe ser igual al **Canal de datos** proporcionado anteriormente. Para obtener más información, consulte [Reglas de aplicabilidad](e-invoicing-configuration-rcs.md#applicability-rules).
12. Seleccione **Guardar** y cierre la página.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Configurar un canal de Microsoft SharePoint

Configure un canal de Microsoft SharePoint si la característica de facturación electrónica importa facturas electrónicas de proveedores desde archivos colocados en carpetas de SharePoint.

1. En RCS, seleccione la característica de facturación electrónica que creó. Asegúrese de seleccionar la **Versión** con el estado **Borrador**.
2. En la pestaña **Configuraciones**, en la cuadrícula, seleccione una configuración de característica y después **Editar**.
3. En la pestaña **Canal de datos** en el grupo de campos **Parámetros**, seleccione **Dirección de SharePoint** e introduzca la URL de SharePoint.
4. Seleccione **Puerto del servidor** e introduzca el puerto utilizado por el proveedor de la cuenta de correo electrónico.
5. Seleccione **Id. de aplicación** e introduzca el nombre del secreto de Key Vault que contiene el id. del cliente de SharePoint.
6. Seleccione **Secreto de aplicación** e introduzca el nombre del secreto de Key Vault que contiene la contraseña del cliente de SharePoint.
7. Seleccione **Filtro de archivo**. Revise y actualice la máscara para filtrar los archivos que contienen la factura electrónica del proveedor para importar.
8. En la pestaña **Reglas de aplicabilidad**, revise y actualice los criterios si es necesario. Para obtener más información, consulte [Reglas de aplicabilidad](e-invoicing-configuration-rcs.md#applicability-rules).
9. Seleccione **Guardar** y cierre la página

### <a name="deploy-an-electronic-invoicing-feature"></a>Implementar una característica de facturación electrónica

Para implementar la función de facturación electrónica, consulte [Implementar la función de facturación electrónica en el entrono de Servicio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Configurar la improtación de facturas electrónicas en Finance o Supply Chain Management
Complete los pasos de las dos secciones siguientes para configurar diferentes tipos de importación de facturas de proveedor.

### <a name="import-brazilian-nf-e-from-email"></a>Importar NF-e de Brasil desde el correo electrónico

1. Inicie sesión en su entorno de Finance o Supply Chain Management y verifique que se encuentra en la entidad jurídica correcta.
2. Vaya a **Administración de la organización** > **Configuración** > **Parámetros de documentos electrónicos**.
3. En la página **Características**, asegúrese de que **NF-e Federal - Factura electrónica brasileña** está seleccionado.
4. En la pestaña **Canales externos**, en el grupo de campos **Canales**, seleccione **Agregar**.
5. En el campo **Canal**, introduzca **NFe** (el nombre del canal dado en la configuración del canal de datos para la característica de Facturación Electrónica en RCS).
6. En el campo **Descripción**, escriba una descripción. En el campo **Empresa**, seleccione la entidad jurídica.
7. En el campo **Contexto del documento**, seleccione **Contexto de documento fiscal: modelo de contexto de factura de cliente**.
8. En el grupo de campos **Importar fuentes**, seleccione **Agregar**.
9. En el campo **Nombre**, introduzca **XmlFile** (el nombre del **Filtro de anexos** dado en la configuración del canal de datos para la característica de Facturación Electrónica en RCS).
10. En el campo **Descripción**, introduzca una descripción y en el campo **Nombre de la entidad de datos**, seleccione **Documentos XML NF-e recibidos**.
11. En el campo **Asignación de modelos**, seleccione **Importación de correo electrónico NF-e – Importación de correo electrónico NF-e (BR)** y seleccione **Guardar**.
12. En la pestaña **Documento electronico**, en el grupo de campos **Informes electrńicos**, seleccione **Añadir** y en el campo **Nombre de tabla**, seleccione **Documento XML NF-recibido**.
13. En el campo **Contexto del documento**, seleccione **Contexto de documento de consulta fiscal: modelo de contexto de factura de cliente**.
14. En el campo **Asignación de modelos de documentos electrónicos**, seleccione **Asignación de consultas: asignación de documentos fiscales**.
15. Seleccione **Tipos de respuesta** y luego seleccione **Nuevo**.
16. En el campo **Tipo de respuesta** , especifique **Respuesta**. En el campo **Estado de envío**, introduzca **Programado**.
17. En el campo **Asignación de modelos**, seleccione **Asignación de modelos del mensaje de respuesta: formato de importación del mensaje de respuesta**.
18. Seleccione **Guardar** y, a continuación, cierre la página.

### <a name="import-peppol-electronic-vendor-invoices"></a>Importar facturas de proveedor de electrónicas PEPPOL

1. Vaya al espacio de trabajo **Informes electrónicos** y seleccione **Configuraciones de informes** .
2. Seleccione **Modelo de contexto de factura de cliente** y luego seleccione **Crear configuración** > **Derivar del nombre: modelo de contexto de factura de cliente, Microsoft** para crear una configuración derivada.
3. En la versión **Borrador**, seleccione **Diseñador** y, en el árbol **Modelo de datos**, seleccione **Asignar modelo a fuente de datos**.
4. En el árbol **Definiciones**, seleccione **DataChannel** y luego seleccione **Diseñador**.
5. En el árbol **Fuentes de datos**, expanda el contenedor **$Context\_Channel**. En el campo **Valor**, seleccione **Editar** e ingrese el nombre del canal de datos. Nombre del canal dado en la configuración del canal de datos para la característica de Facturación Electrónica en RCS. 
7. Seleccione **Guardar** y cierre la página.
8. Cierre la página.
9. Seleccione la configuración derivada que acaba de crear desde el **Modelo de contexto de factura de cliente** y en la ficha desplegable **Versiones**, seleccione **Cambiar estado** > **Terminado**.
10. Vaya a **Administración de la organización** > **Configuración** > **Parámetros de documentos electrónicos** y en la pestaña **Características**, asegúrese de que **Facturas electrónicas de PEPPOL Global** está seleccionado. 
11. En la pestaña **Canales externos**, en el grupo de campos **Canales**, seleccione **Agregar**.
12. En el campo **Canal**, ingrese el nombre del canal de datos y en el campo **Descripción**, ingrese una descripción.
13. En el campo **Empresa**, seleccione la entidad jurídica. 
14. En el campo **Contexto del documento**, seleccione la nueva configuración derivada del **Modelo de contexto de factura de cliente**. La descripción del mapeo debe ser **Contexto del canal de datos**.
15. En el grupo de campos **Importar fuentes**, seleccione **Agregar**.
16. En el campo **Nombre**, introduzca **Nombre del filtro de archivos adjuntos** y en el campo **Nombre de la entidad de datos**, seleccione **Encabezado de la factura del proveedor**.
17. En el campo **Mapeo de modelos**, seleccione **Imprt factura de proveedor - Importar factura de proveedor**.
18. Haga clic en **Guardar** y, a continuación, cierre la página.


## <a name="receive-electronic-invoices"></a>Recibir facturas electrónicas

El servicio de facturación electrónica realiza dos pasos durante la importación de facturas desde los canales de datos:

1. Accede a la casilla de correo y lee el correo electrónico.
2. Procesa los correos electrónicos. 
    
Para realizar estos dos pasos, el cliente debe llamar al servicio manualmente para cada paso. Sin embargo, le recomendamos que configure el lote para recibir documentos electrónicos.

Para recibir facturas electrónicas, siga estos pasos:

1. Vaya a **Administración de la organización** > **Periódico** > **Documentos electrónicos** > **Recibir documentos electrónicos**.
2. Seleccione **Aceptar** y, a continuación, cierre la página.


## <a name="view-receive-logs-for-electronic-invoices"></a>Ver registros de recepción de facturas electrónicas

Para ver los registros de recepción de facturas electrónicas, vaya a **Administración de la organización** > **Periódico** > **Documentos electronicos** > **Registro de recepción de documentos electrónicos**.
Si no ve las facturas procesadas correctamente, elimine el filtro de la tabla.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
