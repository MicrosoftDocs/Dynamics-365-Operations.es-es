---
title: 'Servicios de configuración reglamentaria (RCS): características de globalización'
description: Este tema explica cómo usar los Servicios de configuración regulatoria (RCS) de Microsoft y el repositorio global para crear y usar características de globalización.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: ae46dab5250fbe8096f43e420cb7ef33a5862af0
ms.sourcegitcommit: 97206552616b248f88e516fea08b3f059257e8d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3432056"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Servicios de configuración reglamentaria (RCS): características de globalización

[!include [banner](../includes/banner.md)]

Puede usar los Servicios de configuración regulatoria (RCS) de Microsoft para crear una característica de globalización que se pueda usar en los servicios de globalización, como un servicio de facturación electrónica. RCS le permite realizar estas tareas:

- Definir componentes relacionados de una característica.
- Administre el ciclo de vida de la característica a través del estado de una característica.
- Pong disponible una característica para entornos definidos.
- Comparta una característica con otras organizaciones.

Los siguientes procedimientos explican cómo un usuario en RCS puede agregar una característica de Globalización y componentes relacionados, actualizar el estado de la característica y hacer que la característica esté disponible para que pueda usarse en los servicios de Globalización.

Antes de completar los procedimientos, debe completar los pasos relacionados con las siguientes tareas:

- Acceso a una instancia RCS.
- Creación y activación de un proveedor de configuración. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

En su instancia de aplicaciones Finance and Operations, siga estos pasos.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Si no está aprovisionado ningún entorno RCS en la empresa, seleccione **Regulatory services: Configuración** y luego siga las instrucciones para aprovisionar uno.

> [!NOTE]
> Si ya se ha aprovisionado un entorno RCS para su empresa, use la URL de la página para acceder al entorno, seleccionando la opción de inicio de sesión.

## <a name="turn-on-the-globalization-features"></a>Active las características de globalización

1. En su instancia de RCS, seleccione el mosaico **Gestión de características**.
2. En el espacio de trabajo **Administración de características**, seleccione **Características de globalización** en la lista y luego seleccione **Habilitar ahora**.

    ![Características de globalización en Administración de características](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Características de globalización

Para usar una característica de globalización, primero debe importarla desde el repositorio global y crear su propia versión. Hay dos formas de agregar características de globalización:

- Agregue una característica derivada que se base en una característica existente que ha sido publicada o compartida.
- Agregue una nueva característica que haya creado desde cero.

## <a name="access-globalization-features"></a>Acceder a características de globalización

1. Asegúrese de que la característica **Características de globalización** está activada en Administración de características, como se describió anteriormente en este tema.
2. Abra el nuevo espacio de trabajo **Características de globalización**, y luego, en **Caracteristicas**, seleccione el mosaico **Facturación electrónica**.

    ![Espacio de trabajo Características globales](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    Se abre la página **Funciones de facturación electrónica**.

    ![Página de características de facturación electrónica](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Agregar una característica de globalización derivada

Puede agregar una nueva característica de Globalización derivándola de una característica existente que se ha publicado o compartido.

1. Seleccione **Importar** para abrir la página **Importar característica del repositorio global**.

    ![Importar característica de la página del repositorio global](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. Seleccione **Sincronizar**para obtener las últimas características.

    La lista sincronizada incluye características que están disponibles para usted, ya sea porque fueron publicadas por Microsoft o porque fueron compartidas con usted por otro proveedor de configuración.

    ![Lista sincronizada de características](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. En la lista, seleccione las características para importar y luego seleccione **Importar**. Recibirá un mensaje cuando las características seleccionadas se hayan importado correctamente.

    ![Mensaje de importación correcta](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Seleccione **Añadir** y luego, en el cuadro de diálogo desplegable, seleccione la opción **Basado en la versión existente**.
5. Especifique un nombre y descripción para la característica.
6. En la lista de características disponibles, seleccione la versión base de la característica y luego seleccione **Crear característica**.

    ![Agregar una característica derivada](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    La característica que agregó se crea y tiene un estado de **Borrador**.

    ![Característica derivada que tiene estado Borrador](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Revise los componentes de la característica para determinar si se requieren actualizaciones:

    - Revise las configuraciones, en caso de que necesite personalizar los formatos de informes electrónicos (ER) y su vínculo con asignaciones de formatos para la versión de la característica.
    - Revise la configuración, en caso de que necesite personalizar la pestaña **Acciones**, la pestaña **Reglas de aplicabilidad** o la pestaña **Variables** para la versión de la característica.

8. En la pestaña **Versiones**, seleccione una fecha **Válido desde** e introduzca una descripción si el campo **Descripción** está en blanco.
9. Seleccione **Cambiar Estado** para completar la característica. Las características completas pueden estar disponibles para un entorno específico para que puedan usarse en los servicios de globalización, o pueden publicarse en el repositorio global.

> [!NOTE]
> Las características que tienen un valor de **Estado de la versión de la característica** en **Publicado** se pueden compartir con organizaciones externas.

## <a name="add-a-new-globalization-feature"></a>Agregar una nueva característica de globalización

Puede agregar una nueva característica de Globalización creándola desde cero.

1. En la página **Importar característica del repositorio global**, seleccione **Añadir** y luego, en el cuadro de diálogo desplegable, seleccione la opción **Nueva característica**.
2. Especifique un nombre y descripción para la característica.
3. Seleccione **Crear característica**.

    ![Agregar una nueva característica](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. En la pestaña **Versiones**, seleccione una fecha **Válido desde** y luego seleccione **Cambiar Estado**para completar la característica. Las características completas pueden estar disponibles para un entorno específico para que puedan usarse en los servicios de globalización, o pueden publicarse en el repositorio global.

> [!NOTE]
> Las características que tienen un valor de **Estado de la versión de la característica** en **Publicado** se pueden compartir con organizaciones externas.

## <a name="feature-component-overview"></a>Visión general de componentes de características

Las características de globalización tienen varios componentes:

- **Versión**: este componente admite la gestión del ciclo de vida de la característica y permite a los usuarios administrar el estado de las diferentes versiones de la característica.
- **Configuraciones**: este componente permite a los usuarios administrar, ver y editar formatos ER relacionados y mapeos de formatos.
- **Configuraciones**: este componente permite a los usuarios de servicios de globalización, como un servicio de facturación electrónica, administrar la configuración de la versión de la característica relacionada. Por lo tanto, apoya la construcción flexible de reglas de comunicación y respuestas.
- **Entorno**: este componente permite a los usuarios de los servicios de globalización, como un servicio de facturación electrónica, gestionar el entorno donde se utiliza la configuración de la versión de la característica y otorgar autorización a los usuarios que tendrán acceso a ella.
- **Organizaciones**: este componente permite a los usuarios compartir la característica con organizaciones externas.

## <a name="configuring-feature-components"></a>Configurar componentes de características

### <a name="version-and-status"></a>Estado y versión

La versión se utiliza para administrar el ciclo de vida de la característica de globalización.

El estado se puede cambiar en el campo **Estado**, en la pestaña **Versión**. Los siguientes estados están disponibles:

- **Borrador**: la característica solo se puede editar cuando está en este estado.
- **Completa**: la característica y todos los componentes relacionados se han finalizado (completado) y no se pueden editar.
- **Publicado**: la característica y todos los componentes relacionados se han publicado en el repositorio global.
- **Compartido**: la característica y todos los componentes relacionados se han compartido con organizaciones externas.
- **Habilitado**: la característica y todos los componentes relacionados se han habilitado para su uso en un servicio de globalización, como un servicio de facturación electrónica.

> [!NOTE]
> Las características deben moverse secuencialmente a través de algunos de estos estados. Por lo tanto, no todos los estados pueden estar disponibles en todas las etapas del ciclo de vida.

### <a name="configurations"></a>Configuraciones

Las siguientes acciones están disponibles para configuraciones:

- **Ver**: ver las configuraciones de características subyacentes que no requieren ninguna actualización.
- **Editar**: cree una versión de borrador de una configuración seleccionada para que pueda editar el formato o la asignación de formato en el Diseñador de formatos.
- **Eliminar**: eliminar una configuración seleccionada de la característica.
- **Cambiar**: cambiar la base de la característica. Para obtener más información, consulte la sección [Cambiar la base de características de globalización rerivadas](#rebase), más adelante en este tema.

### <a name="setups"></a>Configuraciones

Las siguientes acciones están disponibles para configuraciones de características:

- **Añadir**: crear una nueva configuración de características. Esta configuración de características puede derivarse de una configuración de características existente o crearse desde cero.
- **Eliminar**: eliminar una configuración de característica seleccionada.
- **Ver**: ver una configuración de características subyacente que no requiere ningún cambio.
- **Editar**: cree, elimine o modifique los atributos de los tres componentes principales de una configuración de características:

    - Acciones y sus parámetros
    - Reglas de aplicabilidad
    - Variables

![Página de configuración de versión de características](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Entornos

Las siguientes acciones están disponibles para entornos:

- **Habilitar**: para una versión de característica seleccionada, seleccione un entorno publicado y seleccione una fecha **Válido desde** en que debería estar disponible. Para obtener más información, consulte la sección [Configurar entornos para habilitación](#configureenvironment), más adelante en este tema.
- **Cancelar**: eliminar un entorno para una configuración de características.

### <a name="organizations"></a>Organizaciones

Siga estos pasos para compartir una característica de globalización con una organización externa.

1. En la página **Funciones de facturación electrónica**, seleccione la característica y la versión de la característica para compartir.
2. En la pestaña **Organizaciones**, seleccione **Compartir con**, y luego, en el cuadro de diálogo desplegable, introduzca el nombre de dominio de la organización.
3. Seleccione **Compartir**.

    ![Compartir una característica con una organización](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

La característica se comparte con la organización seleccionada y está disponible para esa organización en el repositorio global. A partir de ahí, la característica se puede importar a la instancia de RCS de la organización o Dynamics 365 Finance para que pueda usarse.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Cambiar la base de características de globalización derivadas

Puede cambiar la base de una característica de Globalización derivada a la versión de característica base nueva o actualizada. De esta manera, los cambios que se han producido en la versión base se pueden actualizar automáticamente. La versión de la característica base actualizada la crea el proveedor de configuración de origen, y luego se publica o comparte.

![Versión de característica base actualizada](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Por ejemplo, si desea cambiar la base de la versión derivada de una característica que creó, primero debe obtener la última versión de la característica importándola del repositorio global.

1. En la página **Funciones de facturación electrónica**, seleccione **Importar**.
2. Seleccione **Sincronizar**para obtener las últimas características.
3. En la lista de características, seleccione las características para importar y luego seleccione **Importar**.

    ![Importación de la última versión de una característica](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. En la lista de características, seleccione la característica para cambiar de base.
5. En la pestaña **Versión**, seleccione **Nuevo** para crear una versión de borrador.

    ![Nueva versión de borrador creada](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Seleccione **Cambiar de basee**.
7. En el cuadro de diálogo **Cambiar de base**, seleccione la última versión de la característica a cambiar de base.

    ![Cuadro de diálogo Cambiar de base](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Seleccione **Aceptar**.
9. Revise los componentes de la característica y realice los cambios necesarios.
10. Seleccione **Cambiar Estado** para completar la característica cambiada de base. Cuando se completa el cambio de base, puede realizar acciones adicionales. Por ejemplo, puede publicar la característica y ponerla a disposición para su uso en los servicios de globalización.

    ![Estado de la característica actualizado a Completado](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>Configurar entornos para características de globalización

Los usuarios de los servicios de globalización pueden administrar el entorno para configurar una característica de globalización y otorgar autorización a otros usuarios que tendrán acceso a ella.

1. En el espacio de trabajo **Características de globalización**, en **Entornos**, seleccione el mosaico **Facturación electrónica**.

    ![Espacio de trabajo Características de globalización](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Seleccione **Parámetros clave del almacén** y luego seleccione **Nuevo** para crear un almacén de claves de Azure.
3. Introduzca un nombre y una descripción para el almacén de claves y luego, en el campo **URI de almacén de claves**, introduzca la URL que identifica el recurso de almacén de claves en Azure.
4. En la ficha desplegable **Certificados**, seleccione **Añadir** para agregar el certificado e introduzca un nombre y una descripción para cada certificado.

    ![Certificado agregado](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Seleccione **Nuevo** para crear un nuevo entorno.
6. introduzca un nombre, una descripción y el secreto de token de firma de acceso compartido requerido para el almacenamiento.
7. En la ficha desplegable **Usuarios**, seleccione **Nuevo** para agregar un usuario que tendrá permiso para acceder a este entorno.
8. introduzca el id. y la dirección de correo electrónico del usuario.
9. Repita los pasos 7 y 8 para agregar más usuarios.
10. Seleccione **Publicar** para publicar el entorno.

    ![Entorno publicado](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
