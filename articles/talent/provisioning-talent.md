---
title: Aprovisionar Microsoft Dynamics 365 for Talent
description: Este tema recorre con usted el proceso de aprovisionar un nuevo entorno para Microsoft Dynamics 365 for Talent.
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Talent
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
ms.sourcegitcommit: 6ffb97b53f522cfe8ccd8e89df854cbc557e4f1f
ms.openlocfilehash: fadc373b2c1c06987f22d4d9c20a9ab07b0c85d5
ms.contentlocale: es-es
ms.lasthandoff: 11/20/2017

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Aprovisionar Microsoft Dynamics 365 for Talent
Este tema recorre con usted el proceso de aprovisionar un nuevo entorno para Microsoft Dynamics 365 for Talent. Este tema asume que ha comprado Talent a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). Si dispone de una licencia existente de Microsoft Dynamics 365 que ya incluye el plan de servicio de Talent y no puede realizar los pasos de este tema, póngase en contacto con soporte.

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
2. Talent siempre se aprovisiona en un entorno de Microsoft PowerApps, para habilitar la integración de PowerApps y la extensibilidad. Si todavía no tiene un entorno de PowerApps, siga los pasos de la sección “Crear un nuevo entorno de PowerApps (si procede)” de este tema para que pueda continuar.

    > [!NOTE]
    > Para ver entornos existentes o crear nuevos entornos, debe asignarse el administrador de inquilinos que aprovisiona Talent a la licencia de PowerApps P2. Si su organización no dispone de una licencia de PowerApps P2, puede obtener una de su CSP o en la [Página de precios para PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

3. Seleccione **Agregar**, y seleccione el entorno en el que se aprovisionará Talent.
4. Seleccione **Sí** para aceptar los términos e iniciar la implementación.

    Su nuevo entorno aparece en la lista de los entornos en el panel de navegación de la izquierda. Sin embargo, no puede empezar a usar el entorno hasta que el estado de la implementación se actualice a **Implementado**. Este proceso tarda normalmente solo algunos minutos. Si el aprovisionamiento da un error, debe ponerse en contacto con Soporte.

6. Seleccione **Iniciar sesión en Talent** para usar el nuevo entorno.

> [!NOTE]
> Si aún no ha dado la aprobación final a los requisitos finales, puede implementar una instancia de prueba de Talent en el proyecto. Puede utilizar esta instancia para probar su solución hasta que dé la aprobación final. Si usa su nuevo entorno para las pruebas, deberá repetir este procedimiento para crear un entorno de producción.

## <a name="create-a-new-powerapps-environment-if-required"></a>Cree un nuevo entorno de PowerApps (si procede)
1. Seleccione **Administrar entornos** en el LCS. Irá a [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/environments), donde podrá ver los entornos existentes y crear nuevos entornos.
2. Seleccione el botón (**+**) **Nuevo entorno**.
3. Escriba un nombre único para el entorno, y seleccione la ubicación donde realizar la implementación.

    > [!NOTE]
    > Talent no está disponible en todas las regiones. Por lo tanto, asegúrese de comprobar su disponibilidad antes de seleccionar la ubicación para su entorno.

4. Cuando se le pregunte si desea crear una base de datos, seleccione **Crear base de datos** para crear la base de datos Common Data Service (CDS) que debe alojar parte de los datos de Talent. Creando una base de datos, también puede integrar aplicaciones de PowerApps con Talent.
5. Se le preguntará sobre el nivel de acceso que desea utilizar para la base de datos. Le recomendamos que seleccione **Restringir el acceso**, porque esta opción evita que los usuarios de Talent obtengan acceso directamente a datos confidenciales mediante una aplicación de PowerApps.
6. La base de datos de CDS que se crea contiene datos de demostración. Estos datos de prueba son útiles porque puede usar la empresa de los datos de prueba para realizar pruebas o crear grabaciones de tareas o guías de tareas. Sin embargo, los datos de demostración agregan empleados inactivos y direcciones fantasmas, entre otra información, al entorno de producción. Para quitar los datos de prueba, siga estos pasos después de que haya terminado de crear la base de datos de CDS:

    > [!IMPORTANT]
    > Si ha creado una base de datos de CDS anteriormente y ha introducido datos de producción de la empresa en ella, tenga en cuenta que estos pasos eliminan **todos** los datos de la base de datos seleccionada, incluso los datos de producción de la empresa.

    1. Iniciar sesión en [PowerApps](https://preview.web.powerapps.com/home), y vaya al entorno que ha creado en el paso 2.
    2. Seleccione **Entidades**. En el lado derecho de la página, seleccione el botón de la elipse (**...**) y seleccione **Borrar todos los datos**.
    3. Seleccione **Eliminar datos** para confirmar que desea eliminar los datos. Esta acción elimina todos los datos de prueba que se incluyen en CDS de forma predeterminada. También elimina cualquier otra información que se haya especificado en la base de datos seleccionada.

Ahora puede utilizar su nuevo entorno.

