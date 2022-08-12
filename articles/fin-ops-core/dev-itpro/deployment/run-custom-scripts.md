---
title: Ejecutar scripts X++ personalizados sin tiempo de inactividad
description: Este artículo describe cómo cargar y ejecutar paquetes desplegables que contienen secuencias de comandos X++ personalizadas sin tener que suspender el sistema.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: aad48fbd3ee2f28f39f6061b5e922f5c4f47c8f6
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103532"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Ejecutar scripts X++ personalizados sin tiempo de inactividad

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Esta función le permite cargar y ejecutar paquetes implementables que contienen scripts X++ personalizados sin tener que pasar por Microsoft Dynamics Lifecycle Services (LCS) o suspender su sistema. Por lo tanto, puede corregir inconsistencias de datos menores sin causar ningún tiempo de inactividad disruptivo.

El beneficio de usar un script X++ para corregir inconsistencias de datos menores es que el sistema ajustará automáticamente todas las tablas relacionadas según sea necesario cuando ejecute el script. Este enfoque ayuda a garantizar la integridad de la corrección y ayuda a minimizar el riesgo de introducir nuevas inconsistencias.

> [!IMPORTANT]
> Esta característica está destinada únicamente a la corrección de inconsistencias de datos menores. No debe ser utilizado para los siguientes propósitos o cualquier otro propósito:
>
> - Recopilación de datos
> - Cambios en los esquemas
> - Migración de datos u otros procesos de ejecución prolongada
> - Corrección de datos que se pueden corregir a través de otros medios, como procesos comerciales regulares, herramientas de consistencia de datos u otras herramientas de autoservicio
>
> La función permite a los usuarios autorizados cambiar entidades y sus registros directamente, sin tener que ejecutar la lógica comercial asociada con esas entidades. Estos cambios pueden causar problemas de integridad de datos. Por lo tanto, su organización puede requerir que obtenga la aprobación y aprobación de los auditores internos y externos (u otras partes interesadas equivalentes) antes y/o después de ejecutar un script. Por motivos de cumplimiento, es posible que los cambios que afecten a algunas características también deban divulgarse en informes externos (como los estados financieros) o informarse a las autoridades gubernamentales. Su organización es la única responsable de cualquier cambio que se realice en sus datos a través de esta función, cualquier aprobación y firma o divulgación de esos cambios y el cumplimiento de las leyes aplicables. Usted asume todos los riesgos de utilizar esta función.

Todos los paquetes implementables que se cargan en el sistema pasan por un flujo de trabajo obligatorio. Como medida de seguridad y para ayudar a garantizar la segregación de funciones, el usuario que sube un paquete desplegable no puede aprobarlo para los siguientes pasos del flujo de trabajo. Otro usuario debe aprobarlo. Sin embargo, una vez que se apruebe el paquete, el usuario que lo cargó podrá completar los pasos restantes.

El sistema requiere que todos los paquetes implementables pasen por una ejecución de prueba. Antes de que se permita que el script se ejecute en datos de producción, un usuario debe validar que la salida sea correcta seleccionando **Aceptar registro de prueba**. Si el resultado no es correcto, el usuario debe marcar el paquete como fallido seleccionando **Abandonar**. En este caso, el script no podrá ejecutarse en datos de producción.

Cada paquete cargado se guarda en el sistema y pasa por un flujo de trabajo definido de eventos. Para cada evento, el sistema mantiene un registro que incluye una marca de tiempo y la identidad de la persona que realizó el evento. De esta forma, el sistema se asegura de que exista un registro de auditoría.

Como muestra la siguiente ilustración, el sistema proporciona detalles sobre cómo se ejecutó cada paquete implementable en X++ y qué entidades se tocaron.

![Página Detalles de script](media/script-details.png "Página Detalles de script")

## <a name="assign-duties-to-users-to-control-access"></a>Asignar deberes a los usuarios para controlar el acceso.

Esta función ofrece los siguientes derechos: Los administradores pueden usar estos derechos para ayudar a controlar el acceso a la función.

- **Mantener scripts personalizados** – Este derecho otorga la capacidad de cargar, probar, verificar y ejecutar scripts X++ personalizados en entornos (pruebas de aceptación del usuario \[UAT\] y producción).
- **Aprobar scripts personalizados** – Este derecho otorga la capacidad de aprobar un script X++ personalizado cargado. La aprobación es un paso obligatorio antes de que cualquier script pueda probarse, verificarse y ejecutarse.

Para ayudar a minimizar el riesgo de acciones maliciosas, cada secuencia de comandos debe ser aprobada explícitamente por un usuario que no sea el usuario que la cargó. Antes de que pueda usar esta función en su organización, un administrador debe asignar las funciones anteriores a al menos dos usuarios relevantes y altamente confiables. Aunque un solo usuario puede tener ambas funciones, ese usuario no podrá aprobar sus propios scripts.

## <a name="create-a-deployable-package"></a>Crear un paquete implementable

La función requiere un paquete desplegable regular que se puede crear en Visual Studio. Para obtener instrucciones, consulte [Crear paquetes implementables de modelos](../deployment/create-apply-deployable-package.md).

Su paquete implementable debe contener exactamente una clase X++ ejecutable. En otras palabras, debe tener una clase que incluya un método que tenga la siguiente firma.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> El nombre del método principal debe estar en minúscula.

## <a name="code-example"></a>Código de ejemplo

El siguiente ejemplo de código muestra cómo se puede estructurar un paquete desplegable.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Prácticas recomendadas

La siguiente lista describe algunas de las mejores prácticas para escribir, implementar y ejecutar correctamente un script. La lista no es exhaustiva y debe considerarse solo una guía.

- **Recomendado**: escriba un mensaje de éxito al final del guión. De esta forma, podrá ver que el script se ejecutó sin excepciones.
- **Recomendado:** agregue el manejo explícito del alcance de la transacción.
- **Recomendado:** utilizar la lógica empresarial existente, como métodos `update()`, pero **no** eludir la lógica empresarial mediante el uso de los métodos `doUpdate()`, `doInsert()` y `doDelete()`. Este enfoque ayudará a garantizar que los datos dependientes se manejen correctamente. También reducirá significativamente el riesgo de más inconsistencias en los datos.
- **Recomendado:** afirmar el contexto de la empresa. Este enfoque expondrá errores comunes a medida que se ejecuta un script. Por ejemplo, revelará si el script se está ejecutando en la empresa equivocada.
- **Recomendado:** afirme que el número de registros afectados coincide con sus expectativas. Este enfoque revelará si los datos cambiaron inesperadamente en el sistema mientras se preparaba el script.
- **Recomendado:** use nombres de clase únicos para cada secuencia de comandos (por ejemplo, al incluir una referencia a un elemento de trabajo en el nombre). Este enfoque evitará problemas de conflicto de nombres cuando cargue el script. Si se requiere una nueva iteración de un script, asegúrese de darle un nuevo nombre.
- **Recomendado:** primero pruebe cada secuencia de comandos en un entorno que no sea de producción. Pruebe el impacto previsto y los efectos secundarios no intencionales en los datos relacionados. Asegúrese de que todos los procesos comerciales que puedan verse afectados puedan completarse exitosa y completamente después.

## <a name="upload-and-run-a-deployable-package"></a>Cargue y ejecute un paquete desplegable

Utilice el siguiente procedimiento para cargar y ejecutar un script.

1. En su aplicación de finanzas y operaciones, vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Guiones personalizados**.
1. Seleccione **Cargar**.
1. Seleccione el paquete desplegable que creó como se describe anteriormente en este artículo. Se le pedirá que especifique el propósito del script.
1. El script ahora debe ser aprobado por un usuario que no sea el usuario que lo cargó. El aprobador debe seguir estos pasos:

    1. Ir a **Administracion del sistema \> Periódico \> Base de datos \> Guiones personalizados**.
    1. Seleccione la secuencia de comandos para aprobar y, a continuación, seleccione **Detalles**.
    1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Inicio**, seleccione **Aprobar** o **Rechazar**. Si selecciona **Aprobar**, el script se marca como aprobado y se desbloquea para realizar pruebas. Si selecciona **Rechazar**, el script está bloqueado. En ambos casos, el evento se registra y se guarda una copia del script en el sistema.

1. El script debe probarse para asegurarse de que hace lo que debe hacer. El probador puede ser el mismo que subió o aprobó, o puede ser un tercer usuario que tenga los permisos requeridos. El probador debe seguir estos pasos:

    1. Ir a **Administracion del sistema \> Periódico \> Base de datos \> Guiones personalizados**.
    1. Seleccione la secuencia de comandos para probar y, a continuación, seleccione **Detalles**.
    1. En el panel Acciones, en la pestaña **Flujo de trabajo de proceso**, en el grupo **Prueba**, seleccione **Ejecutar prueba**. El script se ejecuta dentro de una transacción temporal que el sistema cancelará automáticamente mientras recopila varios registros y declaraciones SQL.
    1. Cuando el script haya terminado de ejecutarse, revise los registros y verifique que los resultados cumplan con sus expectativas. Siga uno de estos pasos:

        - Si está satisfecho con el resultado de la prueba, seleccione **Aceptar registro de prueba** en el grupo **Prueba** en el panel **Flujo de trabajo del proceso** del panel de acciones para permitir que se ejecute el script. El registro de eventos reflejará el hecho de que se probó el script e indicará quién lo probó y cuándo.
        - Si no está satisfecho con el resultado de la prueba, seleccione **Abandonar** en el grupo **Fin** en el panel **Flujo de trabajo del proceso** del panel de acciones para evitar que se ejecute el script. El sistema mantendrá una copia del script junto con un registro de su historial.

1. Cuando esté seguro de que el guión cumple con sus expectativas, seleccione **Ejecutar** en el grupo **Ejecutar** en la pestaña **Flujo de trabajo del proceso** del panel de acciones para ejecutarlo. Este comando hace lo mismo que la ejecución de prueba anterior, pero la transacción se confirmará al final.
1. Una vez que la secuencia de comandos haya terminado de ejecutarse, verifique el resultado y confirme que la secuencia de comandos funcionó según lo previsto. Siga uno de estos pasos:

    - Si está satisfecho con el resultado, seleccione **Propósito resuelto** en el grupo **Fin** en la pestaña **Flujo de trabajo del proceso** del Panel de acciones. El registro de eventos reflejará el hecho de que se ejecutó correctamente el script e indicará quién lo verificó y cuándo. El script se guarda, pero ahora está bloqueado y no se puede volver a ejecutar.
    - Si no está satisfecho con el resultado, seleccione **Propósito no resuelto** en el grupo **Fin** en la pestaña **Flujo de trabajo del proceso** del Panel de acciones. El registro de eventos reflejará el hecho de que el script no cumplió su finalidad prevista e indicará quién lo ejecutó y cuándo. El script se guarda, pero ahora está bloqueado y no se puede volver a ejecutar. Sin embargo, el sistema no deshace automáticamente la acción del script. Es posible que deba escribir, importar y ejecutar un nuevo script para deshacer el efecto que tuvo el script fallido en su sistema.

Su selección en el último paso define el estado final del script. Puedes repetir el proceso según lo requieras.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Cargue y ejecute un paquete desplegable a través de LCS

En lugar de implementar su paquete implementable a través de la interfaz de usuario de su aplicación de finanzas y operaciones, como se describe en la sección anterior, puede cargarlo en LCS y usar el procedimiento normal para implementarlo. Para más información, vea [Instalar paquetes implementables desde la línea de comandos](../deployment/install-deployable-package.md).

Aunque este enfoque tiene menos restricciones, proporciona menos protección contra errores. Además, debido a que requiere un reinicio de todos los servidores, provocará cierto tiempo de inactividad.

