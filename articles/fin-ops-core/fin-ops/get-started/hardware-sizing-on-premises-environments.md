---
title: Requisitos de dimensionamiento de hardware para entornos locales
description: Este tema muestra los requisitos de dimensionamiento de hardware para un entorno local.
author: sericks007
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 460297651f2766f96c34b258edbe94a7114ee090
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343967"
---
# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>Requisitos de dimensionamiento de hardware para entornos locales

[!include [banner](../includes/banner.md)]

Antes de comenzar el proceso de dimensionamiento de hardware e infraestructura para un entorno local, familiarícese con los [Requisitos del sistema para implementaciones en la nube](system-requirements.md) y las [Instrucciones de configuración e implementación](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md) para obtener una comprensión sólida de la infraestructura subyacente.

> [!NOTE]
> Preste mucha atención a las prácticas recomendadas de configuración del sistema para un rendimiento óptimo.

Una vez que haya revisado la documentación, puede iniciar el proceso de calcular el volumen de usuarios transaccional y simultáneo y dimensionar su entorno en función del rendimiento básico medio.

## <a name="factors-that-affect-sizing"></a>Factores que afectan al dimensionamiento

Todos los factores que se muestran en la siguiente ilustración contribuyen al dimensionamiento. Cuanta más información detallada se recopile, con mayor precisión podrá determinar el dimensionamiento. Es probable que el dimensionamiento de hardware, sin datos complementarios, sea impreciso. El requisito mínimo absoluto para todos los datos necesarios es la carga de línea de transacción máxima por hora.

[![Dimensionamiento de hardware para entornos locales.](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

Visto de izquierda a derecha, el primer y más importante factor necesario para calcular el dimensionamiento con precisión es un perfil de transacción o una caracterización de transacción. Es importante encontrar siempre el volumen transaccional máximo por hora. Si hay varios periodos máximos, estos periodos tienen que definirse de manera detallada.

A medida que comprenda la carga que afecta a su infraestructura, también debe entender más detalles acerca de estos factores:

- **Transacciones** - Normalmente, las transacciones tienen ciertos máximos durante el día/semana. Esto depende sobre todo del tipo de transacción. Las entradas de hora y gasto suelen mostrar máximos una vez a la semana, mientras que las entradas de pedido de ventas suelen venir de forma masiva a través de la integración o el goteo durante el día.
- **Número de usuarios simultáneos** - El número de usuarios simultáneos es el segundo factor de dimensionamiento más importante. No podrá obtener estimaciones del dimensionamiento de forma segura en base al número de usuarios simultáneos, por lo que si estos son los únicos datos que tiene disponibles, calcule un número aproximado y luego vuelva a visitar esto cuando tenga más datos. Una definición precisa de usuario simultáneo significa que:

    - Los usuarios denominados no son usuarios simultáneos.
    - Los usuarios simultáneos son siempre un subconjunto de usuarios denominados. 
    - La carga de trabajo máxima define la concurrencia máxima para el dimensionamiento.

    Los criterios para los usuarios simultáneos son que el usuario cumpla todos los criterios siguientes:

    - Haber iniciado sesión.
    - Trabajar con transacciones/consultas a la hora del recuento.
    - No tener una sesión inactiva.

- **Composición de datos** - Es principalmente acerca de cómo el sistema se ajustará y configurará. Por ejemplo, cuántas entidades jurídicas tendrá, cuántos artículos, cuántos niveles de L. de M. y cómo de compleja será su configuración de seguridad. Cada uno de estos factores puede tener un pequeño impacto en el rendimiento, por lo que se pueden compensar mediante opciones inteligentes cuando se trata de una infraestructura.
- **Extensiones** - Las personalizaciones pueden ser simples o complejas. El número de personalizaciones y la naturaleza de la complejidad y el uso tienen un impacto variado en el tamaño de la infraestructura necesaria. Para las personalizaciones complejas, se aconseja realizar evaluaciones de rendimiento para garantizar que no solo se prueba su eficacia, sino que también ayuda a comprender las necesidades de la infraestructura. Esto es aún más crítico cuando las extensiones no se codifican de conformidad con las prácticas recomendadas para el rendimiento y la escalabilidad.
- **Informes y análisis** - Normalmente, estos factores incluyen grandes consultas con distintas bases de datos del sistema. Comprender y reducir la frecuencia cuando se ejecutan informes costosos le ayudará a comprender el impacto de estos.
- **Soluciones de terceros** - Estas soluciones, como los ISV, tienen las mismas implicaciones y recomendaciones que las extensiones.

## <a name="sizing-your-environment"></a>Ajustar el tamaño del entorno

Para comprender los requisitos de dimensionamiento, tiene que conocer el volumen máximo de transacciones que necesita procesar. La mayoría de sistemas auxiliares, como Management Reporter o SSRS, son menos fundamentales para la misión. Como resultado, este documento se centra principalmente en AOS y SQL Server.

> [!NOTE]
> En general, los niveles de cálculo escalan horizontalmente y deben configurarse en un modo N+1, lo que significa que si calcula tres AOS, tiene que agregar un cuarto AOS. El nivel de la base de datos debe configurarse en una configuración de alta disponibilidad Always On.

## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Dimensionamiento

- De 3000 a 15 000 líneas de transacción por hora por núcleo en servidor DB.
- Proporción 3:1 de núcleo típico AOS a SQL para el SQL Server principal. Los núcleos adicionales se obligatorios en función de la configuración de alta disponibilidad elegida.

    - El procesamiento de operaciones pesadas en la base de datos puede hacer retroceder esto a 2:1.

- Los siguientes factores influyen en las variaciones:

    - Configuración de parámetros en uso.
    - Niveles de extensiones.
    - Uso de la funcionalidad adicional, como registro de base de datos y alertas. El registro extremo de base de datos reducirá aún más el rendimiento por hora por núcleo por debajo de las 3000 líneas.
    - Complejidad de la composición de datos - Un plan de cuentas sencillo frente a un plan de cuentas fino y detallado tiene implicaciones en el rendimiento (como un ejemplo).
    - Caracterización de la transacción.
    - 2 GB a 16 GB de memoria para cada núcleo
    - Bases de datos auxiliares en servidor DB como Management Reporter y bases de datos de SSRS.
    - DB temporal = 15% del tamaño de la DB, con tantos archivos como procesadores físicos.
    - Tamaño y rendimiento de SAN basados en el volumen/uso total de la transacción simultánea.

### <a name="high-availability"></a>Alta disponibilidad

Le recomendamos que utilice siempre el SQL Server en un clúster o una configuración de replicación. El segundo nodo de SQL debe tener el mismo número de núcleos que el nodo principal.

### <a name="active-directory-federation-services-ad-fs"></a>Servicios de federación de Active Directory (AD FS)

Para el dimensionamiento de los AD FS, consulte [Documentación de la capacidad del servidor de los AD FS](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

Hay una [hoja de cálculo de dimensionamiento](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx) disponible para planificar el número de instancias en su implementación.

## <a name="aos-online-and-batch"></a>AOS (en línea y lote)

### <a name="sizing"></a>Dimensionamiento

- Dimensionamiento por volumen/uso de transacción

    - 2000 a 6000 líneas por núcleo
    - 16 GB por instancia
    - Caja estándar – 4 a 24 núcleos
    - 10 a 15 usuarios de Enterprise por núcleo
    - 15 a 25 usuarios de Activity por núcleo
    - 25 a 50 miembros del equipo por núcleo

- Lote

    - 1 a 4 subprocesos de lote por núcleo
    - Tamaño basado en la caracterización de la ventana de lotes

- Tenga en cuenta que el AOS, la administración de datos y el lote se encuentran en el mismo rol en el Service Fabric. Tiene que dimensionar estas tres cargas de trabajo combinadas y no separar éstas como en Microsoft Dynamics AX 2012.
- Aquí se aplican los mismos factores de variabilidad para SQL Server.

### <a name="high-availability"></a>Alta disponibilidad

- Asegúrese de que tiene al menos 1 o 2 AOS más disponibles de lo que calcula.
- Asegúrese de tiene al menos 3 o 4 hosts virtuales disponibles.

## <a name="management-reporter"></a>Management Reporter

En la mayoría de los casos, salvo que se utilicen extensivamente, los requisitos mínimos recomendados usando dos nodos deberían funcionar bien. Solo se necesitarán más de dos nodos en casos en los que haya un uso pesado. Escale según sea necesario.

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services

Solo puede implementarse un nodo SSRS para la versión de disponibilidad general. Controle su nodo SSRS mientras realiza la prueba y aumente el número de núcleos disponible para SSRS en función de las necesidades. Asegúrese de que tiene un nodo secundario preconfigurado disponible en un host virtual que sea diferente de la MV de SSR. Esto es importante si hay un problema con la máquina virtual que aloja a SSRS o al host virtual. Si este es el caso, tendría que reemplazarse.

A partir de la versión 10.0.17, es posible configurar nodos SSRS adicionales para lograr una alta disponibilidad. Para obtener más información, consulte [Configurar la alta disponibilidad para los nodos de SQL Server Reporting Services (SSRS)](../../dev-itpro/deployment/onprem-ssrsha.md)

## <a name="environment-orchestrator"></a>Orquestador de entorno

El servicio del orquestador es el servicio que administra su implementación y la comunicación relacionada con LCS. Este servicio se implementa como el servicio principal del Service Fabric y requiere al menos tres MV. Este servicio se ubica en el mismo lado que los servicios de orquestación de Service Fabric. Este debe dimensionarse a la carga máxima del clúster. Para obtener más información, consulte [Planificar y preparar la implementación del clúster autónomo de Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="virtualization-and-oversubscription"></a>Virtualización y sobresuscripción

Los servicios fundamentales para la misión, como el AOS, deben hospedarse en host virtuales que tiene recursos dedicados - núcleos, memoria y disco.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
