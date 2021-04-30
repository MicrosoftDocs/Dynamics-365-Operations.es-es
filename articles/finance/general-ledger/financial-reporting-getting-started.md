---
title: Visión general de informes financieros
description: Este tema describe cómo acceder a los informes financieros en Microsoft Dynamics 365 Finance y cómo usar las capacidades de informes financieros.
author: aprilolson
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4de7f7f5f501024b7698736ded80405b9291cb58
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897045"
---
# <a name="get-started-with-financial-reporting"></a>Introducción a Financial Reporting 

[!include [banner](../includes/banner.md)]

Este tema describe cómo acceder a los informes financieros y cómo usar las capacidades de informes financieros. También incluye una descripción de los informes financieros predeterminados proporcionados.

<a name="accessing-financial-reporting"></a>Acceso a informes financieros
-----------------------------

Encontrará el menú **Informes financieros** en los siguientes lugares:

-   **Contabilidad general** &gt; **Consultas e informes**
-   **Gestión presupuestaria** &gt; **Consultas e informes** &gt; **Gestión presupuestaria básica**
-   **Gestión presupuestaria** &gt; **Consultas e informes** &gt; **Gestión presupuestaria básica**
-   **Gestión presupuestaria** &gt; **Consultas e informes** &gt; **Control presupuestario**
-   Consolidaciones

Para crear y generar informes financieros para una entidad jurídica, debe configurar la siguiente información para esa entidad jurídica:

-   Calendario fiscal
-   Contabilidad
-   Plan de cuentas
-   Divisa
-   Publica una transacción en al menos una cuenta
-   MainAccount aparece en la columna selecciona en **Libro mayor > Configuración de libro mayor > Configuración de Financial Reporting**

## <a name="granting-security-access-to-financial-reporting"></a>Concesión de acceso de seguridad a los Financial Reporting
Las funciones de informes financieros están disponibles para los usuarios que tienen los privilegios y los derechos adecuados asignados con sus roles de seguridad. Las secciones siguientes muestran estos privilegios y deberes, junto con los roles asociados.

### <a name="duties"></a>Deberes

| Etiqueta de arancel                            | Descripción                                                             | Nombre AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Mantener seguridad de informes financieros | Mantener la seguridad de los informes financieros y realizar tareas administrativas. | FinancialReportsSecurityMaintain |
| Mantener informes financieros            | Diseñar y mantener informes financieros.                                  | FinancialReportsMaintain         |
| Generar informes financieros            | Generar y actualizar informes financieros.                                 | FinancialReportsGenerate         |
| Revisar rendimiento financiero          | Revisar y analizar rendimiento financiero.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilegios

| Etiqueta del privilegio                       | Descripción                                                             | Nombre AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Mantener seguridad de informes financieros | Mantener la seguridad de los informes financieros y realizar tareas administrativas. | FinancialReportsSecuritySystemMaintain |
| Mantener informes financieros            | Diseñar y mantener informes financieros.                                  | FinancialReportsMaintainReports  |
| Generar informes financieros            | Generar y actualizar informes financieros.                                 | FinancialReportsGenerateReports  |
| Ver informes financieros                | Ver informes financieros.                                                 | FinancialReportsView             |

### <a name="roles"></a>Roles

| Etiqueta del privilegio                       | Derecho                                  | Roles                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Mantener seguridad de informes financieros | Mantener seguridad de informes financieros | Administrador de seguridad                                                          |
| Mantener informes financieros            | Mantener informes financieros            | Administrador contable, Supervisor de contabilidad, Controlador financiero, Administrador presupuestario |
| Generar informes financieros            | Generar informes financieros            | Director financiero, CFO, contable                                                            |
| Ver informes financieros                | Revisar rendimiento financiero          | Ninguno asignado                                                                   |

Tras la adición de un usuario o el cambio de un rol, el usuario debe poder tener acceso a informes financieros al cabo de unos minutos. 

> [!NOTE]
> El rol sysadmin se agrega a todos los roles en informes financieros.

## <a name="report-deletions-and-expirations"></a>Notificar eliminaciones y vencimientos
Los usuarios que generan un informe pueden eliminar sus propios informes. Los usuarios con el deber **Mantener seguridad de informes financieros** puede eliminar los informes de otros. 

En la versión 10.0.8, se introdujo el concepto de fechas de vencimiento. Está habilitada una nueva función requerida en la página **Todas**, dentro del espacio de trabajo de gestión de características. La característica **Políticas de retención de informes financieros** contiene los siguientes cambios:
* Los informes recién generados se marcarán automáticamente con una fecha de vencimiento de 90 días a partir de la fecha en que se generen.
* Cualquier informe existente que sea anterior a la instalación de la característica tendrá un período de vencimiento de 90 días. La fecha puede mostrarse en blanco durante un corto período de tiempo hasta que se ejecute el servicio de informes financieros, se genere un informe y el servicio realice la actualización de los informes existentes con una fecha de vencimiento en blanco. 
* Los usuarios con **Mantener seguridad de informes financieros** tienen acceso a esta funcionalidad. Cualquier usuario con el deber **Mantener informes financieros** que tenga concedido el privilegio **Mantener el vencimiento del informe financiero** también tendrá la capacidad de modificar el período de vencimiento. Actualmente hay dos opciones de retención disponibles: 
  * Un vencimiento de 90 días.
  * La opción de establecer que el informe nunca venza.
  
Cuando se selecciona un vencimiento, como 90 días, se aplica 90 días a partir de hoy. Este es un comportamiento diferente al de los 90 días desde la fecha de generación original establecida cuando se generó el informe. 
  
Se considerarán opciones adicionales en la funcionalidad futura. El vencimiento de 90 días será el predeterminado y los usuarios con los permisos adecuados pueden anular la configuración predeterminada en la página de lista **Informes financieros**.    

## <a name="default-reports"></a>Informes predeterminados
Los informes financieros proporcionan 22 informes financieros predeterminados. Cada informe usa las categorías de cuenta principal predeterminada. Puede usar estos informes tal cual o como punto de partida para las necesidades de informes financieros. Además de los informes financieros tradicionales, como Informe financiero y Balance de situación, estos informes predeterminados incluyen informes que muestran los diferentes tipos de informes financieros que puede crear. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Informe predeterminado                                                                                         | Descripción                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Informe de ingresos de columna única móvil de 12 meses – predeterminado | Vea la rentabilidad de una organización durante los últimos 12 meses en una sola columna.                                                                                                                                                                                                                                      |
| Informe de ingresos de tendencias de 12 meses – predeterminado                 | Vea la rentabilidad de una organización para cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                             |
| Real frente a presupuesto - predeterminado                                | Vea información detallada de saldo para todas las cuentas para el presupuesto original y compare el presupuesto revisado con los valores reales que tienen una desviación.                                                                                                                                                                          |
| Detalles de auditoría - predeterminado                                  | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito en la divisa de notificación y la divisa local, junto con la información de transacciones adicional, como el id. de usuario, el usuario que modificó los datos por última vez, la fecha de la última modificación y el id. de diario. |
| Lista de saldos - predeterminado                                   | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de apertura y cierre, y los saldos de débito y crédito para el período actual y el año hasta la fecha, junto con la información de transacciones adicional, como el asiento.                                                                    |
| Balance de situación - predeterminado                                   | Vea la posición financiera de la organización para el año.                                                                                                                                                                                                                                                             |
| Balance de situación e informe de ingresos en paralelo - predeterminado | Ver la rentabilidad y posición financiera de la organización para el año de forma simultánea.                                                                                                                                                                                                                              |
| Flujo de efectivo - predeterminado                                       | Obtenga información del efectivo que entra y sale de la organización.                                                                                                                                                                                                                                   |
| Revisión de JE y TB detallada – predeterminado                      | Vea el saldo de apertura y la información de la actividad para todas las cuentas.                                                                                                                                                                                                                                                      |
| [Saldo de comprobación detallado - predeterminado](trial-balance-financial-reports.md)| Vea información de saldo para todas las cuentas que tengan saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                                                                                                                                  |
| Tendencia trimestral de tres años de gastos – predeterminado             | Obtenga información de los gastos de los últimos 12 trimestres durante los tres años anteriores.                                                                                                                                                                                                                                   |
| Revisión de JE y TB de títulos financieros – predeterminado            | Muestra una visión general de los saldos y de la actividad de los títulos financieros del activo, el pasivo, los recursos propios del propietario, los ingresos, los gastos, el incremento o las pérdidas o ganancias.                                                                                                                                                                           |
| [Informe de ingresos – predeterminado](income-statement-financial-report.md)| Vea la rentabilidad de la organización para el período actual y para el ejercicio hasta la fecha.                                                                                                                                                                                                                                   |
| Lista de transacciones contables – predeterminado                        | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito, junto con la información de transacciones adicional, como la fecha de transacción, el número de diario, el asiento, el tipo de registro y el número de seguimiento.                                                                            |
| Coeficientes – predeterminado                                          | Vea los coeficientes de solvencia, rentabilidad y eficiencia para la organización durante el año.                                                                                                                                                                                                                           |
| Gastos de 12 meses continuos – predeterminado                       | Obtenga información de los gastos de cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                                       |
| Informe de ingresos de trimestres continuos – predeterminado               | Vea la rentabilidad de la organización cada trimestre durante el último año y también del año hasta la fecha.                                                                                                                                                                                                                   |
| Balance de situación en paralelo – predeterminado                      | Vea la posición financiera de la organización para el año. Este informe muestras activos y pasivo y los recursos propios de los accionistas en paralelo.                                                                                                                                                                                |
| [Resumen de saldo de comprobación – predeterminado](trial-balance-financial-reports.md)| Vea la información de saldo para todas las cuentas que tienen saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.                                                                                                                                                                  |
| [Resumen de saldo de comprobación año por año – predeterminado](trial-balance-financial-reports.md)| Vea la información de saldo para todas las cuentas que tienen saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior.                                                                                                                           |
| Ventas y descuentos semanales - predeterminado                     | Obtenga información de las ventas y los descuentos para cada semana de un mes. Este informe incluye un total de cuatro semanas.                                                                                                                                                                                                              |
| Depositar fondos presupuestarios disponibles - Valor predeterminado                         | Vea una comparación detallada de presupuesto revisado, gastos reales, reservas de presupuesto y fondos de presupuestos disponibles para todas las cuentas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura de informes financieros
Al seleccionar el menú **Informes financieros**, se muestra la lista de informes financieros predeterminados para la empresa. A continuación, puede abrir o modificar un informe. Para abrir uno de los informes predeterminados, seleccione el nombre del informe. La primera vez que se abre un informe, se genera automáticamente para el mes anterior. Por ejemplo, si abre un informe por primera vez en agosto de 2019, el informe se genera para el 31 de julio de 2019. Tras abrir un informe, puede empezar a explorarlo profundizando en fragmentos específicos de datos y cambiando las opciones de informe.

## <a name="creating-and-modifying-financial-reports"></a>Creación y modificación de informes financieros
A partir de la lista de informes financieros, puede crear un nuevo informe o modificar un informe existente. Si dispone de los permisos adecuados, puede crear un nuevo informe financiero seleccionando **Nuevo** en el panel Acciones. Se descarga un programa del diseñador de informes en el dispositivo. Una vez iniciado el diseñador de informes, puede crear el nuevo informe. Tras guardar el nuevo informe, aparece en la lista de informes financieros. En la lista se muestran solo los informes que se crearon para la empresa que está usando en Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Definiciones de los organigramas 
Uno de los componentes que se utiliza para crear informes financieros es una definición de árbol de informes. Una definición de árbol de informes ayuda a definir la estructura y la jerarquía de la organización. Es una estructura jerárquica dimensional que se basa en las relaciones dimensionales de los datos financieros. Proporciona información en el nivel de la unidad de informes y en un nivel de resumen para todas las unidades del árbol.

Puede crear un número ilimitado de organigramas para mostrar los datos de su organización de distintas maneras. Cada árbol de informes puede contener cualquier combinación de departamentos y unidades de resumen, pero una definición de informe solo puede vincularse a un árbol de informes a la vez. 


## <a name="troubleshooting-issues-opening-report-designer"></a>Solución de problemas al abrir Diseñador de informes
Existen algunos problemas comunes que pueden causar problemas al abrir Diseñador de informes. Esos problemas y los pasos para resolverlos son los siguientes.

Problema 1: Diseñador de informes no se inicia cuando selecciona **Nuevo** o **Editar**.

* En Internet Explorer, seleccione **Configuración** y luego **Opciones de Internet**. Seleccione la pestaña **Seguridad**. Seleccione Sitios de confianza y luego elija **Sitios**. En **Agregar este sitio web a la zona**, introduzca "\*\.dynamics.com" (sin comillas) y luego seleccione **Agregar**. 
* En Internet Explorer, seleccione **Configuración** y luego **Opciones de Internet**. Seleccione la pestaña **Seguridad**. Seleccione Sitios de confianza. En el área etiquetada como Nivel de seguridad para esta zona, cambie la opción a **Medio-bajo**.
* Deshabilite el bloqueador de elementos emergentes en su navegador.
* Se requieren estaciones de trabajo para instalar Microsoft .NET Framework 4.6.2 o superior. Esta versión de Microsoft .NET Framework puede descargarse e instalarse desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53345).
* Si está usando el explorador Chrome, debe instalar una extensión ClickOnce para descargar el cliente de Diseñador de informes. Si está ejecutando Chrome en modo ingógnito, asegúrese de que la extensión ClickOnce esté activada para el modo incógnito. Para obtener más información acerca de la extensión ClickOnce de Chrome, consulte [Requisitos del sistema para implementaciones en la nube](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Si esta usando Microsoft Edge con un navegador Chrome, no es necesario instalar una extensión ClickOnce para Edge Chromium. Sin embargo, debe habilitar la opción ClickOnce para descargar el cliente Diseñador de informes. Si está ejecutando en modo incógnito, asegúrese de que la extensión ClickOnce está activada para el modo incógnito.
     1. Abra un nuevo navegador en Microsoft Edge.
     2. Introduzca **edge://flags** y seleccione **Intro**.
     3. Busque la opción **Soporte ClickOnce** o utilice este enlace directo: **edge://flags/#edge-click-once**.
     4. Establezca la opción del menú desplegable en **Habilitado**.
     5. Seleccione **Reiniciar navegador**.

Problema 2: al usuario no se le han asignado los permisos necesarios para utilizar Financial Reporting. 

* Para verificar si el usuario no tiene permiso, seleccione **Sí** en el error “No se puede conectar con el servidor de Financial Reporting. Seleccione Sí caso de que desee continuar y especifique una dirección de servidor diferente.” Luego, seleccione **Prueba de conexión**. Si no tiene permiso, verá un mensaje que dice "Error en el intento de conexión. El usuario no tiene los permisos adecuados para conectarse al servidor. Póngase de contacto con el administrador del sistema”.
* Los permisos requeridos se enumeran anteriormente, en [Conceder acceso de seguridad a Financial Reporting](#granting-security-access-to-financial-reporting). La seguridad en Financial Reporting se basa en estos privilegios. No tendrá acceso a menos que se le asignen estos privilegios (u otra función de seguridad que incluya estos privilegios). 
* La tarea de integración **Proveedor de usuarios empresariales a la empresa** (que también es responsable de la integración de usuarios y se la llama así) se ejecuta en un intervalo de 5 minutos. Pueden pasar hasta 10 minutos para que cualquier cambio de permiso entre en vigencia en Financial Reporting. 
  Si otro usuario puede abrir el Diseñador de informes, seleccione **Herramientas** y luego seleccione **Estado de integración**. Verifique que el mapa de integración, "Proveedor de usuarios empresariales a la empresa" se haya ejecutado correctamente porque se le asignó permiso para usar Financial Reporting. 
* Es posible que otro error haya impedido que termine **Integración de usuario de Dynamics con usuario de Financial Reporting**. O es posible que se haya iniciado un reinicio de datamart y aún no se haya completado, o que se haya producido otro error del sistema. Intente ejecutar el proceso nuevamente más tarde. Si el problema persiste, comuníquese con el administrador del sistema.

Problema 3: puede pasar de la página de inicio de sesión ClickOnce de Diseñador de informes, pero no puede completar el inicio de sesión en Diseñador de informes. 

* La hora establecida en el ordenador local cuando introduce sus credenciales de inicio de sesión debe estar dentro de los cinco minutos posteriores a la hora del servidor de Financial Reporting. Si hay una diferencia de más de cinco minutos, el sistema no permitirá el inicio de sesión. 
* En este caso, recomendamos habilitar la opción de Windows para configurar la hora de su PC automáticamente. 

## <a name="additional-resources"></a>Recursos adicionales
- [Ver informes financieros](view-financial-reports.md)
- [Definiciones de organigramas en informes financieros](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]