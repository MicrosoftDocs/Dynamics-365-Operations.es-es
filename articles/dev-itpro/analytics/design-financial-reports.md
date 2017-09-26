---
title: "Ver y diseñar informes financieros"
description: "En este artículo se proporcionan ejercicios que le enseñarán a visualizar y crear informes financieros para Microsoft Dynamics 365 for Finance and Operations."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0dc453ab56a2d381afa6e22d847f0b1eb7a16e7e
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# <a name="view-and-design-financial-reports"></a>Ver y diseñar informes financieros

[!include[banner](../includes/banner.md)]


En este artículo se proporcionan ejercicios que le enseñarán a visualizar y crear informes financieros para Microsoft Dynamics 365 for Finance and Operations. El informe financiero consta de una experiencia de visualización en Finance and Operationsy un diseñador de informes con un solo clic que le permite crear y editar informes financieros.  

<a name="exercise-1-generate-and-explore-a-default-financial-report"></a>Ejercicio 1: Generar y explorar un informe financiero predeterminado
-----------------------------------------------------------

Para este ejercicio, generará y explorará un informe predeterminado existente. Este informe incluye todas las cuentas y también contiene las propiedades de la cuenta (atributos) para las cuentas. Explorará en profundidad el detalle de la transacción, aplicando filtros de dimensiones, cambiando la divisa del informe. En primer lugar, actualizaremos el orden de visualización de las dimensiones para informes financieros. Esto le permite seleccionar cómo se muestran las dimensiones no solo al diseñar y ver informes financieros.

1.  Vaya a **Configuración de la dimensión financiera para la integración de aplicaciones** en **Dimensiones del plan de cuentas** en Contabilidad general.
2.  Mueva las dimensiones para que se encuentren en el siguiente orden:
    1.  Cuenta principal
    2.  Unidad de negocio
    3.  Centro de coste
    4.  Departamento

    Nota: Las demás dimensiones pueden permanecer en el orden en el que se encuentran actualmente.
3.  Guarde la configuración de la dimensión. A continuación, generaremos un informe y exploraremos los datos del informe.
4.  Vaya a **Informes financieros** en **Consultas e informes** en Contabilidad general.
5.  Seleccione la fila para el informe denominado **Detalle de contabilidad general – predeterminado**.
6.  Seleccione **Editar**. Nota: Se le pedirá que descargue el diseñador de informes con un solo clic y que inicie sesión. Use sus credenciales para iniciar sesión.
7.  Cambie el año base a 2012 y seleccione **Generar**. Cuando se genera un informe desde el diseñador de informes, se abrirá en una pestaña nueva del explorador. Puede explorador el informe en la nueva pestaña del explorador o ir a su pestaña del explorador original y abrir el informe desde allí seleccionándolo en la lista **Informes financieros**.
8.  En el informe abierto, seleccione uno de los importes para explorar el detalle de la cuenta para el informe.
9.  Una vez en el detalle de la cuenta, seleccione una cuenta con datos y realice la acción **Obtener detalles de nivel de transacción de informe**. En el nivel de la transacción del informe, puede ver las propiedades (atributos) que están incluidos en el diseño del informe. En función de la transacción y de la cuenta, se pueden mostrar algunos o todos los atributos.
10. Cierre el nivel de transacción del informe.
11. Seleccione la misma cuenta u otra diferente y realice la acción **Abrir transacciones de comprobantes**. Las transacciones de asiento se filtran hasta la combinación de período, el año y cuenta +dimensión de la cuenta seleccionada. Desde las transacciones de asiento, puede elegir explorar otra información sobre la transacción.
12. Cierre las transacciones de asiento. Dentro de un informe financiero, puede elegir ver los datos para un período o ejercicio diferente o con diferentes atributos y dimensiones aplicadas. Para ello se utiliza la opción **Opciones de informe**.
13. Seleccione **Opciones de informe**.
14. Seleccione **Agregar una dimensión de filtro** y elija **Unidad de negocio**.
15. Escriba 001 en el campo y seleccione **Aceptar**. El informe muestra ahora solo los datos para la unidad de negocio 001. Esta es una vista personalizada del informe y no está disponible para que la vean los demás.
16. Cierre el informe filtrado. Los informes financieros se pueden mostrar en cualquier divisa que se agregue a Finance and Operations.
17. Seleccione **Divisa** y, a continuación, seleccione **EUR**. El informe se muestra ahora en euros. Los códigos de divisa o los símbolo de divisa incluidos en el diseño del informe se muestran ahora en la divisa aplicada. Si no se define ningún símbolo de divisa para una divisa, no se muestra el símbolo de la divisa.
18. Cierre el informe **Detalle de contabilidad general**.
19. Cierre el **Diseñador de informes**.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>Ejercicio 2: Agregar propiedades de cuenta adicionales a un diseño de informe
En este ejercicio, modificará un informe predeterminado existente. Actualizará tanto la definición de fila para incluir todas las cuentas como la definición de columna para contener atributos de cuenta. Una vez que se completen las actualizaciones, generará el informe recién creado y explorará el informe. Empezaremos por la lista Informes financieros.

1.  Vaya a **Informes financieros** en Consultas e informes en Contabilidad general.
2.  Seleccione la fila para el informe denominado **Resumen de saldo de comprobación – predeterminado**.
3.  Seleccione **Editar**. **Resumen de saldo de comprobación – predeterminado** se abrirá en el diseñador de informes.
4.  Seleccione **Archivo** y, a continuación, **Guardar como** y asigne al informe el nombre Saldo de comprobación detallado con atributos. Nota: siempre que se crea un nuevo informe en el diseñador de informes, se actualizan los informes financieros en Finance and Operations.
5.  Desde la definición del informe, seleccione el icono de la definición de filas para abrir la definición de fila **Saldo de comprobación - predeterminado**.
6.  Guarde la definición de fila como **Saldo de comprobación detallado con atributos**.
7.  Con el cursor en la fila 50, seleccione **Editar** y, a continuación, **Insertar filas de dimensiones**. Insertar filas de dimensiones le permite elegir qué dimensiones desea tener en la definición de fila. Para este ejercicio, vamos a crear la definición de fila con Cuenta principal.
8.  Asegúrese de que **Cuenta principal** contiene todas las Y comerciales y seleccione **Aceptar**. La definición de fila contiene ahora todas las cuentas principales para la entidad jurídica USMF.
9.  Desplácese hasta la fila 11110 y elimínela.
10. En la fila 11080, seleccione **--- (importes con subrayado)**.
11. En la fila 11140, escriba **Total de todas las cuentas** en la columna B.
12. En la columna C, seleccione **TOT** en la lista desplegable.
13. Escriba **50:11080** en la columna D.
14. Seleccione **Guardar** la definición de fila. La definición de fila contiene ahora todas las cuentas más una fila total para agregar todas las cuentas de forma conjunta. A continuación, actualizaremos la definición de columna para incluir atributos de cuenta adicionales.
15. En la definición del informe **Saldo de comprobación detallado con atributos**, seleccione el icono de definición de columna para abrir la definición de columna **Resumen de saldo de comprobación – predeterminado**.
16. Guarde la definición de columna como **Saldo de comprobación detallado con atributos**. La definición de columna contiene columnas de datos financieros, una columna de la descripción y columnas de cálculo. Vamos a agregar columnas de atributo a la definición de columna para proporcionar detalles adicionales acerca de las cuentas.
17. Los atributos siguientes se agregarán a la definición de columna:
    -   Número de diario
    -   Descripción del diario
    -   Fecha de la transacción
    -   Creado por
    -   Última modificación por

18. En la columna I, seleccione **ATTR** como el tipo de columna. A continuación, seleccione **Número de diario** como la categoría del atributo.
19. Continúe agregando columnas para los atributos restantes.
20. En la fila **Encabezado 2**, agregue las descripciones para cada una de las nuevas columnas que se han agregado.
21. Guarde la definición de columna. Ahora que se han actualizado la definición de fila y la definición de columna, necesitaremos agregarlas a la definición del informe.
22. En la definición del informe **Saldo de comprobación detallado con atributos**, seleccione Saldo de comprobación detallado con atributos tanto para la definición de fila como para la definición de columna.
23. Cambie el año base a **2012**.
24. **Guarde** la definición del informe y **genere**. Una vez que el informe se termine de generar y se abra, puede explorarlo como lo hizo en el primer ejercicio. Explore en profundidad distintas cuentas para ver cómo se muestran los atributos adicionales.
25. Cierre el informe **Saldo de comprobación detallado con atributos**.
26. Cierre el **Diseñador de informes**.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>Ejercicio 3: Crear un informe multidimensional mediante un organigrama
Para este ejercicio, modificará un informe predeterminado existente. Se creará un organigrama y se agregará a una definición del informe para producir un informe de ingresos de centro de coste o por división. Una vez que se completen las actualizaciones, generará el informe de ingresos de centro de coste o por división y explorará el informe con el organigrama. Empezaremos por la lista Informes financieros.

1.  Vaya a **Informes financieros** en Consultas e informes en Contabilidad general.
2.  Seleccione la fila para el informe denominado **Informe de ingresos – predeterminado**.
3.  Seleccione **Editar**. **Informe de ingresos – predeterminado** se abrirá en el diseñador de informes.
4.  En el menú **Archivo**, seleccione **Nuevo** y, a continuación, haga clic en **Definición del organigrama**.
5.  En el menú **Editar**, haga clic en **Insertar unidades de notificaciones desde dimensiones**.
6.  Desactive las casillas para todas las dimensiones, excepto **Centro de coste**.
7.  Haga clic en el campo **Desde la dimensión** para la dimensión Centro de coste, escriba **007** y, a continuación, presione la tecla de tabulador. En el campo **Hasta la dimensión**, escriba **018**.
8.  **Guarde** el árbol resultante con el nombre **Centros de coste por división**. Ahora que se ha creado el organigrama, lo modificará para que contenga tres nuevas unidades de acumulación: Marketing, Operaciones y Venta minorista.
9.  En el menú **Ventana**, haga clic en **Centros de coste por división**. (Si el organigrama se ha cerrado; selecciónelo en las Definiciones de los organigramas en el panel de navegación.)
10. Haga clic en la unidad número dos, **Ferias de muestras** y haga clic en el icono **Insertar unidad de informe**.
11. Haga doble clic en la columna de la entidad de la fila en blanco y seleccione **USMF**.
12. Escriba **Marketing** en las columnas B y C.
13. Haga clic en el número de unidad cinco, **Operaciones de servicio** y haga clic con el botón secundario. Seleccione **Insertar unidad de informe**.
14. Repita el paso 11.
15. Escriba **Operaciones** en las columnas B y C.
16. Haga clic en la unidad número doce, **Tienda**, y haga clic con el botón secundario. Seleccione **Insertar unidad de informe**.
17. Repita el paso 11.
18. Escriba **Venta minorista** en las columnas B y C. Observe que las unidades Marketing, Operaciones y Venta minorista se muestran en el mismo nivel que las unidades de acumulación actuales. Las nuevas unidades se organizan a continuación. Las unidades de informes se organizan con las opciones de botón secundario; promover y disminuir, o arrastrar y colocar.
19. Compruebe que la unidad tres **Ferias de muestras**, está activa y haga clic con el botón secundario.
20. Seleccione **Disminuir nivel de una unidad de notificación**. Observe ahora que la unidad se muestra como elemento secundario de **Marketing**.
21. Haga clic en la unidad cuatro, **Marketing** **Campaña** y haga clic con el botón secundario.
22. Seleccione **Disminuir nivel de una unidad de notificación**.
23. Haga clic en la visualización gráfica **Operaciones de servicio**. Mantenga presionado el botón izquierdo mouse mientras arrastra la unidad arriba hasta **Operaciones**. Libere el botón izquierdo del mouse para colocar la unidad en la acumulación de la Operación. Repita para **Producción, Control de calidad, Logística, Adquisición y Administración**.
24. Haga **Mercado**, **Súper**, **Centro comercial** y **En línea** elementos secundarios de **Venta minorista** disminuyéndolos de nivel o arrastrándolos y colocándolos.
25. Guarde la reorganización resultante. Ahora que tenemos el árbol creado y organizado, se puede agregar a la definición del informe.
26. En el menú **Ventana**, seleccione **Informe de ingresos – predeterminado** para abrir la definición del informe.
27. Haga clic en la flecha desplegable **Tipo de árbol** y seleccione **Organigrama**.
28. Haga clic en la flecha desplegable Árbol y seleccione **Centros de coste por división**.
29. Cambie el año base a **2012**, **guarde** los cambios y **genere** el informe. Después de que el informe complete la generación y se abra, puede explorar el informe.
30. Seleccione la lista desplegable **Organigrama** para ver las unidades de informe. Como alternativa, puede explorar en profundidad una fila del informe para ver todos los saldos para todas las unidades del organigrama.
31. Cierre **Informe de ingresos - predeterminado**.
32. Cierre el **Diseñador de informes**.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>Ejercicio 4: Crear un informe consolidado con una jerarquía organizativa
Para este ejercicio, modificará un informe predeterminado existente. Agregará una jerarquía organizativa en la definición del informe para producir un informe de ingresos consolidado y un balance de situación. Una vez que se completen las actualizaciones, generará el informe consolidado y explorará el informe con el organigrama. Empezaremos por la lista Informes financieros.

1.  Vaya a **Informes financieros** en Consultas e informes en Contabilidad general.
2.  Seleccione la fila del informe denominado **Balance de situación e informe de ingresos en paralelo – predeterminado**
3.  Seleccione **Editar**. **Balance de situación e informe de ingresos en paralelo – predeterminado** se abrirá en el diseñador de informes.
4.  Seleccione **Archivo** &gt; **Guardar como** y asígnele el nombre **Balance de situación consolidado e informe de ingresos en paralelo al informe**.
5.  Cambie el año base a 2012.
6.  Haga clic en la flecha desplegable Árbol y seleccione **Jerarquías organizativas**.
7.  Haga clic en la flecha desplegable Árbol y seleccione **Contoso Holdings**.
8.  Guarde los cambios y genere el informe. Si se le solicita, seleccione todas las unidades de informe. Después de que el informe complete la generación y se abra, puede explorar el informe.
9.  Seleccione **Opciones de informe**.
10. Seleccione **Agregar una dimensión de filtro** y elija **Departamento**.
11. Escriba **022** en el campo y seleccione **Aceptar**.
12. Cierre el informe filtrado.
13. Seleccione la lista desplegable **Organigrama** para ver las unidades de informe. Como alternativa, puede explorar en profundidad una fila del informe para ver todos los saldos para todas las unidades del organigrama.
14. Cierre **Balance de situación consolidado e informe de ingresos en paralelo**.
15. Cierre el **Diseñador de informes**.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>Ejercicio 5: Crear un informe de departamento en paralelo
En este ejercicio, creará un informe nuevo. El informe es un informe de ingresos de departamento en paralelo. Usará una definición de fila existente, pero creará una definición del informe nueva y una definición de columna nueva que use filtros de dimensión. Empezaremos por la lista Informes financieros.

1.  Vaya a **Informes financieros** en Consultas e informes en Contabilidad general.
2.  Seleccione **Nuevo**. El diseñador de informes se abrirá con una definición del informe en blanco abierta. Su primera tarea será crear la definición de columna.
3.  Cree una nueva definición de columna haciendo clic en **Archivo**, **Nuevo** y, a continuación, en **Definición de columnas**.
4.  En la **Columna A**, seleccione **DESC** para el tipo de columna.
5.  En la **Columna B**, seleccione **FD** para el tipo de columna.
6.  Haga doble clic en el campo **Filtro de dimensiones**.
7.  En la ventana **Dimensión**, haga doble clic en la columna **Departamento**.
8.  En la sección Individual o intervalo del diálogo, haga clic en los **puntos suspensivos** para el campo **De** para que aparezca una lista de departamentos.
9.  Seleccione el departamento **022**, **Ventas y marketing** y, a continuación, haga clic en **Aceptar**.
10. Repita los pasos 5 al 8 para los departamentos 23-25.
11. En la fila **Encabezado 2** para cada columna FD, escriba las siguientes descripciones de departamento:
    -   Columna B – Ventas y marketing
    -   Columna C – Operaciones
    -   Columna D – Finanzas
    -   Columna E - TI

12. Guarde la definición de columna como Departamentos en paralelo. Dado que estamos usando una definición de fila existente, la definición del informe se puede modificar ahora para tener la definición de columna recién creada y la definición de fila existente.
13. En el menú **Ventana**, seleccione **Nueva definición del informe** para abrir la definición del informe.
14. Seleccione **Informe de ingresos - predeterminado** como la definición de fila y **Departamentos en paralelo** como la definición de columna.
15. Guarde la definición del informe como **Informe de ingresos de departamento en paralelo**.
16. Cambie el año base a **2012**.
17. Cambiar el nivel de detalle a **Financiero, Cuenta y Transacción**.
18. **Guarde** sus cambios y **genere**. Una vez que el informe complete la generación y se abra, puede explorar el informe.

## <a name="additional-resources"></a>Recursos adicionales
[Informes financieros](/dynamics365/unified-operations/financials/general-ledger/financial-reporting-getting-started) 
[Ver informes financieros](/dynamics365/unified-operations/financials/general-ledger/view-financial-reports) 
[Blog de Dynamics Financial Reporting](http://blogs.msdn.com/b/dynamics_financial_reporting/)




