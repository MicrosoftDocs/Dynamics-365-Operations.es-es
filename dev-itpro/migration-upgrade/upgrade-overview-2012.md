---
title: "Actualización Dynamics 2012 a Dynamics 365 for Finance and Operations, Enterprise Edition"
description: "Este tema describe el proceso que los clientes que ejecutan actualmente Microsoft Dynamics AX 2012 pueden utilizar para mover sus datos y código a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: es-es
ms.lasthandoff: 06/15/2017

---

# Actualizar Microsoft Dynamics AX 2012 a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition
<a id="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition" class="xliff"></a>

[!include[banner](../includes/banner.md)]

En la actualización de plataforma 8, Microsoft Dynamics 365 for Finance and Operations, Enterprise edition proporciona una ruta de actualización que los clientes que ejecutan actualmente Microsoft Dynamics AX 2012 pueden utilizar para mover sus datos y código a Finance and Operations. El proceso de actualización se basa en los siguientes elementos:

- Herramientas para ayudarle a introducir el código de aplicación personalizada existente de AX 2012.
- Un proceso de actualización de datos que puede usar para introducir su base de datos. Por lo tanto, puede actualizar todo su historial de transacciones.

## Información general
<a id="overview" class="xliff"></a>

El proceso de actualización total se puede visualizar como tres fases globales: analizar, ejecutar, y validar.

En el diagrama siguiente se muestra el proceso de actualización de principio a fin, y las actividades que consideramos la parte de cada fase. 

![Proceso de actualización](./media/upgrade-process.png)

## Analizar
<a id="analyze" class="xliff"></a>

Las actividades en la fase de analizar le ayudan a estimar el esfuerzo necesario para la actualización. También le ayudan a preparar un plan del proyecto. Estas actividades pueden ser realizadas antes de adquirir Finance and Operations. Le ayudarán a tomar una decisión informada de la decisión de compra ofreciendo datos sobre el esfuerzo y los recursos que requerirá.

### Inscripción para obtener una vista previa pública en el LCS
<a id="sign-up-for-a-public-preview-in-lcs" class="xliff"></a>

Para realizar actividades de análisis antes de comprar Finance and Operations, puede registrarse para obtener una vista previa pública. La vista previa pública le permite implementar sus propios entornos de Finance and Operations. También ofrece acceso a herramientas Microsoft Dynamics Lifecycle Services (LCS) que se usan para evaluar el entorno de AX 2012 y el código personalizado existente.

Si tiene un proyecto existente de LCS para AX 2012, también tiene que inscribirse para que un nuevo proyecto adicional evalúe Finance and Operations.

Para obtener información acerca de cómo obtener una vista previa pública para clientes, vaya a https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Para obtener información acerca de cómo obtener una vista previa pública para socios, vaya a https://mbs.microsoft.com/partnersource/global/news-events/news/Microsoft_Dynamics_AX_Public_Preview..

Tenga en cuenta que esta vista previa pública es diferente de una [prueba de 30 días](https://aka.ms/D365OperationTrials) Las pruebas de 30 días proporcionan una instancia de Finance and Operations que puede usar para explorar y para evaluar la aplicación. Sin embargo, las actividades de analizar requieren la experiencia y las herramientas completas del LCS.

### Seleccionar la metodología de actualización
<a id="select-the-upgrade-methodology" class="xliff"></a>
En su nuevo proyecto de LCS, defina la metodología del proyecto en **Actualizar AX 2012 a Dynamics 365 for Operations**. Esta metodología se crea para especialmente para clientes AX 2012 que estén actualizando. Describe las tres fases en detalle y ofrece vínculos a toda la documentación de ayuda sobre el proceso.

![Metodología de actualización(./media/methodology.png)
 
### Ejecutar el analizador de actualización
<a id="run-the-upgrade-analyzer" class="xliff"></a>
La herramienta de analizador de actualización se ejecuta en su entorno de AX 2012 e identificar tareas que se deben realizar para preparar el entorno de AX 2012, para ayudarle a mejorar y abaratar la experiencia actualización:

- **Eliminación de datos** Este proceso permite identificar los datos que puede quitar sin provocar la pérdida de funcionalidad. La herramienta identifica distintos tipos de datos que puede reducir mediante un proceso de limpieza. Para cada tipo de datos, se ofrece una explicación sobre el impacto de limpieza. A continuación, decide si desea ejecutar el proceso de limpieza. Parte del coste de la suscripción de Finance and Operations se basa en el tamaño de la base de datos. Por lo tanto, reduciendo el tamaño, disminuye este componente del coste de la suscripción y también ayuda a reducir el tiempo necesario para el proceso de actualización. Una base de datos más pequeña ayuda a garantizar una actualización más rápida.
- **Configuración de SQL** - Este proceso revisa la configuración de SQL y recomienda optimizaciones. Asegurándose de que SQL se realiza de manera óptima, ayuda a que este proceso reduzca el tiempo necesario para el proceso de actualización.
- **Características obsoletas** Este proceso identifica características que se están utilizando actualmente, pero que no están disponibles en Finance and Operations. Por lo tanto, el proceso ayuda a detectar lagunas en la funcionalidad pronto. También proporciona sugerencias de alternativas.

Además, como parte de este paso, debe instalar KBXXXXXXX en el entorno de AX 2012. Esta revisión proporciona una lista de comprobación previa a la actualización. En el entorno de AX 2012, puede usar esta lista de comprobación para introducir los datos que se requerirán para el procedimiento de la actualización. Por ejemplo, en una tarea de la lista de comprobación previa a la actualización, ofrece a Microsoft Azure Active Directory (Azure AD) información de suscripción de cada usuario actual de AX 2012, para que cada usuario pueda suscribirse a Finance and Operations.

El resultado de este paso se convierte en el flujo de trabajo del plan del proyecto de actualización de los administradores de su sistema AX 2012.

Para obtener más información, consulte [Análisis: Uso del analizador de actualización para planificar el trabajo de la migración](upgrade-analyzer-tool.md).

### Ejecutar las herramientas de estimación de actualización de código
<a id="run-the-code-upgrade-estimation-tools" class="xliff"></a>
Este paso toma su código de AX 2012, lo convierte al nuevo formato, y proporciona retroalimentación sobre los conflictos que un desarrollador debe resolver posteriormente. Este paso forma la base para la estimación del coste de su actualización de código.

Para completar este paso, debe exportar el código de AX 2012 como exportación del almacén modelo y cargarlo en la herramienta de actualización de código de LCS. La herramienta de actualización de código generará una versión actualizada del código y de un informe acerca de los conflictos restantes que se deben resolver. Su desarrollador puede revisar a continuación el código actualizado y el informe para determinar el esfuerzo que será necesario para actualizar la base del código.

El resultado de este paso representa el flujo de trabajo del plan del proyecto de actualización de los desarrolladores de Microsoft Dynamics AX.

Para obtener más información, consulte [Análisis: Estimación del esfuerzo para actualizar el código](analyze-code-upgrade.md).

### Implementar un entorno de demostración
<a id="deploy-a-demo-environment" class="xliff"></a>
Los entornos de demostración son los entornos predeterminados que contienen los datos de prueba (no sus propios datos) y el código del estándar (sin personalizaciones). Es recomendable implementar un entorno de prueba para evaluar las nuevas características, así como realizar un análisis de lagunas de idoneidad básico de los procesos del estándar que se usan en AX 2012 pero que podrían haber cambiado en Finance and Operations. Puede implementar estos entornos de demostración en Azure o descargarlos como una máquina virtual (VM) que se ejecuta en su propio hardware. Si los implementa en Azure, debe especificar su suscripción a Azure, ya que aún utiliza un proyecto público de vista previa y aún no ha adquirido una suscripción a Finance and Operations.

El resultado de este paso representa el flujo de trabajo del plan del proyecto para sus usuarios funcionales o empresariales.

Para obtener más información, consulte [Análisis: Implementación de un entorno de espacio aislado](analysis-sandbox.md)

### Crear un plan de proyecto
<a id="create-a-project-plan" class="xliff"></a>
Una plantilla para un plan de proyecto se ofrece en la metodología de actualización. En este paso, se utilizará el resultado de los pasos anteriores de la fase de analizar para rellenar el plan de proyecto del proyecto de actualización. El plan de proyecto también contendrá todos los detalles de prueba: prueba de actualización de datos, prueba de transferencia del sistema, las repeticiones del paso de la prueba funcional y detalles sobre las diferentes asignaciones de recursos para esas tareas.

En esta etapa, el plan del proyecto proporciona un punto de datos que puede ayudarle a comprender el tiempo y el coste que implica una actualización a Finance and Operations.

## Ejecutar
<a id="execute" class="xliff"></a>
Durante la fase de ejecución, se procesan las tareas planificadas durante la fase de analizar. Para pasar a la fase de ejecutar, debe comprar Finance and Operations, y debe tener los recursos disponibles que pueden trabajar en la actualización.

### Cambio al proyecto de implementación de LCS
<a id="switch-to-the-lcs-implementation-project" class="xliff"></a>
El proyecto público de vista previa que usó para la fase de analizar ha logrado su propósito. Ahora puede descartarlo. Para los pasos restantes, se requiere solo el plan de proyecto que creó en el paso final de la fase de analizar.

Si compra una suscripción a Finance and Operations, recibirá los detalles acerca de cómo suscribirse para un proyecto nuevo de LCS. Este proyecto se conoce como proyecto de implementación y será el nuevo proyecto de LCS permanente de su suscripción, mientras siga teniendo dicha suscripción. Este proyecto difiere del proyecto público de vista previa en que lo gestiona Microsoft. Por lo tanto, este proyecto tiene estas características:

- Todos los entornos del proyecto se hospedan en Azure.
- La suscripción a Azure asociada al proyecto se gestiona a través de Microsoft. Por tanto, no hay una factura diferente para los costes de Azure. Los costes están cubiertos en la suscripción de Finance and Operations.
- El entorno de producción en el proyecto lo mantiene Microsoft. Por lo tanto, las implementaciones de códigos, las actualizaciones y el mantenimiento de la infraestructura los ejecuta directamente Microsoft, no el personal. 

### Realizar tareas de preparación de AX 2012
<a id="perform-the-ax-2012-preparation-tasks" class="xliff"></a>
Realice las tareas que ha descubierto la herramienta de analizador de actualización y que se documentan en su plan del proyecto de actualización. El administrador del sistema Microsoft Dynamics AX y administrador de la base de datos (DBA) deben completar estas tareas.

[Actualización de datos de AX 2012 a Dynamics 365 for Operations - Lista de comprobación de previa a la actualización en AX 2012](prepare-data-upgrade.md)

### Realizar actualización de código
<a id="perform-code-upgrade" class="xliff"></a>
Realice las tareas que fueron planeadas durante el paso de la estimación de actualización de código de la fase de analizar. Los programadores deben ejecutar estas tareas.

A partir de este momento, los cambios del código de AX 2012 deben quedar congelados. Solo los cambios del código de emergencia se deben permitir en AX 2012. Si se realiza un cambio, debe introducirse manualmente en la nueva base de códigos.

### Desarrollar un nuevo código
<a id="develop-new-code" class="xliff"></a>
Realice las tareas de análisis de lagunas de idoneidad realizado durante el paso “Implementar un entorno de prueba” de la fase de analizar. Estas tareas serán probablemente una combinación de tareas funcionales que definen la configuración y de tareas de desarrollo para las personalizaciones relacionadas con las nuevas características que se están adoptando.

### Actualización de datos (entorno integrado)
<a id="data-upgrade-development-environment" class="xliff"></a>
Una vez que sus tareas de actualización de código hayan finalizado, puede actualizar la base de datos de AX 2012 a Finance and Operations por primera vez. Esta primera actualización aparece en un entorno de desarrollo, de modo que puede solucionar o depurar más fácilmente los problemas que se encuentre en esta etapa. En un entorno de desarrollo, un problema se puede depurar inmediatamente, un código se puede ajustar y se puede volver a ejecutar la actualización en cuestión de minutos. Los entornos de espacio aislado más grandes no proporcionan esta agilidad y un mínimo de varias horas es necesario para depurar y solucionar problemas, actualizar el código, implementar el código actualizado y volver a ejecutar la actualización.

En la ilustración siguiente se muestra el proceso. Simplemente realice una copia de seguridad de la base de datos de AX 2012, cárguela en Azure, restáurela en el entorno de Finance and Operations y después ejecute la actualización de datos.

![Actualización de datos en un entorno de desarrollo](./media/data-upgrade-dev.png)
 
La actualización de datos se realiza a través de un tipo especial de paquete desplegable. El mismo mecanismo se usa para implementar el nuevo código de Finance and Operations a partir de un entorno a otro entorno.

El marco subyacente que se usa para convertir los datos de la base de datos durante este proceso es en parte el mismo que el marco de actualización en AX 2012 basado en los trabajos por lotes X++ que ejecutan clases **ReleaseUpdatexxx** .

Para obtener detalles, vea [Actualización de datos de AX 2012 a Dynamics 365 for Operations en un entorno de desarrollo](data-upgrade-2012.md).

### Actualización de datos (entornos aislados)
<a id="data-upgrade-sandbox-environments" class="xliff"></a>
Cuando la actualización de datos en un entorno de desarrollo se ha completado, el mismo proceso se puede ejecutar en un entorno aislado. El entorno aislado es el entorno donde los usuarios empresariales y los miembros del equipo funcionales pueden probar procesos empresariales con los datos y el código actualizados de AX 2012.

La ilustración siguiente muestra el proceso para ejecutar la actualización de datos en un entorno aislado. La diferencia aquí es que la herramienta del bacpac se usará en lugar de una copia de seguridad de SQL tradicional. Esta herramienta se requiere para la conversión entre Microsoft SQL Server y la base de datos SQL de Azure. Es una herramienta estándar de SQL y no es específica de Finance and Operations.

![Actualización de datos en un entorno aislado](./media/data-upgrade-sandbox.png)

Para obtener detalles, vea [Actualización de datos de AX 2012 a Dynamics 365 for Operations en un entorno aislado](upgrade-data-sandbox.md).
 
## Validar
<a id="validate" class="xliff"></a>
Cuando pasa a la fase de validar, tendrá disponibles entornos que incluyan el código personalizado actualizado y sus datos actualizados. Esta fase describe el proceso de validar y probar que el entorno actualizado funciona según lo deseado. También describe el proceso de preparación para el lanzamiento.

### Realizar la prueba de la transferencia de sistema y crear un plan de transferencia de sistema
<a id="perform-cutover-testing-and-create-a-cutover-plan" class="xliff"></a>
El término _transferencia de sistema_ se usa aquí y describe el proceso final de lanzamiento del nuevo sistema activo. Este proceso consta de las tareas que se producen después de que se apague AX 2012 y antes de que se encienda Finance and Operations. 

El objetivo de la prueba es practicar el proceso de transferencia de sistema. De esta manera, puede ayudar a garantizar que todo el mundo que participa en la transferencia de sistema real para el lanzamiento tenga una transición suave.

Existen dos flujos de trabajo principales:

- **Flujo de trabajo técnico**: este flujo de trabajo incluye el proceso de ejecución de la actualización de datos. Su empresa impondrá un límite de tiempo de inactividad permitido. Durante este tiempo de inactividad, ni AX 2012 ni Finance and Operations estarán disponibles. Es posible que este flujo de trabajo tenga que ajustar +el procedimiento de actualización de datos para cumplir el límite de tiempo de inactividad de la empresa. 
- **Flujo de trabajo funcional** Tras la actualización de datos, existen diversas tareas de configuración que son necesarias en el entorno de Finance and Operations. Todas estas tareas deben ser documentadas y cuantificadas, y debe asignarse un recurso, ya que deben poder realizarse junto a las tareas técnicas en el límite de tiempo de inactividad de la empresa.

Para obtener detalles, consulte 
- [Validar: prueba de transferencia](upgrade-cutover-testing.md)
- [Validar: proceso de validación de la aplicación](app-validation-process.md)

### Aprobación de la prueba funcional
<a id="functional-test-pass" class="xliff"></a>
Se debe completar una aprobación completa de la prueba funcional de todos los procesos empresariales. Esta aprobación de la prueba será una amplia nueva prueba de todos los procesos de negocio de Finance and Operations. Estos procesos de negocio incluyen los antiguos procesos transferidos desde AX 2012 y los nuevos procesos que implican las nuevas características introducidas por primera vez en Finance and Operations. 

En función de calidad del código, la solución de problemas y las nuevas pruebas pueden requerir varias repeticiones de la aprobación de la prueba funcional. Cuando se corrija un error, asegúrese de probar todos los procesos que están implicados, para ayudar a garantizar que el proceso anterior o siguiente no se verá afectado por el cambio.

Para obtener detalles, consulte [Validar: Prueba funcional](upgrade-functional-validation.md).

### Lista de comprobación previa al lanzamiento
<a id="pre-go-live-checklist" class="xliff"></a>
La lista de comprobación previa al lanzamiento es un procedimiento recomendado que puede ayudar a reducir el riesgo de errores durante la transferencia de sistema final para el lanzamiento. Resulta útil parar los cambios de configuración en AX 2012 una semana antes del lanzamiento previsto (es decir, en módulo\>\Configuración \<). Esta restricción en los cambios de configuración es un simple procedimiento. Los administradores del sistema de Microsoft Dynamics AX solo aceptan poner en espera los cambios de este tipo en este punto.

Es recomendable también congelar los cambios de código en la base de código de Finance and Operations. No se debe permitir ningún otro cambio, a menos que se hayan evaluado y que se haya demostrado que no bloquean el lanzamiento.  

Una vez que la restricción de la configuración y la congelación del código se han realizado, la actualización de los datos se debe ejecutar por última vez la antes de la transferencia de sistema. De esta manera, se garantiza que aún funcione todo del modo esperado. 

Para ver detalles, consulte [Validar: prepararse para el lanzamiento](upgrade-go-live-prep.md).



### Rutas de actualización admitidas
<a id="supported-upgrade-paths" class="xliff"></a>
En junio de 2017, la actualización en Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, versión 0617 se admite desde Microsoft Dynamics AX 2012 R3. Se admiten todas las actualizaciones acumulativas (CU) de AX 2012 R3.

Microsoft Dynamics AX 2012 R2 y Microsoft Dynamics AX 2012 RTM no se admiten actualmente. La compatibilidad se agregará más adelante en 2017.

Solo se admiten las actualizaciones de la versión en nube de Finance and Operations. La actualización a la versión local no se admite. La compatibilidad para la actualización de la versión local se agregará más adelante en 2017.

