---
title: Generar un informe financiero
description: "Este tema proporciona información acerca de la generación de un informe financiero."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 01bb8999e5d9c0e16f133a621ebfe1d102565f2f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="generate-a-financial-report"></a>Generar un informe financiero

[!include[banner](../includes/banner.md)]


Este tema proporciona información acerca de la generación de un informe financiero. 

Para generar un informe, abra la definición del informe y haga clic en el botón Generar en la barra de herramientas. La ventana Estado de la cola del informe abrirá e indicará la ubicación del informe en la cola. De forma predeterminada, el informe generado se abrirá en el visor de la web.
| ![Nota](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Nota")**Nota**        |
|------------------------------------------------------------------------------------------------|
| Puede generar informes únicamente en las carpetas y ubicaciones en las que tiene permiso de acceso. |

En la siguiente tabla se explican las opciones disponibles para generar informes.

| Opción                                                                                | Para obtener más información |
|---------------------------------------------------------------------------------------|----------------------|
| Configurar una programación para generar un informe o a un grupo de informes automáticamente              |                      |
| Revisar cuentas o datos que faltan en un informe y validar la precisión de un informe |                      |

Al generar un informe, se usan las opciones que ha especificado en la pestaña Definición del informe . La pestaña Salida y distribución permite especificar una ubicación de la biblioteca del informe, lo cual proporciona una manera fácil de compartir el informe.

## <a name="schedule-report-generation"></a> Generación del informe de la programación
Muchas empresas tienen un conjunto básico de informes que se ejecutan en intervalos programados para alinearlos con sus procesos de negocio. Puede programar un informe para que se genere con regularidad, por ejemplo diaria, semanal, mensual o anualmente. Esto puede realizarse en un solo informe o en un grupo de informes que incluye varias compañías. Deberá especificar las credenciales para cada una de las compañías especificadas, tales como las de una definición de organigrama. Si las credenciales no son válidas, el informe mostrará solo la información a la que tiene permiso de acceso, como la empresa en la que ha iniciado sesión en este momento. La información de salida se lee primero en el grupo de informes y luego en los informes individuales.

A medida que se crean y se guardan las programaciones del informe, se muestran en el panel de navegación en Programaciones del informe. Puede crear carpetas para organizar los informes. Si un informe en una programación no se ejecuta, el resto de los informes seguirán ejecutándose.
| ![Importante](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Importante")**Importante**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Para crear, modificar y eliminar las programaciones de informes, debe tener el rol de diseñador o de administrador. Cuando se ejecuta un informe, se usan las credenciales del usuario que creó la programaciónpara generar el informe. |

### <a name="create-a-report-schedule"></a>Crear una programación del informe

1.  En el diseñador de informes, en el menú Archivo, haga clic en Nuevo y luego seleccione Programación del informe. Se abre el cuadro de diálogo Nueva programación del informe.
2.  En Configuración, seleccione un informe individual o un grupo de informes para programar. Solo estarán disponibles los informes o grupos de informes de la selección de compañía o bloque de creación en la que haya iniciado sesión.
3.  Active la casilla Activo para activar la programación de informes. Solamente el creador del informe o un administrador puede activar o desactivar una programación de informe.
4.  Haga clic en el botón Permisos para especificar las credenciales de la compañía. De manera predeterminada, la información de inicio de sesión se usa para la compañía en la que haya iniciado sesión. Si se incluyen otras compañías, por ejemplo en las definiciones de organigrama, seleccione Usar otras credenciales y especifique las credenciales de otra compañía incluida en la programación de informes. Puede seleccionar Autenticación de Windows o escribir un nombre de usuario y una contraseña para cada compañía. Active la casilla Guardar credenciales para guardar las credenciales de dichas empresas y, a continuación, haga clic en Aceptar para cerrar el cuadro de diálogo.
5.  En Frecuencia, en el campo Iniciar periodicidad, seleccione la fecha en la que comenzará la programación. De manera predeterminada, se selecciona la fecha de sistema actual del equipo cliente.
6.  En el campo Ejecutar el informe a las, seleccione la hora a la que debe ejecutarse el informe. Si especifica una hora anterior a la hora actual del sistema, el informe se ejecutará en la siguiente fecha programada.
7.  En el área Patrón de periodicidad, especifique la frecuencia de ejecución del informe. De forma predeterminada, Todos los días se selecciona con un valor de Intervalo (días) de 1. Otras opciones incluyen Todas las semanas, Todos los meses y Todos los años.
8.  En el área Intervalo de periodicidad, seleccione cuándo el informe debe dejar de generarse.
    -   Sin fecha de finalización: la programación de informe se ejecuta de manera indefinida.
    -   Establecer número de instancias: la programación de informe se ejecuta el número de veces especificado y luego se desactiva.
    -   Finalizar antes del: la programación de informe finaliza en la fecha especificada.

9.  Haga clic en Guardar en la barra de herramientas. En el cuadro de diálogo Guardar como, especifique un nombre y una descripción únicos para la programación del informe.

Para copiar una programación de informe, debe tener el rol de diseñador o de administrador. Incluso si un administrador modifica la programación del informe, el informe mantiene las credenciales del usuario que creó el informe.
### <a name="copy-a-report-schedule"></a>Copiar una programación nueva

1.  En el diseñador de informes, haga clic en Programaciones del informe en el panel de navegación y abra la programación del informe que desea copiar.
2.  En el menú Archivo, haga clic en Guardar como y especifique un nombre nuevo y una descripción de la programación en el cuadro de diálogo Guardar como. Haga clic en Aceptar. La nueva programación se mostrará en el panel de navegación.
3.  En la nueva programación, modifique los campos y la información según sea necesario, y haga clic en Guardar en la barra de herramientas, o haga clic en Guardar en el menú Archivo.

Para eliminar una programación del informe, debe ser el propietario de la programación del informe o tener un rol de administrador.
### <a name="delete-a-report-schedule"></a>Eliminar una programación del informe

1.  En el diseñador de informes, haga clic en Programaciones de informes en el panel de navegación.
2.  Seleccione la programación de informe que desee eliminar y haga clic en Eliminar o presione la tecla Supr.
3.  En el cuadro de diálogo de confirmación de eliminación, haga clic en Sí para eliminar permanentemente la programación de informe. Si no tiene permiso para eliminar la programación, se mostrará un mensaje y el informe no se eliminará.

### <a name="credentials-and-report-schedules"></a>Credenciales y programaciones de informes

Si no especifica las credenciales necesarias para todas las empresas incluidas en los informes, aparece el siguiente mensaje al guardar la programación del informe: “Debe especificar sus credenciales para las empresas que se incluyen en esta programación del informe. seleccionar el botón Permisos para especificar las credenciales.

Por ejemplo, Fernanda inicia sesión en la empresa A usando su nombre y contraseña. Crea una programación para un informe que usa una definición del orgnaigrama para recopilar datos de varias empresas. Al guardar la programación del informe, se le solicita a Yolanda que especifique las credenciales para las demás compañías especificadas en la definición de organigrama. Cuando caduquen sus credenciales, los informes afectados en la programación del informe no se generarán hasta que se hayan actualizado las credenciales. Aparecerá un mensaje en la cola de informes para indicar que se deben actualizar los permisos. La programación del informe falla si tienen lugar las siguientes situaciones (porque requieren credenciales):
-   Se ha agregado a una nueva empresa a un árbol de informes para un informe individual.
-   Se modificó un informe en un grupo de informes.
-   Se agregó a un grupo de informes un nuevo informe para una compañía adicional.

Para continuar, haga clic en el botón Permisos en el cuadro Programación de informes y, a continuación especifique las credenciales adecuadas.

## <a name="missing-account-analysis-feature"></a>Característica que falta de análisis de la cuenta
Puede buscar las dimensiones y las cuentas financieras que podrían faltar en las definiciones de filas, informando definiciones de organigramas y definiciones del informe en un grupo de bloques de creación. Esto es útil cuando crea o se actualiza varias cuentas o bloques de creación durante un período de tiempo corto, y desea comprobar que toda la nueva información se incluye en los informes.

Las cuentas que faltan se determinan mediante los valores más bajos y más altos de la definición de filas o de la definición del organigrama, y después muestra una lista de cuentas que no están en la definición de filas o en la definición del organigrama, sino en los datos financieros. Si una cuenta que falta es superior o inferior a los valores en la definición de filas, esa cuenta no se incluye en la lista de cuentas que faltan.
| ![Sugerencia](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Sugerencia")**Sugerencia**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| Para fines de validación, este proceso debe ser ejecutado antes de generar informes mensuales y al crear nuevos bloques de creación. |

No suelen faltar cuentas en los informes que tiene intervalos de valores. Si es posible, use los intervalos en el bloque de creación para incluir nuevas cuentas cuando se crean. Si una definición del informe se establece como empresa @ANY, puede iniciar sesión en una empresa específica y ejecutar un análisis de cuentas que faltan para esa empresa.
| ![Nota](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Nota")**Nota**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si se ha agregado una nueva empresa, debe agregar la nueva empresa a los organigramas en cualquier informe existente o la empresa no estará incluida en el análisis de cuentas que faltan. |

### <a name="run-missing-account-analysis"></a>Ejecutar análisis de cuentas que faltan

1.  En el diseñador del informe, haga clic en Herramientas y luego haga clic en Análisis de cuentas que faltan.
2.  En el campo Filtro de compañía, seleccione una compañía según la que filtrar los resultados o seleccione Todo (sin filtro) para mostrar los resultados de todas las compañías disponibles.
3.  En el campo Filtro de dimensiones, seleccione una dimensión según la que filtrar los resultados o seleccione Todo (sin filtro) para ver toda la información de dimensión de todas las dimensiones disponibles.
4.  En el campo Agrupar por, seleccione una opción para ordenar los resultados. Puede ordenar los resultados según el bloque de creación afectado u ordenar los resultados por conjuntos de dimensiones y valores.
5.  Revise los resultados que se muestran. Cuando selecciona un elemento en el panel superior, el panel inferior muestra información adicional acerca de la excepción. Esto incluye las dimensiones, los valores y los informes relacionados.
6.  Para abrir el elemento afectado, haga clic en el icono asociado que se muestra en el panel de la lista, o haga clic con el botón secundario en el elemento y seleccione Abrir. Para seleccionar varios elementos, mantenga presionada la tecla Ctrl mientras selecciona los elementos en el panel inferior.
7.  Si se devuelven algunos valores, bloques de creación o informes que no deberían estar incluidos en el análisis, haga clic con el botón secundario en el elemento y seleccione Excluir o active la casilla Excluir unto al elemento para quitar el elemento de la lista. Los artículos excluidos no se incluyen al actualizar la lista. Para seleccionar varios elementos, mantenga presionada la tecla Ctrl mientras selecciona los elementos en el panel inferior. Para ver todos los elementos, incluidos los resultados que haya seleccionado anteriormente para excluir de análisis, active la casilla Muestra los bloques de creación y los valores excluidos y, a continuación, haga clic en Actualizar.
8.  Haga clic en Actualizar para actualizar las excepciones tratadas. Haga clic en Sí para realizar una actualización completa de todos los resultados o haga clic en No para realizar una actualización parcial.
    | ![Nota](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Nota")**Nota**                    |
    |------------------------------------------------------------------------------------------------------------|
    | El formulario se actualiza automáticamente cuando se abre, a menos que el formulario se haya abierto en los 15 últimos minutos. |

9.  Cuando los problemas estén resueltos, haga clic en Aceptar para cerrar el cuadro de diálogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Métodos abreviados de teclado para el análisis de cuentas que faltan
Cuando se ejecuta un análisis de cuentas que faltan, los métodos abreviados de teclado siguientes están disponibles.

| Para realizar esta tarea                           | Use este método abreviado de teclado |
|--------------------------------------|----------------------------|
| Filtrar por empresa                    | Alt+C                      |
| Filtrar por dimensión                  | Alt+D                      |
| Seleccionar el campo Agrupar por            | Alt+G                      |
| Mostrar bloques de creación y valores excluidos      | Alt+S                      |
| Actualizar los resultados                      | Alt+R                      |
| Excluir el bloque de creación seleccionado  | Alt+X                      |
| Excluir la definición de fila seleccionada  | Ctrl+B                     |
| Excluir el valor de dimensión seleccionado | Ctrl+D                     |
| Abrir la definición del informe seleccionado  | Ctrl+R                     |
| Abrir la definición de fila seleccionada     | Ctrl+O                     |

 
<a name="see-also"></a>Consulte también
--------

[Informes financieros](financial-reporting-intro.md)

[Interfaz del diseñador de informes](report-designer-interface.md)



