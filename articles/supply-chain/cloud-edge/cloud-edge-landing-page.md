---
title: Unidades de escalado en la nube y en el perímetro para cargas de trabajo de gestión de almacenes y fabricación
description: Este tema proporciona información sobre las unidades de escalado en la nube y en el perímetro para cargas de trabajo de gestión de almacenes y fabricación.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 28301cdfb86d00ea6f04e996fe7fb1485e83b2d4
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104973"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Unidades de escalado en la nube y en el perímetro para cargas de trabajo de gestión de almacenes y fabricación

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Las unidades de escala en la nube y en el borde permiten la distribución de las cargas de trabajo de ejecución de la planta y el almacén entre diferentes entornos. Esta funcionalidad puede ayudar a mejorar el rendimiento, prevenir interrupciones del servicio y maximizar el tiempo de actividad. Lo proporcionan los siguientes complementos:

- Complemento de unidad de escala de nube para Dynamics 365 Supply Chain Management
- Complemento de unidad de escala perimetral para Dynamics 365 Supply Chain Management

Las empresas que trabajan con fabricación y distribución deben poder ejecutar procesos comerciales clave 24 horas al día, 7 días a la semana, sin interrupciones y a gran escala. Las unidades de escala en la nube y en el borde permiten a las empresas ejecutar procesos clave de fabricación y almacenamiento de misión crítica sin interrupciones, incluso cuando se enfrentan a problemas ocasionales de latencia o conectividad de red.

## <a name="public-preview-information"></a>Información de vista previa pública

La vista previa proporciona un entorno que funciona como un centro basado en la nube de su entorno de Dynamics 365 Supply Chain Management y un entorno que funciona como una unidad de escala de nube.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Disponibilidad de vista previa

La versión preliminar de las unidades de escala en la nube y en el borde estará disponible para los clientes existentes de Supply Chain Management en octubre de 2020.

Para acceder a la versión preliminar de octubre 10.0.15 / Actualización de la plataforma 39 para la implementación en su entorno de [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), debe ser parte del programa de acceso anticipado de vista previa (también conocido como PEAP) para Supply Chain Management. Puede unirse a PEAP si ya es miembro de [Dynamics Insider Program](https://experience.dynamics.com/insider). Simplemente seleccione el programa específico que se llama "Finanzas y operaciones: Vista previa del programa de acceso temprano (PEAP)".

> [!IMPORTANT]
> La capacidad de la unidad de escalado de Supply Chain Management está disponible solo si acepta los [términos perimetrales y de nube para Finance and Operations](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Procesamiento de datos para la vista previa

Durante la versión preliminar pública, algunos servicios de administración solo se alojarán en los Estados Unidos. Sin embargo, cuando la función esté disponible de forma generalizada, estos servicios de gestión estarán disponibles en todas las geografías admitidas por Supply Chain Management. Esto afecta la transferencia y el almacenamiento de la información administrativa utilizada por el gerente de la unidad de báscula, que incluye:

- Sus nombres e identificaciones de inquilinos
- ID de su proyecto de LCS
- Correos electrónicos de administrador utilizados para iniciar sesión
- ID de entorno para unidades de escala y concentradores
- Configuraciones de carga
- Métricas recopiladas (como latencia y rendimiento) que se muestran en la página de análisis del mapa

Los datos transferidos y almacenados en los centros de datos de EE. UU. Se eliminarán cuando se apaguen los entornos de vista previa.

### <a name="sign-up-for-the-preview"></a>Registrarse para la versión preliminar

Para suscribirse a la vista previa en la nube y en el borde de Supply Chain Management, su organización ya debe tener un entorno en la nube de Supply Chain Management en vivo.

Las capacidades de la unidad de escala se encuentran actualmente en versión preliminar pública. Cuando se registra, debe usar una cuenta de usuario en el inquilino específico. También debe ser propietario de proyecto o administrador de entorno en LCS para un proyecto activo de Dynamics 365 LCS en ese inquilino.

Cuando se registre para la vista previa, seleccionará un inquilino y seguirá los pasos de registro. Tan pronto como Microsoft pueda asignar la capacidad de vista previa, le enviaremos un correo electrónico que incluye los detalles de aprovisionamiento y los códigos de promoción (promo) para dos entornos (un concentrador y una unidad de escala) para el proyecto LCS apropiado. Luego podrá implementar los dos entornos como entornos sandbox de nivel 2. Esos entornos tendrán una validez de 60 días a partir de la fecha de creación de los códigos promocionales. No debe utilizar los dos entornos hasta que se complete el paso que se describe en el siguiente párrafo.

Después de confirmar con Microsoft que los dos entornos se han implementado mediante el uso de los códigos de promoción, uno de los entornos se configurará para funcionar como un centro y el otro se configurará para funcionar como una unidad de escala. A continuación, puede configurar las unidades de escala e implementar cargas de trabajo de fabricación y administración de almacén seleccionadas mediante el [Portal de Scale Unit Manager](https://aka.ms/SCMSUM).

Los entornos de vista previa se eliminarán automáticamente después de 60 días. Sin embargo, es posible que se eliminen antes si parece que no se están utilizando. Una vez que se hayan eliminado los entornos de vista previa, puede registrarse y hacer cola para una nueva implementación de vista previa.

Para registrarse para la vista previa, vaya al [Portal de Scale Unit Manager](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Limitaciones que se aplican durante el período de vista previa

> [!IMPORTANT]
> Para la fase inicial del programa de vista previa de esta función, Microsoft solo admite centros que tienen unidades de escala en la nube, no centros que tienen unidades de escala de borde. Las unidades de escala de borde se instalan en las instalaciones y se espera que estén disponibles durante una próxima fase del programa.

Debido a que las unidades de escala en la nube y en el borde son una función de vista previa, los servicios relacionados con ellas están disponibles actualmente en países y regiones limitados. Al habilitar las unidades de escala en la nube y en el borde, usted afirma que comprende que algunos datos relacionados con la configuración y el procesamiento de las unidades de escala en la nube y en el borde pueden almacenarse en un centro de datos ubicado en los Estados Unidos. Al habilitar las unidades de escala en la nube y en el borde, también acepta las [condiciones de vista previa de nube y perímetro para Finance and Operations](https://Aka.ms/SCMCnETerms). Para obtener más información sobre las unidades de escala de borde y nube, consulte la [documentación](https://aka.ms/scmcne).

Su privacidad es importante para Microsoft. Para obtener más información, lea nuestra [Declaracion de privacidad](https://aka.ms/privacy).

> [!IMPORTANT]
> Algunas funciones comerciales no son totalmente compatibles en la versión preliminar pública cuando se utilizan cargas en unidades de escalado. Para obtener más información acerca de las cargas funcionales, vea las secciones posteriores en este tema.

## <a name="scale-units-and-dedicated-workloads"></a>Unidades de escalado y cargas de trabajo dedicadas

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 con unidades de escalado":::

Las unidades de escala amplían su entorno central de Supply Chain Management agregando capacidad de procesamiento dedicada. Las unidades de escala se pueden ejecutar en la nube. Alternativamente, pueden ejecutarse en el borde en las instalaciones de su instalación local. Las unidades de báscula se pueden desconectar temporalmente del entorno del concentrador. Cuando están conectadas, las unidades de báscula reciben toda la información necesaria para ejecutar el procesamiento dedicado para las cargas de trabajo asignadas.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Opciones de unidad de escala en la vista previa pública":::

Para la vista previa pública, puede configurar un entorno de concentrador con cargas de trabajo seleccionadas en una unidad de escala en la nube mediante el portal Scale Unit Manager. Los participantes de vista previa que tienen acceso a un entorno local de datos comerciales locales (LBD) también pueden configurar el entorno LBD como una unidad de escala de borde.

Una carga de trabajo es un conjunto definido de funciones comerciales que se pueden factorizar y delegar a una unidad de escala. Actualmente, la vista previa presenta dos tipos de cargas de trabajo:

- Ejecución de fabricación
- Gestión de almacenes

Puede asignar uno de cada tipo de carga de trabajo por unidad de báscula. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Capacidades de carga de trabajo de ejecución de fabricación dedicadas en una unidad de escala

Para la ejecución de fabricación, las unidades de escala en la nube y en el borde ofrecen las siguientes capacidades, incluso cuando las unidades en el borde no están conectadas a la nube:

- Los operadores de máquinas y los supervisores de planta pueden acceder al plan de producción operativo.
- Los operadores de máquinas pueden mantener el plan actualizado mediante la ejecución de trabajos de fabricación discretos y de proceso.
- El supervisor de planta puede ajustar el plan operativo.
- Los trabajadores pueden acceder al tiempo y la asistencia para el registro de entrada y salida en el borde, para garantizar el cálculo correcto del salario del trabajador.

Para obtener más información, consulte los [Detalles de la carga de trabajo de la unidad de escala de fabricación](cloud-edge-workload-manufacturing.md).

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Capacidades de carga de trabajo de administración de almacén dedicadas en una unidad de escala

Para la administración de almacén, las unidades de escalado en la nube y en el perímetro ofrecen las siguientes capacidades, incluso cuando las unidades en el borde no están conectadas a la nube:

- El procesamiento de los métodos de oleada seleccionados está habilitado para pedidos de cliente y reabastecimiento de demanda.
- Los trabajadores del almacén pueden ejecutar el trabajo de almacén de reabastecimiento de ventas y demanda mediante la aplicación de almacén.
- Los trabajadores del almacén pueden consultar el inventario disponible mediante la aplicación del almacén.
- Los trabajadores del almacén pueden crear y ejecutar movimientos de inventario mediante la aplicación del almacén.
- Los trabajadores de almacén pueden registrar órdenes de compra y realizar trabajos de almacenamiento mediante la aplicación de almacén.

Para obtener más información, consulte los [detalles de la carga de trabajo de la unidad de escala de almacén](cloud-edge-workload-warehousing.md).

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Unidades de báscula a bordo para su entorno de Supply Chain Management

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Implementar la vista previa para unidades de escalado en el perímetro y en la nube

La siguiente ilustración muestra el flujo de registro y aprovisionamiento para la vista previa pública para unidades de escala en la nube.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Vista previa de los pasos de registro":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Seleccione el inquilino de su proyecto LCS y el proceso de vista previa detallado

En la vista previa pública, el [Portal de Scale Unit Manager](https://aka.ms/SCMSUM) muestra la lista de inquilinos de los que forma parte su cuenta y dónde es propietario o administrador de entorno para un proyecto LCS.

Si el inquilino que está buscando no está en esta lista, vaya a [LCS](https://lcs.dynamics.com/v2) y asegúrese de ser administrador del entorno o propietario del proyecto LCS para ese inquilino. Tenga en cuenta que solo las cuentas de Azure Active Directory (Azure AD) del inquilino seleccionado están autorizadas para completar la experiencia de registro.

> [!NOTE]
> Después de aplicar los cambios a LCS, la lista de inquilinos puede tardar hasta 30 minutos en reflejar los cambios.

Para cada inquilino, la lista muestra el estado de registro.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Opción de registro para una suscripción":::

Seleccione el enlace **Haga clic aquí para registrarte** para registrar a su inquilino LCS para participar en la vista previa. Debe aceptar los términos. También debe proporcionar una dirección de correo electrónico comercial a la que Microsoft pueda enviar comunicaciones relacionadas con el proceso de suscripción de vista previa.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Envío de registro para una suscripción":::

Microsoft revisará su solicitud y le informará sobre los próximos pasos enviando un correo electrónico a la dirección que proporcionó en el formulario de registro.

Una vez que se le haya otorgado acceso al programa de vista previa, recibirá dos códigos de promoción para su proyecto LCS. Ahora puede usar esos códigos de promoción para implementar dos entornos en LCS. Los entornos deben utilizar PEAP versión 10.0.15 o posterior. Cuando haya terminado de aplicar los códigos de promoción, notifique a Microsoft (según las instrucciones), para que podamos terminar de habilitar los entornos para las funciones de vista previa. Microsoft le informará cuando se complete este paso de configuración.

Ahora puede comenzar a configurar unidades de escala y cargas de trabajo en su entorno de vista previa.

> [!IMPORTANT]
> Cuando configura unidades de escala en la nube, puede [realizar todos los pasos necesarios en el portal Scale Unit Manager](#scale-unit-manager-portal).
<!-- 
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Administre cargas de trabajo y unidades de escala en la nube mediante el portal Scale Unit Manager

Vaya al [Portal de Scale Unit Manager](https://aka.ms/SCMSUM) e inicie sesión con su cuenta de inquilino. En la página **Configurar unidades de escala**, puede agregar un entorno de concentrador si aún no está en la lista. Luego, puede seleccionar el concentrador que desea configurar con unidades de escala y cargas de trabajo.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Experiencia en gestión de cargas de trabajo y unidades de escala":::

Para agregar una o más unidades de escala que están disponibles en su topología, seleccione **Agregar unidades de escala**. En la vista previa, debería ver la unidad de escala de nube que implementó a partir de uno de los códigos promocionales que recibió como parte del programa de vista previa.

<!--  [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

En la pestaña **Cargas de trabajo definidas**, use el botón **Crear carga de trabajo** para agregar una carga de trabajo de ejecución de fabricación o gestión de almacén a una de sus unidades de báscula. Para cada carga de trabajo, debe especificar el contexto de los procesos que serán propiedad de la carga de trabajo. Para las cargas de trabajo de gestión de almacenes, el contexto es un almacén específico en un sitio y entidad legal específicos. Para las cargas de trabajo de ejecución de fabricación, el contexto es un sitio específico en una entidad legal.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Creación de cargas de trabajo":::

> [!IMPORTANT]
> El portal Scale Unit Manager en la vista previa no le permite eliminar cargas de trabajo de las unidades de báscula o anular la asignación de una unidad de báscula de un centro después de realizar la asignación. Si debe eliminar una asignación, comuníquese con su persona de contacto para la administración del programa de vista previa.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->
