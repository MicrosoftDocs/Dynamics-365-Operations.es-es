---
title: Componentes de los informes electrónicos
description: Este tema describe los componentes de informes electrónicos (ER).
author: nselin
ms.date: 09/28/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.topic: overview
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a24aa52c805722c20045b6227ceac0103cfbe6b
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "8324044"
---
# <a name="electronic-reporting-components"></a>Componentes de los informes electrónicos

[!include [banner](../includes/banner.md)]

Los informes electrónicos (ER) admiten los siguientes tipos de componentes:

- Modelo de datos
- Asignación de modelos
- Formato
- Metadatos

## <a name="data-model-component"></a>Componente de modelo de datos

Un componente de modelo de datos es una representación abstracta de una estructura de datos. Describe un área de dominio empresarial específico con los detalles suficientes para cumplir los requisitos de creación de informes para dicho dominio. Un componente del modelo de datos consta de las siguientes partes:

- **Modelo de datos**: un conjunto de entidades específicas de empresa de dominio y una definición jerárquicamente estructurada de las relaciones entre esas entidades.
- **Asignación de modelo**: vincula orígenes de datos seleccionados de la aplicación a elementos individuales de un modelo de datos que especifica, en tiempo de ejecución, el flujo de datos y las reglas de población de datos empresariales en un componente de modelo de datos.

La entidad de negocio de un modelo de datos se representa como un contenedor o registro. Las propiedades de la entidad empresarial se representan como elementos de datos o campos. Cada elemento de datos tiene un nombre, ficha, descripción y valor únicos. El valor de cada elemento de datos se puede diseñar para que se reconozca como cadena, entero, real, fecha, enumeración (enum) o valor booleano. Además, el artículo de datos puede ser otro registro o lista de registros.

Un único componente del modelo de datos puede contener varias jerarquías de entidades empresariales de dominio específicas. También contiene asignaciones de modelo que admiten un flujo de datos de informes específico en el runtime. Las jerarquías se distinguen por un único registro que se ha seleccionado como raíz para la asignación de modelo. Por ejemplo, el modelo de datos del área de dominio de pago puede admitir las asignaciones siguientes:


- Empresa \> Proveedor \> Transacciones de pago del dominio de proveedores
- Cliente \> Empresa \> transacciones de pago del dominio de clientes

Entidades empresariales como las transacciones de empres y de pago se diseñan una vez. Diferentes asignaciones pueden reutilizarlos según sea necesario.

## <a name="model-mapping-component"></a>Componente de asignación de modelos

La asignación de modelo vincula orígenes de datos seleccionados de la aplicación a elementos individuales de un modelo de datos que especifica, en tiempo de ejecución, el flujo de datos y las reglas de población de datos empresariales en un componente de modelo de datos.

Una asignación de modelo que admite documentos electrónicos salientes tiene las siguientes capacidades:

- Puede utilizar distintos tipos de datos como orígenes de datos para un modelo de datos. Estos tipos de datos incluyen tablas, entidades de datos, métodos y enumeraciones.
- Admite parámetros de entrada de usuario que se pueden definir como orígenes de datos para un modelo de datos cuando algunos datos se deben especificar en el runtime.
- Admite la transformación de los datos en los grupos necesarios. También puede, filtrar, clasificar y sumar datos y anexar campos lógicos calculados que están diseñados con las fórmulas que se asemejan las fórmulas de Microsoft Excel. Para obtener más información, consulte [Diseñador de fórmulas en los informes electrónicos (ER)](general-electronic-reporting-formula-designer.md).

Una asignación de modelo que admite documentos electrónicos entrantes tiene las siguientes capacidades:

- Puede utilizar distintos elementos de datos actualizables como objetivos. Estos elementos de datos incluyen tablas, entidades de datos y vistas. Los datos se pueden actualizar con los datos entrantes de los documentos electrónicos. Se pueden utilizar diversos objetivos en una sola asignación de modelo.
- Admite parámetros de entrada de usuario que se pueden definir como orígenes de datos para un modelo de datos cuando algunos datos se deben especificar en el runtime.

Se diseña un componente de modelo de datos para cada dominio empresarial que se utiliza como fuente de datos unificada para la generación de informes. La fuente de datos unificada aísla los informes de la implementación física de las fuentes de datos. El componente representa conceptos y funcionalidades de dominio de negocio específicos en un formulario que hace que el diseño inicial del formato y el mantenimiento posterior sean más eficientes.

## <a name="format-component"></a>Componente de formato

### <a name="format-components-for-outgoing-electronic-documents"></a>Componentes del formato para los documentos electrónicos salientes

Un componente de formato es el esquema de la salida de informes que se genera en el runtime. Un esquema consta de los siguientes elementos:

- Un formato que define la estructura y el contenido del documento electrónico saliente que se genera en runtime.
- Orígenes de datos como un conjunto de parámetros de entrada del usuario y un modelo determinado de los datos de dominio que usa la asignación de modelo seleccionado.
- Una asignación de formato como un conjunto de vinculaciones de los orígenes de datos de formato que tienen elementos individuales de formato que especifican, en runtime, el flujo de datos y las reglas de generación de salida de formato.
- Una validación del formato como un conjunto de reglas configurables que controlan la generación de informes en el runtime en función de contexto de ejecución. Por ejemplo, puede haber una regla que detenga la generación de los pagos de proveedor y produzca una excepción cuando falten los atributos específicos del proveedor seleccionado, por ejemplo el número de cuenta bancaria.

Un componente de formato admite las siguientes características:

- Crear una salida de informes como archivos individuales en diversos formatos, como por ejemplo, texto, XML, documentos de Microsoft Word u hojas de cálculo
- Crear de varios archivos por separado y encapsulación de los mismos en archivos zip

Un componente de formato le permite adjuntar archivos específicos que se pueden usar en la salida de informes:

- Libros de Excel que contienen una hoja de cálculo que se puede usar como plantilla para salida en el formato de hoja de cálculo de OPENXML
- Los archivos de word que contienen un documento que se puede usar como plantilla para salida en el formato de documento de Microsoft Word
- Otros archivos que se pueden incorporar en la salida de formato como archivos predefinidos

La ilustración siguiente muestra fluyen los datos para estos formatos.

[![Flujo de datos para componentes de formato entrante.](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Para ejecutar una única configuración del formato de ER para importar datos desde un documento electrónico entrante, debe identificar la asignación deseada de una configuración del formato, así como el punto de la integración de una asignación de modelo. Puede usar la misma asignación y destinos de modelos así como los formatos diferentes para los tipos distintos de documentos de entrada.

## <a name="component-versioning"></a>Control de versiones de componentes

El control de versiones se admite para componentes de ER. El flujo de trabajo siguiente se proporciona para gestionar cambios en los componentes de ER:

1. La versión que se creó originalmente se marca como una versión **Borrador**. Esta versión se puede editar y está disponible para ejecuciones de prueba.
2. La versión **Borrador** puede convertirse en una versión **Completado**. Esta versión se puede utilizar en procesos de informes locales.
3. La versión **Completado** puede convertirse en una versión **Compartido**. Esta versión se publica en Microsoft Dynamics Lifecycle Services (LCS) y puede utilizarse en procesos globales de informes.
4. La versión **Compartido** puede convertirse en una versión **Interrumpida**. Esta versión se puede eliminar.

Las versiones que tienen el estado **Completado** o **Compartido** están disponibles para otro intercambio de datos. En un componente que tiene estos estados se pueden realizar las siguientes acciones:

- El componente se puede serializar en formato XML y exportar como archivo en formato XML.
- El componente puede volver a serializar desde un archivo XML e importar en la aplicación como una nueva versión de un componente de ER.

## <a name="component-date-effectivity"></a>Eficacia de la fecha del componente

Las versiones del componente de ER tienen fecha de vigencia. Puede establecer fecha "Vigente desde" para que un componente de ER especifique la fecha en la que el componente se hace efectivo para procesos de informes. La fecha de sesión de la aplicación se usa para definir si un componente es válido para la ejecución. Si hay más de una versión válida para una fecha específica, la última versión se usa para procesos de informes.

## <a name="component-access"></a>Acceso del componente

El acceso a los componentes del formato ER depende de la configuración del código de país / región de la Organización Internacional de Normalización (ISO). Si esta opción está en blanco para una versión seleccionada de una configuración de formato, se puede obtener acceso a un componente de formato desde cualquier empresa en runtime. Si esta configuración contiene códigos de país o región ISO, un componente de formato solo está disponible desde las empresas que tienen una dirección principal que está definida para uno de los códigos de país o región ISO de un componente de formato.

Diferentes versiones de un componente de formato de datos pueden tener distintos ajustes de los códigos de país o región ISO.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

