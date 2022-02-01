---
title: Información general de la administración de características
description: Este tema describe la función de Administración de características y cómo puede utilizarla.
author: Peakerbl
ms.date: 01/10/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 6605fe68576ce80726438b60c1f1fbf3782d0934
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984468"
---
# <a name="feature-management-overview"></a>Información general de la administración de características

[!include [banner](../../includes/banner.md)]

Las características se suman y se actualizan en cada versión. La experiencia de administración de la característica proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión. A continuación, puede utilizar el espacio de trabajo para ver la documentación de las funciones y habilitar o deshabilitar funciones.

## <a name="the-feature-management-workspace"></a>El espacio de trabajo Administración de características.

Puede abrir el espacio de trabajo **Administración de características** seleccionando el mosaico adecuado en el panel de información. Verá una página que muestra una lista de características para todos las versiones que son compatibles con la experiencia de Administración de características. 

La lista de características incluye la información siguiente:

- **Nombre de la característica** - Una descripción de la función que se ha agregado.
- **Estado** - Un símbolo indica si una característica está activada (marca de verificación), no está activada (en blanco), se ha programado para ser activada (reloj), es obligatoria (candado), requiere atención antes de activarla (símbolo de advertencia) o no se puede activar (X). El valor que se muestra se usa para todas las entidades jurídicas. Tenga en cuenta que incluso cuando se ha activado, una característica aún se controla mediante la seguridad. Por lo tanto, la característica sólo estará disponible para los usuarios que tengan acceso a ella, en función de su rol de seguridad. También estará disponible solo en las entidades jurídicas a las que tiene acceso el usuario.
- **Fecha de habilitación** - La fecha en que la característica se ha activado o está programado que lo haga.
- **Característica agregada** - La fecha en que la característica se ha agregado al entorno. Esta fecha se introduce automáticamente durante la actualización del entorno durante los ciclos de lanzamiento mensuales.
- **Estado de la característica** - El estado actual del ciclo de vida de la característica: **Vista previa**, **Publicada** (se muestra en blanco), **Activada por defecto** y **Obligatoria**. Los estados se tratan con más detalles más adelante en este tema. 
- **Módulo** - El módulo afectado por la nueva característica.

> [!NOTE]
> LLa columna **Estado de la característica** se incluye a partir de la versión 10.0.21.

Al seleccionar una característica, más información aparece en el panel de información a la derecha de la lista de la función. En la parte superior del panel podrá ver el nombre de la función, la fecha en la que la característica se ha agregado, el módulo afectado por la función, y un vínculo a **Más información** . Seleccione este vínculo para ver la documentación para la característica. Si la documentación no está disponible, le llevarán a una página temporal. El panel de detalles también incluye un campo **Comentarios** donde puede agregar sus propios comentarios acerca de la característica.

El espacio de trabajo **Administración de características** también tiene varias pestañas y cada una muestra una lista de funciones de ella.

- **Nuevo** - Esta pestaña muestra todas las características que se han agregado desde la última actualización de mensual. Si ha omitido cualquier actualización mensual, la ficha muestra todas las nuevas características que se han agregado desde la última vez que se actualizó. Las características más nuevas aparecen en la parte superior de la lista. El número total de nuevas características también se muestra en un mosaico en la parte superior de la página.
- **No habilitado** - La ficha muestra todas las funciones que no se han activado. Las características más nuevas aparecen en la parte superior de la lista. Además, un mosaico en la parte superior de la página muestra el número total de funciones nuevas que están actualmente desactivadas.
- **Programado** - Esta pestaña muestra todas las características que se han programado para ser habilitadas en el futuro. Las características que tienen la fecha programada más próxima aparecen en la parte superior de la lista. También se muestra en un mosaico en la parte superior de la página que muestra el número total de las funciones programadas.
- **Todas** - La ficha muestra todas las funciones. Las características más nuevas aparecen en la parte superior de la lista.

## <a name="feature-states"></a>Estados de características
Las funciones pueden pasarde unos estados a otros, desde introducirse en la gestión de funciones hasta que eventualmente se vuelven obligatorias en el producto. Esta sección describe los estados válidos de las funciones.

### <a name="preview-features-optional"></a>Características en vista previa (opcional)

Los equipos de productos pueden decidir iniciar al principio una nueva característica como una característica en vista previa. Las características en vista previa no están habilitadas de forma predeterminada y son opcionales. El equipo del productos propietario actualizará las funciones a publicadas después de que hayan completado un período de vista previa exitoso.

> [!NOTE]
> Las características en vista previa están sujetas a una vista previa específica [Términos y condiciones](https://go.microsoft.com/fwlink/?linkid=2105274). 

### <a name="released-features-optional"></a>Funciones publicadas (opcional)

La columna **Estado de la función** de estas funciones está en blanco. Las funciones que se agregan inicialmente como publicadas no están activadas de forma predeterminada y habilitarlas es opcional. Las funciones que se actualizan desde la vista previa mantendrán su estado de habilitación.

### <a name="on-by-default-features-optional"></a>Características activadas por defecto (opcional)

Funciones que se actualizan a **Activada por defecto** están activadas de forma predeterminada, pero se pueden desactivar. Después de que las funciones que se pueden deshabilitar hayan estado en el estado **Publicado** durante al menos seis meses, se espera que se trasladen a este estado en la próxima versión importante. Se espera que las aracterísticas que hacen la transición a **Activada por defecto** se comuniquen en el tema [Novedades](../whats-new-changed.md) para el lanzamiento. La actualización la inicia el equipo de producto propietario.

> [!NOTE]
> Debido a que estas funciones se habilitarán automáticamente, es importante que determine si su organización está lista para adoptar estas funciones o si se requiere más tiempo. Si se requiere más tiempo, puede que sea necesario deshabilitar temporalmente estas funciones. Tenga en cuenta que la transición de una función a **Activado de forma predeterminada** se realiza normalmente en la versión principal antes de que la función esté destinada a convertirse en **Obligatoria**. En ese momento, no tendrá la opción de deshabilitar la función. 

### <a name="mandatory"></a>Obligatoria

**Obligatoria** es el estado final esperado de las características. Indica que las funciones están activadas y que no puede desactivarlas sin ponerse en contacto con Microsoft. Se espera que las características opcionales sean obligatorias después de dos versiones principales. Las características críticas pueden, por excepción, introducirse como obligatorias.

## <a name="example-of-expected-feature-lifecycles"></a>Ejemplo de ciclos de vida esperados de características

Se espera que las funciones que se pueden deshabilitar y que se agregaron como publicadas y opcionales antes o como parte de la versión de abril pasen a **Activada de forma predeterminada** en el siguiente lanzamiento de octubre. Se espera que se conviertan en **Obligatoria** en abril del año siguiente.

Se espera que las funciones que no se pueden deshabilitar y que se agregaron como publicadas y opcionales antes o como parte de la versión de abril pasen a **Obligatoria** en abril del año siguiente.

## <a name="enable-a-feature"></a>Habilitar una característica

Si una característica no se ha activado, un botón **Habilitar ahora** aparece en el panel de detalles. Puede usar este botón para habilitar la característica.

Algunas funciones no se pueden deshabilitar tras habilitarlas. Si la función que intenta activar no se puede activar, se mostrará una advertencia. En este punto, puede seleccionar **Cancelar** para cancelar la operación y para dejar la característica deshabilitada. Sin embargo, si se selecciona **Habilitar** para habilitar la característica, no podrá deshabilitarla posteriormente.

Algunas funciones mostrarán un mensaje con información adicional antes de activarlas. Estas funciones están marcadas con un símbolo amarillo de advertencia. Debe leer la información adicional cuidadosamente para averiguar qué sucederá cuando se habilite la función. No obstante, aún podrá seleccionar **Habilitar** para activar la función.

Algunas funciones mostrarán un mensaje de que la característica no puede habilitarse hasta que se tomen medidas. Estas funciones se indican con un símbolo de una X roja. Debe realizar los pasos que se describen en la descripción antes de que se habilite la función. Por ejemplo, si no puede usar una característica hasta que se deshabilite una clave de configuración, debe deshabilitar la clave de configuración primero y después volver a la administración de características para habilitar la función.

Después de que se habilite una característica, aparece un mensaje bajo el vínculo **Más información** en el panel de detalles. Este mensaje confirma que la característica se ha activado o indica la fecha futura en la que está programada que se active. Aparecerá cada vez que seleccione la característica en la lista de la función.

Las características programadas para activarse en el futuro aparecen en la pestaña **Programado**. Un proceso por lotes las activará a medianoche en la fecha especificada, en función de la zona horaria que se representa por la fecha del sistema.

## <a name="reschedule-a-feature"></a>Reprogramar una característica

Si una característica se ha programado para activarse en el futuro, un botón **Programar** aparece en el panel de detalles. Puede usar este botón para cambiar el valor de **Fecha de habilitación** a otra distinta.

1. Seleccione la característica programada que desea reprogramar y, a continuación, en el panel de detalles, seleccione **Programar**.
2. En el cuadro de diálogo que aparece, en el campo **Fecha de habilitación**, especifique la nueva fecha en que la característica se debe activar.
3. Seleccione **Habilitar** para volver a programar la característica o **Deshabilitar** para cancelar la programación.

## <a name="disable-a-feature"></a>Deshabilitar una característica

Si una característica se ha habilitado, un botón **Deshabilitar** aparece en el panel de detalles. Puede usar este botón para deshabilitar la característica. El botón **Deshabilitar** no está disponible si la característica no se puede deshabilitar. 

Después de que se deshabilite una característica, aparece un mensaje bajo el vínculo **Más información** en el panel de detalles. Este mensaje afirma que la característica no se ha activado. Aparecerá cada vez que seleccione la característica en la lista de la función. Las funciones que no se han activado aparecen en la pestaña **No activado**.

## <a name="features-that-must-be-enabled"></a>Características que deben habilitarse

A veces se lanza una característica crítica que se activará automáticamente cuando se actualice. Estas características se activan automáticamente en la fecha especificada en el campo **Fecha de habilitación**. Para estas características, aparece un mensaje bajo el vínculo **Más información** en el panel de detalles. Este mensaje confirma que la característica se ha activado o indica cuándo lo hará en el futuro. Aparecerá cada vez que seleccione la característica en la lista de la función.

## <a name="enable-all-features"></a>Habilitar todas las características

Puede habilitar todas las funciones seleccionando el botón **Habilitar todo**. 

Cuando selecciona **Habilitar todo**, aparece una opción donde debe proporcionar la siguiente información:

- Una lista de todas las características que requieren confirmación antes de que puedan habilitarse. Si desea habilitar las características de la lista, seleccione **Sí** para el botón **Habilitar las características que requieren confirmación**.
- Se mostrará una lista de todas las características que no se pueden habilitar. Estas características no se habilitarán.

Todas las funciones que se pueden habilitar se habilitarán. Si una característica ya está programada para ser habilitada en el futuro, la programación no cambiará. 

## <a name="enable-all-features-automatically"></a>Activar todas las funciones automáticamente

Si se desea activar automáticamente todas las nuevas características, puede usar la lista desplegable bajo al título del espacio de trabajo para cambiar qué ocurre cuando se agregan las nuevas características.

- Seleccione **Habilitar nuevas características automáticamente** para activar automáticamente todas las nuevas características cuando se añaden al entorno.
- Seleccione **No habilitar nuevas características automáticamente** si todas las nuevas características aplicables deberían estar desactivadas de forma predeterminada cuando se añadan al entorno.

Si habilita todas las características automáticamente, se habilitan todas las funciones que se habilitarían al hacer clic en el botón **Habilitar todo**. No se habilitarán las características que requieren confirmación o las características que no se pueden habilitar hasta que se tomen medidas.

## <a name="check-for-updates"></a>Buscar actualizaciones

Las características se agregan al entorno después de cada actualización. Sin embargo, puede comprobar manualmente la existencia de actualizaciones haciendo clic en el botón **Buscar actualizaciones**. Cualquier función que fuera agregada al sistema tras la actualización se agregará a la lista de características. Por ejemplo, si se habilita una característica por tramos después de una versión, puede comprobar la existencia de actualizaciones y la función se agregará a la lista.

## <a name="assigning-roles"></a>Asignar roles

El espacio de trabajo **Administración de características** lo pueden abrir administraciones del sistema, y también usuarios que están asignados a roles de Administrador de características o Visores de características. Estos dos roles fueron creados para dar soporte a la experiencia de administración de características. Los usuarios del rol de Administrador de características pueden activar o desactivar cualquier característica. También pueden actualizar el campo **Comentarios** para la característica. Los usuarios en el rol de Visor de características solo pueden ver el espacio de trabajo **Administración de características** . No pueden activar o desactivar las características.

El rol de Administrador de características y el de Visor de características no anulan la seguridad existente que tiene un usuario. Simplemente controlan si el usuario puede activar y desactivar características. No proporciona acceso a las características en sí.

## <a name="features-that-use-configuration-keys"></a>Características que usan claves de configuración

Si una característica usa una clave de configuración, pero la clave de configuración no está activada, el espacio de trabajo **Administración de características** no muestra la función en la lista de características disponibles. Tras activar o desactivar la clave de configuración, debe actualizar la característica mediante el elemento de menú **Buscar actualización**. La característica aparece entonces en la lista de características.

Si desactiva la clave de configuración, la característica no se elimina de la lista de características.

## <a name="data-entities"></a>Entidades de datos

Una entidad de datos que se llama **Administración de las características** le permite exportar la configuración de la gestión de la característica desde un entorno y después importarla en otro entorno. Esta entidad solo actualiza características existentes. La lógica de negocios en la entidad también ayuda a garantizar que las mismas reglas que se usan en el espacio de trabajo **Administración de características** se aplicarán cuando se realiza la importación. Por ejemplo, no puede invalidar un valor obligatorio de la característica quitando la fecha durante la importación.

Los ejemplos siguientes describen lo que ocurre cuando utilice la entidad **Administración de características** para importar datos.

- Si cambia el valor del campo **Habilitado** a **Sí** la característica está activa y el campo **Fecha de habilitación** se establece en la fecha actual.
- Si cambia el valor del campo **Habilitado** a **No** o deja el campo **Fecha de habilitación** en blanco, la característica está desactivada y el campo **Fecha de habilitación** queda vacío. No puede desactivar una característica obligatoria o una función que no se puede desactivar después de que se haya activado.
- Si cambia el valor del campo **EnableDate** a una fecha futura, la característica se programa para esa fecha.
- Si cambia el valor del campo **Habilitado** a **Sí** y cambia el valor del campo **EnableDate** a una fecha futura, la característica se programa para esa fecha. 
- Si cambia el valor del campo **Habilitado** a **No** pero también cambia el valor del campo **EnableDate** a una fecha futura, la característica se programa para esa fecha.
- Si una característica está activada y se agrega un campo **EnableDate** que se establece en una fecha futura, la característica continuará activada. Para reprogramar la característica, debe cambiar el valor del campo **Habilitado** a **No**.

## <a name="feature-management-and-flighting"></a>Administración de características y distribución de paquetes piloto

La Administración de características le permite controlar las características que se añaden en cada versión. La distribución de paquetes piloto permite a los Microsoft Teams presentar características a un número limitado de clientes para poder ser probadas y validarlas las características sin afectar a todos los clientes. La Administración de características no controla la distribución de paquetes piloto de cualquier característica.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Usar la Administración de características para activar las características de ISV o las personalizadas

La administración de características no está actualmente disponible para las características de los fabricantes de software independientes (ISVs) y las características personalizadas. Sin embargo, Microsoft está añadiendo más funcionalidad para ampliar la administración de características. Después de que las mejoras hayan finalizado, Microsoft configurará la administración de características para todas las características y proporcionará instrucciones para actualizar sus características para usarla.

## <a name="frequently-asked-questions-faq"></a>Preguntas frecuentes

### <a name="when-are-features-added-removed-or-changed"></a>¿Cuándo se agregan, quitan o cambian características? 
Los equipos de producto propietarios son los que agregan, eliminan y cambian las características mediante cambios en el código. Los entornos deben actualizarse para recibir esos cambios.

### <a name="does-a-feature-become-mandatory-automatically"></a>¿Una característica se vuelve obligatoria automáticamente? 
No, una característica no se vuelve obligatoria automáticamente. El equipo de producto propietario necesita hacer un cambio de código.

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>¿Por qué no hay una "fecha habilitada obligatoria" específica? 
El tiempo de actualización es variable, el tiempo de actualización del entorno es variable y los clientes pueden optar por omitir algunas actualizaciones. Como resultado, las fechas específicas son difíciles de determinar. 

### <a name="wheres-the-documentation-for-features-that-are-mandatory"></a>¿Dónde está la documentación de las características que son obligatorias? 
Esta documentación proviene de cada equipo de aplicación de Dynamics 365. A menudo, estas características se mencionarán en [Actualizaciones de los estados de las funciones del cliente](/dynamics365-release-plan/2021wave1/finance-operations/finance-operations-crossapp-capabilities/updates-client-feature-states) o [Funciones eliminadas o en desuso](../../../dev-itpro/migration-upgrade/deprecated-features.md). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>¿Hay una notificación en el producto o una señal de que una característica será obligatoriamente habilitada? 
Hoy en día no existe un mecanismo de notificación relacionado con hacer que una característica sea obligatoria.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>¿Se habilitan las características sin que el cliente lo sepa? 
Sí, las funciones se pueden habilitar sin el conocimiento del cliente en las siguientes situaciones:
- Una característica se mueve a **Activada por defecto**. En este estado, la función aún se puede deshabilitar. 
- Una función se actualiza a **Obligatoria**. Este cambio solo se producirá en combinación con una versión principal. Las características críticas podrían, por excepción, moverse a **Obligatoria** en cualquier actualización.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>¿Qué es el paquete piloto de características y cómo se relaciona con la gestión de características? 
Los paquetes piloto de características son interruptores de encendido y apagado en tiempo real que controla Microsoft. Están fuera del control del cliente que proporciona Feature Management. 
- Las características de versión preliminar privada no aparecerán en Feature Management hasta que se activen en el paquete piloto. En el entorno de producción, el cliente debe aceptar ser parte de un programa especial para que eso se produzca.
- Las características de versión preliminar pública (generalmente disponibles) se enumerarán en Feature Management a menos que estén desactivadas. Desactivar una característica del paquete piloto se considera una opción de último recurso para los equipos de productos si se encuentra un problema crítico y, por lo general, sería una operación por cliente.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>¿Se deshabilitan características del paquete piloto sin que el cliente lo sepa? 
Sí, si una característica está afectando al funcionamiento de un entorno que no tiene un impacto funcional, entonces se pueden habilitar de forma predeterminada.

### <a name="how-can-feature-enablement-be-checked-in-code"></a>¿Cómo se puede verificar la habilitación de funciones en el código?
Utilice el método **isFeatureEnabled** en la clase **FeatureStateProvider**, pasándole una instancia de la clase de entidad. Ejemplo: 

```xpp
if (FeatureStateProvider::isFeatureEnabled(BatchContentionPreventionFeature::instance()))
```

### <a name="how-can-feature-enablement-be-checked-in-metadata"></a>¿Cómo se puede verificar la habilitación de funciones en los metadatos?
La propiedad **FeatureClass** se puede utilizar para indicar que algunos metadatos están asociados con una característica. Se debe usar el nombre de clase utilizado para la característica, como **BatchContentionPreventionFeature**. Estos metadatos son visibles solo en esa función. La propiedad **Clase característica** está disponible en menús, elementos de menú, valores de enumeración y campos de tabla / vista.

### <a name="what-is-a-feature-class"></a>¿Qué es una clase de entidad?
Las funciones en la Gestión de funciones se definen como *clases de entidades*. Una clase de entidad **implementa IFeatureMetadata** y utiliza el atributo de clase de entidad para identificarse en el espacio de trabajo de Gestión de entidades. Hay numerosos ejemplos de clases de entidad disponibles que se pueden verificar para su habilitación en el código usando la API **FeatureStateProvider** y en metadatos usando la propiedad **FeatureClass**. Ejemplo: 

```xpp
[ExportAttribute(identifierStr(Microsoft.Dynamics.ApplicationPlatform.FeatureExposure.IFeatureMetadata))]
internal final class BankCurrencyRevalGlobalEnableFeature implements IFeatureMetadata
```

### <a name="what-is-the-ifeaturelifecycle-implemented-by-some-feature-classes"></a>¿Qué es el IFeatureLifecycle implementado por algunas clases de entidad?
IFeatureLifecycle es un mecanismo interno de Microsoft para indicar la etapa del ciclo de vida de la característica. Las características pueden ser:
- `PrivatePreview`: necesita que se lance como paquete piloto para ser visible.
- `PublicPreview`: se muestra de forma predeterminada, pero con una advertencia de que la función está en vista previa.
- `Released`: completamente publicada.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
