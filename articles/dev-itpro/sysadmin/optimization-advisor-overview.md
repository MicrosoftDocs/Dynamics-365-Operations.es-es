---
title: Asesor de optimización
description: Este tema describe cómo puede usar el asesor de optimización para ayudar a garantizar la configuración óptima de Microsoft Dynamics 365 Finance and Operations.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: fce7cfd8619cc533aa444409f7ffa3044eb7378a
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851396"
---
# <a name="optimization-advisor"></a>Asesor de optimización

[!include [banner](../includes/banner.md)]

Este tema describe cómo puede usar el asesor de optimización para ayudar a garantizar la configuración óptima de Microsoft Dynamics 365 Finance and Operations.

## <a name="overview"></a>Información general

La configuración incorrecta y la configuración de un módulo pueden afectar negativamente a la disponibilidad de funciones de Finance and Operations, el rendimiento del sistema, y la ejecución fluida de procesos empresariales. La calidad de datos empresariales (por ejemplo, la corrección, la integridad y la limpieza de los datos) también afecta al rendimiento del sistema, así como a las capacidades de toma de decisiones de una organización, su productividad, etc.

El espacio de trabajo **Asesor de optimización** es una herramienta que permite a los usuarios avanzados, analistas de negocios, consultores funcionales, y las funciones del soporte para la TI identificar problemas en la configuración y datos empresariales de módulo. El asesor de optimización sugiere las prácticas recomendadas para la configuración de módulo e identifica los datos empresariales que son obsoletos o incorrectos.

El asesor de optimización ejecuta periódicamente un conjunto de reglas de prácticas recomendadas. Lanzan al mercado un conjunto de reglas predeterminado así como Microsoft Dynamics 365 for Finance and Operations versión 8.0 (abril de 2018). Sin embargo, los usuarios también pueden crear reglas que sean específicas a sus personalizaciones, soluciones de fabricantes de software independientes (ISV) y datos de la empresa. Para obtener más información acerca de cómo crear reglas, consulte [Crear nuevas reglas](./create-rules-optimization-advisor.md).

Cuando una infracción de una regla se detecta, se genera una oportunidad de optimización y aparece en el espacio de trabajo **Asesor de optimización**. Un usuario puede realizar la acción correctora adecuada directamente desde el espacio de trabajo **Asistente de optimización**.

Las ocasiones pueden ser específicas de la empresa o entre empresas, en función del tipo de configuración y de datos que se estén validando. Las oportunidades entre empresas se pueden ver desde todas las empresas. Para ver las oportunidades de una empresa específica, primero debe seleccionar la empresa.

Las directivas de seguridad estándar se aplican a las oportunidades de optimización. Por ejemplo, las oportunidades de optimización relacionadas con la configuración del módulo **Administración de almacenes** están visibles solo para los usuarios que tengan acceso a la gestión de almacenes y puedan cambiar su configuración.

Cuando realiza acciones en algunas oportunidades de optimización, el sistema calcula el impacto de la oportunidad en términos de reducción del tiempo de ejecución de procesos empresariales. Desafortunadamente, esta característica no está disponible para todas las oportunidades de optimización.

Para obtener más información acerca de aviso de optimización, vea el breve vídeo [Asesor de optimización en Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ).

## <a name="optimization-rules"></a>Reglas de optimización

Para ver la lista completa de reglas del asesor de optimización y para ver con qué frecuencia se evalúan las reglas, vaya **Administración del sistema** &gt; **Tareas periódicas** &gt; **Mantener la regla de validación de los diagnósticos**. Solo se evalúan las reglas que tengan un estado **Activo**. La frecuencia de evaluación se puede establecer **Diario**, **Semanal**, **Mensual**, o **No programado**.

Para activar una evaluación de reglas no programadas, o reevaluar reglas periódicas de fuera de la programación predefinida, vaya **Administración del sistema** &gt; **Tareas periódicas** &gt; **Regla de validación de los diagnósticos de programación**. A continuación, en el cuadro de diálogo **Validación de diagnóstico de la regla**, seleccione una frecuencia de evaluación. Todas las reglas que tengan la frecuencia especificada serán evaluadas.

El conjunto de reglas actual de optimización se puede dividir en las categorías siguientes.

### <a name="module-configuration-and-setup"></a>Instalación y configuración de módulo

La configuración de la gestión de almacenes es un proceso complicado. Para que el proceso sea más sencillos, algunas reglas se han introducido para ayudar a validar la corrección de la configuración. Por ejemplo, una regla valida la configuración de las directivas de la ubicación del almacén para las ubicaciones fijas de la variante del producto para los pedidos de ventas y pedidos de transferencia.

Además, algunas reglas comprueban si las características que se han habilitado se están utilizando realmente. Por ejemplo, una regla determina si está usando el módulo **Planificación maestra**. Si la regla determina que no está usando el módulo, se genera una oportunidad de optimización para sugerir que desactive los procesos de planificación.

### <a name="system-configuration"></a>Configuración del sistema

Si la funcionalidad específica que se controla mediante una clave de configuración no se utiliza, se genera una oportunidad de optimización que sugiere que deshabilite la clave de configuración. Los ejemplos de claves de configuración incluyen **Peso capturado**, **Planificación presupuestaria**, **Proyecto** y **Lista de proveedores aprobada**.

### <a name="business-data-consistency-and-cleanup"></a>Coherencia y limpieza de datos empresariales

Si los datos maestros no son correctos (por ejemplo, si tiene conversiones de unidad de medida para las unidades que no se han definido o si tiene conversiones de unidad de medida que tengan una división por 0 \[cero\]), se genera una oportunidad de optimización para sugerir que corrija los datos. 

Si tiene demasiadas entradas del historial de trabajos por lotes, artículos obsoletos, entradas disponibles cerradas para los artículos habilitados de almacenes, etc., o si estas entradas y artículos son demasiado antiguos, se generan oportunidades de optimización para sugerir que limpie los datos. Conservando los datos limpios, puede ayudar a mejorar el rendimiento general del sistema.

### <a name="best-practices"></a>Prácticas recomendadas

Si no está ejecutando algunos procesos de negocio según las prácticas recomendadas (por ejemplo, si se ejecuta el cierre previo de inventario antes de cerrar el inventario, o si usa el lote programado para la transferencia por lotes del subdiario contable), las oportunidades de optimización le informarán acerca de la práctica recomendada y le pedirán que la siga.

## <a name="optimization-opportunities"></a>Oportunidades de optimización

Para ver las oportunidades de optimización que se generan durante la evaluación de las reglas de optimización, abra el espacio de trabajo **Asesor de optimización**.

En este espacio de trabajo, puede ver más información acerca de una oportunidad seleccionando **Más información**. Si desea que el sistema tome medidas y corrija la configuración, limpie los datos, etc., de modo que usted no tenga que abrir las páginas correspondientes, seleccione **Tomar medidas**.

No hay flujo de trabajo para las oportunidades de optimización. Tras seleccionar **Tomar medidas** o utilizar una ruta de navegación que se proporcione en el cuadro de diálogo **Más información**, la oportunidad de optimización desaparece de la lista. Si la acción correctiva no resuelve un problema completamente, la oportunidad se generará de nuevo la próxima vez que se evalúe la regla.

Si una oportunidad no aplica a su rol, puede seleccionar **Ocultar de mi lista**. Incluso si la regla detrás de esta oportunidad se activa de nuevo más adelante, no verá la oportunidad en la lista.

Para desactivar la evaluación de reglas específicas, seleccione la oportunidad que generó la regla y, a continuación seleccione **Desactivar análisis**.

## <a name="additional-resources"></a>Recursos adicionales

[Crear nuevas reglas](./create-rules-optimization-advisor.md)

[Asesor de optimización en Dynamics 365 for Finance and Operations (vídeo)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)
