---
title: Crear una cuenta de proveedor
description: Este procedimiento muestra cómo crear una cuenta de proveedor y agregar una dirección e información de contacto.
author: mkirknel
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8cd2bb7b03c0415a5c5656f0e3ffada961973e
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017216"
---
# <a name="create-a-vendor-account"></a>Crear una cuenta de proveedor

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear una cuenta de proveedor y agregar una dirección e información de contacto. El procedimiento no muestra cómo rellenar todos los campos para realizar compras o de uso financiero. Para obtener más información acerca de estos campos, lea las descripciones de los campos. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Las cuentas de proveedor las crean normalmente los profesionales de compras o el personal de cuentas de cliente.


## <a name="create-a-vendor-account"></a>Crear una cuenta de proveedor
1. Vaya al **Panel de exploración > Módulos > Adquisición y abastecimiento > Proveedores > Todos los proveedores**.
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta de proveedor** , escriba un valor.
    - El valor se puede completar automáticamente. Si así es, puede omitir este paso.  
    - Puede crear cuentas de proveedor para una persona o una organización. Esto afectará a qué campos quedan disponibles. En este ejemplo, crearemos una cuenta de proveedor para una organización.   
4. En el campo **Nombre** , especifique o seleccione un valor. Si el proveedor está ya registrado en el sistema, podrá usar la lista desplegable y seleccionarlo en este campo; la nueva cuenta de proveedor heredará la dirección y la información de contacto ya registrada.
5. En el campo **Grupo** , especifique o seleccione un valor. El grupo de proveedores se utiliza para agrupar proveedores con alguno de los siguientes parámetros en común: condiciones de pago, período de liquidación, cuentas contables de registro de inventarios, incluido el grupo de impuestos, cuentas contables predeterminadas, códigos de filtro de producto o configuración de previsión de suministro.
6. En el campo **Número de empleados** , especifique un número.
7. En el campo **Número de organización** , escriba un valor.

## <a name="add-an-address"></a>Adición de una dirección
1. Expanda la sección **Direcciones**.
2. Haga clic en **Agregar**.
3. En el campo **Propósito** , especifique o seleccione un valor. Puede seleccionar uno o más propósitos. Estos se usan para seleccionar la dirección correcta para un propósito dado. Por ejemplo, si el propósito es “Factura”, dicha dirección se usará al enviar facturas.
4. En el campo **Nombre o descripción** , escriba un valor.
5. En el campo **País o región** , especifique o seleccione un valor. Especifique los detalles de la dirección. El país o región que haya seleccionado determinará los campos visibles, según el formato de dirección del país o la región. 
6. Haga clic en **Aceptar**.

## <a name="add-contact-information"></a>Adición de información de contacto
1. Expanda la sección **Información de contacto**.
2. Haga clic en **Agregar**.
3. En el campo **Descripción** , escriba un valor.
4. En el campo **Tipo** , seleccione una opción.
5. En el campo **Dirección y número de contacto** , escriba un valor. Puede activar la casilla Principal si se trata del contacto principal.  
6. Haga clic en **Guardar**.
7. Cierre la página.
8. Cierre la página.

