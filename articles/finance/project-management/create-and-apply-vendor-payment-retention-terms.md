---
title: Crear y aplicar términos de retención de pago a proveedores
description: Este tema proporciona información acerca de la configuración y el mantenimiento de los términos de retención de pagos a proveedores.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410265"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Crear y aplicar términos de retención de pago a proveedores

[!include [banner](../includes/banner.md)] 

Configurar los términos de retención de pagos del proveedor para un proyecto es útil cuando su organización desea retener parte de los pagos realizados a un proveedor. Por ejemplo, cuando desea retener el pago a un proveedor hasta que los productos entregados cumplan con sus expectativas. Cuando negocie un contrato de proveedor, puede especificar las condiciones de retención de pagos de proveedor.

## <a name="create-vendor-payment-retention-terms"></a>Condiciones de retención de pagos a proveedor

Puede especificar el porcentaje de un pago de proveedor a retener y el porcentaje de los importes retenidos anteriormente a liberar. Los importes se retienen automáticamente en las facturas de proveedor hasta que el contrato alcance el estado especificado de finalización. Una vez que haya configurado las condiciones de retención para un proveedor, puede aplicarlas a cualquier proyecto de ese proveedor.

Use los pasos siguientes para configurar y mantener las condiciones de retención de pagos a proveedor. 

1. Vaya a **Gestión de proyectos y contabilidad** > **Retencion** > **Términos de retención de pago a proveedor**.
2. Seleccione **Nuevo** para agregar una nueva condición de retención de proveedor. El valor de **Id. de regla** de la nueva condición se especifica automáticamente. 
3. Introduzca una breve descripción en el campo **Descripción** y, en la ficha desplegable **Condiciones**, seleccione **Añadir línea** para introducir valores de término para lo siguiente:

   - **Porcentaje de unidades entregado**: introduzca un porcentaje de completado del término. Los importes se retienen automáticamente en las facturas al proveedor hasta que la etapa de proyecto de finalización sea igual al porcentaje especificado. Por ejemplo, si especifica 50,00, los importes se retienen hasta que el proyecto se haya completado en un 50 por ciento.
   - **Porcentaje a retener**: introduzca un porcentaje del importe de una factura de proveedor a retener. Por ejemplo, si especifica 10,00, el 10 por ciento del importe de una facturas a proveedor se retiene hasta que el proyecto alcance el porcentaje de finalización seleccionado en el campo **Porcentaje de unidades entregado**.
   - **Porcentaje a liberar**: seleccione **Agregar línea** para introducir un porcentaje de los importes retenidos anteriormente que se liberarán en el nivel seleccionado de finalización del proyecto.

> [!NOTE]
> Si tiene más de un hito para distintos niveles de finalización del proyecto, especifique una línea de termino de retención independiente al proveedor para cada regla de retención. Cada línea puede especificar otro porcentaje de retención y otro porcentaje de liberación para cada nivel designado de finalización del proyecto.

Una vez que haya creado las condiciones de retención para un proveedor, puede aplicarlos a un proyecto.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Aplicar términos de retención a proveedor a un proyecto

1. Vaya a **Gestión de proyectos y contabilidad** > **Proyectos** > **Todos los proyectos** y abra un proyecto desde la página de lista de proyectos.
2. En la ficha desplegable **Contratos de proveedor**, seleccione **Agregar línea**.
3. En el campo **Código de cuenta**, seleccione una de las opciones siguientes: 

   - **Tabla**: las condiciones de retención al proveedor se aplican a un único proveedor.
   - **Grupo**: las condiciones de retención al proveedor se aplican a todos los proveedores de un grupo de proveedores.
   - **Todos**: las condiciones de retención al proveedor se aplican a todos los proveedores.

4. En el campo **Proveedor/Grupo de proveedores**, seleccione el proveedor o el grupo de proveedores a los que las condiciones de retención de proveedor se aplican. Este campo no está disponible si ha seleccionado **Todos** en el paso anterior.
5. En el campo **Términos de retención a proveedor**, seleccione uno de los términos de retención que creó en el procedimiento anterior.
6. Si el proyecto también tiene condiciones de pago al cobro (AaC) configuradas para el proveedor, especifique el porcentaje de umbral para el proyecto en el campo **Porcentaje del umbral AaC**.

Las condiciones de retención de proveedor también se muestran en los pedidos de compra que se crean para el proveedor.
