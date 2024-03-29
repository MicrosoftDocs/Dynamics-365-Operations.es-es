---
title: Información general de informes financieros
description: Este artículo describe cómo acceder a los informes financieros en Microsoft Dynamics 365 Finance y cómo usar las capacidades de informes financieros.
author: aprilolson
ms.date: 06/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "10444"
- intro-internal
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d0c2e821ee504cd62a536674ef91ee89a25c0a9
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066429"
---
# <a name="get-started-with-financial-reporting"></a>Introducción a los informes financieros 

[!include [banner](../includes/banner.md)]

Este artículo describe cómo acceder a los informes financieros y cómo usar las capacidades de informes financieros. También incluye una descripción de los informes financieros predeterminados proporcionados.

## <a name="enable-financial-reporting"></a>Habilitar informes financieros
Para usar el servicio de informes financieros para su organización, un administrador de Lifecycle Services (LCS) debe habilitar este servicio en el portal de LCS para su organización. Si los informes financieros no se han aprovisionado para su entorno, comuníquese con su administrador de LCS para habilitar el servicio. 

## <a name="accessing-financial-reporting"></a>Acceso a los informes financieros

Encontrará el menú **Informes financieros** en los siguientes lugares:

- **Contabilidad general** > **Consultas e informes**
- **Gestión presupuestaria** > **Consultas e informes** > **Gestión presupuestaria básica**
- **Gestión presupuestaria** > **Consultas e informes** > **Gestión presupuestaria básica**
- **Gestión presupuestaria** > **Consultas e informes** > **Control presupuestario**
- Consolidaciones

Para crear y generar informes financieros para una entidad jurídica, debe configurar la siguiente información para esa entidad jurídica:

- Calendario fiscal
- Contabilidad
- Plan de cuentas
- Divisa
- Publica una transacción en al menos una cuenta
- MainAccount aparece en la columna **Seleccionada** en la página **Configuración de Financial Reporting** (**Contabilidad general > Configuración de la contabilidad general > Configuración de Financial Reporting**)

## <a name="granting-security-access-to-financial-reporting"></a>Concesión de acceso de seguridad a Financial Reporting

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

| Etiqueta del privilegio                       | Deber                                  | Roles                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Mantener seguridad de informes financieros | Mantener la seguridad de informes financieros | Administrador de seguridad                                                          |
| Mantener informes financieros            | Mantener informes financieros            | Administrador contable, Supervisor de contabilidad, Controlador financiero, Administrador presupuestario |
| Generar informes financieros            | Generar informes financieros            | Director financiero, CFO, contable                                                            |
| Ver informes financieros                | Revisar rendimiento financiero          | Ninguno asignado                                                                   |

Tras la adición de un usuario o el cambio de un rol, el usuario debe poder tener acceso a Financial reporting al cabo de unos minutos. 

> [!NOTE]
> El rol sysadmin se agrega a todos los roles en informes financieros.

## <a name="report-deletions-and-expirations"></a>Notificar eliminaciones y vencimientos

Los usuarios que generan un informe pueden eliminar sus propios informes. Los usuarios con el deber **Mantener seguridad de informes financieros** puede eliminar los informes de otros. 

En la versión 10.0.8, se introdujo el concepto de fechas de vencimiento. Está habilitada una nueva función requerida en la página **Todas**, dentro del espacio de trabajo de administración de características. La característica **Políticas de retención de informes financieros** contiene los siguientes cambios:
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
| Balance de situación e informe de ingresos en paralelo - predeterminado | Vea la rentabilidad y posición financiera de la organización para el año de forma simultánea.                                                                                                                                                                                                                              |
| Flujo de efectivo - predeterminado                                       | Obtenga información del efectivo que entra y sale de la organización.                                                                                                                                                                                                                                   |
| Revisión de JE y TB detallada – predeterminado                      | Vea el saldo de apertura y la información de la actividad para todas las cuentas.                                                                                                                                                                                                                                                      |
| [Saldo de comprobación detallado - predeterminado](trial-balance-financial-reports.md)| Vea información de saldo para todas las cuentas que tengan saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                                                                                                                                  |
| Tendencia trimestral de tres años de gastos – predeterminado             | Obtenga información de los gastos de los últimos 12 trimestres durante los tres años anteriores.                                                                                                                                                                                                                                   |
| Revisión de JE y TB de títulos financieros – predeterminado            | Muestra una visión general de los saldos y de la actividad de los subtítulos financieros del activo, el pasivo, los recursos propios del propietario, los ingresos, los gastos, el incremento o las pérdidas o ganancias.                                                                                                                                                                           |
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

## <a name="update-the-financial-reporting-version-through-slipstreaming"></a>Actualizar la versión de informes financieros a través de la integración

Las aplicaciones de finanzas y operaciones se actualizan todos los meses. Sin embargo, los informes financieros no se actualizan necesariamente con esa cadencia. Además, los clientes tienen más opciones sobre cuándo implementar actualizaciones para las aplicaciones de finanzas y operaciones. Las actualizaciones de informes financieros se instalan automáticamente. Los informes financieros tienen una versión designada que se utiliza en un entorno de cliente cuando se implementa una actualización de servicio, cuando se inicia el tiempo de inactividad o cuando el entorno de un cliente está en modo de mantenimiento. Este proceso se conoce como *deslizamiento* o *verdad hasta*, porque todas las implementaciones de los clientes están configuradas con la misma versión de informes financieros.

Los cambios que se publican en cada versión se pueden encontrar en [Novedades y cambios de Dynamics 365 Finance](../../finance/get-started/whats-new-home-page.md). Las actualizaciones de la plataforma y las correcciones de errores se pueden encontrar en la sección "Recursos adicionales" en la parte inferior de la página de cada versión.

La versión de deslizamiento seleccionada es una versión revisada y validada de los informes financieros que está lista para la producción. Es compatible con cualquier versión anterior o futura de Dynamics 365 Finance. Por ejemplo, los informes financieros pueden estar en la última compilación 10.0.19, mientras el cliente todavía tiene la versión 10.0.16 de la aplicación.

> [!NOTE]
> La única circunstancia en la que los clientes pueden pasar a una versión anterior (un escenario de degradación) ocurre si Microsoft detiene un lanzamiento real debido a un problema. Tan pronto como haya una solución disponible, se aplicará automáticamente.

El proceso de deslizamiento está completamente automatizado y no requiere ninguna acción por parte del cliente. Tres topologías utilizan deslizamiento, cada una de una forma ligeramente diferente:

- **En el entorno local**: las implementaciones locales no son compatibles con deslizamiento y verdad hasta.
- **Infraestructura como servicio (IaaS)**: la lógica de deslizamiento se aplica durante cualquier operación que intente actualizar los informes financieros. Incluye actualizaciones binarias o difusiones que contienen actualizaciones binarias.
- **Autoservicio**: cualquier operación que requiera tiempo de inactividad de los informes financieros aplica la lógica de deslizamiento:

    - Actualizaciones binarias o difusiones que incluyen actualizaciones binarias
    - Parcheo S u otro tiempo de inactividad de la infraestructura
    - Implementaciones de paquete de AOT

## <a name="troubleshooting-issues-opening-report-designer"></a>Solución de problemas al abrir Diseñador de informes

Existen algunos problemas comunes que pueden causar problemas al abrir Diseñador de informes. Esos problemas y los pasos para resolverlos son los siguientes.

Problema 1: Diseñador de informes no se inicia cuando selecciona **Nuevo** o **Editar**.

* En Internet Explorer, seleccione **Configuración** y luego **Opciones de Internet**. Seleccione la pestaña **Seguridad**. Seleccione Sitios de confianza y luego elija **Sitios**. En **Agregar este sitio web a la zona**, introduzca "\*\.dynamics.com" (sin comillas) y luego seleccione **Agregar**. 
* En Internet Explorer, seleccione **Configuración** y luego **Opciones de Internet**. Seleccione la pestaña **Seguridad**. Seleccione Sitios de confianza. En el área etiquetada como Nivel de seguridad para esta zona, cambie la opción a **Medio-bajo**.
* Deshabilite el bloqueador de elementos emergentes en su navegador.
* Se requieren estaciones de trabajo para instalar Microsoft .NET Framework 4.7.2 o superior. Esta versión de Microsoft .NET Framework puede descargarse e instalarse desde el [Centro de descarga de Microsoft](https://dotnet.microsoft.com/download/dotnet-framework/net472).
* Si está usando el explorador Chrome, debe instalar una extensión ClickOnce para descargar el cliente de Diseñador de informes. Si está ejecutando Chrome en modo ingógnito, asegúrese de que la extensión ClickOnce esté activada para el modo incógnito. Para obtener más información acerca de la extensión ClickOnce de Chrome, consulte [Requisitos del sistema para implementaciones en la nube](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Si esta usando Microsoft Edge con un navegador Chrome, no es necesario instalar una extensión ClickOnce para Edge Chromium. Sin embargo, debe habilitar la opción ClickOnce para descargar el cliente Diseñador de informes. Si está ejecutando en modo incógnito, asegúrese de que la extensión ClickOnce está activada para el modo incógnito.

    1. Abra un nuevo navegador en Microsoft Edge.
    2. Introduzca **edge://flags** y seleccione **Intro**.
    3. Busque la opción **Soporte ClickOnce** o utilice este enlace directo: **edge://flags/#edge-click-once**.
    4. Establezca la opción del menú desplegable en **Habilitado**.
    5. Seleccione **Reiniciar navegador**.

Problema 2: al usuario no se le han asignado los permisos necesarios para utilizar informes financieros. 

* Para verificar si el usuario no tiene permiso, seleccione **Sí** en el error "No se puede conectar con el servidor de informes financieros. Seleccione Sí caso de que desee continuar y especifique una dirección de servidor diferente". Luego, seleccione **Prueba de conexión**. Si no tiene permiso, verá un mensaje que dice "Error en el intento de conexión. El usuario no tiene los permisos adecuados para conectarse al servidor. Póngase en contacto con el administrador del sistema".
* Los permisos requeridos se enumeran anteriormente, en [Conceder acceso de seguridad a Financial Reporting](#granting-security-access-to-financial-reporting). La seguridad en Financial Reporting se basa en estos privilegios. No tendrá acceso a menos que se le asignen estos privilegios (u otra función de seguridad que incluya estos privilegios). 
* La tarea de integración **Proveedor de usuarios empresariales a la empresa** (que también es responsable de la integración de usuarios y se la llama así) se ejecuta en un intervalo de 5 minutos. Pueden pasar hasta 10 minutos para que cualquier cambio de permiso entre en vigencia en los informes financieros. 

    Si otro usuario puede abrir el Diseñador de informes, seleccione **Herramientas** y luego seleccione **Estado de integración**. Verifique que el mapa de integración, "Proveedor de usuarios empresariales a la empresa" se haya ejecutado correctamente porque se le asignó permiso para usar informes financieros. 

* Es posible que otro error haya impedido que termine **Integración de usuario de Dynamics con usuario de informes financieros**. O es posible que se haya iniciado un reinicio de datamart y aún no se haya completado, o que se haya producido otro error del sistema. Intente ejecutar el proceso nuevamente más tarde. Si el problema persiste, comuníquese con el administrador del sistema.

Problema 3: puede pasar de la página de inicio de sesión **ClickOnce Report Designer** pero no puede completar el inicio de sesión en Report Designer. 

* La hora establecida en el ordenador local cuando introduce sus credenciales de inicio de sesión debe estar dentro de los cinco minutos posteriores a la hora del servidor de informes financieros. Si hay una diferencia de más de cinco minutos, el sistema no permitirá el inicio de sesión. 
* Si la hora en su ordenador difiere de la hora en el servidor de Financial reporting, le recomendamos que habilite la opción de Windows para configurar la hora de su ordenador automáticamente. 

## <a name="troubleshoot-report-designer-issues-with-event-viewer"></a>Solucionar problemas de Report Designer con el visor de eventos

Puede utilizar el visor de eventos para analizar algunos de los problemas que surgen al utilizar Financial reporting. 

### <a name="what-happens-when-you-have-connections-issues-with-financial-reporting"></a>¿Qué sucede cuando tiene problemas de conexión con Financial reporting? 

A continuación se incluyen algunos pasos que puede seguir para que su conversación con el soporte técnico de Microsoft sea más eficaz y lo lleve a una resolución más rápida. 
 
Los siguientes pasos describen el proceso de activación de los mensajes del visor de eventos para Financial reporting. Los registros que genera el visor de eventos ayudarán a los ingenieros de soporte a identificar rápidamente el origen del problema de conexión. Envíe copias de estos registros junto con su vale cuando se comunique con el soporte técnico.


1. Copie el archivo RegisterETW.zip en la estación de trabajo del cliente (preferiblemente el escritorio) y extraiga [RegisterETW.zip](https://mbs2.microsoft.com/fileexchange/?fileID=60b1106b-d5f8-4e0f-8041-039102505122).
2. Asegúrese de que el visor de eventos de Windows esté cerrado.
3. Abra un símbolo del sistema de Administrador de PowerShell y vaya al directorio donde se encuentra RegisterETW.ps1.
4. Ejecute el siguiente comando: .\RegisterETW.ps1

    Una salida exitosa en PowerShell se verificará con el mensaje **Script de RegisterETW completado**.

    Vuelva a abrir el visor de eventos y ahora verá estos registros en **Microsoft > Dynamics**:

    * MR-Client
    * MR-DVT
    * MR-Integration
    * MR-Logger
    * MR-Reporting
    * MR_SchedulerTasks
    * MR-Sql
    * MR-TraceManager

5. Reproduzca el problema en el Report Designer.
6. Exporte los eventos de MR-Logger usando el visor de eventos.

## <a name="troubleshoot-issues-connecting-to-financial-reporting"></a>Solucionar problemas conectándose a Financial reporting

Problema: recibe el error "No se puede conectar al servidor de informes financieros".

* Determine si el problema ocurre en los navegadores de Internet Chrome y Edge.
* Si el problema ocurre solo en un navegador, podría ser un problema de ClickOnce. 
* Cuando reciba el mensaje de error de conexión, seleccione **Prueba** para probar la conexión y vea qué mensaje aparece. 
* El problema podría ser el resultado de que otro usuario no tenga acceso a Financial reporting. Si un usuario no tiene acceso, recibirá un mensaje indicándole que no tiene permiso.
* Si el problema ocurre en varios navegadores, asegúrese de que el reloj de su estación de trabajo esté configurado en Automático.
* Trabaje con un usuario que tenga derechos de administrador de seguridad en Dynamics 365 Finance y derechos de administrador en el dominio de red para iniciar sesión en su estación de trabajo y ver si puede conectarse. Si puede conectarse, el problema podría estar relacionado con los permisos de red.
* En la estación de trabajo, desactive temporalmente el firewall. Si puede conectarse a Report Designer, el problema está en su firewall. Trabaje con el departamento de TI de su organización para resolver el problema.

## <a name="additional-resources"></a>Recursos adicionales

- [Ver informes financieros](view-financial-reports.md)
- [Definiciones de organigramas en informes financieros](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

