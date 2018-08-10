---
title: "Importar catálogo de proveedores"
description: "En este tema se describe el proceso para importar datos de catálogos de proveedores."
author: mkirknel
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.search.region: Global
ms.search.industry: 
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ac7754bd6361ad74f7ab4d564ae3114dd4b9f165
ms.openlocfilehash: caf801ea27ade63c24bb0907313e7f8294c50702
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2018

---

# <a name="import-vendor-catalogs"></a>Importar catálogo de proveedores
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Importación de catálogos de proveedores

En Microsoft Dynamics 365 for Finance and Operations, los encargados de compras pueden crear y mantener catálogos que los empleados de las empresas pueden utilizar cuando piden servicios y artículos para su uso interno. Para crear un catálogo de compras, puede agregar los artículos y servicios que desea poner a disposición de los empleados, ya sea importando los datos del catálogo de productos o agregando manualmente los datos del catálogo de productos al producto maestro. 

Puede cargar los datos del catálogo enviados por un proveedor del cliente de Microsoft Dynamics 365.

Los datos de producto que le envía un proveedor, con el formato de un archivo de solicitud de mantenimiento del catálogo (CMR), debe estar en formato de archivo XML. El archivo de CMR debe contener los detalles de los productos que el proveedor proporciona a su compañía.

## <a name="import-vendor-catalog-data"></a>Importar datos de catálogos de proveedores

Para importar datos de catálogos de proveedores, debe completar las tareas siguientes:

1.  Configure un proyecto en el espacio de trabajo de administración de datos donde ha definido sus reglas de asignación de datos. Seleccione **Administración de datos** y luego seleccione **Configurar roles para proyectos de datos**. 

2.  Configurar una jerarquía de categorías de compras y asignar sus proveedores a categorías de compras. Si usa códigos de mercancías, agregue los códigos de mercancías a las categorías de compra. Para obtener información sobre la configuración de una jerarquía de categorías de compras, consulte [Configurar una jerarquía de categorías de compras](../procurement/tasks/set-up-procurement-category-hierarchy.md)

3.  Configurar el proveedor para la importación de catálogos. Seleccione un proveedor y, a continuación, seleccione **Adquisición** > **Configurar** > **Configurar proveedor para importación de catálogo**.

4.  Configurar el flujo de trabajo para la importación de catálogos. Cree una plantilla del archivo de CMR y compártala con el proveedor.

5.  Seleccione **Adquisición y abastecimiento** \> **Común** \> **Catálogos** \> **Catálogos de proveedores** para crear un catálogo de proveedores. Los archivos de solicitud de mantenimiento del catálogo (CMR) que recibe del proveedor se agrupan en este catálogo. 

6.  Cargar el archivo de CMR.

7.  Revisar, aprobar o rechazar los productos del catálogo de proveedores. Los productos se asignan automáticamente a las categorías de compras de Dynamics 365 for Finance and Operations. 
    
Los productos aprobados se agregan al producto maestro y se liberan en las entidades jurídicas seleccionadas. Solo se pueden agregar productos aprobados al catálogo de compras.

## <a name="generate-a-catalog-import-file-template"></a>Generar una plantilla del archivo de importación de catálogos

La plantilla del archivo de importación de catálogos es un archivo XSD que se usa para crear un archivo de CMR para los productos de un proveedor. Puede usar el archivo de CMR para crear un nuevo catálogo, o sustituir o modificar un catálogo existente.

1.  Seleccione **Adquisición y abastecimiento** \> **Catálogos** \> **Catálogos de proveedores** y haga doble clic en el catálogo con el que desea trabajar.

2.  Descargue una plantilla actual de importación de catálogos (archivo XSD). En la página **Actualizar catálogo**, en el **Panel de acciones**, en la pestaña **Catálogos**, en el grupo **Información relacionada** , haga clic en **Generar plantilla de catálogo** y seleccione **Categoría de compras**.

    -   Con la opción **Categoría de compras** puede generar una plantilla de catálogo que incluya las categorías de compras en las que el proveedor tenga autorización para proporcionar sus productos.

3. En el cuadro de diálogo **Guardar como**, seleccione la ubicación en la que desea almacenar la plantilla del archivo de catálogo y guarde el archivo.

Para obtener más información y ver ejemplos, consulte esta entrada de blog: [Catálogos de proveedor en Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).

