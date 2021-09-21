---
title: Unidades de escalado en una topología híbrida distribuida
description: Este tema proporciona información sobre las unidades de escalado en la nube y en el perímetro para cargas de trabajo de gestión de almacenes y fabricación.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 59d246dd348bca6c00dc90b19353a382986841f2
ms.sourcegitcommit: a21166da59675e37890786ebf7e0f198507f7c9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2021
ms.locfileid: "7471749"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>Unidades de escalado en una topología híbrida distribuida

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> La capacidad de la unidad de escala para Microsoft Dynamics 365 Supply Chain Management está disponible para usted bajo los términos que rigen el uso del servicio. Para obtener más información, consulte [Información legal de Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Al habilitar las unidades de escala en la nube y en el borde, se le pedirá que afirme que comprende que algunos datos relacionados con la configuración y el procesamiento de las unidades de escala en la nube y en el borde pueden almacenarse en un centro de datos ubicado en los Estados Unidos. Para obtener más información sobre el procesamiento de datos para unidades de escala de borde y nube, consulte [Procesamiento de datos durante la gestión de unidades de escala](#data-processing-management) sección más adelante en este tema.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>Propuesta de valor central para una topología híbrida distribuida

Las empresas que trabajan con fabricación y distribución deben poder ejecutar procesos comerciales clave 24 horas al día, 7 días a la semana, sin interrupciones y a gran escala. Una topología híbrida distribuida permite a las empresas ejecutar procesos clave de fabricación y almacenamiento de misión crítica sin interrupciones, incluso cuando se enfrentan a problemas ocasionales de latencia o conectividad de red.

Una topología híbrida distribuida introduce el concepto de *unidades de escala*, que permiten la distribución de las cargas de trabajo de ejecución de la planta y el almacén entre diferentes entornos. Esta funcionalidad puede ayudar a mejorar el rendimiento, prevenir interrupciones del servicio y maximizar el tiempo de actividad. Las unidades de escala se proporcionan a través de los siguientes complementos para su suscripción a Supply Chain Management:

- Complemento de unidad de escala de nube para Dynamics 365 Supply Chain Management (*disponible en abril de 2021*)
- Complemento de unidad de escala de Edge para Dynamics 365 Supply Chain Management (*disponible pronto*)

Las capacidades de carga de trabajo se lanzan de forma continua a través de mejoras incrementales.

## <a name="scale-units-and-dedicated-workloads"></a>Unidades de escalado y cargas de trabajo dedicadas

Las unidades de escala amplían su entorno central de Supply Chain Management agregando capacidad de procesamiento dedicada. Las unidades de escala se pueden ejecutar en la nube. Alternativamente, pueden ejecutarse en el borde, en las instalaciones de su instalación local.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 con unidades de escalado.":::

Las unidades de escala proporcionan resistencia, confiabilidad y escala para las cargas de trabajo asignadas. Las unidades de escala de borde se pueden desconectar temporalmente del entorno del centro de la nube y los trabajadores continúan trabajando en las cargas de trabajo asignadas en el borde.

Una *carga de trabajo* es un conjunto definido de funciones comerciales que se pueden factorizar y delegar a una unidad de escala. Aunque se ha liberado la carga de trabajo para la gestión de almacenes, la carga de trabajo para la ejecución de fabricación todavía está en vista previa.

Puede configurar un entorno de concentrador con unidades de escala de nube para cargas de trabajo seleccionadas mediante el [portal Scale Unit Manager](https://sum.dynamics.com). También puede asignar múltiples cargas de trabajo por unidad de báscula. Para obtener información sobre los requisitos previos y las limitaciones de las unidades de escala en la nube en la versión actual, consulte [Requisitos previos y limitaciones para las unidades de escala en la nube](#cloud-scale-unit-prerequisites) más adelante en este tema.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Capacidades de carga de trabajo de administración de almacén dedicadas en una unidad de escala

La carga de trabajo de administración de almacén es la primera carga de trabajo distribuida para unidades de escala que se ha lanzado para disponibilidad general.

Para la gestión de almacenes, las unidades de báscula ofrecen las siguientes capacidades:

- El sistema puede procesar métodos de oleada seleccionados está habilitado para pedidos de cliente y reabastecimiento de demanda.
- Los trabajadores del almacén pueden ejecutar el trabajo de almacén de reabastecimiento de ventas y demanda mediante la aplicación móvil Warehouse Management.
- Los trabajadores del almacén pueden consultar el inventario disponible mediante la aplicación móvil Warehouse Management.
- Los trabajadores del almacén pueden crear y ejecutar movimientos de inventario mediante la aplicación móvil Warehouse Management.
- Los trabajadores de almacén pueden registrar órdenes de compra y realizar trabajos de almacenamiento mediante la aplicación móvil Warehouse Management.

Para más información, vea [Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Capacidades de carga de trabajo de ejecución de fabricación dedicadas en una unidad de escala

La primera versión de la carga de trabajo de fabricación se encuentra actualmente en versión preliminar y ofrece las siguientes capacidades:

- Los operadores de máquinas y los supervisores de planta pueden acceder al plan de producción operativo.
- Los operadores de máquinas pueden mantener el plan actualizado mediante la ejecución de trabajos de fabricación discretos y de proceso.
- El supervisor de planta puede ajustar el plan operativo.
- Los trabajadores pueden acceder al tiempo y la asistencia para el registro de entrada y salida en el borde, para garantizar el cálculo correcto del salario del trabajador.

Para más información, vea [Cargas de trabajo de ejecución de fabricación para unidades de escalado en el perímetro y en la nube](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Consideraciones antes de habilitar la topología híbrida distribuida para Supply Chain Management

Al habilitar la topología híbrida distribuida, realiza la transición de su entorno de nube de Supply Chain Management para que funcione como un centro. También puede asociar entornos adicionales configurados como unidades de escala en la nube o en el borde.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Requisitos previos y limitaciones de unidades de escalado en la nube

En la versión actual para unidades de escala, algunas capacidades aún no están disponibles, pero podrían agregarse en versiones incrementales con el tiempo.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Debe ser un cliente con licencia de Supply Chain Management

Para incorporarse a la topología distribuida, debe tener una licencia para Supply Chain Management. Su entorno de nube existente se convertirá en el centro de su topología híbrida. Puede declarar entornos de espacio aislado y entornos de producción como entornos de concentrador, y puede agregar unidades de escala según los complementos que adquiera.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>Su proyecto existente debe administrarse a través de la versión comercial global de LCS

Su proyecto existente de Microsoft Dynamics Lifecyle Services (LCS) debe cumplir con los siguientes requisitos de versión:

- El proyecto debe administrarse a través de la versión comercial global de LCS en [lcs.dynamics.com](https://lcs.dynamics.com).
- Versiones locales de LCS (como [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) y [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)) no son compatibles.
- Las versiones gubernamentales de LCS en la nube no son compatibles.
- La versión Mooncake de LCS no es compatible.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>Su entorno de producción actual debe ser del tipo de autoservicio en LCS

Su entorno de producción actual debe etiquetarse con el tipo de **autoservicio** en LCS. Este tipo indica que el inquilino de su proyecto LCS ya se ha convertido para que admita el modelo de hospedaje de Azure Service Fabric.

> [!IMPORTANT]
> No se admiten los tipos de entorno que se ejecutan como infraestructura como servicio (IaaS). Estos entornos suelen estar etiquetados con el tipo **Administrado por Microsoft** en LCS. Si tiene entornos de este tipo, trabaje con su contacto de Microsoft para comprender su cronograma de migración al tipo **Autoservicio**.

Microsoft está en proceso de transición de todos los entornos en la nube de Supply Chain Management de un modelo IaaS a una topología alojada en Service Fabric. Este movimiento brinda una mejor escalabilidad y ayuda a facilitar la administración del servicio. Por lo tanto, las operaciones de implementación y mantenimiento son más rápidas. Asimismo, los componentes del servicio se están migrando al concepto de microservicios y el modelo de hospedaje de servicios [cambiará](/virtualization/windowscontainers/about/containers-vs-vm) de un modelo de máquina virtual (VM) a una arquitectura ligera en contenedores.

En última instancia, la misma infraestructura de servicios en contenedores basada en Service Fabric impulsará tanto las instancias en la nube como en el borde del servicio, independientemente de si una instancia es un centro en la nube o una unidad de escala en la nube o en el borde.

Antes de poder incorporarse a la topología híbrida que admite unidades de escala, el inquilino del proyecto debe realizar la transición al modelo alojado en Service Fabric. Además, se debe convertir cualquier entorno que actúe como centro.

> [!TIP]
> Para consultar sobre el estado del inquilino de su proyecto LCS, busque el tipo de su entorno en [LCS](https://lcs.dynamics.com/) o póngase en contacto con su socio o contacto de Microsoft.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>Los entornos de datos comerciales locales (locales) no se admiten como centros para unidades de escala

Los entornos locales no pueden funcionar como centros para unidades de escala. Los entornos de concentrador siempre deben estar alojados en la nube.

#### <a name="scale-unit-management-capabilities-are-limited"></a>Las capacidades de gestión de la unidad de escala son limitadas

Las capacidades de gestión que pueden ayudar con el movimiento de cargas de trabajo son limitadas. Algunas operaciones de administración no se admiten en forma de autoservicio y es posible que deba solicitar soporte a través de su socio o contacto de Microsoft. Los ejemplos incluyen algunos movimientos de carga de trabajo entre unidades de escala y movimientos ad-hoc temporales en escenarios de desastre.

#### <a name="metrics-and-measurements-arent-yet-available"></a>Las métricas y medidas aún no están disponibles

Las métricas y medidas que podrían ayudarlo a seleccionar la mejor aplicación para sus unidades de báscula aún no están disponibles. Trabaje con su contacto de Microsoft o socio de implementación para seleccionar la aplicación más beneficiosa.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Procesamiento de datos durante la gestión de unidades de escala

Cuando habilita su entorno de Dynamics 365 para admitir la topología híbrida distribuida para unidades de escala de borde y nube, algunos servicios de administración se alojarán solo en los Estados Unidos, como para LCS. Este comportamiento afecta la transferencia y el almacenamiento de cierta información administrativa y de configuración que utiliza el [Portal de Scale Unit Manager](https://sum.dynamics.com). A continuación, encontrará algunos ejemplos:

- Sus nombres e identificaciones de inquilinos
- ID de su proyecto de LCS
- Direcciones de correo electrónico del administrador y del propietario del proyecto que se utilizan para iniciar sesión
- ID de entorno para unidades de escala y concentradores
- Configuraciones de carga de trabajo, incluidos los nombres y direcciones físicas de entidades e instalaciones legales, para que su topología se pueda mostrar en un mapa geográfico.
- Métricas recopiladas (como latencia y rendimiento) que se mostrarán en la página de análisis del mapa para ayudarlo a seleccionar el uso más beneficioso de sus unidades de escala.

Los datos que se transfieren y almacenan en los centros de datos de EE. UU. Se eliminarán de acuerdo con las políticas de retención de datos de Microsoft. Su privacidad es importante para Microsoft. Para obtener más información, lea nuestra [Declaracion de privacidad](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboarding-in-two-stages"></a>Incorporación en dos etapas

El proceso de incorporación a la topología híbrida distribuida tiene dos etapas. Durante la primera etapa, debe validar las personalizaciones para asegurarse de que funcionen en la topología distribuida que tiene unidades de escala. Los entornos sandbox y de producción se mueven solo durante la segunda etapa.

### <a name="stage-1-evaluate-customizations-in-one-box-development-environments"></a>Etapa 1: evaluar las personalizaciones en entornos de desarrollo de una sola caja

Antes de comenzar a incorporar sus entornos sandbox o de producción, le recomendamos que explore las unidades de escala en una configuración de desarrollo, como un entorno de una sola caja (también conocido como entorno de nivel 1), para que pueda validar procesos, personalizaciones, y soluciones. Durante esta etapa, los datos y las personalizaciones se aplicarán a los entornos one-box. Un entorno asume el papel de centro y el otro el papel de unidad de escala. Esta configuración proporciona la mejor manera de identificar y solucionar problemas. La última compilación de acceso temprano (PEAP) también se puede utilizar para completar esta etapa.

Para la etapa 1, debe usar las [herramientas de implementación de unidades de escala para entornos de desarrollo de una sola caja](https://github.com/microsoft/SCMScaleUnitDevTools). Estas herramientas le permiten configurar unidades de escala y concentradores en uno o dos entornos de una sola caja separados. Las herramientas se proporcionan como una versión binaria y en código fuente en GitHub. Estudie la wiki del proyecto, que incluye una [Guía de uso paso a paso](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) que describe cómo se utilizan las herramientas.

### <a name="stage-2-acquire-add-ins-and-deploy-in-your-sandbox-and-production-environments"></a>Etapa 2: Adquiera complementos e impleméntelos en sus entornos sandbox y de producción

Para incorporar uno de sus entornos sandbox o de producción a la nueva topología, debe adquirir complementos para una o más unidades de escala de nube (y, en el futuro, para unidades de escala de borde). Los complementos otorgarán los espacios correspondientes al proyecto y al entorno en [LCS](https://lcs.dynamics.com/) para que se puedan implementar los entornos de la unidad de escala.

> [!NOTE]
> Los complementos de la unidad de escala no están acoplados a un número limitado de usuarios, pero pueden ser utilizados por cualquier usuario de la suscripción existente, según los roles que asigne el administrador.

Las unidades de báscula se ofrecen en varias unidades de mantenimiento de existencias (SKU) y opciones de precios. Por lo tanto, puede elegir la opción que mejor se adapte a los requisitos de rendimiento y volumen de transacciones mensuales planificados.

El SKU de nivel de entrada se conoce como *Básico* y el SKU de mayor rendimiento se conoce como *Estándar*. Cada SKU viene precargado con un número específico de transacciones mensuales. Sin embargo, puede aumentar el presupuesto de transacciones mensual agregando complementos excedentes para cada SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Complementos para unidades de escala de nube.":::

> [!TIP]
> Para identificar el tamaño que mejor se adapte a sus necesidades, trabaje con su socio y Microsoft para comprender el tamaño de transacción mensual que necesita.

La compra de cada complemento de unidad de báscula no solo le brinda un volumen mensual de transacciones, sino que también le da derecho a un número específico de espacios de entorno en LCS. Por cada complemento de unidad de escala en la nube, tiene derecho a una nueva ranura de producción y una nueva ranura de espacio aislado. Durante el proceso de incorporación, se agregará un nuevo proyecto LCS que tiene estos espacios. Los derechos de uso de las ranuras están vinculados de modo que las ranuras se deben usar como unidades de escala que tienen un centro en la nube.

Los complementos excedentes no le dan derecho a nuevas ranuras de entorno.

Si desea adquirir más entornos de sandbox, puede comprar ranuras de sandbox regulares adicionales. Microsoft puede ayudarlo a habilitar esas ranuras como unidades de escala de espacio aislado para la topología híbrida.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Incorporarse a la topología híbrida distribuida para Supply Chain Management

### <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Seleccione el inquilino de su proyecto LCS y el proceso de incorporación detallado

Una vez que haya terminado de planificar cómo se incorporará a la topología híbrida distribuida para Supply Chain Management, utilizará el [Portal de Scale Unit Manager](https://aka.ms/SCMSUM) para comenzar el proceso de incorporación. En el portal, seleccione la pestaña **Inqulinos de Dynamics 365**. Esta pestaña muestra la lista de inquilinos de los que forma parte su cuenta y dónde es propietario o administrador de entorno para un proyecto LCS.

Si el inquilino que está buscando no está en la lista, vaya a [LCS](https://lcs.dynamics.com/v2) y asegúrese de ser administrador del entorno o propietario del proyecto LCS para ese inquilino. Solo las cuentas de Azure Active Directory (Azure AD) del inquilino seleccionado están autorizadas para completar la experiencia de registro.

> [!NOTE]
> Después de aplicar los cambios a LCS, la lista de inquilinos puede tardar hasta 30 minutos en reflejar los cambios.

Para cada inquilino, la lista muestra el estado de incorporación.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Lista de inquilinos en la pestaña Dynamics 365 Tenants.":::

Seleccione **Haz clic para comenzar** para solicitar la incorporación del inquilino de LCS. Debe aceptar los términos. También debe proporcionar una dirección de correo electrónico comercial a la que Microsoft pueda enviar comunicaciones relacionadas con el proceso de incorporación.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Envío de registro para una suscripción.":::

Microsoft revisará su solicitud y le informará sobre los próximos pasos enviando un correo electrónico a la dirección que proporcionó en el formulario de registro. Microsoft trabajará en estrecha colaboración con usted para habilitar las unidades de escala en la topología híbrida para su escenario empresarial.

Una vez completada la incorporación, puede usar el puerto para configurar las unidades de báscula y las cargas de trabajo.

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Administre cargas de trabajo y unidades de escala en la nube mediante el portal Scale Unit Manager

Vaya al [Portal de Scale Unit Manager](https://aka.ms/SCMSUM) e inicie sesión con su cuenta de inquilino. En la página **Configurar unidades de escala**, puede agregar un entorno de concentrador si aún no está en la lista. Luego, puede seleccionar el concentrador que desea configurar con unidades de escala y cargas de trabajo.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Experiencia en gestión de cargas de trabajo y unidades de escala.":::

Para agregar una o más unidades de escala que están disponibles en sus suscripciones, seleccione **Agregar unidades de escala**.

En la pestaña **Cargas de trabajo definidas**, use el botón **Crear carga de trabajo** para agregar una carga de trabajo de gestión de almacén a una de sus unidades de báscula. Para cada carga de trabajo, debe especificar el contexto de los procesos que serán propiedad de la carga de trabajo. Para las cargas de trabajo de gestión de almacenes, el contexto es un almacén específico en un sitio y entidad legal específicos.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Creación de cargas de trabajo.":::

> [!TIP]
> Con el tiempo, se agregarán mejoras incrementales a la experiencia de Scale Unit Manager para ayudar a facilitar las operaciones de administración del ciclo de vida. Las capacidades específicas para la versión actual están documentadas en un manual de incorporación que está disponible para los clientes que están en el proceso de incorporación a la topología híbrida distribuida para Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
