---
title: Configurar la asignación para los campos de estado de pedidos de ventas
description: Este tema explica cómo configurar los campos de estado de pedido de ventas para doble escritura.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4457001"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a>Configurar la asignación para los campos de estado de pedidos de ventas

[!include [banner](../../includes/banner.md)]

Los campos que indican el estado del pedido de ventas tienen distintos valores de enumeración en Microsoft Dynamics 365 Supply Chain Management y en Dynamics 365 Sales. Se requiere una configuración adicional para asignar estos campos en doble escritura.

## <a name="fields-in-supply-chain-management"></a>Campos en Supply Chain Management

En Supply Chain Management, dos campos reflejan el estado del pedido de ventas. Los campos que debe asignar son **Estado** y **Estado del documento**.

La enumeración **Estado** especifica el estado general del pedido. Este estado se muestra en el encabezado del pedido.

La enumeración **Estado** tiene los siguientes valores:

- Pedido abierto
- Entregado
- Facturado
- Cancelada

La enumeración **Estado del documento** especifica el documento más reciente que se generó para el pedido. Por ejemplo, si se confirma el pedido, este documento es una confirmación de pedido de ventas. Si un pedido de ventas se factura parcialmente y después se confirma la línea restante, el estado del documento sigue siendo **Factura**, ya que la factura se genera posteriormente en el proceso.

La enumeración **Estado del documento** tiene los siguientes valores:

- Confirmación
- Lista de selección
- Albarán
- Factura

## <a name="fields-in-sales"></a>Campos en Sales

En Sales, dos campos indican el estado del pedido. Los campos que debe asignar son **Estado** y **Estado de procesamiento**.

La enumeración **Estado** especifica el estado general del pedido. Tiene los siguientes valores:

- Activa
- Emitido
- Cumplido
- Facturado
- Cancelada

Se ha incluido la enumeración **Estado de procesamiento** para que el estado se pueda asignar de forma más precisa con Supply Chain Management.

La siguiente tabla muestra la asignación de **Estado de procesamiento** en Supply Chain Management.

| Estado de procesamiento   | Estado en Supply Chain Management | Estado del documento en Supply Chain Management |
|---------------------|-----------------------------------|--------------------------------------------|
| Activa              | Pedido abierto                        | None                                       |
| Confirmado           | Pedido abierto                        | Confirmación                               |
| Seleccionado              | Pedido abierto                        | Lista de selección                               |
| Parcialmente entregado | Pedido abierto                        | Albarán                               |
| Entregado           | Entregado                         | Albarán                               |
| Parcialmente facturado  | Entregado                         | Factura                                    |
| Facturado            | Facturado                          | Factura                                    |
| Cancelada           | Cancelada                         | No aplicable                             |

En la tabla siguiente se muestra la asignación de **Estado de procesamiento** entre Sales y Supply Chain Management.

| Estado de procesamiento   | Estado en Sales | Estado en Supply Chain Management |
|---------------------|-----------------|-----------------------------------|
| Activa              | Activa          | Pedido abierto                        |
| Confirmado           | Emitido       | Pedido abierto                        |
| Seleccionado              | Emitido       | Pedido abierto                        |
| Parcialmente entregado | Activa          | Pedido abierto                        |
| Parcialmente facturado  | Activa          | Pedido abierto                        |
| Parcialmente facturado  | Cumplido       | Entregado                         |
| Facturado            | Facturado        | Facturado                          |
| Cancelada           | Cancelada       | Cancelada                         |

## <a name="setup"></a>Configurar

Para configurar la asignación para los campos de estado del pedido de ventas, debe habilitar los atributos **IsSOPIntegrationEnabled** y **isIntegrationUser**.

Para habilitar el atributo **IsSOPIntegrationEnabled**, siga estos pasos.

1. En un explorador, vaya a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Reemplace **\<test-name\>** con el enlace de su empresa en Sales.
2. En la página que se abre, busque **organizationid** y anote el valor.

    ![Cómo encontrar organizationid](media/sales-map-orgid.png)

3. En Sales, abra la consola del explorador y ejecute el siguiente script. Use el valor **organizationid** del paso 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Código JavaScript en la consola del explorador](media/sales-map-script.png)

4. Compruebe que **IsSOPIntegrationEnabled** está establecido en **true**. Use la dirección URL del paso 1 para comprobar el valor.

    ![IsSOPIntegrationEnabled establecido en true.](media/sales-map-integration-enabled.png)

Para habilitar el atributo **isIntegrationUser**, siga estos pasos.

1. En Sales, vaya a **Configuración \> Personalización \> Personaliza el sistema**, seleccione **Entidad de usuario** y abra **Formulario \> Usuario**.

    ![Abrir el formulario de usuario](media/sales-map-user.png)

2. En el explorador de campos, busque **Modo de usuario de integración** y haga doble clic en él para agregarlo al formulario. Guarde el cambio.

    ![Agregar el campo Modo de usuario de integración al formulario](media/sales-map-field-explorer.png)

3. En Sales, vaya a **Configuración \> Seguridad \> Usuarios** y cambie la vista de **Usuarios habilitados** a **Usuarios de la aplicación**.

    ![Cambiar la vista de usuarios habilitados a usuarios de aplicaciones](media/sales-map-enabled-users.png)

4. Seleccione las dos entradas para **DualWrite IntegrationUser**.

    ![Lista de usuarios de aplicación](media/sales-map-user-mode.png)

5. Cambie el valor del campo **Modo de usuario de integración** a **Sí**.

    ![Cambiar el valor del campo Modo de usuario de integración](media/sales-map-user-mode-yes.png)

Ahora los pedidos de ventas están asignados.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]