---
title: Configuración de pedidos de calidad
description: Este procedimiento le muestra cómo habilitar un proceso de administración de calidad donde el inventario entrante se debe examinar inmediatamente después del registro de llegada.
author: perlynne
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, InventTestTable, DefaultDashboard, InventTestVariable, InventTestVariableOutcome, InventItemSampling, InventTestQualityGroup, InventTestItemQualityGroupAdd, SysQueryForm, InventTestItemQualityGroup, InventTestGroup, InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4577b8b189403b3d71eb634e159d51d2fa53ce12
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437108"
---
# <a name="set-up-quality-orders"></a>Configuración de pedidos de calidad

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo habilitar un proceso de administración de calidad donde el inventario entrante se debe examinar inmediatamente después del registro de llegada. El procedimiento lo realizará normalmente un gestor de calidad. El proceso incluye la creación de un grupo de calidad para definir los artículos que se van a muestrear y un grupo de pruebas para agrupar las pruebas que deben llevarse a cabo en los artículos del grupo de calidad. Puede ejecutar esta guía en la empresa de datos de demostración USMF.


## <a name="enable-quality-management"></a>Habilitar la administración de calidad
1. Vaya a **Panel de navegación > Módulos > Gestión del inventario > Configurar > Inventario y parámetros de gestión de inventario y almacenes**.
2. Haga clic en la ficha **Administración de calidad**.
3. Defina la **opción Usar administración de calidad** en Sí.
4. Haga clic en **Configuración del informe.** En USMF, ya se ha definido la configuración del informe para la administración de calidad. Si no se hiciera esto, agregaría nuevas líneas aquí para los diferentes tipos de informes y seleccionaría el tipo de documento que se utilizará para cada informe.  
5. Cierre la página.
6. Cierre la página.

## <a name="create-a-test"></a>Crear una prueba
1. Vaya a **Gestión del inventario > Configurar > Control de calidad > Pruebas.**
2. Haga clic en **Nuevo**.
3. En el campo **Prueba**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Tipo**, seleccione "Opción". En este ejemplo, seleccionaremos “Opción”, que permitirá asignar los resultados de prueba en función de los valores predefinidos.  
6. Haga clic en **Guardar**.
7. Cierre la página.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Crear variables de prueba para definir la manera en la que se registran los resultados de prueba
1. Vaya a **Gestión del inventario > Configurar > Control de calidad > Variables de prueba**.
2. Haga clic en **Nuevo**.
3. En el campo **Variable**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Haga clic en **Guardar**.
6. Haga clic en **Resultados**.
7. Haga clic en **Nuevo**.
8. En el campo **Resultado,** escriba un valor.
9. En el campo **Descripción**, escriba un valor.
10. En el campo **Estado del resultado**, seleccione "Aprobado".
11. Haga clic en **Guardar**.
12. Haga clic en **Nuevo**.
13. En el campo **Resultado,** escriba un valor.
14. En el campo **Descripción**, escriba un valor.
15. Haga clic en **Guardar**.
16. Cierre la página.
17. Cierre la página.

## <a name="set-up-item-sampling"></a>Configurar el muestreo de artículos
1. Vaya a **Gestión del inventario > Configurar > Control de calidad > Muestreo de artículos.**
2. Haga clic en **Nuevo**.
3. En el campo **Muestreo de artículos,** escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Valor,** especifique un número. Este valor está relacionado con la especificación de cantidad seleccionada en el campo adyacente.  
6. Expanda o contraiga la sección **Procesar**.
7. Active o desactive la casilla **Bloqueo completo**. Si selecciona esta opción, se bloquea la cantidad total del lote o de la línea de pedido si se produce un error en una prueba. Si no la selecciona, solo se bloquean los artículos del pedido de calidad.  
8. Haga clic en **Guardar**.
9. Cierre la página.

> [!NOTE]
> La característica *Gestión de calidad para procesos de almacén* proporciona capacidades de muestreo de elementos adicionales. Agrega un concepto de *alcance de muestreo del artículo* y la capacidad de definir una matrícula completa como especificación de cantidad. Si ha habilitado esta función, vea [Gestión de calidad para procesos de almacén](../quality-management-for-warehouses-processes.md) para más detalles.

## <a name="create-a-quality-group"></a>Crear un grupo de calidad
1. Vaya a **Gestión del inventario > Configurar > Control de calidad > Grupos de calidad**.
2. Haga clic en **Nuevo**.
3. En el campo **Grupo de calidad,** escriba un valor. Use un nombre descriptivo que le ayude a identificar qué clase de artículos contendrá el grupo (sus criterios de muestreo).  
4. En el campo **Descripción**, escriba un valor.
5. Haga clic en **Guardar**.
6. Haga clic en **Agregar artículos**.
7. Seleccione la fila **Númerode artículo**. En este ejemplo, el filtrado se ejecutará en función del número de artículo.  
8. En el campo **Criterios**, escriba un valor. Por ejemplo, escriba T* para filtrar en los números de artículo que empiecen por T.  
9. Haga clic en **Aceptar**.
10. Haga clic en **Aceptar**.
11. Haga clic en **Grupos de calidad de artículos**.
12. Cierre la página.
13. Cierre la página.

## <a name="create-a-test-group"></a>Crear un grupo de pruebas
1. Vaya a **Gestión del inventario > Configurar > Control de calidad > Grupos de prueba.**
2. Haga clic en **Nuevo**.
3. En el campo **Grupo de prueba,** escriba un valor. Asigne un nombre al **grupo de pruebas** que le ayude a recordar qué clase de pruebas se están ejecutando y con qué grupo de calidad deben estar asociadas. Por ejemplo, si se va a usar con un grupo de calidad que seleccione los artículos que empiecen por “T”, podría llamarlo “T- pruebas de artículo”.  
4. En el campo **Descripción**, escriba un valor.
5. En el campo de **muestreo de artículos**, seleccione la línea de muestreo de artículos que ha creado antes.
6. En la lista, busque y seleccione el registro deseado.
7. Haga clic en **Agregar**.
8. En el campo **Número de secuencia**, especifique un número.
9. En el campo **Prueba**, seleccione la prueba que ha creado anteriormente.
10. En la lista, busque y seleccione el registro deseado.
11. Haga clic en la pestaña **Prueba**.
12. En el campo **Variable**, seleccione la variable de prueba que ha creado anteriormente.
13. En la lista, busque y seleccione el registro deseado.
14. En el campo **Resultado predeterminado**, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. Haga clic en **Guardar**.
17. Cierre la página.

## <a name="define-when-quality-orders-will-be-created"></a>Definir cuándo se crearán los pedidos de calidad
1. Vaya a **Gestión del inventario > Configurar > Control de calidad > Asociaciones de calidad**.
2. Haga clic en **Nuevo**.
3. En el campo **Tipo de referencia,** seleccione una opción.
4. En el campo **Código de artículo,** seleccione "Grupo". En este ejemplo, seleccionaremos “Grupo” y utilizaremos el grupo de calidad que creamos antes. También puede establecer esto en “Tabla” para especificar los artículos manualmente o para seleccionar “Todos” con el fin de agregar todos los artículos al pedido de calidad.  
5. En el campo **Artículo,** seleccione el grupo de calidad que ha creado anteriormente. Las opciones disponibles en el campo Artículo dependen de lo que se establezca en el campo Código de artículo.  
6. En la lista, busque y seleccione el registro deseado.
7. Expanda o contraiga la sección Procesar.
8. En el campo **Tipo de evento,** seleccione una opción. Este es el evento que desencadena la prueba. Las opciones disponibles aquí dependen de qué proceso ha seleccionado en el campo Tipo de referencia.  
9. En el campo **Ejecución**, seleccione una opción.
10. Expanda o contraiga la sección **Proceso de pedido de calidad**.
11. En el campo **Bloqueo de eventos**, haga clic en el botón desplegable para abrir la búsqueda. Este campo muestra la lista de procesos que es posible bloquear si el pedido de calidad aún está abierto. Las opciones dependen de su elección en el campo Tipo de evento.  
12. En la lista, haga clic en el vínculo de la fila seleccionada. Esto estará en función de los valores seleccionados anteriores. Seleccione si los siguientes procesos deben bloquearse mientras haya pedidos de calidad abiertos vinculados a una línea de documento de origen.  
13. Expanda o contraiga la sección **Especificaciones**.
14. En el campo **Grupo de prueba**, seleccione el grupo de prueba que ha creado anteriormente.
15. En la lista, busque y seleccione el registro deseado.
16. Haga clic en **Guardar**.
17. Cierre la página.

> [!NOTE]
> La característica *Administración de calidad para procesos de almacén* proporciona opciones adicionales para configurar asociaciones de calidad. Agrega una nueva condición (**Tipo de almacén aplicable**) y una nueva configuración (**Política de procesamiento de calidad**). Si ha habilitado esta función, vea [Gestión de calidad para procesos de almacén](../quality-management-for-warehouses-processes.md) para más detalles.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]