---
title: Migración de tipo de datos de divisa para doble escritura
description: Este tema describe cómo cambiar la cantidad de lugares decimales que admite la escritura dual para las divisas.
author: RamaKrishnamoorthy
ms.date: 04/06/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: eaf0cd931e763f31faa334d5353ae6950ed7ee4f
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782816"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Migración de tipo de datos de divisa para doble escritura

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Puede aumentar el número de lugares decimales admitidos para valores de divisa a un máximo de 10. El límite predeterminado es cuatro decimales. Al aumentar el número de lugares decimales, ayuda a evitar la pérdida de datos cuando utiliza la escritura dual para sincronizar datos. El aumento del número de decimales es un cambio opcional. Para implementarlo, debe solicitar asistencia de Microsoft.

El proceso de cambiar el número de lugares decimales tiene dos pasos:

1. Solicite la migración de Microsoft.
2. Cambiar el número de decimales en Dataverse.

La aplicación Finance and Operations y Dataverse debe admitir el mismo número de decimales en los valores de divisa. De lo contrario, se puede producir una pérdida de datos cuando esta información se sincroniza entre aplicaciones. El proceso de migración reconfigura la forma en que se almacenan los valores de divisa y de tipo de cambio, pero no cambia ningún dato. Una vez completada la migración, se puede aumentar el número de lugares decimales para los códigos de divisa y el precio se puede aumentar, y los datos que los usuarios especifican y ven pueden tener más precisión decimal.

La migración es opcional. Si puede beneficiarse de la compatibilidad para más decimales, le recomendamos que considere la migración. Las organizaciones que no requieren valores con más de cuatro decimales no tienen que migrar.

## <a name="requesting-migration-from-microsoft"></a>Solicitar la migración de Microsoft

El almacenamiento para columnas de divisa existentes en Dataverse no puede admitir más de cuatro decimales. Por lo tanto, durante el proceso de migración, los valores de divisa se copian en nuevas columnas internas en la base de datos. Este proceso ocurre continuamente hasta que se hayan migrado todos los datos. Internamente, al final de la migración, los nuevos tipos de almacenamiento reemplazan a los antiguos, pero los valores de los datos no cambian. Las columnas de divisa pueden admitir hasta 10 decimales. Durante el proceso de migración, Dataverse puede continuar usándose sin interrupción.

Al mismo tiempo, los tipos de cambio se modifican para que admitan hasta 12 decimales en lugar del límite actual de 10. Este cambio es necesario para que el número de decimales sea el mismo en la aplicación Finance and Operations y Dataverse.

La migración no cambia ningún dato. Después de convertir las columnas de divisa y tipo de cambio, los administradores pueden configurar el sistema para usar hasta 10 decimales para las columnas de moneda especificando el número de lugares decimales para cada divisa de transacción y para la fijación de precios.

### <a name="request-a-migration"></a>Solicitar una migración

Para que esta función esté disponible, envíe un correo electrónico a **CDSExpandDecimal@microsoft.com** e incluya la siguiente información:

+ **Asunto:** Solicitud para habilitar la compatibilidad decimal expandida para \<organizationID\>
+ **Cuerpo:** Me gustaría habilitar la compatibilidad decimal expandida para mi organización \<organizationID\>.

Un representante de Microsoft se comunicará con usted dentro de dos o tres días hábiles para los próximos pasos.

Cuando solicite una migración, debe tener en cuenta los siguientes detalles y planificarlos en consecuencia:

+ El tiempo que se requiere para migrar los datos depende de la cantidad de datos en el sistema. La migración de grandes bases de datos puede llevar varios días.
+ El tamaño de la base de datos aumenta temporalmente mientras se ejecuta la migración, porque se necesita espacio adicional para los índices. La mayor parte del espacio adicional se libera cuando se completa la migración.
+ Durante el proceso de migración, si se producen errores que impiden que se complete la migración, el sistema genera alertas al Soporte técnico de Microsoft, para que el personal de Soporte técnico pueda intervenir. Sin embargo, incluso si se producen errores durante la migración, Dataverse permanece totalmente disponible para uso regular.
+ El proceso de migración no es reversible.

## <a name="changing-the-number-of-decimal-places"></a>Cambiar el número de decimales

Una vez completada la migración, Dataverse puede almacenar números con más decimales. Los administradores pueden elegir cuántos decimales se usan para códigos de divisa específicos y para precios. Los usuarios de Microsoft Power Apps, Power BI y Power Automate luego pueden ver y usar números que tienen más decimales.

Para realizar este cambio, debe actualizar la siguiente configuración en Power Apps:

+ **Configuración del sistema: precisión de la divisa para la fijación de precios**: la columnas **Establecer la precisión de la divisa que se usa para fijar precios en todo el sistema** define cómo se comportará la divis para la organización cuando se selecciona **Precisión de precios**.
+ **Gestión empresarial: divisas**: la columna **Precisión de divisa** le permite especificar un número personalizado de decimales para una moneda específica. Hay una reserva en la organización (configuración amplia).

Hay algunas limitaciones:

+ No puede configurar la columnas de divisa en una tabla.
+ Puede especificar más de cuatro decimales solo en los niveles **Precios** y **Divisa de la transacción**.

### <a name="system-settings-currency-precision-for-pricing"></a>Configuración del sistema: precisión de la moneda para la fijación de precios

Una vez completada la migración, los administradores pueden establecer la precisión de la divisa. Vaya a **Configuración \> Administración** y seleccione **Ajustes del sistema**. Luego, en la pestaña **General**, cambie el valor de la columna **Establecer la precisión de la divisa que se usa para fijar precios en todo el sistema**, como se muestra en la siguiente ilustración.

![Configuraciones del sistema para la divisa.](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Administración empresarial: divisas

Si necesita que la precisión de la divisa para una divisa específica difiera de la precisión de la divisa que se usa para fijar el precio, puede cambiarla. Vaya a **Configuraciones \> Administración empresarial**, S¡seleccione **Divisas** y seleccione la divisa que se va a cambiar. Luego configure la columna **Precisión de la divisa** según número de decimales que desee, como se muestra en la siguiente ilustración.

![Configuración de la divisa para un entorno local específico.](media/specific-currency.png)

### <a name="tables-currency-column"></a>tablas: columna Divisa

El número de decimales que se pueden configurar para columnas de divisa específicas está limitado a cuatro.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]