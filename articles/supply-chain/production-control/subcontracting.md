---
title: Subcontratación
description: Este tema le ayudará a compilar un tutorial de subcontratación en la fabricación en Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1cc1040393d843f39ca8c741a7c51435c7169c00
ms.sourcegitcommit: edb46dce498df42b09e8f5ad6de00f86c8022dfa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2020
ms.locfileid: "3346431"
---
# <a name="subcontracting"></a>Subcontratación

[!include [banner](../includes/banner.md)]

Este tema le ayudará a compilar un tutorial de subcontratación en la fabricación en Microsoft Dynamics 365 Supply Chain Management. La primera parte de este tema describe la configuración de los datos. La segunda parte le guía a través de los pasos en el tutorial.

## <a name="target-audience"></a>Público objetivo

En este tema, aprenderá a configurar la subcontratación en la fabricación. Usará datos existentes en la entidad jurídica de HQUS para realizar la configuración básica de un flujo de actividad de subcontratación. Los datos de prueba en la entidad jurídica de HQUS incluyen los parámetros de configuración que se han preestablecido para admitir los pasos del tutorial. Aunque el tutorial aborda puntos y desafíos del panel de claves para varios roles, lo puede completar el administrador del sistema.

## <a name="demo-scenario"></a>Supuesto de demostración

En la entidad jurídica de HQUS, se fabrican altavoces de tecnología avanzada. Durante el proceso de fabricación, los altavoces pasan por las tres operaciones siguientes.

- **Pre-ensamblado**: se ensambla la caja acústica del altavoz. El material para la caja acústica se selecciona en el almacén de material antes de iniciarse la operación.
- **Capa** Después de ensamblar la caja acústica, tiene que revestirse. Esta operación la completa un proveedor (subcontratista). La caja acústica del altavoz premontado se envía al subcontratista de la capa junto con dos materiales.
- **Acabado** Después de que el subcontratista haya puesto una cobertura en la caja acústica del altavoz premontada, esta se devuelve a la entidad jurídica de HQUS de modo que el ensamblado final del orador se pueda completar.

La ilustración siguiente muestra las tres operaciones y los materiales que consumen.

![Operaciones de pre-ensamblado, capa, y acabado, y los materiales que consumen.](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Configuración

Antes del inicio del tutorial, debe configurar los datos.

### <a name="set-up-the-finished-product"></a>Configurar el producto acabado

Este procedimiento lo lleva por el proceso de configuración del producto emitido D8100, “Caja acústica con revestimiento".

1. Seleccione **Gestión de información de productos \> Productos \> Productos emitidos** para abrir la página **Detalles de producto emitido**.
2. En el campo de filtro rápido, escriba **D8100** para encontrar el producto emitido existente.

    ![Filtrado del producto emitido D8100 en la página de Detalles de producto emitido](./media/subcontract02_filtering-released-products.png)

3. En el panel de acciones, en la pestaña **Ingeniero**, seleccione **Ruta** para abrir la página **Ruta**.

    La página **Ruta** muestra las ocho versiones de ruta para el producto emitido D8100. Las ocho versiones de ruta se dividen en cuatro ruta en el sitio 1 y el sitio. 5. La ruta 000400 se utiliza para la gestión de costes, la ruta 00041 se usa cuando la operación de la capa es una operación interna, y la ruta 00042 se usa cuando la operación de la capa es una operación externa.

    ![Ocho versiones de ruta en la página de la ruta](./media/subcontract03_route-page.png)

4. En el panel superior, en la cuadrícula **Versiones**, seleccione la versión de ruta **00042** para el sitio **5**.
5. En el panel inferior, en la pestaña **Visión general**, seleccione la operación **20** (**Cbnt CtSc**) en la cuadrícula.

    ![Operación 20 para la versión de ruta 00042 del sitio 5 seleccionado](./media/subcontract04_route-version-operation.png)

6. Seleccione la ficha **General**.

    Observe que el campo **Tipo de ruta** del campo está establecido en **Proveedor**. Este valor indica que la operación 20 (Cbnt CtSc) es una operación subcontratada.

    ![Campo de tipo de ruta establecido en Proveedor en la pestaña General](./media/subcontract05_general-tab.png)

7. Seleccione la ficha **Requisitos de recursos**.

    Las capacidades se usarán para buscar un recurso aplicable durante la programación de producción. Para la operación 20 (Cbnt CtSc), observe que se requiere un recurso que tiene dos capacidades, **Capa** y **Cajas acústicas con revestimiento**.

    ![Capacidades de Capa y cajas acústicas con revestimiento en la ficha de los requisitos de recursos](./media/subcontract06_resource-requirements-tab.png)

8. Seleccione **Recursos aplicables** para abrir el cuadro de diálogo **Recursos aplicables**.

    Se encuentran tres recursos que coinciden con los requisitos de origen para la operación. Observe que los recursos 8851 y 8852 son del tipo **Proveedor**.

    ![Tres recursos apropiados en el cuadro de diálogo Recursos aplicables.](./media/subcontract07_applicable-resources-dialog.png)

9. Seleccione **Aceptar** para cerrar el cuadro **Recursos aplicables** y regresar a la página **Ruta**.
10. Cierre la página **Ruta** para volver a la página **Detalles de producto emitido**.

    ![Página de detalles de productos emitidos](./media/subcontract08_released-product-details-page.png)

11. En el panel de acciones, en la pestaña **Ingeniero**, seleccione **Versiones de L. MAT** para abrir la página **Versiones de L. MAT**.

    La página **Versiones de L. MAT** muestra las cuatro versiones de la lista de materiales (L.MAT) del producto emitido D8100. L.MAT 000040 se utiliza para la gestión de costes y la planificación, L.MAT 000041 se usa si la operación de la capa se realiza internamente, y los L.MAT 000042 y 000043 se usan si se subcontrata la operación de la capa.

    Tenga en cuenta que el elemento S8050 es un producto del tipo del elemento **Servicio**. Este elemento representa el trabajo subcontratado.

    ![Cuatro versiones de L.MAT en la página de las versiones de L.MAT](./media/subcontract09_bom-versions-page.png)

12. En la ficha desplegable **Líneas de lista de materiales**, seleccione **Editatr** para abrir el cuadro **Editar línea de L.MAT**.

    Cuando un pedido de producción se crea y se estima para el producto emitido D8100, un pedido de compra se generará automáticamente para el artículo S8050. Este pedido de compra será vinculado al pedido de producción. Para que los pedidos de compra se generen automáticamente, el campo **Tipo de línea** se debe establecer en **Proveedor**, y la cuenta del proveedor para el subcontratista se debe seleccionar. En este caso, la cuenta de proveedor es US-801.

    Observe que la línea de L.MAT está conectada a la operación de la capa a través del número de operación (en este caso, 20).

    ![Edición del cuadro de diálogo de la línea de L MAT](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Crear una contraseña para los trabajadores de almacén

Debe definir una contraseña para los trabajadores de almacén que usan el dispositivo de mano.

1. Seleccione **Administración de almacenes \> Configuración \> Trabajador** para abrir la página **Usuarios de trabajo**.
2. En la ficha desplegable **Usuarios**, seleccione la fila del usuario **51**.

    ![Página de usuario de trabajo](./media/subcontract11_work-users-page.png)

3. Seleccione **Restablecer contraseña**.
4. En los campos **Contraseña** y **Confirmar contraseñas**, especifique **1**.
5. Seleccione **Establecer contraseña**.

## <a name="step-by-step-walkthrough"></a>Tutorial paso a paso

**Escenario y antecedentes**

Un pedido de producción de 10 piezas se crea para el producto D8100, “Caja acústica con revestimiento”. La capa de las cajas acústicas es una operación subcontratada que se realiza en los locales del proveedor, US-801, Perfect Coating Solutions. El pedido de producción está formado por tres operaciones. En la primera operación, la caja acústica se monta previamente como operación interna. El material para el preensamblado se libera para seleccionar en el almacén de la materia prima. Una vez que el ensamblado previo se ha completado, la caja acústica montada previamente se envía a Perfect Coating Solutions junto con dos materiales necesarios para la operación de la capa. Cuando se recibe la caja acústica con revestimiento del proveedor, esta pasa por una operación de ensamblado interna final antes de que se notifique como terminada.

1. Seleccione **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** para abrir la página **Todos los pedidos de producción**.
2. En el panel de acciones, seleccione **Nuevo pedido de producción** para abrir el cuadro **Crear orden de producción**.

    ![Cuadro de diálogo Crear un pedido de producción](./media/subcontract12_create-production-order-dialog.png)

3. En el campo **Código de artículo**, seleccione **D8100**.
4. Después de seleccionar el número de elemento, se muestran los campos para las dimensiones del inventario. En el campo **Color**, seleccione **Cromo**.

    Un cuadro de mensaje aparece que pregunta si las versiones activas de la lista de materiales y la ruta deben insertarse.

    ![Cuadro de mensaje](./media/subcontract13_message-box.png)

5. Seleccione **Sí**. 

    En el cuadro de diálogo **Crear orden de producción**, las versiones activas de L. MAT y la ruta para el producto D8100 se seleccionan automáticamente en los campos **Número de L.MAT** y **Número de ruta** respectivamente. En este caso, se seleccionan L. MAT **000040** y la ruta **000040**.
    
    > [!NOTE]
    > Para la L. MAT y la ruta, se usa la versión 000040 para la gestión de costes y la planificación.

6. En el campo **Sitio**, seleccione **5**.
7. En el campo **Almacén**, seleccione **51**.
8. En los campos **Número de L. MAT** y **Número de ruta**, cambie el valor que se ha seleccionado automáticamente para **000042**.

    > [!NOTE]
    > Para la L. MAT y la ruta, la versión 000042 se utiliza para subcontratar la capa de la caja acústica con el proveedor US-801.

    ![Valores establecidos en el cuadro de diálogo Crear pedido de producción](./media/subcontract14_create-production-order-dialog-set.png)

9. Seleccione **Crear** para crear el pedido de producción y regresar a la página **Todos los pedidos de producción**.

    ![Nuevo pedido de producción en la página Todos los pedidos de producción](./media/subcontract15_new-production-order.png)

10. En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Estimación** para abrir el cuadro **Estimación**.

    ![Cuadro de diálogo Estimación](./media/subcontract16_estimate-dialog.png)

11. Seleccione **Aceptar** para confirmar la estimación y regresar a la página **Todos los pedidos de producción**.

    > [!NOTE]
    > Cuando se estima el pedido de producción, el pedido de compra del artículo de servicio S8050 se genera para el proveedor US-801.

12. En el panel de acciones, en la pestaña **pedido de producción**, seleccione **L. MAT** para abrir la página **L. MAT**, donde puede ver las líneas de L. MAT para el pedido de producción.

    Para el artículo de servicio S8050, observe que se hace referencia al pedido de compra que se ha generado cuando se estimó al pedido de producción.

    ![Líneas de L. MAT del pedido de producción en la página de L. MAT](./media/subcontract17_production-order-bom-lines.png)

13. Cierre la página **L. MAT** para regresar a la página **Todos los pedidos de producción**.
14. En el panel de acciones, en la ficha **Programación**, seleccione **Programar trabajos** para abrir el cuadro de diálogo **Programación de trabajos**.
15. Especifique los valores siguientes:

    - En el campo **Dirección de programación**, seleccione **Remitir a partir de hoy**.
    - Establezca la opción **Capacidad limitada** a **Sí**.

    ![Cuadro de diálogo Programación de trabajos](./media/subcontract18_job-scheduling-dialog.png)

16. Seleccione **Aceptar** para cerrar el cuadro **Programación de trabajos** y regresar a la página **Todos los pedidos de producción**.
17. En el panel de acciones, en la pestaña **Programación**, seleccione **Gantt** para abrir la página **Diagrama de Gantt - vista de recursos**.

    El gráfico de Gantt proporciona una visión general visual de cómo los trabajos de producción se programan en los recursos. Observe que la operación de capa externa consta de tres trabajos: un trabajo de proceso, un trabajo de transporte, y un trabajo de tiempo en cola.

    ![Diagrama de Gantt en el gráfico de Gantt - página de la vista de recursos](./media/subcontract19_gantt-chart.png)

18. Cierre la página **Diagrama de Gantt - vista de recursos** para regresar a la página **Todos los pedidos de producción**.
19. En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Liberar** para abrir el cuadro **Liberar**.

    ![Cuadro de diálogo Liberar](./media/subcontract20_release-dialog.png)

20. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Liberar**.
21. Seleccione **Control de producción \> Tareas periódicas \> Liberar al almacén \> Liberación automática de L. MAT. y líneas de fórmula** para abrir el cuadro de diálogo **Liberación automática de L. MAT. y líneas de fórmula**.

    ![Cuadro de diálogo Liberación automática de L. MAT. y líneas de fórmula](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Seleccione **Aceptar** para ejecutar el trabajo de liberación automática de L. MAT y líneas de fórmula.

    Este trabajo libera el trabajo de selección de materias primas al almacén.

23. Seleccione **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** para abrir la página **Todos los pedidos de producción**.
24. Use el campo de filtro rápido para seleccionar el pedido de producción en el que ha estado trabajando.
25. En el panel de acciones, en la pestaña **Almacén**, seleccione **Detalles del trabajo** para abrir la página **Trabajo**.

    Observe que la página muestra dos conjuntos de trabajos para la selección de la materia prima. El primer trabajo es para los materiales M8100 y M8101. Estos materiales los consume la operación 10. El segundo trabajo es para los materiales M8202 y M8250. Estos materiales los consume la operación 20, que es la operación subcontratada.

    ![Dos conjuntos de trabajos para la selección de la materia prima en la página Trabajo](./media/subcontract22_work-page.png)

26. Inicie la aplicación del almacén para procesar el trabajo del almacén para la operación 10.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Seleccione **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** para abrir la página **Todos los pedidos de producción**.
28. Use el campo de filtro rápido para seleccionar el pedido de producción en el que ha estado trabajando.
29. En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Inicio** para abrir el cuadro **Inicio**.
30. En la ficha **General**, especifique los valores siguientes:

    - En el campo **Desde n.º oper.** seleccione **10**.
    - En el campo **Hasta n.º oper.** seleccione **10**.

    ![Valores definidos en la ficha General](./media/subcontract23_start-dialog.png)

31. Seleccione **Aceptar** para cerrar el cuadro **Inicio** y regresar a la página **Todos los pedidos de producción**.

    Tenga en cuenta que el estado del pedido de producción ahora es **Iniciado**. El material para la operación 10 es consumido por un registro automático del diario de lista de selección. El consumo de tiempo para la operación 10 se indica mediante un registro automático de un diario de tarjeta de ruta.

32. Inicie la aplicación del almacén para procesar el trabajo del almacén para la operación 20.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Inicio** para abrir el cuadro **Inicio**.
34. En la ficha **General**, especifique los valores siguientes:

    - En el campo **Desde n.º oper.** seleccione **20**.
    - En el campo **Hasta n.º oper.** seleccione **20**.
    - En el campo **Cantidad**, especifique **10**.
    - Establezca la opción **Registrar ahora la lista de selección** en **No**.

    ![Valores definidos en la ficha General](./media/subcontract24_general-tab.png)

35. Seleccione **Aceptar** para cerrar el cuadro **Inicio** y regresar a la página **Todos los pedidos de producción**.

    Se crea una lista de selección para los materiales que se utilizan para la operación de la capa, y para el artículo de servicio. El artículo de servicio representa el coste de la operación subcontratada.

36. En el panel de acciones, en la pestaña **Ver**, seleccione **Lista de selección** para abrir la página **Lista de selección**.
37. Seleccione la lista de selección que no está registrada, y seleccione el número de diario para ver las líneas de diario.

    ![Líneas del diario en la página lista de selección](./media/subcontract25_picking-list.png)

38. En el panel de acciones, seleccione **Imprimir** \> **Informe de lista de selección** para abrir el cuadro de diálogo **Informe de lista de selección**.
39. Establezca la opción **Utilizar diseño de nota de entrega** a **Sí**.

    ![Cuadro de diálogo Informe Lista de selección](./media/subcontract26_picking-list-report-dialog.png)

40. Seleccione **Aceptar** para generar un informe de **lista de selección**.

    En este caso, una nota de entrega de proveedor se imprime desde el diario de lista de selección de producción. La nota de entrega especifica los materiales que se envían al proveedor que realizará la operación de capa.

    ![Informe de lista de selección](./media/subcontract27_picking-list-report.png)

41. Cierre el informe **lista de selección** para volver a la página **lista de selección**.
42. En el panel de acciones, seleccione **Registrar** para abrir el cuadro de diálogo **Registrar diario**.

    ![Cuadro de diálogo Registrar diario](./media/subcontract28_post-journal-dialog.png)

43. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Registrar diario**.
44. Abra el pedido de compra.

    ![Página Pedido de compra](./media/subcontract29_purchase-order-page.png)

45. En el panel de acciones, en la pestaña **Compra**, seleccione **Confirmar**.
46. Seleccione **Registrar** para abrir el cuadro de diálogo **Registrar diario**.
47. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Registrar diario** y regresar a la página **Pedido de compra**.
48. Cambie el precio unitario de **33** a **40**.

    ![Precio por unidad cambiado en la página del pedido de compra](./media/subcontract30_unit-price.png)

49. Confirme el pedido de compra de nuevo.
50. Recepción de producto.

    ![Cuadro de diálogo Registro de recepción de productos](./media/subcontract31_posting-product-receipt-dialog.png)

51. Factura de compra.
52. Actualizar el estado de conciliación.

    ![Página de factura del proveedor](./media/subcontract32_vendor-invoice-page.png)

53. Notificar como terminado.

    ![Cuadro de diálogo Notificar como terminado](./media/subcontract33_report-as-finished-dialog.png)

54. Fin.

    ![Cuadro de diálogo Fin](./media/subcontract34_end-dialog.png)

55. Comparación del coste.

    ![Gráficos de comparación del coste](./media/subcontract35_cost-comparison-charts.png)

Configuración que falta en datos.
