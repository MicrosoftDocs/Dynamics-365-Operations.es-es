---
title: Configurar información de grupo de TDS, PAN y TAN para proveedores y clientes
description: Este tema explica cómo configurar información sobre el grupo de impuestos deducidos en el origen (TDS), el número de cuenta permanente (PAN) y el número de cuenta de impuestos (TAN) para proveedores y clientes.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b736838f1743a39d1f899f2679a31a2c0fe9a2b31e03b29d22af821314f329c9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745757"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>Configuración de la información de grupo de TDS, PAN y TAN para proveedores y clientes

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar información sobre el grupo de impuestos deducidos en el origen (TDS), el número de cuenta permanente (PAN) y el número de cuenta de impuestos (TAN) para proveedores y clientes.

1. Vaya a **Proveedores \> Proveedores \> Todos los proveedores** o **Clientes \> Clientes \> Todos los clientes**.

    [![Página de todos los proveedores.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. En el panel de acciones, seleccione **Nuevo** para crear un proveedor o cliente e introduzca los detalles requeridos. Alternativamente, seleccione un proveedor o cliente existente.
3. En la ficha desplegable **Factura y entrega**, en la sección **Retención de impuestos**, establezca la opción **Calcular retención de impuestos** a **Sí** para calcular la retención de impuestos, TDS o impuestos cobrados en el origen (TCS) para el proveedor o cliente.
4. El TDS para una factura de compra se calcula en función del grupo de TDS predeterminado que se define para el proveedor o cliente. En el campo **Grupo de TDS**, seleccione el grupo de TDS predeterminado.

    > [!NOTE]
    > Cuando selecciona un grupo de TDS en el campo **Grupo de TDS**, los campos **Grupo de retención de impuestos** y **Grupo de TCS** dejan de estar disponibles.

5. En la ficha desplegable **Información de impuestos**, en la sección **Información de PAN**, en el campo **Estado**, seleccione el estado del número de cuenta permanente para el proveedor o cliente.

    - **No disponible**: el proveedor o cliente no tiene PAN.
    - **Recibido**: el proveedor o cliente tiene un PAN.
    - **Solicitado**: el proveedor o cliente ha solicitado un PAN.
    - **No válido**: el proveedor o cliente tiene un PAN, pero no es válido.

6. Si ha seleccionado **Recibido** en el campo **Estado** para indicar que el proveedor o cliente tiene un PAN, introduzca el PAN en el campo **Número**. El PAN debe constar de cinco caracteres alfabéticos, luego cuatro caracteres numéricos y luego un carácter alfabético. Este es un ejemplo: **ABCDE1260A**.
7. Si ha seleccionado **Solicitado** en el campo **Estado** para indicar que el proveedor o cliente ha solicitado un PAN, introduzca el número de referencia en el campo **Número de referencia**.
8. En el campo **Naturaleza del evaluado**, seleccione la categoría de naturaleza del evaluado a la que pertenece el proveedor o cliente:

    - Empresa
    - HUF
    - En firme
    - Individual
    - AOP
    - BOI
    - Autoridad local
    - Otros

    [![Ficha desplegable de información de impuestos.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. En el Panel de acciones, en la pestaña **Proveedor**, en el grupo **Registro**, seleccione **Id. de registro** para abrir la página **Administrar direcciones**.
10. En la página **Administrar direcciones**, en la ficha desplegable **Información de impuestos**, seleccione **Agregar** o **Editar** para abrir la página **Administrar información de impuestos**, donde puede mantener la entrada de registro de impuestos.
11. En la página **Administrar información de impuestos**, en la ficha desplegable **Retención de impuestos**, en el campo **Número de cuenta de impuestos (TAN)**, introduzca el TAN. El TAN debe constar de cuatro caracteres alfabéticos, luego cinco caracteres numéricos y luego un carácter alfabético. Este es un ejemplo: **AFGH54821T**.
12. Cierre la página.
