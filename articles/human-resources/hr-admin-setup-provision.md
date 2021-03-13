---
title: Aprovisionar Human Resources
description: Este artículo recorre con usted el proceso de aprovisionar un nuevo entorno de producción para Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1a57180c60be4b4686c274aecbf86f0bc6c8b2fb
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114087"
---
# <a name="provision-human-resources"></a>Aprovisionar Human Resources

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo recorre con usted el proceso de aprovisionar un nuevo entorno de producción para Microsoft Dynamics 365 Human Resources. Este artículo asume que ha comprado Human Resources a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). Si dispone de una licencia existente de Microsoft Dynamics 365 que ya incluye el plan de servicio de Human Resources y no puede realizar los pasos de este artículo, póngase en contacto con soporte.

Para empezar, el administrador global debe iniciar sesión en [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) y crear un nuevo proyecto de Human Resources. A menos que un problema de licencia le impida aprovisionar Human Resources, no es obligatoria la ayuda de Soporte o de los representantes de la ingeniería de servicio de Dynamics.

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

4. Human Resources siempre se aprovisiona en un entorno de Microsoft Power Apps para habilitar la integración y la extensibilidad de Power Apps. Lea la sección “Selección de un entorno de Power Apps” de este artículo antes de continuar. Si todavía no tiene un entorno de Power Apps, seleccione Administrar entornos en el LCS o vaya el centro de gestión de Power Apps. A continuación siga los pasos a [Crear entorno de Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Seleccione el entorno para aprovisionar Human Resources.

6. Seleccione **Sí** para aceptar los términos e iniciar la implementación.

   Su nuevo entorno aparece en la lista de los entornos en el panel de navegación de la izquierda. Sin embargo, no puede empezar a usar el entorno hasta que el estado de la implementación se actualice a **Implementado**. Este proceso tarda normalmente algunos minutos. Si el proceso de abastecimiento es incorrecto, debe ponerse en contacto con el soporte técnico.

7. Seleccione **Iniciar sesión en Human Resources** para usar el nuevo entorno.

    > [!NOTE]
    > Si aún no ha dado la aprobación final a los requisitos finales, puede implementar una instancia de prueba de Human Resources en el proyecto. Puede utilizar esta instancia para probar su solución hasta que dé la aprobación final. Si usa su nuevo entorno para las pruebas, deberá repetir este procedimiento para crear un entorno de producción.

    > Puede considerar aprovechar un período gratuito de 60 días [Entorno de prueba de Human Resources](https://go.microsoft.com/fwlink/p/?LinkId=2115962). Aunque un entorno de prueba es propiedad del usuario que lo solicitó, se puede invitar a otros usuarios a través de la experiencia de administración del sistema para Human Resources. Los entornos de prueba contienen datos ficticios que se pueden usar para explorar el programa de forma segura. No están destinados para su uso como entornos de producción. Tenga en cuenta que cuando un entorno de prueba caduca después de 60 días, todos los datos que contiene se eliminan y no se pueden recuperar. Puede registrarse para obtener un nuevo entorno de prueba una vez que caduque el entorno existente.

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
   
    - **Regiones no admitidas**: actualmente, Human Resources solo se admite en las regiones siguientes: Estados Unidos, Reino Unido, Europa, Australia, Canadá y Asia.

    > [!NOTE]
    > El entorno de Human Resources está provisto en la misma región en la que está provisto el entorno Power Apps. No se admite la migración de un entorno de Human Resources a otra región.

6. Una vez que haya determinado el entorno correcto para utilizar, podrá continuar con el proceso de abastecimiento. 
 
## <a name="grant-access-to-the-environment"></a>Conceda acceso al entorno

De forma predeterminada, solo tiene acceso el administrador global que creó el entorno. Debe conceder acceso de forma explícita a los usuarios de aplicaciones adicionales. Debe agregar usuarios y asignar los roles adecuados a ellos en el entorno de Human Resources. El administrador global que implementó Human Resources también debe poner en Attract y Onboard para completar la inicialización y para habilitar el acceso a otros usuarios inquilinos. Hasta que esto ocurra, otros usuarios no podrán tener acceso a Attract y Onboard y obtendrán errores de infracción de acceso. Para obtener más información, consulte [Crear nuevos usuarios](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) y [Asignar usuarios a roles de seguridad](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
