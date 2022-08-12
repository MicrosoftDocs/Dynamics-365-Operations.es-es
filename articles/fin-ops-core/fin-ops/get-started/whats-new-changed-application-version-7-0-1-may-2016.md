---
title: Novedades o cambios en la aplicación Dynamics AX versión 7.0.1 (mayo de 2016)
description: Este artículo describe las características que son nuevas o que han cambiado en la aplicación Microsoft Dynamics AX versión 7.0.1. Esta versión se publicó en mayo de 2016 y tiene un número de compilación de 7.0.1265.23014.
author: sericks007
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 6c65c56dfe5d1e32c440789d207f787169c57269
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124878"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Novedades o cambios en la aplicación Dynamics AX versión 7.0.1 (mayo de 2016)

[!include [banner](../includes/banner.md)]

Este artículo describe las características que son nuevas o que han cambiado en la aplicación Microsoft Dynamics AX versión 7.0.1. Esta versión se publicó en mayo de 2016 y tiene un número de compilación de 7.0.1265.23014.

## <a name="electronic-reporting-er"></a>Informes electrónicos (ER)

| ¿Qué se puede hacer? | ¿Por qué esto es importante? |
|------------------|------------------------|
| Configure un cuadro de diálogo en tiempo de ejecución para diseñar informes de informes electrónicos (ER), de manera que los usuarios puedan seleccionar las dimensiones financieras que desean. | En tiempo de ejecución, en el cuadro de diálogo para ejecutar un informe de ER, los usuarios pueden seleccionar varias dimensiones financieras. Los detalles de las dimensiones financieras seleccionadas se mostrarán en el documento electrónico que se genera. |
| Configure el acceso a varias dimensiones financieras durante el diseño de un informe de ER, mediante una asignación única al origen de datos deseado. | La misma configuración de informes de ER se puede utilizar para generar documentos electrónicos que presentan datos transaccionales junto con detalles de las dimensiones financieras, independientemente del número de dimensiones financieras seleccionadas por el usuario o configuradas por la instancia o entidad jurídica actual. |
| Configure un informe de ER para introducir datos en las columnas generadas dinámicamente de un documento electrónico que se crea en el formato de hoja de cálculo OPENXML. | Un informe de ER puede introducir datos en una hoja de cálculo OPENXML que se genera a través de columnas de replicación horizontal. Por lo tanto, se puede reutilizar la misma configuración de informes de ER para generar documentos electrónicos que tienen un número diferente de columnas generadas dinámicamente. |
| Configure los destinos de ER para que el resultado de salida de un formato se dirija a un destino específico: archivo o correo electrónico (carpeta de Microsoft SharePoint o Almacenamiento de Microsoft Azure). | Anteriormente, cuando ejecutaba una configuración de ER, aparecería un cuadro de mensaje que requería la acción de usuario para guardar o abrir un archivo. Ahora puede preconfigurar un destino para cada configuración de formato y para cada componente de salida (una carpeta o un archivo) por separado. Los usuarios que tienen derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>PDV - Microsoft Dynamics AX Retail

| ¿Qué se puede hacer? | ¿Por qué esto es importante? |
|------------------|------------------------|
| Utilice el explorador de Google Chrome. | Los minoristas pueden iniciar ahora Cloud POS desde el explorador de Chrome y pueden probar toda la funcionalidad que está disponible en la versión de Microsoft Edge e Internet Explorer de Cloud POS. |

## <a name="financial-reporting"></a>Informes financieros

| ¿Qué se puede hacer? | ¿Por qué esto es importante? |
|------------------|------------------------|
| Vuelva a generar el data mart de informes financieros. | Al mover las bases de datos de Dynamics AX entre entornos o realizar otros cambios invasivos en el entorno, es posible que se tenga que volver a generar la base de datos de informes financieros. Ahora se proporciona un script de Windows PowerShell para volver a generar la base de datos. |
| Ya no se pueden seleccionar opciones del diseñador de informes que no son válidas. | Varias opciones del diseñador de informes que se utilizaban en las versiones del mercado de Management Reporter no se aplican a esta versión de Dynamics AX. Estas opciones estaban relacionados con el diseño de informes financieros, salida y vinculación. Estas opciones se han quitado del diseñador de informes financieros para evitar errores de usuario. |

## <a name="financial-management"></a>Administración financiera

| ¿Qué se puede hacer? | ¿Por qué esto es importante? |
|------------------|------------------------|
| Generar archivos de pago positivos para los pagos de proveedores. | Los archivos positivos de pago se pueden generar para ayudar a evitar fraude de cheques. |

## <a name="warehouse-and-production"></a>Almacén y producción

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definir una directiva de trabajo de almacén que controle la creación de trabajo para un conjunto de productos en almacenes específicos.</td>
<td>Los procesos de almacén no siempre incluyen trabajo. Mediante la nueva directiva de trabajo de almacén, puede evitar la creación de trabajo para picking de materia prima y ubicación de bienes terminados para un conjunto de productos en ubicaciones específicas.</td>
</tr>
<tr>
<td>Especificar que una ubicación de salida de producción no está controlada por matrículas de entidad de almacén.</td>
<td>Ahora puede especificar que una ubicación de salida de producción no está controlada por matrículas de entidad de almacén. Por ejemplo, esta característica es útil cuando un pedido de producción ascendente notifica artículos como terminados directamente a una ubicación que actúa como la ubicación de entrada de producción para un pedido de producción descendente.</td>
</tr>
<tr>
<td>Admitir listas de materiales que incluyan artículos con diferentes dimensiones de producto del mismo artículo.</td>
<td>Cuando se utiliza una o varias de las dimensiones del producto en producción, tendrá situaciones en las que desee producir un artículo, en función de una variante diferente del mismo artículo. Para obtener más información, consulte <a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">este blog</a>.</td>
</tr>
<tr>
<td>Los pedidos de producción con estructuras circulares en el primer nivel de sus listas de materiales se excluyen del cálculo del nivel de L. MAT para la planificación de recursos materiales.</td>
<td>No es posible asignar niveles de L. MAT correctos a las variantes de producto para los pedidos de producción que causan circularidad en la jerarquía de L. MAT.</td>
</tr>
<tr>
<td>Calcule niveles de L. MAT independientes para la planificación de recursos materiales y el cálculo de costes:
<ul>
<li>Para la planificación de recursos materiales, los niveles de L. MAT se calculan en la nueva tabla <strong>ReqItemLevel</strong>. Los pedidos de producción finalizados se omiten en el cálculo.</li>
<li>Para el cálculo de costes de producción, los niveles de L. MAT se calculan en la <strong>InventTable</strong>. Los pedidos de producción finalizados se incluyen en el cálculo.</li>
</ul>
</td>
<td>
<ul>
<li>Cuando se ejecuta la planificación de recursos materiales, por ejemplo, la expansión y la programación de la planificación maestra, solo se tienen que volver a calcular los niveles de la lista de materiales utilizados para la planificación de recursos de materiales. En otras palabras, no hay ninguna necesidad de calcular niveles de lista de materiales utilizados para el cálculo de gestión de costes de producción.</li>
<li>Al ejecutar operaciones de gestión de costes, por ejemplo, el cierre de inventario, solo se tienen que volver a calcular los niveles de lista de materiales para el cálculo de gestión de costes de producción.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionales

[Página principal de Novedades y cambios en finanzas y operaciones](whats-new-changed.md)

[Guías de tareas nuevas o actualizadas (mayo de 2016)](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
