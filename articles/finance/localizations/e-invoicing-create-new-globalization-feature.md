---
title: Crear una característica de globalización
description: En este artículo se explica cómo crear una característica de Globalización.
author: gionoder
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5432de8f8a70a4e6a0facd546083b37fd8690556
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283187"
---
# <a name="create-a-globalization-feature"></a>Crear una característica de globalización

[!include [banner](../includes/banner.md)]

Puede crear una característica de facturación electrónica desde cero o basarla en una característica existente. Al crear una característica desde cero, debe agregar manualmente las configuraciones de Informes electrónicos (ER) y otros componentes, como los detalles de la configuración de características y la configuración de aplicaciones. Cuando crea una característica que se basa en una característica existente, la nueva característica hereda todas las configuraciones y parámetros de la característica base. Puede revisar lo que se copia de la característica base a la nueva característica.

## <a name="create-a-feature-from-scratch"></a>Crear una característica desde cero

En esta sección se explica cómo crear una nueva característica de facturación electrónica cuando no hay ninguna característica de Globalización disponible en el repositorio Global para sus escenarios empresariales listos para usar.

Para crear una característica de facturación electrónica, siga estos pasos.

1. Inicie sesión en su cuenta del Servicio de configuración reguladora (RCS).
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. Seleccione **Agregar** y luego, en el cuadro de diálogo desplegable, seleccione la opción **Nueva característica**.
4. Especifique un nombre y una descripción para la característica de facturación electrónica.
5. Seleccione **Crear característica**. La primera versión de la nueva característica aparece en el lado derecho de la página y tiene un estado de **Borrador**.

    A continuación, debe agregar configuraciones de ER y configuraciones de características. Para agregar configuraciones de formato ER nuevas o existentes, asegúrese de que existan en su repositorio RCS local.

6. Seleccione la característica de facturación electrónica en la que está trabajando.
7. En la pestaña **Configuraciones**, seleccione **Añadir**.
8. En la cuadrícula **Configuraciones**, busque y seleccione las configuraciones de formato que se requieren para la canalización de procesamiento (por ejemplo, para generar archivos de facturas electrónicas o procesar respuestas de servicios web externos).
9. Seleccione **Aceptar**. Ahora puede usar las configuraciones en acciones de la canalización de procesamiento. Para obtener más información, consulte [Trabajar con configuraciones](e-invoicing-work-configurations.md).
10. Para agregar una configuración de características de facturación electrónica, créela en la pestaña **Configuraciones** de la página **Nueva característica**. Para obtener más información, consulte [Trabajar con configuraciones de características](e-invoicing-feature-setup.md).
11. Complete la configuración e implemente la característica de facturación electrónica en el entorno del servicio. Para obtener más información, consulte [Completar, publicar e implementar una característica de globalización](e-invoicing-complete-publish-deploy-globalization-feature.md).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Cree configuraciones de formato de archivo que se deriven del modelo de factura existente

Puede omitir esta sección si no tiene que crear configuraciones de ER, pero puede reutilizar las versiones existentes como base.

Este procedimiento muestra cómo crear las configuraciones de formato de archivo que se requieren para la nueva característica de facturación electrónica que desea crear. Cree la configuración de formato de archivo de factura electrónica y cualquier otra configuración de formato de archivo que su nueva característica de facturación electrónica requiera.

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Informe electrónico**, seleccione el mosaico **Configuraciones de informes** .
3. Seleccione el **Modelo de factura** o, para escenarios brasileños, seleccione el **Modelo fiscal**.
4. Seleccione **Crear configuración** y, a continuación, en el cuadro de diálogo desplegable, seleccione la opción **Formato basado en factura de modelo de datos**.
5. Especifique un nombre y una descripción para la configuración de formato.
6. En el campo **Tipo de formato**, seleccione el tipo de extensión del archivo.
7. En el campo **Definición del modelo de datos**, seleccione la estructura raíz al que asignar el formato. Por ejemplo, **InvoiceCustomer** se utiliza para los formatos de factura de cliente.
8. Seleccionar **Crear configuración**.
9. Seleccione la nueva configuración de formato.
10. Seleccione **Diseñador** y utilice la herramienta de diseño de formato para configurar el diseño del archivo de modo que cumpla con las especificaciones de formato de archivo.
11. Cierre la página.
12. En la pestaña **Versiones**, seleccione **Cambiar estado** \> **Completar**.
13. Seleccione **Cambiar Estado** \> **Compartir** para publicar la configuración de formato en el repositorio global.

Las nuevas configuraciones de formato de archivo deben compartirse con el dominio de Microsoft para que pueda consumirlas el servicio de facturación electrónica.

1. Seleccione la configuración de formato en la que está trabajando. El estado de la configuración debe ser **Compartido**.
2. En la pestaña **Versiones**, seleccione **Uso compartido avanzado** \> **Repositorio global**.
3. En la pestaña, **Compartido con**, seleccione **Organización**.
4. En el campo **Parámetros**, introduzca **microsoft.com** para compartir la configuración de formato con el dominio de Microsoft.
5. Seleccione **Aceptar**.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Crear una característica que se base en una característica existente

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En el campo **Proveedor de configuración**, asegúrese de que su proveedor de configuración activo está seleccionado. De esta forma, la nueva característica de facturación electrónica aparecerá en la lista una vez creada. Si su proveedor de configuración activo no está seleccionado, la nueva característica se excluirá de la lista.
4. Seleccione **Añadir** y luego, en el cuadro de diálogo desplegable, seleccione la opción **Basado en la versión existente**.
5. Especifique un nombre y descripción para la característica.
6. En el campo **Característica base**, seleccione la versión base de la característica.
7. Seleccione **Crear característica**. La característica que crea y tiene un estado de **Borrador**.
8. Revise los componentes de la característica para determinar si se requieren actualizaciones:

    - Revise las configuraciones, en caso de que deba personalizar los formatos de informes electrónicos y su vínculo con asignaciones de formatos para la versión de la característica.
    - Revise la configuración, en caso de que deba personalizar la pestaña **Acciones**, la pestaña **Reglas de aplicabilidad** o la pestaña **Variables** para la versión de la característica.

9. Complete la configuración e implemente la característica de facturación electrónica en el entorno del servicio. Para obtener más información, consulte [Completar, publicar e implementar una característica de globalización](e-invoicing-complete-publish-deploy-globalization-feature.md).
