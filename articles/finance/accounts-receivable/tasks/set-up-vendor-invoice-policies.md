---
title: Configurar directivas de factura de proveedor
description: En este tema se explica cómo configurar políticas de facturas de proveedor.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f9707c7b283f42729126efa57e890e0df65ca8b
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109765"
---
# <a name="set-up-vendor-invoice-policies"></a>Configurar directivas de factura de proveedor

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo configurar políticas de facturas de proveedor. Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página **Factura de proveedor** y al abrir la página de **infracciones de directiva** de factura de proveedor. También puede configurar el flujo de trabajo de la factura de proveedor para ejecutar las directivas de factura de proveedor cada vez que envíe una factura al flujo de trabajo. 

- Las directivas de facturas de proveedor no se aplican a las facturas creadas en el registro de facturas o el diario de facturas.  
- La validación de conciliación de facturas no usa directivas de factura de proveedor, sino que se configura en la página **Parámetros de proveedores**.  
- Esta grabación usa la empresa de demostración USMF. El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos. Antes de empezar, asegúrese de que la clave de configuración **Conciliación de facturas** esté seleccionada.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Preparación de la creación de directivas de facturas de proveedor
1. Vaya a **Panel de exploración > Módulos > Proveedores > Configuración > Parámetros de proveedores**.
2. Seleccione la pestala **Validación de factura**.
3. Active o desactive la casilla **Actualizar estado de encabezado de factura automáticamente**.
4. Seleccione **Aceptar**.
5. En el campo **Registrar factura con discrepancias**, seleccione una opción.
6. Cierre la página.
7. Vaya a **Panel de navegación > Módulos > Proveedores > Configuración de directivas > Directivas de facturas de proveedor**.
8. Seleccione **Parámetros**.
9. Seleccione **Agregar**.
10. Cierre la página para regresar a la página principal.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Crear tipos de regla de directivas para facturas de proveedor
1. Vaya a **Panel de navegación > Módulos > Proveedores > Configuración de directivas > Tipos de reglas de directivas de facturas de proveedor**.
2. Seleccione **Nuevo**.
3. Escriba valores en los campos **Nombre de regla** y **Descripción**.
4. En el campo **Nombre de consulta**, seleccione el botón de la lista desplegable para abrir la búsqueda y seleccione el registro deseado.
5. Seleccione **Guardar**.
6. Cierre la página para regresar a la página principal.

## <a name="define-a-vendor-invoice-policy"></a>Definir una directiva de facturas de proveedor
1. Vaya a **Panel de navegación > Módulos > Proveedores > Configuración de directivas > Directivas de facturas de proveedor**.
2. Seleccione **Nuevo**.
3. Escriba valores en los campos **Nombre** y **Descripción**.
4. Expanda o contraiga la sección **Organizaciones de directivas**.
5. En el árbol, seleccione **Contoso Entertainment System USA**.
6. Seleccione **Agregar**.
7. Expanda o contraiga la sección **Reglas de directivas**.
8. Seleccione **Crear regla de directivas**.
9. En el campo **Descripción de regla de directivas**, escriba un valor.
10. Seleccione **Filtro**.
11. Seleccione **Agregar**. Seleccione el registro que desee.
12. En **Tabla**, **Tabla derivada** y **Campo**, seleccione o introduzca opciones de los menús desplegables.
13. Cierre la página.
14. En el campo **Criterios**, escriba un valor.
15. Seleccione **Aceptar**.
16. Seleccione **Aceptar**.
17. Cierre las páginas para regresar a la página principal.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
