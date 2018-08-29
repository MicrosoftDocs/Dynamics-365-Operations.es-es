---
title: Aprovisionar Talent
description: Este tema recorre con usted el proceso de aprovisionar un nuevo entorno para Microsoft Dynamics 365 for Talent.
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 2fc4119f3b33aa583274f4d823e296752cdde41d
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="provision-talent"></a>Aprovisionar Talent

[!include [banner](includes/banner.md)]

Este tema recorre con usted el proceso de aprovisionar un nuevo entorno de producción para Microsoft Dynamics 365 for Talent. Este tema asume que ha comprado Talent a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). Si dispone de una licencia existente de Microsoft Dynamics 365 que ya incluye el plan de servicio de Talent y no puede realizar los pasos de este tema, póngase en contacto con soporte.

Para empezar, el administrador global debe iniciar sesión en [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) y crear un nuevo proyecto de Talent. A menos que un problema de licencia le impida aprovisionar Talent, no es obligatoria la ayuda de Soporte o de los representantes de la ingeniería de servicio de Dynamics.

## <a name="create-an-lcs-project"></a>Crear un proyecto de LCS
Para usar LCS para administrar sus entornos de Talent, primero debe crear un proyecto de LCS.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index) mediante la cuenta que ha utilizado para suscribirse a Talent.
2. Seleccione el signo más (**+**) para crear un proyecto.
3. Seleccione **Microsoft Dynamics 365 for Talent** como nombre del producto y versión del producto.
4. Seleccione la metodología **Dynamics 365 for Talent**.
5. Seleccione **Crear**.

Para obtener información sobre cómo comenzar con Talent, consulte la metodología **Talent** que ha creado en su nuevo proyecto. Una vez que haya terminado de crear el proyecto, realice el procedimiento siguiente para aprovisionar el entorno de Talent.

## <a name="provision-a-talent-project"></a>Aprovisionar un proyecto de Talent
Después de crear un proyecto de LCS, puede aprovisionar Talent en un entorno.

1. En su proyecto de LCS seleccione el mosaico **Gestión de la app Talent**.
2. Talent siempre se aprovisiona en un entorno de Microsoft PowerApps, para habilitar la integración de PowerApps y la extensibilidad. Lea la sección “Selección de un entorno de PowerApps” de este tema antes de continuar. 
3. Si todavía no tiene un entorno de PowerApps, siga los pasos de la sección “Crear un nuevo entorno de PowerApps (si procede)” de este tema para que pueda continuar.

    > [!NOTE]
    > Para ver entornos existentes o crear nuevos entornos, debe asignarse el administrador de inquilinos que aprovisiona Talent a la licencia de PowerApps P2. Si su organización no dispone de una licencia de PowerApps P2, puede obtener una de su CSP o en la [Página de precios para PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Seleccione **Agregar**, y seleccione el entorno en el que se aprovisionará Talent.
5. Seleccione la opción “Incluir datos de la demostración” si desea que el entorno incluya el mismo conjunto de datos de demostración utilizado en la experiencia de la prueba de conducción de Talent.  Esto es beneficioso para los entornos de demostración o de formación a largo plazo, y no se debe usar nunca en entornos de producción.  Tenga en cuenta que debe elegir esta opción durante la implementación inicial y no puede actualizar una implementación existente más adelante.
6. Seleccione **Sí** para aceptar los términos e iniciar la implementación.

    Su nuevo entorno aparece en la lista de los entornos en el panel de navegación de la izquierda. Sin embargo, no puede empezar a usar el entorno hasta que el estado de la implementación se actualice a **Implementado**. Este proceso tarda normalmente solo algunos minutos. Si el proceso de abastecimiento es incorrecto, debe ponerse en contacto con el soporte técnico.

7. Seleccione **Iniciar sesión en Talent** para usar el nuevo entorno.

> [!NOTE]
> Si aún no ha dado la aprobación final a los requisitos finales, puede implementar una instancia de prueba de Talent en el proyecto. Puede utilizar esta instancia para probar su solución hasta que dé la aprobación final. Si usa su nuevo entorno para las pruebas, deberá repetir este procedimiento para crear un entorno de producción.

> [!NOTE]
> Dado que solo dos entornos de CD se permiten como parte de la suscripción de Talent, también puede considerar aprovechar los 60 días gratuitos [Entorno de prueba de Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Aunque un entorno de prueba es propiedad del usuario que lo solicitó, se puede invitar a otros usuarios a través de la experiencia de administración del sistema para Core HR. Los entornos de prueba contienen datos ficticios que se pueden usar para explorar el programa de forma segura. No están destinados para su uso como entornos de producción. Tenga en cuenta que cuando un entorno de prueba caduca después de 60 días, todos los datos que contiene se eliminan y no se pueden recuperar. Puede registrarse para obtener un nuevo entorno de prueba una vez que caduque el entorno existente.

## <a name="select-a-powerapps-environment"></a>Seleccione un entorno de PowerApps

La integración entre los entornos de Talent y PowerApps le permite integrar y ampliar el uso de los datos de Talent mediante herramientas PowerApps. La comprensión del propósito de los entornos de PowerApps no solo le ayudará a compilar aplicaciones para ampliar Talent, sino también puede ayudarle a seleccionar el entorno correcto al aprovisionar Talent. Para obtener información sobre los entornos de PowerApps, incluido el ámbito de entorno, el acceso de entorno y la creación y elección de un entorno, consulte [Anuncio de entornos de PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Use la orientación siguiente al determinar en qué entorno de PowerApps implementar Talent: 
1. En el LCS, seleccione administrar entornos, o navegue directamente al centro de gestión de PowerApps, donde puede ver los entornos existentes y crear unos nuevos entornos.
2. Un solo entorno de Talent se asigna a un solo entorno de PowerApps.
3. Un entorno de PowerApps "contiene" la aplicación de Talent, junto con el correspondiente PowerApps, Flow, y las aplicaciones de CDS. Si se elimina el entorno de PowerApps, también se eliminan las aplicaciones que contiene.
4. La integración de datos y estrategias de prueba se deben considerar, por ejemplo: Espacio aislado, UAT, producción. Por lo tanto, se recomienda que tenga en cuenta las distintas implicaciones para la implementación, ya que no es fácil cambiar el entorno de Talent que se asigna al entorno de PowerApps posteriormente.
5. Los entornos de PowerApps siguientes no se pueden usar para Talent y se filtrarán de la lista de selección dentro de LCS:
 
    **CDS entornos 2.0** CDS 2.0 estará disponible al público el 21 de marzo de 2018; sin embargo, Talent aún no admite CDS 2.0. Aunque puede ver y crear bases de datos CDS 2.0 en el centro de administración de PowerApps, no se pueden utilizar en Talent. La opción de usar entornos de CDS 2.0 en las implementaciones de Talent estará disponible posteriormente.
   
   > [!Note]
   > Para distinguir entre los entornos de CDS 1.0 y 2.0 en el portal de administración, seleccione un entorno y consulte los **Detalles**. Todos los entornos CDS 2.0 hacen referencia al hecho de que "puede gestionar estos parámetros en el centro de administración de Dynamics 365" apunta a una versión de la instancia y no tiene ninguna ficha de base de datos. 
 
   **Entornos predeterminados de Power Apps** Aunque cada inquilino se aprovisiona automáticamente con un entorno de PowerApps predeterminado, no se recomienda su uso con Talent puesto que todos los usuarios del inquilino tienen acceso al entorno de PowerApps y podrían dañar inintencionadamente datos de producción al probar y explorar con las integraciones de PowerApps o Flow.
   
   <strong>Entornos de versión de prueba</strong> Entornos con un nombre tipo “TestDrive – alias@domain” se crearán con un período de vencimiento de 60 días y caducarán transcurrido ese periodo, haciendo que el entorno se elimine automáticamente.
   
   **Regiones no admitidas** Actualmente, Talent solo se admite en las regiones siguientes: Estados Unidos, Europa o Australia.
  
6. No hay ninguna acción específica una vez que haya determinado el entorno correcto que se utilizará. Continúe con el proceso de aprovisionamiento. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Cree un nuevo entorno de PowerApps (si procede)

Ejecuta un script de PowerShell para crear un nuevo entorno de PowerApps para Talent en el contexto de la gestión de suscriptores que tiene la licencia PowerApps Plan 2. La secuencia de comandos automatiza los pasos siguientes:


 + Creación de un entorno de PowerApps
 + Creación de una base de datos de CDS 1.0
 + Borre todos los datos de ejemplo en la base de datos de CDS 1.0


Complete las siguientes instrucciones para ejecutar la secuencia de comandos:

1. Descargue el archivo de ProvisionCDSEnvironment.zip de la siguiente ubicación: [ProvisionCDSEnvironment scripts](https://go.microsoft.com/fwlink/?linkid=870436)  

2. En la carpeta de descargas, haga clic con el botón secundario en el archivo ProvisionCDSEnvironment.zip que se acaba de descargar y seleccione **Propiedades**.  Si hay una nota de seguridad en la parte inferior de diálogo que indica “este archivo vino de otro equipo y puede ser bloqueado para ayudar a proteger este equipo”, marque la casilla **Desbloquear** y, continuación, haga clic en **Aplicar** y luego en **Aceptar**.

3. Descomprima el contenido completo del archivo ProvisionCDSEnviroinment.zip en una carpeta que no sea la carpeta raíz.

4. Ejecute el programa de Windows PowerShell o ISE de Windows PowerShell como administrador.

   Visite el tema [Establecer la Directiva de ejecución](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) para obtener más información acerca de cómo establecer la directiva de la ejecución para poder ejecutar secuencias de comandos. Sugerimos que use el siguiente: “Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process”, pero asegúrse de seguir las directivas de seguridad de la empresa y de cerrar la ventana de PowerShell cuando haya terminado. 
  
5. Dentro de PowerShell, navegue a la carpeta donde se descomprimió el archivo y ejecute el siguiente comando, reemplazando los valores tal como se indica a continuación:
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   **MyNewEnvironment** debe reemplazarse con su nombre de entorno. Este nombre aparecerá en el CD y estará visible cuando los usuarios seleccionen el entorno de Talent que se utilizará. 

   **YourLocation** debe reemplazarse con una de las regiones admitidas para Talent: unitedstates, Europa, Australia. 

   **- Detallado** es opcional y proporcionará información detallada para enviar a soporte si se detectan problemas.

6. Continúe con el proceso de aprovisionamiento.
 

## <a name="grant-access-to-the-environment"></a>Conceda acceso al entorno
De forma predeterminada, solo tiene acceso el administrador global que creó el entorno. Sin embargo, los usuarios de aplicaciones adicionales debe conceder acceso de forma explícita. Para conceder acceso, [agregue usuarios](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) y [asigne los roles adecuados a ellos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles) en el entorno Core HR. El administrador global que implementó Talent también debe poner en las aplicaciones Attract y Onboard para completar la inicialización y para habilitar el acceso a otros usuarios inquilinos.  Hasta que esto ocurra, otros usuarios no podrán tener acceso a las aplicaciones Attract y Onboard y obtendrán errores de infracción de acceso.


