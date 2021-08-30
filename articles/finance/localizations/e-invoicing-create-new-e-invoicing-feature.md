---
title: Crear una nueva característica de facturación electrónica
description: En este tema se explica cómo crear una nueva función de facturación electrónica cuando no hay ninguna función configurable disponible para su país o región lista para usar.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744944"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Crear una nueva característica de facturación electrónica

[!include [banner](../includes/banner.md)]

En este tema se explica cómo crear una nueva función de facturación electrónica cuando no hay ninguna función configurable disponible para su país o región lista para usar.

Para crear una nueva característica de facturación electrónica, complete estas tareas:

1. Cree una nueva configuración de formato de archivo utilizando la configuración del modelo de factura que se proporciona y aprovechando la asignación de factura existente para la función que desea crear.
2. Agregue las configuraciones de formato de archivo a las configuraciones de características de facturación electrónica.
3. Crear la configuración de la característica de facturación electrónica.
4. Complete la nueva característica de facturación electrónica y publíquela en el repositorio global de su organización.
5. Implemente la nueva característica de facturación electrónica en el entorno del servicio.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Cree nuevas configuraciones de formato de archivo que se deriven del modelo de factura existente

En este procedimiento, creará las configuraciones de formato de archivo que se requieren para la nueva característica de facturación electrónica que desea crear. Puede crear la configuración de formato de archivo de factura electrónica y cualquier otra configuración de formato de archivo que su nueva característica de facturación electrónica pueda requerir.

Antes de comenzar este procedimiento, inicie sesión en su cuenta de Regulatory Configuration Service (RCS).

1. En Microsoft Dynamics 365 Finance, en el espacio de trabajo **Informes electrónicos**, seleccione **Repositorios** para el proveedor de configuración de **Microsoft**.
2. Seleccione **Global**, seleccione **Abrir** y luego, en el panel izquierdo, seleccione la configuración **Modelo de factura**.

    > [!IMPORTANT]
    > Para Brasil, seleccione la configuración del modelo **Documentos fiscales**.

3. En la pestaña **Configuraciones**, seleccione **Importar**.
4. Cierre la página.
5. Cierre la página.
6. Seleccione el icono **Configuraciones de informes** y, a continuación, seleccione el modelo de factura que importó.
7. Seleccione **Crear configuración** y luego seleccione **Formato basado en el modelo de contexto de factura**.
8. Especifique un nombre y una descripción para la configuración de formato.
9. En el campo **Tipo de formato**, seleccione el tipo de extensión del archivo.
10. Seleccione **Crear configuración** y luego seleccione la configuración de formato que ha creado.
11. Seleccione **Diseñador** y utilice la herramienta de diseño de formato para configurar el diseño del archivo de modo que cumpla con las especificaciones de formato de archivo.
12. Cierre la página.
13. En la pestaña **Versiones**, seleccione **Cambiar estado** \> **Completar**.
14. Seleccione **Cambiar Estado** \> **Compartir** para publicar la configuración de formato en el repositorio global.

La nueva configuración de formato de archivo debe compartirse con el dominio de Microsoft antes de que el servicio de facturación electrónica pueda consumir la configuración.

1. Seleccione la configuración de formato en la que está trabajando. El estado de la configuración debe ser **Compartido**.
2. En la pestaña **Versiones**, seleccione **Uso compartido avanzado** \> **Repositorio global**.
3. En la pestaña, **Compartido con**, seleccione **Organización**.
4. En el campo **Parámetros**, introduzca **Microsoft.com** para compartir la configuración de formato con el dominio de Microsoft.
5. Seleccione **Aceptar**.

## <a name="create-the-new-electronic-invoicing-feature"></a>Crear la nueva característica de facturación electrónica

1. En RCS, en el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
2. Seleccione **Añadir** y, a continuación, **Nueva característica**.
3. Especifique un nombre y una descripción para la característica de facturación electrónica.
4. Seleccione **Crear característica**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Agregar configuraciones de característica de facturación electrónica

1. Seleccione la característica de facturación electrónica en la que está trabajando.
2. En la pestaña **Configuraciones**, seleccione **Añadir**.
3. En la cuadrícula **Configuraciones**, explore y seleccione las configuraciones de formato de archivo que su característica de facturación electrónica requiere para generar el archivo de factura electrónica.
4. Seleccione **Aceptar**.

## <a name="add-electronic-invoicing-feature-setups"></a>Agregar configuraciones de característica de facturación electrónica

1. En la pestaña **Configuraciones**, seleccione **Añadir** y luego seleccione **Configuración personalizada**.
2. Especifique un nombre y una descripción para la configuración.
3. En el campo **Tipo de configuración**, seleccione **Canalización del proceso**.
4. Seleccione **Crear**.
5. Seleccione la configuración en la que está trabajando y, a continuación, seleccione **Editar**.
6. En la pestaña **Canalización del proceso**, seleccione **Nueva** para añadir una acción de canalización. Para obtener más información sobre canalizaciones, consulte [Acciones](e-invoicing-configuration-rcs.md#actions).
7. En la pestaña **Reglas de aplicabilidad**, seleccione **Nueva** para añadir cláusulas de reglas de aplicabilidad. Para obtener más información acerca de las reglas de aplicabilidad, consulte [Reglas de aplicabilidad](e-invoicing-configuration-rcs.md#applicability-rules).
8. En la pestaña **Variables**, seleccione **Nueva** para agregar variables según sea necesario.
9. Seleccione **Guardar** y luego seleccione **Validar** para comprobar la coherencia de la configuración.
10. Cierre la página.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Implemente la característica de facturación electrónica en el entorno del servicio

Para obtener información sobre cómo completar esta tarea, consulte [Implementar la característica de facturación electrónica en el entorno de servicio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Implementar la característica de facturación electrónica en una aplicación conectada

Para obtener información sobre cómo completar esta tarea, consulte [Configurar los ajustes de la aplicación](e-invoicing-get-started.md#configure-the-application-setup) e [Implementar la característica de facturación electrónica en la aplicación conectada](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
