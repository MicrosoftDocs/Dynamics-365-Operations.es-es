---
title: Crear contratos avanzados para facturación basada en progreso
description: Este tema explica cómo crear contratos de proyectos para que pueda generar facturas para los clientes, en función de un porcentaje del trabajo completado.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
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
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282847"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Crear contratos avanzados para facturación basada en progreso
[!include [banner](../includes/banner.md)]

Este tema explica cómo crear contratos de proyectos para que pueda crear facturas para los clientes, en función de un porcentaje del trabajo completado. Los importes de factura de las categorías presupuestarias del trabajo que ha configurado para un proyecto se calculan automáticamente. El tiempo de las facturas se configura al negociar el contrato de proyecto con el cliente.

Use los procedimientos de este tema para configurar un contrato, un proyecto asociado y las reglas de facturación que calculan los importes de las facturas para las categorías presupuestarias de trabajo configuradas para el proyecto.

Una vez que haya creado el contrato y el proyecto, puede configurar los detalles del proyecto. Por ejemplo, puede definir las actividades y asignar trabajadores al proyecto.

## <a name="example"></a>Ejemplo

Su organización es una empresa de desarrollo de software. Acuerda desarrollar un paquete de contabilidad de nóminas para un cliente por una cuota total de 20 000 USD. Su organización acepta facturar al cliente a medida que se completan los porcentajes de trabajo específicos del proyecto. Configura las siguientes categorías de proyectos para el trabajo, de modo que pueda usarlas en el proceso de facturación:

- Asesoría
- Diseño
- Instalación

También configura reglas de facturación que calculan automáticamente los importes de las facturas por el porcentaje de trabajo del proyecto completado en cada categoría.

El administrador de presupuestos crea un presupuesto para las categorías de proyecto. El importe de trabajo completado se calcula automáticamente como un porcentaje de trabajo real en comparación con los importes presupuestados.

## <a name="prerequisites"></a>Requisitos previos

Antes de crear un proyecto que use reglas de facturación, debe configurar las secuencias numéricas para las reglas de facturación y un diario de tarifas que se utiliza para publicar facturas de progreso.

1. Vaya a **Administración de proyectos y contabilidad** \> **Configuración** \> **Parámetros de administración de proyectos y contabilidad**.
2. En la página **Gestión de proyectos y parámetros contables**, en la pestaña **Secuencias numéricas**, configure la secuencia numérica que desea usar cuando se crean las reglas de facturación.
3. Vaya a **Integración en la contabilidad y gestión de proyectos** \> **Diarios** \> **Cuota**.
4. En la página **Diario de tarifas**, seleccione **Nuevo** e ingrese el nombre del diario.

## <a name="create-a-contract-for-progress-billings"></a>Crear un contrato para las facturaciones de progreso

Use este procedimiento para crear un contrato de proyecto para un proyecto de precio fijo. Cree una factura de proyecto cuando el trabajo que se ha completado del proyecto alcance un porcentaje especificado.

1. Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Contratos de proyecto**.
2. En la página **Contratos de proyecto**, seleccione **Nuevo**.
3. En el cuadro de diálogo **Nuevo contrato de proyecto**, establezca los campos siguientes:

    - **Nombre**
    - **Tipo de financiación**
    - **Fuente de financiación**
    - **Divisa de ventas**: de forma predeterminada, esta divisa se utiliza para las facturas de cliente asociadas al contrato de proyecto. Sin embargo, puede cambiar la divisa de ventas en una factura de cliente específica.

4. Seleccione **Aceptar**. La información se copia en el encabezado de la página **Contratos de proyectos**.
5. En la página **Contratos de proyectos**, complete el resto de la información requerida para el proyecto.

## <a name="create-a-project-for-progress-billings"></a>Crear un proyecto para las facturaciones de progreso

Siga estos pasos para crear un proyecto y todos los subproyectos asociados a un contrato de proyecto.

1. Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**.
2. En la página **Todos los proyectos**, seleccione **Nuevo**.
3. En el cuadro de diálogo **Nuevo proyecto**, en el campo **Tipo de proyecto**, seleccione **Tiempo y material**.
4. Seleccionar un grupo de proyectos. Un grupo de proyectos define la información de registro de los proyectos que se asignan al grupo.
5. Seleccione **Crear proyecto**.
6. Después de crear el proyecto, defina la etapa del proyecto como **En proceso**.

## <a name="create-a-budget-for-a-project"></a>Crear un presupuesto para un proyecto

Las categorías presupuestarias se usan para calcular automáticamente los importes de factura por el porcentaje de trabajo completado en cada categoría. Siga estos pasos para crear categorías de presupuesto para los costos estimados.

1. Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**.
2. En la página **Todos los proyectos**, seleccione y abra el proyecto que desee.
3. En la página **Proyectos**, en el Panel de acciones, en la pestaña **Plan**, en el grupo **Presupuesto**, seleccione **Presupuesto del proyecto**.
4. En la página **Presupuesto del proyecto**, especifique el coste estimado para cada categoría del proyecto.

## <a name="create-billing-rules-for-progress-billings"></a>Creación de reglas de facturación para las facturaciones de progreso

1. Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Contratos de proyecto**.
2. En la página **Contratos de proyectos**, seleccione y abra un contrato de proyecto.
3. En la página del contrato del proyecto, en la ficha desplegable **Reglas de facturación**, seleccione **Agregar**.
4. En la página **Regla de facturación**, en el campo **Tipo de línea**, seleccione **Progreso**.
5. En la ficha desplegable **Detalles de línea de regla de facturación**, en el campo **Valor contractual**, especifique el valor total del contrato.
6. En el campo **Categoría**, seleccione la categoría en la que se registrará la transacción de cuota.
7. En el campo **Proyecto**, seleccione el proyecto que usa la regla de facturación.
8. Opcional: asigne la regla de facturación a otros proyectos. En la ficha desplegable **Proyecto**, en la sección **Proyectos disponibles**, seleccione un proyecto y luego seleccione el botón de flecha derecha para agregar el proyecto a la sección **Proyectos seleccionados**.
9. Opcional: calcule el importe porcentual que el cliente retiene de pagos en una factura. En la ficha desplegable **Condiciones de retención de pago**, seleccione la fuente de financiación y, a continuación, en el campo **Porcentaje de retención**, especifique el porcentaje de retención.
10. Repita estos pasos para crear reglas de facturación adicionales para el contrato de proyecto.
