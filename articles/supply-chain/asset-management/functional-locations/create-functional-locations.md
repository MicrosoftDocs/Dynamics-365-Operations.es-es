---
title: Crear ubicaciones técnicas
description: En este tema se explica cómo crear una ubicación técnica en Administración de activos.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationCopyStructure, EntAssetFunctionalLocationCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8bdf8367cb7a54520c671fbc05807b891e0cc45
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813854"
---
# <a name="create-functional-locations"></a>Crear ubicaciones técnicas

[!include [banner](../../includes/banner.md)]

 

En este tema se explica cómo crear una ubicación técnica en Administración de activos.

Al crear una estructura de ubicación técnica tenga en cuenta que, una vez creada, no podrá moverla de la ubicación original. Esto significa que debe estudiar minuciosamente la estructura de sus ubicaciones técnicas antes de empezar a crearlas en Administración de activos. Si se equivoca al crear una ubicación técnica, puede eliminarla siempre que no se haya utilizado aún.

Para poder trabajar con ubicaciones técnica, se crean para empezar dos "categorías" de ubicaciones técnicas:

- Cree *una* ubicación técnica predeterminada sin ubicaciones subordinadas. Esta ubicación técnica sólo se utiliza como la ubicación estándar para activos al crear activos nuevos.  
- Cree las estructuras de ubicación técnica necesarias para administrar los trabajos de mantenimiento en la empresa.

## <a name="create-a-default-functional-location"></a>Crear una ubicaciones técnica predeterminada

Al usar ubicaciones técnicas, empiece por crear la ubicación predeterminada que se utilizará al crear nuevos activos. Esta ubicación técnica es la que se selecciona en **Administración de activos** > **Configurar** > **Parámetros de administración de activos** >  enlace **Activos** > **Ubicación técnica predeterminada**. La ubicación técnica predeterminada se puede utilizar cuando se crean nuevos activos y aún no se ha configurado una estructura ubicación técnica para esos activos.

1. Seleccione **Administración de activos** > **Común** > **Ubicaciones técnicas** > **Todas las ubicaciones técnicas**.  
2. En **Todas las ubicaciones técnicas**, seleccione **Nuevo**.
3. Inserte un identificador en el campo **Ubicación técnica** (por ejemplo, "0000" o "Predeterminado) para indicar que se trata de una ubicación técnica especial.
4. Inserte el nombre de la ubicación técnica predeterminada en el campo **Nombre**.
5. *No* seleccione un artículo principal en el campo **Principal**. Deje este campo en blanco.
6. En el campo **Tipo de ubicación técnica**, seleccione el tipo de ubicación técnica que se utilizará como ubicación técnica predeterminada. Consulte [Tipos de ubicación técnicas](../setup-for-functional-locations/functional-location-types.md) para obtener más información sobre cómo configurar tipos de ubicaciones técnicas.
7. Seleccione **Aceptar**. No debe agregar otros datos a la ubicación técnica, ya que solo se usa como ubicación temporal para los nuevos activos hasta que se hayan instalado en las ubicaciones técnicas utilizadas por la empresa.

## <a name="create-functional-locations"></a>Crear ubicaciones técnicas

El siguiente procedimiento describe cómo se crean las ubicaciones técnicas necesarias para la administración del mantenimiento de la empresa.

1. Seleccione **Administración de activos** > **Común** > **Ubicaciones técnicas** > **Todas las ubicaciones técnicas**. Puede crear una ubicación técnica desde la vista de cuadrícula o desde la vista de detalles.
2. Seleccione el botón **Nuevo**.
3. Inserte un identificador en el campo **Ubicación técnica**.
4. Inserte un nombre para la ubicación técnica en el campo **Nombre**.
5. Si la ubicación técnica es una ubicación subordinada en una estructura, seleccione la ubicación principal en el campo **Principal**.
6. Seleccione un tipo en el campo **Tipo de ubicación técnica**.
7. Seleccione **Aceptar**.
8. Seleccione la ubicación técnica y haga clic en el botón **Editar** para agregar información adicional.

>[!NOTE]
>En función de la configuración de los estados del ciclo de vida de la ubicación técnica, es posible que tenga que crear todas las ubicaciones subordinadas para una ubicación técnica y, a continuación, cambiar el estado del ciclo de vida de la ubicación técnica para poder empezar a instalar activos. Consulte [Instalar activos en ubicaciones técnicas](../functional-locations/install-objects-on-functional-locations.md) para obtener más información sobre la instalación de activos. Consulte [Estados de ciclo de vida de ubicación técnica](../setup-for-functional-locations/functional-location-stages.md) para obtener más información acerca de la configuración de los estados de ciclo de vida de ubicación técnica.

En vista Detalles verá fichas desplegables en las que puede agregar y editar información sobre la ubicación técnica.

## <a name="general-information"></a>Información general

Esta sección proporciona una visión general de la información principal y secundaria en la estructura de la ubicación técnica. En la sección **Detalles** puede ver el número de atributos de activo, planes de mantenimiento y activos relacionados con la ubicación técnica. En la sección **Inventario** puede seleccionar el sitio y el almacén con los que la ubicación técnica está relacionada. El sitio y el almacén se utiliza en relación con las previsiones de artículos de la orden de trabajo. Al crear una previsión de artículos, se usa automáticamente la información de sitio y almacén de la ubicación técnica del activo. En la sección **Estado de ciclo de vida** se muestra información de estado de ciclo de vida de la ubicación técnica.

## <a name="installed-assets"></a>Activos instalados

Consulte [Instalar activos en ubicaciones técnicas](../functional-locations/install-objects-on-functional-locations.md) para obtener más información sobre la instalación de activos. Puede usar el botón **Ver** de esta ficha desplegable para mostrar más campos en la ficha desplegable. Se pueden mostrar los campos **Válido desde** y **Activo secundario** en la cuadrícula.

## <a name="asset-attribute-requirements"></a>Requisitos de atributo de activo

En esta ficha desplegable puede agregar requisitos de atributo específicos para los activos que instale en la ubicación técnica. Estos requisitos se usan solo con fines informativos. No impiden que instale activos con otros requisitos de atributos. Seleccione **Agregar línea** y seleccione el tipo de atributo. A continuación, inserte el **Valor** relevante, seleccione un umbral en el campo **Criterios de umbral** y guarde el registro.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Planes de mantenimiento y rondas de mantenimiento

Aquí puede agregar planes de mantenimiento y rondas de mantenimiento a la ubicación técnica, incluida una fecha inicial. Los activos instalados en una ubicación técnica pueden tener otros planes de mantenimiento configurados. Todos los planes de mantenimiento y rondas de mantenimiento se pueden usar para programar las entradas de calendario de activos para una ubicación técnica y los activos instalados actualmente.

>[!NOTE]
>Si actualiza la configuración de los tipos de activos, las marcas de activos y los modelos de activos en los planes de mantenimiento de la vista de detalles **Todas las ubicaciones técnicas** > ficha de desplegable **Planes de mantenimiento** después de haber programado planes de mantenimiento, las entradas actuales de programación de mantenimiento relacionadas con esa ubicación técnica se eliminarán automáticamente. Para crear nuevas entradas de programación que se correspondan con la configuración del plan de mantenimiento actualizado en la ubicación técnica, debe ejecutar una nueva programación del plan de mantenimiento para dicha ubicación técnica. 

## <a name="address"></a>Dirección

Inserte la dirección de la ubicación técnica en la ficha desplegable **Dirección**. Las direcciones de las ubicaciones técnicas se heredan. Es decir, si una ubicación subordinada no tiene una dirección definida, se utilizará la dirección de la ubicación principal.

## <a name="workers"></a>Trabajadores

En esta ficha desplegable puede agregar trabajadores afiliados a la ubicación técnica, y puede seleccionar una ubicación técnica como la principal del trabajador. 

## <a name="attributes"></a>Atributos

En esta ficha desplegable puede establecer valores para los atributos de la ubicación técnica. Estos atributos se pueden utilizar para describir propiedades o características relacionadas con la ubicación técnica, como propiedades estructurales, el tipo de construcción, descripciones de área, o la ubicación por encima o por debajo del suelo.

Seleccione **Agregar línea** y seleccione el tipo de atributo. A continuación, inserta el **Valor** relacionado con el tipo de atributo y guarde el registro.

## <a name="financial-dimensions"></a>Dimensiones financieras

Puede seleccionar dimensiones financieras para la ubicación técnica. Los [Tipos de ubicaciones técnicas](../setup-for-functional-locations/functional-location-types.md) puede configurarse para permitir la actualización automática de dimensiones financieras desde una ubicación técnica. Esto significa que los activos instalados en una dimensión financiera recibirán automáticamente las dimensiones financieras para la ubicación técnica. Esto resulta útil si se desea utilizar centros de coste diferentes, en función de la ubicación.

Cuando se actualizan los datos relativos a **Sitio**, **Almacén**, **Dirección** y **Dimensiones financieras** en una ubicación técnica principal, se pueden actualizar las ubicaciones técnicas subordinadas relacionadas si elige hacerlo durante la actualización. Se abre un cuadro de diálogo que muestra las opciones de actualización.

## <a name="copy-a-functional-location-structure"></a>Copiar una estructura de ubicación técnica

Si su empresa tiene varias ubicaciones técnicas con estructuras de ubicación similares, puede usar la función de copia de Administración de activos para crear rápidamente varias jerarquías de ubicación similares. Al copiar una ubicación técnica específica o una estructura completa, la nueva ubicación o estructura tendrá el mismo nombre que la copiada. Una vez completado el procedimiento de copia, puede cambiar fácilmente el nombre u otros valores de configuración en la nueva ubicación técnica, siempre que lo permita el estado de ciclo de vida de ubicación técnica seleccionado para la nueva ubicación técnica.

1. En **Todas las ubicaciones técnicas**, seleccione la ubicación técnica que desea copiar. Por ejemplo, debe seleccionar una ubicación superior (principal) si desea copiar la estructura completa de la ubicación técnica, incluidas las ubicaciones subordinadas.
2. Seleccione el botón **Copiar estructura de ubicación técnica**. La ubicación seleccionada en la página de lista se muestra en el campo **Copiar de**.
3. Inserte el nombre de la nueva ubicación en el campo **Nueva ubicación técnica**.
4. En el campo **Elemento principal que se va a pegar bajo** debe insertar un identificador principal únicamente si la ubicación que está creando debe formar parte de una estructura de ubicación técnica existente.
5. Haga clic en **Aceptar**. La nueva estructura de ubicación técnica se muestra en **Todas las ubicaciones técnicas**.

>[!NOTE]
>Al copiar una estructura de ubicación técnica, se establecen los estados de ciclo de vida de ubicación técnica de la nueva estructura en el primer "estado" creado para ubicaciones técnicas. Podrá cambiar el nombre de una ubicación técnica o eliminar mediante los botones **Cambiar nombre** y **Eliminar** en **Todas las ubicaciones técnicas** en función del estado de ciclo de vida actual de la ubicación técnica.

## <a name="delete-a-functional-location"></a>Eliminar una ubicación técnica

Se puede eliminar una ubicación técnica con ubicaciones subordinadas relacionadas si no se ha instalado ningún activo en ninguna de las ubicaciones técnicas que intenta eliminar, y si el estado de ciclo de vida actual de la ubicación técnica lo permite.

1. En **Todas las ubicaciones técnicas**, seleccione la ubicación técnica que desea eliminar.
2. Si es necesario, actualice la ubicación técnica con un estado de ciclo de vida de ubicación técnica que permita la eliminación de una ubicación técnica.
3. Seleccione **Eliminar**.

>[!NOTE]
>Si no puede eliminar una ubicación técnica, en su lugar puede controlar la eliminación configurando un estado de ciclo de vida de ubicación técnica con este propósito. Por ejemplo, puede configurar una etapa "Desechado" o "Eliminado" (que no debe ser una etapa activa) en el formulario **Estados de ciclo de vida de ubicación técnica**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]