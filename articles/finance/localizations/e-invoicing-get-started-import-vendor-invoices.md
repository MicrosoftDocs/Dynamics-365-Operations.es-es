---
title: Utilizar el servicio de facturación electrónica para importar facturas de proveedores
description: Este tema proporciona información sobre cómo importar facturas de proveedores mediante el servicio de facturación electrónica.
author: gionoder
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 434bf1f6a5a727a71592493b85ab166cbeff2f0980c2c968c99973a03f4dc660
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751261"
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
3. En la pestañ **Canal de datos** en el grupo de campos **Parámetros**, seleccione **Dirección del servidor** e introduzca el proveedor de la cuenta de correo electrónico.
4. Seleccione **Puerto del servidor** e introduzca el puerto utilizado por el proveedor de la cuenta de correo electrónico.
5. Seleccione **Secreto del nombre de usuario** e introduzca el nombre del secreto de Key Vault que contiene el id. de la cuenta de usuario de correo electrónico.
6. Seleccione **Secreto de la contraseña de usuario** e introduzca el nombre del secreto de Key Vault que contiene la contraseña de la cuenta de usuario de correo electrónico.
7. Seleccione **Filtro de asunto**. Revise y actualice la cadena que contiene el asunto del correo electrónico predeterminado para identificar el correo electrónico que contiene la factura electrónica del proveedor para importar.
8. En la pestaña **Reglas de aplicabilidad**, revise y actualice los criterios si es necesario. Para obtener más información, consulte [Reglas de aplicabilidad](e-invoicing-configuration-rcs.md#applicability-rules).
9. Seleccione **Guardar** y cierre la página.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Configurar un canal de Microsoft SharePoint

Configure un canal de Microsoft SharePoint si la característica de facturación electrónica importa facturas electrónicas de proveedores desde archivos colocados en carpetas de SharePoint.

1. En RCS, seleccione la característica de facturación electrónica que creó. Asegúrese de seleccionar la **Versión** con el estado **Borrador**.
2. En la pestaña **Configuraciones**, en la cuadrícula, seleccione una configuración de característica y después **Editar**.
3. En la pestañ **Canal de datos** en el grupo de campos **Parámetros**, seleccione **Dirección de SharePoint** e introduzca la URL de SharePoint.
4. Seleccione **Puerto del servidor** e introduzca el puerto utilizado por el proveedor de la cuenta de correo electrónico.
5. Seleccione **Id. de aplicación** e introduzca el nombre del secreto de Key Vault que contiene el id. del cliente de SharePoint.
6. Seleccione **Secreto de aplicación** e introduzca el nombre del secreto de Key Vault que contiene la contraseña del cliente de SharePoint.
7. Seleccione **Filtro de archivo**. Revise y actualice la máscara para filtrar los archivos que contienen la factura electrónica del proveedor para importar.
8. En la pestaña **Reglas de aplicabilidad**, revise y actualice los criterios si es necesario. Para obtener más información, consulte [Reglas de aplicabilidad](e-invoicing-configuration-rcs.md#applicability-rules).
9. Seleccione **Guardar** y cierre la página

### <a name="deploy-an-electronic-invoicing-feature"></a>Implementar una característica de facturación electrónica

Para implementar la función de facturación electrónica, consulte [Implementar la función de facturación electrónica en el entrono de Servicio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-and-supply-chain-management"></a>Configurar la improtación de facturas electrónicas en Finance y Supply Chain Management
Complete los pasos de las dos secciones siguientes para configurar diferentes tipos de importación de facturas de proveedor.

### <a name="import-vendor-invoices-from-email"></a>Importar facturas de proveedores desde el correo electrónico

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
2. Seleccione **Modelo de contexto de factura de cliente** y cree una configuración derivada.
3. En la versión **Borrador**, seleccione **Diseñador**.
4. En el árbol **Modelo de datos**, seleccione **Factura del cliente** y luego seleccione **Asignar modelo a fuente de datos**.
5. En el árbol **Definiciones**, seleccione **Factura del cliente** y luego seleccione **Diseñador**.
6. En el árbol **Orígenes de datos**, seleccione **Contexto\_Canal**. En el campo **Valor**, seleccione **PEPPOL**. Nombre del canal dado en la configuración del canal de datos para la característica de Facturación Electrónica en RCS. 
7. Seleccione **Guardar** y cierre la página.
8. Cierre la página.
9. Seleccione **Modelo de contexto de factura de cliente** y en la ficha desplegable **Versiones**, seleccione **Cambiar Estado** > **Terminado**.
10. Vaya a **Administración de la organización** > **Configuración** > **Parámetros de documentos electrónicos** y en la pestaña **Características**, asegúrese de que **Facturas electrónicas de PEPPOL Global** está seleccionado. 
11. En la pestaña **Canales externos**, en el grupo de campos **Canales**, seleccione **Agregar**.
12. En el campo **Canal**, introduzca **PEPPOL**. En el campo **Descripción**, escriba una descripción.
13. En el campo **Empresa**, seleccione la entidad jurídica. En el campo **Contexto del documento**, seleccione **Contexto de factura del cliente: modelo de contexto de factura de cliente**.
14. Seleccione **Guardar** y, a continuación, cierre la página.


## <a name="receive-electronic-invoices"></a>Recibir facturas electrónicas
Para recibir facturas electrónicas, siga estos pasos:

1. Vaya a **Administración de la organización** > **Periódico** > **Documentos electrónicos** > **Recibir documentos electrónicos**.
2. Seleccione **Aceptar** y, a continuación, cierre la página.

## <a name="view-receive-logs-for-electronic-invoices"></a>Ver registros de recepción de facturas electrónicas

Para ver los registros de recepción de facturas electrónicas, vaya a **Administración de la organización** > **Periódico** > **Documentos electronicos** > **Registro de recepción de documentos electrónicos**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
