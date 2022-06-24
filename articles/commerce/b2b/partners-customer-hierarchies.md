---
title: Administrar socios comerciales B2B utilizando jerarquías de clientes
description: Este artículo describe cómo usar jerarquías de clientes para administrar socios comerciales para sitios web de comercio electrónico de empresa a empresa (B2B) para Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddd02045b5df3ce20160a4feaa23339475823d3d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864990"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>Administrar socios comerciales B2B utilizando jerarquías de clientes

[!include [banner](../../includes/banner.md)]

Este artículo describe cómo usar jerarquías de clientes para administrar socios comerciales para sitios web de comercio electrónico de empresa a empresa (B2B) para Microsoft Dynamics 365 Commerce.

En la sede de Commerce, una *jerarquía de clientes* se utiliza para representar a las organizaciones de socios comerciales que utilizarán su sitio de comercio electrónico B2B. Antes de que pueda comenzar a usar jerarquías de clientes para administrar socios comerciales, debe habilitar las capacidades de comercio electrónico B2B en la sede de Commerce y luego definir una secuencia numérica para la jerarquía de clientes.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>Habilitar la característica de comercio electrónico B2B en la sede central de Commerce

Para usar las capacidades de comercio electrónico B2B, primero debe habilitar la característica **Habilitar el uso de funciones de comercio electrónico B2B** en la sede de Commerce.

1. Vaya a **Espacios de trabajo \> Administración de características**.
1. En la pestaña **Todos**, utilice el cuadro de filtro para buscar **Módulo: Retail y Commerce**.
1. Busque la característica llamada **Habilitar el uso de funciones de comercio electrónico B2B**, selecciónela y, a continuación, seleccione **Habilitar ahora** en la esquina inferior derecha.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>Definir una secuencia numérica para la jerarquía de clientes

Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores. Debe definir una secuencia numérica que se utilizará para generar el id. para la jerarquía de clientes. Para obtener más información sobre las secuencias numéricas, consulte [Información general de secuencias numéricas](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Para definir una secuencia numérica para la jerarquía de clientes en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Secuencias numéricas \> Secuencias numéricas**.
1. Cree una nueva secuencia numérica o seleccione una secuencia numérica existente para reutilizarla.
1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos de Commerce**.
1. En la pestaña **Secuencias numéricas**, agregue la secuencia numérica que creó o seleccionó anteriormente a la referencia **Id. de jerarquía del cliente**.

![Secuencia numérica añadida a la referencia de id. de jerarquía del cliente.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>Cómo funciona el proceso de aprobación

Cuando un socio comercial solicita unirse a un sitio de comercio electrónico B2B, el sistema guarda la solicitud como un *cliente potencial*. Una persona de la sede central de Commerce, como un gerente de operaciones minoristas, puede aprobar o rechazar solicitudes de socios. Para obtener más información sobre cómo administrar solicitudes de socios comerciales y aprobaciones de clientes potenciales, consulte [Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B](manage-b2b-users.md).

Cuando se aprueba un cliente potencial, el sistema crea dos nuevos registros de clientes:

- Un registro de cliente del tipo **Organización** representa la organización que solicita convertirse en socio comercial.
- Un registro de cliente del tipo **Persona** representa a la persona que envió la solicitud.

Además, se crea un nuevo registro de jerarquía de clientes en **Retail y Commerce \> Clientes \> Jerarquías de clientes**. Esta jerarquía de cliente tiene las siguientes propiedades de encabezado:

- **Id. de jerarquía de clientes**: el identificador único para la jerarquía de clientes. Este id. usa la secuencia numérica que definió en los parámetros compartidos de Commerce.
- **Nombre**: el nombre de la organización socio comercial, como se especifica en la solicitud de incorporación. Este campo es editable.
- **Objetivo**: esta propiedad se establece en el valor predefinido **Organización de B2B**.
- **Organización**: id. de cliente de la organización socio comercial.

La persona que envió la solicitud de incorporación se agrega en la ficha desplegable **Jerarquía** y se le asigna el rol **Administrador**. A medida que el administrador agrega más usuarios a la organización de socios comerciales en un sitio B2B, se crea un nuevo registro de cliente para cada usuario. El registro de cliente también se agrega al registro de jerarquía de clientes relevante para el socio comercial y se le asigna el rol de **Usuario**.

### <a name="examples"></a>Ejemplo

Una persona que se llama Sam J. envía una solicitud de incorporación en nombre de la organización de Microsoft. Una vez que se aprueba la solicitud, se crean dos nuevas cuentas de cliente: una del tipo **Persona** para Sam J. y una del tipo **Organización** para Microsoft.

Como muestra el ejemplo de la siguiente ilustración, también se crea un nuevo registro de jerarquía de clientes. Este registro tiene el mismo nombre que la organización (**Microsoft**) y el rol **Administrador** se asigna a Sam J. Como administrador, Sam J. agrega cualquier otro usuario de Microsoft del sitio B2B a esta jerarquía y les asigna el **Usuario**. En este ejemplo, Sush R. se ha agregado como usuario.

![Ejemplo de un registro de jerarquía de cliente.](../media/CustomerHierarchy2.png)

Para determinar si un cliente está asociado con una jerarquía de clientes, abra el registro del cliente. Como muestra el ejemplo de la siguiente ilustración, el campo **Id. de jerarquía del cliente** en la sección **B2B** en la ficha desplegable **Retail** muestra si el cliente es parte de una jerarquía de clientes y la opción **Administrador B2B** indica si el cliente es un administrador de esa jerarquía.

![Ejemplo de la sección B2B en la ficha desplegable Retail de un registro de cliente, donde el cliente está asociado a una jerarquía y se especifica como administrador.](../media/CustomerHierarchyMapping2.png)

En la mayoría de los casos, los valores de propiedad de todos los registros de clientes de una jerarquía deben coincidir. Por ejemplo, como todos los usuarios socios comerciales deben obtener precios similares para los productos, su grupo de precios y las configuraciones asociadas deben coincidir. Sin embargo, el sistema no aplica esta coherencia. Por lo tanto, los usuarios de la sede central de Commerce correspondientes son responsables de garantizar que los valores y las configuraciones de las propiedades coincidan para todos los clientes en una jerarquía determinada.

Los usuarios de la sede central de Commerce pueden inspeccionar los valores de propiedades de todos los registros de clientes de la jerarquía en una vista en paralelo. Como muestra el ejemplo de la siguiente ilustración, puede utilizar la opción **General** en la lista desplegable de la ficha desplegable **Jerarquía** y luego seleccionar cualquier sección del registro del cliente para mostrar las propiedades relacionadas. Los usuarios pueden editar directamente los valores de propiedad en esta vista. Para copiar todos los valores de un registro de cliente administrador a todos los usuarios, seleccione **Anular** en la ficha desplegable **Jerarquía**.

![Ejemplo de un registro de jerarquía de clientes, que muestra el botón Anular y la opción en la lista desplegable.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
