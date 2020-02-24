---
title: Búsqueda de formato extendido de informes electrónicos (ER)
description: Este tema describe cómo se puede configurar una referencia de formato ER en la búsqueda de formato ER cuando el formato requerido se almacena en el repositorio Global.
author: NickSelin
manager: AnnBe
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: c72335d7d83934146f827ef0bb568b79a585a7a5
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015381"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>Permitir a los usuarios configurar una referencia de formato ER preguntando un formato desde el repositorio global

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Puede usar el marco de [informes electrónicos](general-electronic-reporting.md) (ER) para configurar [formatos](general-electronic-reporting.md#FormatComponentOutbound) para documentos de salida en función de los requisitos legales de diversos países o regiones. También puede usar el marco ER para configurar [formatos](general-electronic-reporting.md#FormatComponentInbound) para analizar documentos entrantes y usar la información de esos documentos para agregar o actualizar datos de la aplicación. Cada uno de estos formatos puede usarse en su instancia de Dynamics 365 Finance para manejar documentos comerciales entrantes o salientes como parte de un determinado proceso comercial. 

Por lo general, debe especificar qué formato de ER se debe utilizar en un determinado proceso empresarial. Para hacerlo, seleccione un único formato de ER en un campo de búsqueda que esté configurado como parte de los parámetros específicos del proceso empresarial. Estos campos de búsqueda generalmente se implementan utilizando la API apropiada del marco de ER. Para más información, vea [API del marco de ER: código para mostrar una búsqueda de asignación de formato](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

Por ejemplo, cuando configura [parámetros de comercio exterior](https://docs.microsoft.com/dynamics365/finance/localizations/emea-intrastat#set-up-foreign-trade-parameters), debe configurar las referencias a formatos ER individuales que se utilizarán para generar la declaración Intrastat y el informe de control de la declaración Intrastat. Las capturas de pantalla a continuación muestran cómo se ve el campo de búsqueda de formatos ER en la página **Parámetros de comercio exterior**.

Si la instancia actual de Finance no contiene formatos de ER relacionados con el proceso comercial Intrastat, este campo de búsqueda estará vacío.

[![Página Parámetros de comercio exterior](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Si la instancia actual de Finance contiene formatos de ER relacionados con el proceso comercial Intrastat, este campo ofrece los formatos de ER.

[![Página Parámetros de comercio exterior](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

Esta búsqueda ofrece solo los formatos ER que ya se han importado a la instancia actual de Finance. Para [importar](./tasks/er-import-configuration-lifecycle-services.md) soluciones de ER para la instancia actual de Finance, debe tener permisos para ejecutar la función adecuada del marco de ER que admite el [ciclo de vida](general-electronic-reporting-manage-configuration-lifecycle.md) de soluciones de ER que contienen formatos ER.

A partir de la versión 10.0.9 de Finance (versión de abril de 2020), se ha ampliado la interfaz de usuario de la búsqueda de formato ER que se implementa utilizando la API de marco ER. Todavía puede seleccionar los formatos ER existentes, en la ficha desplegable **Seleccionar configuración de formato**. Además de eso, la búsqueda extendida ofrece la nueva opción de buscar en el repositorio global (GR) para localizar formatos ER específicos. Todos los formatos ER del GR se ofrecen en la ficha desplegable **Importar desde el repositorio global**.

[![Página Parámetros de comercio exterior](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

Similar a la ficha desplegable **Seleccionar configuración de formato**, la ficha desplegable **Importar desde el repositorio global** muestra solo los formatos ER que son aplicables al proceso de negocio para el que se selecciona un formato ER en este campo de búsqueda. En este ejemplo, la generación de la declaración Intrastat. El formato ER es aplicable para la compañía en la que el usuario está actualmente conectado, dependiendo del contexto del país de la compañía.

Cuando selecciona un formato ER en la ficha desplegable **Importar desde el repositorio global**, la [configuración](general-electronic-reporting.md#Configuration) del formato ER seleccionado se importa del GR a la instancia actual de Finance.

[![Página Parámetros de comercio exterior](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Luego, si la importación se completa con éxito, la referencia al formato ER importado se almacena en este campo de búsqueda. Tenga en cuenta que cuando accede al GR por primera vez, debe seguir el enlace proporcionado para registrarse en el [Regulatory Configuration Service](https://aka.ms/rcs) (RCS) que se usa para administrar el acceso al almacenamiento GR.

[![Página Parámetros de comercio exterior](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Por defecto, la ficha desplegable **Importar desde el repositorio global** presenta la lista de formatos ER del almacenamiento temporal que se crea automáticamente en función del contenido GR para mejorar el rendimiento. Esto sucede cuando la ficha desplegable **Importar desde el repositorio global** se abre la primera vez, lo que puede llevar varios segundos.

Si no ve el formato ER requerido en la ficha desplegable **Importar desde el repositorio global**, pero está seguro de que este formato ER está almacenado en el GR, seleccione la opción **Sincronizar**. Esto actualizará el almacenamiento temporal y lo sincronizará con el contenido actual del GR.

## <a name="feature-activation"></a>Activación de funciones

La disponibilidad de esta funcionalidad está controlada por la función **Búsqueda extendida de configuraciones de formato ER que permite consultar el repositorio global** en **Administración de características**. De forma predeterminada, esta característica está habilitada.

[![Página Administración de características](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Consideraciones de seguridad

El privilegio **Mantener repositorios de configuración** (**ERMaintainSolutionRepositories**) controla el acceso al GR para un usuario que abre la búsqueda de formato ER con la ficha desplegable **Importar desde el repositorio global** habilitada. Para permitir que los usuarios accedan al contenido GR desde las búsquedas en formato ER, debe cambiar la configuración de seguridad otorgando el privilegio **ERMaintainSolutionRepositories** a los usuarios ya sea directamente o mediante el uso de roles y deberes ya asignados.

La siguiente captura de pantalla muestra cómo se puede otorgar este privilegio a los usuarios asignados al rol **Contable**. Este rol permite a los usuarios configurar parámetros de comercio exterior y establecer referencias a los formatos ER en los campos **Asignación de formato de archivo** y **Asignación de formato de informe** en la página **Parámetros de comercio exterior**.

[![Página Configuración de seguridad](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Limitaciones

El acceso al GR en la búsqueda de formato ER actualmente solo se admite para la selección de formatos ER que se utilizan para generar documentos salientes.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>¿Por qué no puedo acceder al repositorio global desde la búsqueda de formato ER?

Si ha habilitado la característica **Búsqueda extendida de configuraciones de formato ER que permite consultar el repositorio global** en la página **Gestión de funciones** pero los usuarios no pueden ver los formatos ER en la ficha desplegable **Importar desde el repositorio global** y la opción **Sincronizar** está visible pero deshabilitada, asegúrese de que se ha otorgado el privilegio **Mantener repositorios de configuración** (**ERMaintainSolutionRepositories**) al usuario. Póngase en contacto con el administrador del sistema para recibir este privilegio.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [API de marco de informes electrónicos (ER)](er-apis-app73.md)
- [Administrar el ciclo de vida de las configuraciones de los informes electrónicos (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)
