---
title: Aprovisionar Talent
description: Este tema recorre con usted el proceso de aprovisionar un nuevo entorno para Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: 5bcdb50475fb341a538211cb122eb7c13067d86a
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527227"
---
# <a name="provision-talent"></a>Aprovisionar Talent

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema recorre con usted el proceso de aprovisionar un nuevo entorno de producción para Microsoft Dynamics 365 Talent. Este tema asume que ha comprado Talent a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). Si dispone de una licencia existente de Microsoft Dynamics 365 que ya incluye el plan de servicio de Talent y no puede realizar los pasos de este tema, póngase en contacto con soporte.

Para empezar, el administrador global debe iniciar sesión en [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) y crear un nuevo proyecto de Talent. A menos que un problema de licencia le impida aprovisionar Talent, no es obligatoria la ayuda de Soporte o de los representantes de la ingeniería de servicio de Dynamics.

## <a name="create-an-lcs-project"></a>Crear un proyecto de LCS
Para usar LCS para administrar sus entornos de Talent, primero debe crear un proyecto de LCS.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index) mediante la cuenta que ha utilizado para suscribirse a Talent.

2. Seleccione el signo más (**+**) para crear un proyecto.

3. Seleccione **Microsoft Dynamics 365 Talent** como nombre del producto y versión del producto.

4. Seleccionar la metodología de **Dynamics 365 Talent**.

5. Seleccione **Crear**. 

Para obtener información sobre cómo comenzar con Talent, consulte la metodología **Talent** que ha creado en su nuevo proyecto. Una vez que haya terminado de crear el proyecto, realice el procedimiento siguiente para aprovisionar el entorno de Talent.

## <a name="provision-a-talent-project"></a>Aprovisionar un proyecto de Talent

Después de crear un proyecto de LCS, puede aprovisionar Talent en un entorno.

1. En su proyecto de LCS seleccione el mosaico **Gestión de la app Talent**.

2. Indica si se trata de una instancia de producción o de espacio aislado de Talent. Las características de vista previa pueden estar disponibles en instancias de espacio aislado para permitir pruebas y comentarios iniciales. 

    > [!NOTE]
    > El tipo de instancia de Talent no se puede cambiar una vez establecido. Compruebe que se ha seleccionado el tipo de instancia correcto antes de continuar.

    > [!NOTE]
    > El tipo de instancia de Talent es independiente del tipo de instancia del entorno de Microsoft Power Apps, que establece en el Centro de administración de Power Apps.

3. Seleccione la opción **Incluir datos de la demostración** si desea que el entorno incluya el mismo conjunto de datos de demostración utilizado en la experiencia de la prueba de conducción de Talent. Esto es beneficioso para los entornos de demostración o de formación a largo plazo, y no se debe usar nunca en entornos de producción.  Tenga en cuenta que debe elegir esta opción sobre la implementación inicial. No puede actualizar una implementación existente más adelante.

4. Talent siempre se aprovisiona en un entorno de Microsoft Power Apps para habilitar la integración y la extensibilidad de Power Apps. Lea la sección “Selección de un entorno de Power Apps” de este tema antes de continuar. Si todavía no tiene un entorno de Power Apps, seleccione Administrar entornos en el LCS o vaya el centro de gestión de Power Apps. A continuación siga los pasos a [Crear entorno de Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Seleccione el entorno para aprovisionar Talent.

6. Seleccione **Sí** para aceptar los términos e iniciar la implementación.

    Su nuevo entorno aparece en la lista de los entornos en el panel de navegación de la izquierda. Sin embargo, no puede empezar a usar el entorno hasta que el estado de la implementación se actualice a **Implementado**. Este proceso tarda normalmente algunos minutos. Si el proceso de abastecimiento es incorrecto, debe ponerse en contacto con el soporte técnico.

7. Seleccione **Iniciar sesión en Talent** para usar el nuevo entorno.

    > [!NOTE]
    > Si aún no ha dado la aprobación final a los requisitos finales, puede implementar una instancia de prueba de Talent en el proyecto. Puede utilizar esta instancia para probar su solución hasta que dé la aprobación final. Si usa su nuevo entorno para las pruebas, deberá repetir este procedimiento para crear un entorno de producción.

    > Dado que solo dos entornos de CD se permiten como parte de la suscripción de Talent, también puede considerar aprovechar los 60 días gratuitos [Entorno de prueba de Talent](https://dynamics.microsoft.com/talent/overview/). Aunque un entorno de prueba es propiedad del usuario que lo solicitó, se puede invitar a otros usuarios a través de la experiencia de administración del sistema para Human Resources. Los entornos de prueba contienen datos ficticios que se pueden usar para explorar el programa de forma segura. No están destinados para su uso como entornos de producción. Tenga en cuenta que cuando un entorno de prueba caduca después de 60 días, todos los datos que contiene se eliminan y no se pueden recuperar. Puede registrarse para obtener un nuevo entorno de prueba una vez que caduque el entorno existente.

## <a name="select-a-power-apps-environment"></a>Seleccionar un entorno Power Apps

La integración entre los entornos de Talent y Power Apps le permite integrar y ampliar el uso de los datos de Talent mediante herramientas Power Apps. La comprensión del propósito de los entornos de Power Apps no solo le ayudará a compilar aplicaciones para ampliar Talent, sino también puede ayudarle a seleccionar el entorno correcto al aprovisionar Talent. Para obtener información sobre los entornos de Power Apps, incluido el ámbito de entorno, el acceso de entorno y la creación y elección de un entorno, consulte [Anuncio de entornos de Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Use la orientación siguiente al determinar en qué entorno de Power Apps implementar Talent: 

1. En el LCS, seleccione **Administrar entornos**, o vaya directamente al centro de gestión de Power Apps, donde puede ver los entornos existentes y crear unos nuevos entornos.

2. Un solo entorno de Talent se asigna a un solo entorno de Power Apps.

3. Un entorno de Power Apps contiene Talent, junto con el correspondiente Power Apps, Power Automate y las aplicaciones de Common Data Service. Si se elimina el entorno de Power Apps, también se eliminan las aplicaciones que contiene. Al aprovisionar un entorno de Talent, puede aprovisionar un entorno de **Prueba** o **Producción**. Elija el tipo de entorno en función de cómo se usará el entorno. 

4. La integración de datos y estrategias de prueba se deben considerar como Espacio aislado, UAT o producción. Recomendamos que tenga en cuenta las distintas implicaciones para la implementación, ya que no es fácil cambiar el entorno de Talent que se asigna al entorno de Power Apps posteriormente.

5. Los entornos de Power Apps siguientes no se pueden usar para Talent y se filtrarán de la lista de selección dentro de LCS:
 
    - **Entornos predeterminados de Power Apps**: aunque cada inquilino se aprovisiona automáticamente con un entorno de Power Apps predeterminado, no se recomienda su uso con Talent puesto que todos los usuarios del inquilino tienen acceso al entorno de Power Apps y podrían dañar inintencionadamente datos de producción al probar y explorar con las integraciones de Power Apps o Power Automate.
   
    - **Entornos de versión de prueba**: estos entornos se crearán con un período de vencimiento y caducarán transcurrido ese periodo, haciendo que cualquier instancia de Talent incluida en el entorno se elimine automáticamente.
   
    - **Regiones no admitidas**: actualmente, Talent solo se admite en las regiones siguientes: Estados Unidos, Reino Unido, Europa, Australia, Canadá y Asia.
  
6. Una vez que haya determinado el entorno correcto para utilizar, podrá continuar con el proceso de abastecimiento. 
 
## <a name="grant-access-to-the-environment"></a>Conceda acceso al entorno

De forma predeterminada, solo tiene acceso el administrador global que creó el entorno. Sin embargo, los usuarios de aplicaciones adicionales debe conceder acceso de forma explícita. Para conceder acceso, necesita agregar usuarios y asignar los roles adecuados a ellos en el entorno de Human Resources. El administrador global que implementó Talent también debe poner en Attract y Onboard para completar la inicialización y para habilitar el acceso a otros usuarios inquilinos.  Hasta que esto ocurra, otros usuarios no podrán tener acceso a Attract y Onboard y obtendrán errores de infracción de acceso. Para obtener más información, consulte [Crear nuevos usuarios](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) y [Asignar usuarios a roles de seguridad](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]