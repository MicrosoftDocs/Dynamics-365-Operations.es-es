---
title: Investigar y resolver excepciones
description: Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ff53198f61e1d1af3c437e9488c2a246cf820a
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "8110028"
---
# <a name="research-or-resolve-exceptions"></a>Investigar y resolver excepciones

[!include [banner](../../includes/banner.md)]

Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página **Factura de proveedor** y al abrir la página de **infracciones de directiva** de factura de proveedor. También puede configurar el flujo de trabajo de la factura de proveedor para ejecutar las directivas de factura de proveedor cada vez que envíe una factura al flujo de trabajo. 

Las directivas de facturas de proveedor no se aplican a las facturas creadas en el **registro de facturas** o el **diario de facturas**. 

La validación de conciliación de facturas no usa directivas de factura de proveedor, sino que se configura en la página **Parámetros de proveedores**.

Esta grabación usa la empresa de demostración USMF. El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos. Antes de empezar, asegúrese de que la clave de configuración **Conciliación de facturas** esté seleccionada.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Preparación de la creación de directivas de facturas de proveedor
1. Vaya a **Proveedores > Configuración > Parámetros de proveedores**.
2. Haga clic en la ficha **Validación de factura**.
3. Active o desactive la casilla **Actualizar estado de encabezado de factura automáticamente**.
4. Haga clic en **Aceptar**.
5. En el campo **Registrar factura con discrepancias**, seleccione una opción.
6. Cierre la página.
7. Vaya a **Proveedores > Configuración de directivas > Directivas de facturas de proveedor**.
8. Haga clic en **parámetros**.
9. Haga clic en **Agregar**.
10. Cierre la página.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Crear tipos de regla de directivas para facturas de proveedor
1. Vaya a **Proveedores > Configuración de directivas > Regla de directivas de facturas de proveedor**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre de regla**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Nombre de consulta**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en **Guardar**.
9. Cierre la página.

## <a name="define-a-vendor-invoice-policy"></a>Definir una directiva de facturas de proveedor
1. Vaya a **Proveedores > Configuración de directivas > Directivas de facturas de proveedor**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Expanda o contraiga la sección **Organizaciones de directivas**.
6. En el árbol, seleccione "Contoso Entertainment System USA".
7. Haga clic en **Agregar**.
8. Expanda o contraiga la sección **Reglas de directivas**.
9. Haga clic en **Crear regla de directivas.**
10. En el campo **Descripción de regla de directivas**, escriba un valor.
11. Haga clic en **Filtro.**
12. Haga clic en **Agregar**.
13. En la lista, marque la fila seleccionada.
14. En el campo **Tabla**, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. En el campo **Tabla derivada**, haga clic en el botón desplegable para abrir la búsqueda.
17. En la lista, haga clic en el vínculo de la fila seleccionada.
18. En el campo **Campo**, haga clic en el botón desplegable para abrir la búsqueda.
19. En el campo **Campo**, escriba un valor.
20. Cierre la página.
21. En el campo **Criterios**, escriba un valor.
22. Haga clic en **Aceptar**.
23. Haga clic en **Aceptar**.
24. Cierre la página.
25. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
