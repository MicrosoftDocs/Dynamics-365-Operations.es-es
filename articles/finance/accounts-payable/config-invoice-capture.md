---
title: Configuración de Invoice Capture
description: Este artículo explica cómo configurar la solución Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691185"
---
# <a name="configure-the-invoice-capture-solution"></a>Configuración de Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Después de instalar la solución Invoice capture, debe configurar el entorno. El proceso consta de los siguientes pasos básicos.

1. **Requerido:** Sincronizar las entidades legales de Microsoft Dynamics 365 Finance. Este paso se utiliza para configurar la estructura organizativa en Microsoft Power Platform.
2. **Requerido:** Configura los canales para la importación de imágenes de facturas. La solución admite los siguientes canales:

    - Office 365 Outlook (predeterminado)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Opcional:** Defina grupos de configuración adicionales para el servicio de reconocimiento óptico de caracteres (OCR).
4. **Opcional:** Defina reglas de asignación para la entidad jurídica, la cuenta del proveedor, el artículo y el tipo de adquisición.

Este artículo se centra en los dos pasos necesarios del proceso. Para más información sobre los grupos de configuración, vea [Grupos de configuración de la solución de Invoice Capture ](invoice-capture-config-group.md). Para obtener más información acerca de las reglas de asignación, consulte [Reglas de asignación de soluciones de Invoice Capture ](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Administrar entidades jurídicas

Finance define las entidades jurídicas como organizaciones identificadas mediante el registro con autoridades jurídicas. Las actividades comerciales se realizan y registran en entidades legales separadas. En Microsoft Power Platform, las unidades de negocio, los roles de seguridad y los usuarios están vinculados entre sí de una manera que se ajusta al modelo de seguridad basado en roles.

Las unidades de negocio se utilizan junto con los roles de seguridad para controlar el acceso a los datos. Los usuarios solo ven la información que necesitan para hacer su trabajo. La solución de Invoice Capture  proporciona un espacio de configuración donde puede cargar información básica de entidades legales existentes en Finanzas y administrar aquellas entidades que se crean manualmente. Las entidades legales se utilizan en las facturas de los proveedores y en el control de seguridad.

Cuando se crea una entidad jurídica y se muestra en la vista de lista, se crea automáticamente una unidad de negocio predeterminada que tiene el mismo nombre. Se concede al equipo el rol de seguridad **empleado de cuentas por pagar**. Cuando se importan entidades legales, se importan datos maestros básicos de Finance. Los elementos inexistentes se identificarán por entidad jurídica y se agregarán a la solución de Invoice Capture . El grupo de configuración predeterminado se asigna a nuevas entidades jurídicas.

### <a name="sync-legal-entities"></a>Sincronizar entidades jurídicas

No puede crear entidades jurídicas directamente. Sin embargo, puede sincronizar entidades legales desde Finance. Para sincronizar entidades legales, siga estos pasos.

1. Vaya a **Configuración \> Configuración del sistema \> Administrar entidades legales**.
2. Seleccione **Sincronizar entidades legales** y luego seleccione **Aceptar** en el cuadro de diálogo de confirmación.

Una vez completada la sincronización, se muestra el número de nuevas entidades jurídicas. Las nuevas entidades legales se muestran en la vista de lista. El grupo de configuración predeterminado se asigna a las nuevas entidades jurídicas.

## <a name="configure-invoice-import-channels"></a>Configurar canales de importación de facturas

Los proveedores envían facturas desde diferentes canales (correo electrónico, espacio de trabajo de archivos o portal de facturas) a través de diferentes formatos (papel o imagen). La solución de Invoice Capture  puede manejar diferentes canales y formatos. Se admiten los siguientes tipos:

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

Cuando se crea un canal para una cuenta específica, se construye un flujo automatizado que tiene una plantilla predefinida para monitorear los correos electrónicos o archivos entrantes en la bandeja de entrada o el espacio. Cualquier archivo que tenga una factura válida se puede reconocer y enviar al área de facturas para esperar el procesamiento por parte del empleado de Cuentas por pagar (AP). El archivo adjunto debe estar en formato PDF o de imagen. Las facturas se pueden cargar en la solución de Invoice Capture  según la configuración del canal.

### <a name="create-a-channel"></a>Crear un canal

Si ha importado el paquete de solución adicional (Dynamics 365 Invoice Capture: herramientas de instalación), la conexión predeterminada para Office 365 Outlook está listo para usar. Si desea crear más conexiones para diferentes cuentas de correo electrónico u otros tipos de canales, consulte [Crear conexiones adicionales para canales](invoice-capture-advanced-settings.md#create-additional-connections-for-channels).

Para crear un canal, siga estos pasos.

1. Vaya a **Configuración \> Configuración del sistema \> Canales de configuración**.
2. Seleccione **Nuevo**.
3. Establezca los campos siguientes:

    - Nombre del canal
    - Description
    - Tipo
    - Conexión

Solo se pueden importar a la solución correos electrónicos o archivos que coincidan con los siguientes criterios.

| Tipo               | Configuración  | Más información |
|--------------------|----------------|------------------|
| Office 365 Outlook | Carpeta         | La carpeta de correo electrónico debe estar en el directorio raíz. De forma predeterminada, se usa la carpeta Bandeja de entrada. No se admite una subcarpeta. |
|                    | Filtro de asunto | (Opcional) Una subcadena que debe incluirse en el asunto. |
|                    | De           | (Opcional) La dirección de correo electrónico del remitente o los remitentes. Si especifica varias direcciones, utilice puntos y comas (;) como separadores. |
| SharePoint         | Dirección del sitio   | La URL de la dirección del sitio. |
|                    | Carpeta         | La carpeta en la dirección del sitio. |

### <a name="activate-the-channel"></a>Activar el canal

Cuando se guarda un flujo, los campos muestran el estado del canal y la hora en que se creó. Inicialmente, el campo **Estado** se establece en **Inactivo**. El campo **Motivo del estado** indica que el canal ha sido inicializado y está listo para ser activado.

Para activar el canal, seleccione **Activar**. Los campos **Estado** y **Motivo del estado** se actualizan.

Si no se requiere un canal, puede desactivarlo. Para desactivar un canal, seleccione **Desactivar**. Los campos **Estado** y **Motivo del estado** se actualizan.

### <a name="manage-flows-in-flow-management"></a>Administrar flujos en la gestión de flujos

Puede ver un canal en la página **Canales de configuración** o en la gestión de flujo.

Para ver más detalles, vaya a **Sistema de administración \> Solución por defecto \> Flujos de nubes** y seleccione el flujo de destino. Los detalles que se muestran incluyen conexiones vinculadas, propietarios e historiales de ejecución.

Para sincronizar el estado, seleccione **Comprobar** para confirmar que el estado del canal coincide con el estado del flujo.

Algunos casos de manejo de excepciones se muestran en el campo **Motivo del estado**:

- **Falta la conexión de Dataverse** – El usuario actual no ha creado al menos una  referencia de conexión de **Microsoft Dataverse**.
- **Extraviado** – El flujo que está vinculado al canal se ha eliminado en la gestión de flujos. El canal debe guardarse nuevamente para crear un nuevo canal.
- **Desactivado en la gestión de flujo** – El flujo se ha desactivado en la gestión de flujos y el estado del canal difiere del estado del flujo.
- **Activado en la gestión de flujo** – El flujo se ha activado en la gestión de flujos y el estado del canal difiere del estado del flujo.
- **ocurrió un error inesperado** – El usuario debe confirmar que el sitio es un "Sitio de comunicación" y que la carpeta es "Biblioteca de documentos".
