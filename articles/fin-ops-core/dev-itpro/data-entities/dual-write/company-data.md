---
title: Concepto de empresa en Dataverse
description: Este artículo describe la integración de datos de empresa entre finanzas y operaciones y Dataverse.
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: ad0075e2b92ebeb9fba879bcae503100dc7adb47
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9205948"
---
# <a name="company-concept-in-dataverse"></a>Concepto de empresa en Dataverse

[!include [banner](../../includes/banner.md)]




En finanzas y operaciones, el concepto *empresa* es una construcción legal y una construcción empresarial. También es un límite de seguridad y visibilidad para los datos. Los usuarios trabajan siempre en el contexto de una sola empresa y la mayoría de los datos se clasifican por empresa.

Dataverse no tiene un concepto equivalente. El concepto más cercano es *unidad de negocio*, que es un límite principalmente de seguridad y de visibilidad para los datos de usuario. Este concepto no tiene las mismas implicaciones legales o empresariales que el concepto de empresa.

Dado que la unidad de negocio y la empresa no son conceptos equivalentes, no es posible forzar una asignación uno a uno (1: 1) entre ellos para el propósito de la integración de Dataverse. Sin embargo, dado que los usuarios deben, de forma predeterminada, poder ver las mismas filas en la aplicación y Dataverse, Microsoft ha introducido una nueva tabla en Dataverse que se denomina cdm\_Company. Esta tabla es equivalente a la tabla de empresa en la aplicación. Para ayudar a garantizar que la visibilidad de filas es equivalente entre la aplicación y Dataverse de forma inmediata, se recomienda la siguiente configuración para los datos en Dataverse:

+ Para cada fila de empresa de finanzas y operaciones que se habilite para escritura dual, se creará una fila cdm\_Company asociado.

+ Cuando se crea una fila cdm\_Company y se habilita para escritura dual, se crea una unidad de negocio predeterminada con el mismo nombre. Aunque se crea automáticamente un equipo propietario predeterminado para esa unidad de negocio, la unidad de negocio no se utiliza.
+ Se crea un equipo independiente del propietario con el mismo nombre con sufijo de doble escritura. También está asociado con la unidad de negocio.

+ De forma predeterminada, el propietario de cualquier fila que se crea y se escribe de forma dual en Dataverse se establece en el equipo "propietario de DW" vinculado a la unidad de negocio asociada.

En la siguiente ilustración se muestra un ejemplo de esta configuración de datos en Dataverse.

![Configuración de datos en Dataverse.](media/dual-write-company-1.png)

Debido a esta configuración, cualquier fila relacionada con la empresa USMF será propiedad de un equipo que está vinculado a la unidad de negocio de USMF en Dataverse. Por lo tanto, cualquier usuario que tenga acceso a esa unidad de negocio con un rol de seguridad que se establezca en la visibilidad de nivel de unidad de negocio podrá ver dichas filas. El siguiente ejemplo muestra cómo se pueden utilizar los equipos para proporcionar acceso correcto a dichas filas.

+ La función de “director de ventas” se asigna a los miembros del equipo de “ventas de USMF”.
+ Los usuarios con el rol “director de ventas” pueden tener acceso a cualquier fila de la cuenta que sea miembro de la misma unidad de negocio.
+ El equipo de “ventas de USMF" está vinculado a la unidad de negocio de USMF antes mencionada.
+ Por lo tanto, los miembros del equipo de "ventas de USMF" pueden ver cualquier cuenta que sea propiedad del usuario de "USMF DW", que habría llegado de la tabla de la empresa USMF en finanzas y operaciones.

![Cómo se pueden usar los equipos.](media/dual-write-company-2.png)

Como muestra la ilustración anterior, esta asignación 1:1 entre la unidad de negocio, la empresa y el equipo es solo un punto de partida. En este ejemplo, una nueva unidad de negocio “Europa” se crea manualmente en Dataverse como principal para DEMF y ESMF. Esta nueva unidad de negocio raíz no está relacionada con la escritura dual. Sin embargo, se puede usar para dar a los miembros del “equipo de ventas EUR” acceso a los datos de la cuenta en DEMF y ESMF estableciendo la visibilidad de los datos en **BU principal/secundaria** en el rol de seguridad asociado.

Un artículo final a discutir es cómo la escritura dual determina a qué equipo propietario debe asignar las filas. Este comportamiento se controla mediante la columna **Equipo propietario predeterminado** en la fila cdm\_Company. Cuando la fila cdm\_Company está habilitada para la escritura dual, un complemento crea automáticamente la unidad de negocio asociada y el equipo propietario (si no existe ya) y establece la columna **Equipo propietario predeterminado** . El administrador puede cambiar esta columna a un valor distinto. Sin embargo, el administrador no puede desactivar la columna cuando la tabla está habilitada para la escritura dual.

> [!div class="mx-imgBorder"]
![Columna de Equipo propietario predeterminado.](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Fragmentación y arranque de la empresa

La integración de Dataverse aporta paridad a la empresa mediante un identificador de empresa para fragmentar los datos. Como muestra la siguiente ilustración, todas las tablas específicas de la empresa se extienden de modo que tengan una relación muchos a uno (N:1) con la tabla cdm\_Company.

> [!div class="mx-imgBorder"]
![Relación N:1 entre una tabla específica de la empresa y la tabla cdm_Company.](media/dual-write-bootstrapping.png)

+ Para las filas, después de que se agrega y se guarda una empresa, el valor pasa a ser de solo lectura. Por lo tanto, los usuarios deben asegurarse de que se selecciona la empresa correcta.
+ Solo las filas con datos de la empresa son aptos para la escritura dual entre la aplicación y Dataverse.
+ Para los datos existentes de Dataverse, pronto habrá una experiencia de arranque dirigida por el administrador.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Autocompletar el nombre de la empresa en las aplicaciones de involucración del cliente

Hay varias formas de completar automáticamente el nombre de la empresa en las aplicaciones de involucración del cliente.

+ Si es administrador del sistema, puede configurar la empresa predeterminada navegando a **Configuración avanzada > Sistema > Seguridad > Usuarios**. Abra el formulario **Usuario** y, en la sección **Información de la organización**, configure el valor **Empresa predeterminada en formularios**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Establezca la empresa predeterminada en la sección Información de la organización.":::

+ Si tiene acceso de **Escritura** a la tabla **SystemUser** para el nivel **Unidad de negocio**, puede cambiar la empresa predeterminada en cualquier formulario seleccionando una empresa en el menú desplegable **Empresa**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Cambio del nombre de la empresa en una nueva cuenta.":::

+ Si tiene acceso de **Escribir** a los datos en más de una empresa, en ese caso puede cambiar la empresa predeterminada eligiendo una fila que pertenezca a otra empresa.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="La elección de una fila cambia la empresa predeterminada.":::

+ Si es un configurador o administrador del sistema y desea completar automáticamente los datos de la empresa en un formulario personalizado, puede usar [eventos de formulario](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Agregue una referencia de JavaScript a **msdyn_ /DefaultCompany.js** y utilice los siguientes eventos. Puede utilizar cualquier formulario listo para usar, por ejemplo, el formulario **Cuenta**.

    + Evento **OnLoad** para el formulario: establezca la columna **defaultCompany**.
    + Evento **OnChange** para la columna **Empresa**: establezca la columna **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Aplicar filtros basados en el contexto de la empresa

Para aplicar el filtrado basado en el contexto de la empresa en sus formularios personalizados o en las columnas de búsqueda personalizadas agregadas a los formularios estándar, abra el formulario y use la sección **Filtrado de registros relacionados** para aplicar el filtro de empresa. Debe establecer esto para cada columna de búsqueda que requiera filtrado según la empresa subyacente en una fila determinada. El ajuste se muestra para **Cuenta** en la siguiente ilustración.

:::image type="content" source="media/apply-company-context.png" alt-text="Aplicar el contexto de la empresa.":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
