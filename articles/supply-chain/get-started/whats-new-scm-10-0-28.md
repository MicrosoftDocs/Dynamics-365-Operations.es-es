---
title: Vista previa de Dynamics 365 Supply Chain Management 10.0.28 (agosto de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Supply Chain Management 10.0.28.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 2b129481399897337e960ec2d708d69a563b5435
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902064"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10028-august-2022"></a>Vista previa de Dynamics 365 Supply Chain Management 10.0.28 (agosto de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión preliminar 10.0.28. Esta versión tiene el número de compilación 10.0.1264 y está disponible con la siguiente programación:

- **Vista previa de la versión:** mayo 2022
- **Disponibilidad general de la versión (actualización automática):** julio de 2022
- **Disponibilidad general de la versión (actualización automática):** julio de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Inventario y logística | [Entidades de integración de costos descargados para transitarios de terceros](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Información general de entidades de costes en destino](../landed-cost/landed-cost-entities-overview.md) | Habilitado por defecto |
| Planificada | [Planificación de requisitos de materiales basada en la demanda (DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | Próximamente | Administración de características:<br>*(Versión preliminar) DDMRP para optimización de planificación* |
| Planificada | [Compatibilidad de Optimización de planificación para capaz de comprometer (CTP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capable-to-promise-ctp) | Próximamente | Administración de características:<br>*(Versión preliminar) CTP para Optimización de planificación* |
| Planificada | [Soporte de optimización de planificación para vida útil](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Próximamente | Habilitado por defecto |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Gestión de inventario y almacenes | Habilitar que la disponibilidad de empresas vinculadas solo muestre una cantidad disponible distinta de cero | Esta función le permite elegir si los artículos con cero cantidad disponible deben incluirse en la lista disponible de empresas vinculadas. Puede controlar esta opción usando la configuración **No mostrar artículos con cero cantidad disponible en la lista disponible de empresas vinculadas**, que esta función añade a la página **Parámetros de gestión de inventario y almacén**. |
| Gestión de inventario y almacenes | (India) Para las reglas de precios de transferencia, ignorar la ubicación cuando "Código de almacén de salida" está establecido en "Todos" | <p>Esta característica se aplica solo a las localizaciones de India. Hace que el proceso de configuración de precios de transferencia para artículos en transferencias de existencias sea más intuitivo.</p><p>Los precios de transferencia se configuran configurando cada artículo con reglas de precios de transferencia. Una forma de hacer esta configuración es incluir una línea de regla donde el campo **Del código de almacén** se establece en *Todos*. Esta configuración indica que el precio de transferencia definido por la línea debe aplicarse independientemente del almacén del que se recolecte el artículo. Cuando esta característica está habilitada, las reglas de precios de transferencia donde el campo **Del código de almacén** se establece en *Todos* ignorará el ajuste **Ubicación**. Por lo tanto, la regla se aplicará independientemente de la ubicación que se especifique en la orden de transferencia. Este comportamiento es probablemente el esperado, porque la ubicación está debajo del almacén en la jerarquía de dimensiones de almacenamiento.</p><p>Sin esta función, el sistema aplicará reglas de este tipo solo cuando la ubicación en la orden de transferencia coincida exactamente con la ubicación establecida para la regla. (Si se establece una ubicación en blanco para la regla, el sistema aplicará la regla solo a las órdenes de transferencia que también tengan un valor en blanco para la ubicación).</p> |
| Gestión de inventario y almacenes | Limpieza de datos del informe de disponibilidad del inventario | Esta característica ofrece una forma de limpiar los datos que se usan para crear los informes del *Almacenamiento de informes de disponibilidad de inventario*. |
| Control de producción | Asignar actividades de proyecto para el acuerdo de servicio y las líneas de pedido de servicio | Esta función agrega un campo que se denomina **Actividad del proyecto** al contrato de servicio y líneas de orden de servicio, para que pueda establecer una actividad de proyecto para ellos. La función ayudará a evitar errores de bloqueo cuando publique diarios de proyectos de gestión de servicios que requieran que se establezca una actividad de proyecto.  |
| Gestión de almacenes | Servicio de selección manual de línea de transferencia para administración o usuarios de confianza similares | Esta función permite a los administradores seleccionar manualmente las transacciones de inventario relacionadas con las líneas de transferencia. Estas líneas incluyen las líneas que ya se han liberado al almacén. Los administradores deben hacer esta selección solo en casos excepcionales, como cuando el sistema está dañado. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes artículos de Ayuda. Estos artículos no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en las secciones anteriores. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Artículos nuevos o actualizados |
|---|---|
| Gestión de costes | [Precio de recepción fijo](../cost-management/fixed-receipt-price.md) |
| Gestión de costes | [Preguntas frecuentes sobre costes de inventario](../cost-management/inventory-costing-faq.md) |
| Gestión de costes | [Registrar para cargar el principio contable de la cuenta](../cost-management/post-to-charge-account-accounting-principle.md) |
| Administración de inventario | [Detalles de transacción de inventario](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.28 incluye Platform updates. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.28 de aplicaciones de Finanzas y Operaciones (junio de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.28, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022](/dynamics365-release-plan/2022wave1/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
