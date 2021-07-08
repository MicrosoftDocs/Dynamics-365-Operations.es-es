---
title: Aprovisionar Human Resources
description: Este tema recorre con usted el proceso de aprovisionar un nuevo entorno de producción para Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2632616834e405d31facdcf3853baaf96066e9aa
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248830"
---
# <a name="provision-human-resources"></a>Aprovisionar Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema recorre con usted el proceso de aprovisionar un nuevo entorno de producción para Microsoft Dynamics 365 Human Resources. Este tema asume que ha comprado Human Resources a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). Si dispone de una licencia existente de Microsoft Dynamics 365 que ya incluye el plan de servicio de Human Resources y no puede realizar los pasos de este artículo, póngase en contacto con soporte.

Para empezar, el administrador global debe iniciar sesión en [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) y crear un nuevo proyecto de Human Resources. A menos que un problema de licencia le impida aprovisionar Human Resources, no es obligatoria la ayuda de Soporte o de los representantes de la ingeniería de servicio de Dynamics.

## <a name="provision-a-human-resources-trial-environment"></a>Proporcionar un entorno de prueba de recursos humanos

Antes de aprovisionar su primer entorno de pruebas o producción, es posible que desee aprovisionar un [Entorno de prueba de recursos humanos](https://go.microsoft.com/fwlink/p/?LinkId=2115962) para validar la funcionalidad de Recursos Humanos. Los entornos de prueba contienen datos ficticios que se pueden usar para explorar el programa de forma segura. Aunque un entorno de prueba es propiedad del usuario que lo solicitó, se puede invitar a otros usuarios a través de la experiencia de administración del sistema para Human Resources. 

Los entornos de prueba no están destinados para su uso como entornos de producción. Están limitados a un período de prueba de 60 días. Cuando expira el período de prueba, el entorno y todos los datos que contiene se eliminan y no se pueden recuperar. El entorno no se puede convertir en un entorno de pruebas o de producción. Puede registrarse para obtener un nuevo entorno de prueba una vez que caduque el entorno existente.

## <a name="plan-human-resources-environments"></a>Planificar entornos de Human Resources

Antes de crear su primer entorno de Human Resources, debe planificar cuidadosamente las necesidades del entorno para el proyecto. Una suscripción básica a Human Resources incluye dos entornos: un entorno de producción y un entorno de espacio aislado. En función de la complejidad del proyecto, es posible que tenga que comprar entornos de espacio aislado para respaldar las actividades del proyecto. 

Las consideraciones para entornos adicionales incluyen, entre otras, las siguientes:

- **Migración de datos**: es posible que deba considerar un entorno adicional para las actividades de migración de datos a fin de permitir que su entorno de espacio aislado se utilice con fines de prueba durante todo el proyecto. Disponer de un entorno adicional permite que las actividades de migración de datos continúen mientras las actividades de prueba y configuración se llevan a cabo simultáneamente en un entorno diferente.
- **Integración**: es posible que deba considerar un entorno adicional para configurar y probar integraciones. Esto podría incluir integraciones nativas como la de Ceridian Dayforce LinkedIn Talent Hub, o integraciones personalizadas como las de nómina, sistemas de seguimiento de candidatos o sistemas y proveedores de prestaciones.
- **Formación**: es posible que necesite un entorno independiente configurado con un conjunto de datos de entrenamiento para capacitar a sus empleados en el uso del nuevo sistema. 
- **Proyecto multifase**: es posible que necesite un entorno adicional para la configuración, la migración de datos, las pruebas u otras actividades en una fase del proyecto que se planifica después de la puesta en funcionamiento inicial del proyecto.

 > [!IMPORTANT]
 > Le recomendamos que utilice su entorno de producción en todo el proyecto como su entorno de configuración GOLD. Esto es importante, ya que no puede copiar un entorno de espacio aislado en un entorno de producción. Por lo tanto, cuando su entorno GOLD entre en funcionamiento, será su entorno de producción y usted completará las actividades de transición en este entorno.</br></br>
 > Le recomendamos que utilice el espacio aislado u otro entorno para realizar una transición simulada antes de la puesta en funcionamiento. Puede hacer esto actualizando el entorno de producción con la configuración GOLD en el entorno de espacio aislado.</br></br>
 > Le recomendamos que mantenga una lista de comprobación de transición detallada que incluya cada uno de los paquetes de datos necesarios para migrar los datos finales al entorno de producción durante la transición de puesta en funcionamiento.</br></br>
 > También le recomendamos que utilice el entorno de espacio aislado en todo el proyecto como entorno de pruebas. Si necesita entornos adicionales, su organización puede adquirirlos por un coste adicional.</br></br>

## <a name="create-an-lcs-project"></a>Crear un proyecto de LCS

Para usar LCS para administrar sus entornos de Human Resources, primero debe crear un proyecto de LCS.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index) mediante la cuenta que ha utilizado para suscribirse a Human Resources.

   > [!NOTE]
   > Para garantizar un aprovisionamiento exitoso, la cuenta que utiliza para aprovisionar el entorno de Recursos Humanos debe asignarse al rol de **Administrador de sistema** o **Personalizador del sistema** en el entorno de Power Apps asociado al entorno de Recursos Humanos. Vea [Configurar la seguridad del usuario para los recursos](/power-platform/admin/database-security) para obtener más información sobre la asignación de roles de seguridad a los usuarios en Power Platform.

2. Seleccione el signo más (**+**) para crear un proyecto.

3. Seleccione **Microsoft Dynamics 365 Human Resources** como nombre del producto y versión del producto.

4. Seleccionar la metodología de **Dynamics 365 Human Resources**.

5. Seleccione **Crear**.

Para obtener información sobre cómo comenzar con Human Resources, consulte la metodología **Human Resources** que ha creado en su nuevo proyecto. Una vez que haya terminado de crear el proyecto, realice el procedimiento siguiente para aprovisionar el entorno de Human Resources.

## <a name="provision-a-human-resources-project"></a>Aprovisionar un proyecto de Human Resources

Después de crear un proyecto de LCS, puede aprovisionar Human Resources en un entorno.

1. En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.

2. Indique si este entorno es una instancia de producción o de espacio aislado de Human Resources. Las características de vista previa pueden estar disponibles en instancias de espacio aislado para permitir pruebas y comentarios iniciales.
   
    > [!NOTE]
    > El tipo de instancia de Human Resources no se puede cambiar una vez establecido. Compruebe que se ha seleccionado el tipo de instancia correcto antes de continuar.</br></br>
    > El tipo de instancia de Human Resources es independiente del tipo de instancia del entorno de Microsoft Power Apps, que establece en el Centro de administración de Power Apps.
    
3. Seleccione la opción **Incluir datos de la demostración** si desea que el entorno incluya el mismo conjunto de datos de demostración utilizado en la experiencia de la prueba de conducción de Human Resources. Los datos de demostración son beneficiosos para los entornos de demostración o de formación a largo plazo, y no se debe usar nunca en entornos de producción. Debe elegir esta opción sobre la implementación inicial. No puede actualizar una implementación existente más adelante.

4. Human Resources siempre se aprovisiona en un entorno de Microsoft Power Apps para habilitar la integración y la extensibilidad de Power Apps. Lea la sección “Selección de un entorno de Power Apps” de este artículo antes de continuar. Si todavía no tiene un entorno de Power Apps, seleccione Administrar entornos en el LCS o vaya el centro de gestión de Power Apps. A continuación siga los pasos a [Crear entorno de Power Apps](/powerapps/administrator/create-environment).

5. Seleccione el entorno para aprovisionar Human Resources.

6. Seleccione **Sí** para aceptar los términos e iniciar la implementación.

   Su nuevo entorno aparece en la lista de los entornos en el panel de navegación de la izquierda. Sin embargo, no puede empezar a usar el entorno hasta que el estado de la implementación se actualice a **Implementado**. Este proceso tarda normalmente algunos minutos. Si el proceso de abastecimiento es incorrecto, debe ponerse en contacto con el soporte técnico.

7. Seleccione **Iniciar sesión en Human Resources** para usar el nuevo entorno.

    > [!NOTE]
    > Si aún no ha dado la aprobación final a los requisitos finales, puede implementar una instancia de prueba de Human Resources en el proyecto. Puede utilizar esta instancia para probar su solución hasta que dé la aprobación final. Si usa su nuevo entorno para las pruebas, deberá repetir este procedimiento para crear un entorno de producción.

## <a name="select-a-power-apps-environment"></a>Seleccionar un entorno Power Apps

Puede integrar y ampliar el uso de datos de Human Resources utilizando las herramientas de Power Apps. Para obtener información sobre los entornos de Power Apps, incluido el ámbito de entorno, el acceso de entorno y la creación y elección de un entorno, consulte [Anuncio de entornos de Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Use la orientación siguiente al determinar en qué entorno de Power Apps implementar Human Resources: 

1. Seleccione **Administrar entornos** en LCS. También puede ir directamente al Centro de gestión de Power Apps, donde podrá ver los entornos existentes y crear nuevos.

2. Un solo entorno de Human Resources se asigna a un solo entorno de Power Apps.

3. Un entorno de Power Apps contiene Human Resources, junto con el correspondiente Power Apps, Power Automate y las aplicaciones de Dataverse. Si se elimina el entorno de Power Apps, también se eliminan las aplicaciones que contiene. Al aprovisionar un entorno de Human Resources, puede aprovisionar un entorno de **Prueba** o **Producción**. Elija el tipo de entorno en función de cómo se usará el entorno. 

4. La integración de datos y estrategias de prueba se deben considerar como Espacio aislado, UAT o producción. Tenga en cuenta con cuidado las distintas implicaciones para la implementación, ya que no es fácil cambiar el entorno de Human Resources que se asigna al entorno de Power Apps posteriormente.

5. No puede usar los siguientes entornos de Power Apps para Human Resources. Se filtran de la lista de selección dentro de LCS:
 
    - **Entornos predeterminados de Power Apps**: si bien cada inquilino se aprovisiona automáticamente con entorno predeterminado de Power Apps, no recomendamos usarlos con Human Resources. Todos los usuarios suscriptores pueden acceder al entorno de Power Apps y podrían dañar involuntariamente los datos de producción al probar y explorar con integraciones de Power Apps o Power Automate.
   
    - **Entornos de prueba**: estos entornos se crean con una fecha de vencimiento. Al vencimiento, su entorno y cualquier instancia de Human Resources que contenga se eliminarán automáticamente.
   
    - **Geografías no admitidas**: el entorno debe estar en una geografía admitida. Para más información, consulte [Geografías admitidas](hr-admin-setup-provision.md#supported-geographies).

6. Una vez que haya determinado el entorno correcto para utilizar, podrá continuar con el proceso de abastecimiento. 

### <a name="supported-geographies"></a>Geografías admitidas

Actualmente, Recursos Humanos admite las siguientes geografías:

- Estados Unidos
- Europa
- Reino Unido
- Australia
- Canadá
- Asia 

Cuando crea un entorno de recursos humanos, seleccione un entorno de Power Apps para asociarlo con el entorno de Recursos Humanos. A continuación, el entorno de Recursos Humanos se aprovisiona en la misma geografía de Azure que el entorno de Power Apps seleccionado. Puede seleccionar dónde residen físicamente el entorno de Recursos Humanos y la base de datos seleccionando la geografía al crear el entorno de Power Apps que se asociará con el entorno de Recursos Humanos.

Puede seleccionar la *geografía* de Azure en el que se aprovisiona el entorno, pero no puede seleccionar la *región* específica de Azure. La automatización determina la región específica dentro de la geografía en la que se crea el entorno para optimizar el equilibrio de carga y el rendimiento. Puede encontrar información sobre regiones y geografías de Azure en la documentación sobre [Geografías e Azure](https://azure.microsoft.com/global-infrastructure/geographies).

Los datos para el entorno de Recursos Humanos siempre estarán contenidos dentro de la geografía de Azure en la que se crean. Sin embargo, no siempre estarán contenidos en la misma región de Azure. Para fines de recuperación ante desastres, los datos se replicarán tanto en la región principal de Azure como en una región secundaria de conmutación por error dentro de la geografía.

 > [!NOTE]
 > No se admite la migración de un entorno de Recursos Humanos de una región de Azure a otra.

## <a name="grant-access-to-the-environment"></a>Conceda acceso al entorno

De forma predeterminada, solo tiene acceso el administrador global que creó el entorno. Debe conceder acceso de forma explícita a los usuarios de aplicaciones adicionales. Debe agregar usuarios y asignar los roles adecuados a ellos en el entorno de Human Resources. El administrador global que implementó Human Resources también debe poner en Attract y Onboard para completar la inicialización y para habilitar el acceso a otros usuarios inquilinos. Hasta que esto ocurra, otros usuarios no podrán tener acceso a Attract y Onboard y obtendrán errores de infracción de acceso. Para obtener más información, consulte [Crear nuevos usuarios](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) y [Asignar usuarios a roles de seguridad](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
