---
title: Consolidaciones financieras en línea
description: Este artículo describe las consolidaciones financieras en línea en contabilidad general.
author: aprilolson
ms.date: 12/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 5843ac78adf32e738d9882c7f4e9e04a79200700
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838289"
---
# <a name="online-financial-consolidations"></a>Consolidaciones financieras en línea

[!include [banner](../includes/banner.md)]

Este artículo describe las consolidaciones financieras en línea en contabilidad general. Antes de leer este artículo, lea el artículo [Visión general de las consolidaciones financieras y la conversión de divisas](financial-consolidations-currency-translation.md).

Una vez completada la configuración, especifique los detalles de la consolidación en la página **Consolidar [En línea]**. Cuando haya terminado, puede hacer clic en **Aceptar** o en **Lote** para procesar la consolidación.

## <a name="criteria"></a>Criterios
En la pestaña **Criterios** de la página **Consolidar [En línea]**, se definen las cuentas, los períodos, y el tipo de información que se está consolidando.

![Pestaña Criterios.](./media/criteria-consolidate-online.png "Pestaña Criterios")

Esta es una explicación de los diversos campos de esta pestaña:

- **Descripción** Permite especificar una descripción precisa del período que está consolidando.
- **Cuenta principal** Use los campos de esta sección para definir las cuentas principales que se procesarán.

    - **De** y **A** permite especificar un intervalo de cuentas para procesarlas. Si deja estos campos en blanco, todas las cuentas de todas las empresas se moverán a la empresa de consolidación. Por lo tanto, si está consolidando cuatro empresas, y cada empresa tiene un plan contable diferente, todas las cuentas de las cuatro empresas se crearán en la empresa de consolidación.
    - **Cuenta de consolidación** Si se establece esta opción en **Sí**, el campo **Seleccionar cuenta de consolidación de** pasa a estar disponible. En este campo, seleccione si todas las cuentas deben consolidarse en la cuenta de la consolidación que está establecida en la página **Cuentas principales**, o a si desea seleccionar la cuenta en uno de los grupos de cuentas de consolidación.
    - **Grupo de cuentas de consolidación** Seleccione el grupo que se debe utilizar para la asignación de la cuenta principal para la consolidación.

- **Período de consolidación** Use los campos de esta sección para definir el período de consolidación.

    - **De** y **A** permite especificar un intervalo de fechas para la consolidación. Si deja estos campos en blanco, la consolidación se procesará para todos los períodos definidos en el calendario de contabilidad para la empresa. No recomendamos que deje este campo en blanco.
    - **Seleccionar importe de consolidación de**: utilice este campo para especificar si se utilizarán los importes de moneda de contabilidad o los importes de moneda de informes de las empresas de origen para actualizar los importes de moneda de contabilidad de la empresa de consolidación.

        - Seleccione **Moneda de contabilidad** para utilizar los importes de divisa de contabilidad de las empresas de origen para actualizar los importes de divisa de contabilidad en la empresa de consolidación. Cuando se seleccione este valor, use el campo **Consolidar moneda contable** para definir cómo se calcularán las monedas contables en la compañía de consolidación.
        - Seleccione **Moneda de informe** para utilizar los importes de moneda de informe de las empresas de origen para calcular los importes de moneda de contabilidad en la empresa de consolidación.

            - Si la moneda de informe de la empresa de origen es la misma que la moneda de contabilidad de la empresa de consolidación, los importes de la moneda de informe se copian de la empresa de origen a la empresa de consolidación.
            - Si la moneda de informes de la empresa de origen difiere de la moneda de contabilidad de la empresa de consolidación, los valores se convierten utilizando la información de cambio definida en la pestaña **Conversión de moneda** de esta página para calcular los valores de la empresa de consolidación.

    - **Moneda de contabilidad consolidada**: este campo está disponible solo si el campo **Seleccionar monto de consolidación de** está establecido en **Moneda de contabilidad**. Úselo para especificar si los importes de moneda de contabilidad de las empresas de origen se convierten mediante tipos de cambio o se copian en la empresa de consolidación. Seleccione **Usar conversión de moneda** para usar la información de tipo de cambio definida en la pestaña **Conversión de moneda** para calcular la contabilidad de consolidación saldos Seleccione **Usar monto de moneda de contabilidad** para copiar los montos de moneda de contabilidad de las empresas de origen a la empresa de consolidación.

        - Si la moneda contable de la empresa de origen es la misma que la moneda de contabilidad de la empresa de consolidación, los importes de la moneda se copian de la empresa de origen a la empresa de consolidación.
        - Si la moneda contable de la empresa de origen difiere de la moneda de contabilidad de la empresa de consolidación, los valores se convierten utilizando la información de cambio definida en la pestaña **Conversión de moneda** de esta página para calcular los valores de la empresa de consolidación.

    - **Importes reales de inclusión** Establezca esta opción en **Sí** para consolidar los datos reales.
    - **Incluir los importes presupuestarios** Establezca esta opción en **Sí** para consolidar los datos del registro presupuestario.
    - **Volver a crear los saldos durante la consolidación** No se recomienda que establezca esta opción en **Sí**. En su lugar, vuelva a crear saldos como un trabajo por lotes independiente.

- **Modelos presupuestarios** Si se ha seleccionado para consolidar los datos de presupuesto, utilice los campos de esta sección para definir los modelos presupuestarios.

    - **De** y **A** permite especificar el intervalo de modelos que se usará.
    - **Tipo presupuestario** Seleccione el tipo de tasa presupuestaria que se usará para la conversión de la divisa de los datos presupuestarios.

## <a name="financial-dimensions"></a>Dimensiones financieras
En la pestaña **Dimensiones financieras**, se definen las dimensiones que se deben incluir en la empresa de consolidación. Para seleccionar una dimensión, establezca el campo **Especificación** en **Dimensión**, y defina el orden de la dimensión en la empresa de consolidación.

![Pestaña Dimensiones financieras.](./media/financial-dimensions-cons.png "Pestaña Dimensiones financieras")

Independientemente de la orden que se define, **Cuenta principal** siempre será el primer segmento.

## <a name="legal-entities"></a>Entidades jurídicas
En la pestaña **Entidades legales**, se definen las empresas que se deben incluir en la empresa de consolidación. También define el porcentaje de propiedad de esas empresas. Si especifica menos del 100 por ciento de propiedad, el porcentaje especificado se revertirá a la empresa de consolidación. Para las diferencias de conversión, el campo **Tipo de cuenta para diferencias de conversión** se utiliza para seleccionar la cuenta principal de la configuración en la página **Cuentas para transacciones automáticas**.

![Pestaña Entidades jurídicas.](./media/legal-entities-cons.png "Pestaña Entidades jurídicas")

![Página Cuentas para transacciones automáticas.](./media/accounts-for-automatic-cons.png "Página Cuentas para transacciones automáticas")

## <a name="elimination"></a>Período de eliminación
En la pestaña **Eliminación** , tiene tres opciones para procesar las eliminaciones:

- Seleccione la regla de eliminación y, a continuación, en el campo **Opciones de propuesta**, seleccione **Sólo oferta**. Esta opción procesará la eliminación durante el proceso de consolidación, pero no registrará todo en un paso. Puede registrar el diario más adelante.
- Seleccione la regla de eliminación y, a continuación, en el campo **Opciones de propuesta**, seleccione **Sólo registrar**. Esta opción procesará la eliminación durante el proceso de consolidación y registrará todo en un paso.
- Ejecute una propuesta de eliminación de forma independiente del proceso de consolidación usando el diario de eliminación.

![Pestaña eliminación.](./media/elimination-cons-onl.png "Pestaña eliminación")

Para obtener más información acerca de las eliminaciones, consulte [Reglas de eliminación](./elimination-rules.md).

## <a name="currency-translation"></a>Traducción de la divisa
En la pestaña **Conversión de la divisa**, se define la entidad jurídica, la cuenta y el tipo de cambio, y el índice. Si la empresa de consolidación está asignada a cuentas principales diferentes a las de la empresa de origen, la cuenta principal de la empresa de consolidación debe introducirse en la fecha **Desde** y **Hasta fecha**, no las cuentas principales de la empresa de origen. Para cada fila de entidad jurídica y cuentas principales, hay tres opciones disponibles en el campo **Aplicar tipo de cambio de**:

- **Fecha de consolidación** – La fecha que se define en el campo **Periodo de consolidación hasta** de la pestñaa **Criterios** de la consolidación se usarán para obtenr el tipo de cambio. Este tipo es equivalente a la tasa al contado o al índice de final de mes. Se verá una vista previa de la tasa, pero no se puede editar.
- **Fecha de transacción** La fecha de cada transacción se usará para seleccionar un tipo de cambio. Esta opción es la que más se suele usar para los activos fijos y suele denominarse tipo histórico. No puede ver una vista previa de la tasa debido a que habrá muchas tasas para las diversas transacciones en el intervalo de la cuenta.
- **Tasa definida por el usuario** Después de activar esta opción, puede especificar el tipo de cambio que desee. Esta opción puede ser útil para los tipos de cambio medio o si está consolidando con un tipo de cambio fijo.

![Pestaña Conversión de divisas.](./media/currency-translation-cons-online.png "Pestaña Conversión de divisas")

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más información acerca de las conversiones de consolidación y divisas, consulte el artículo principal de este artículo [Visión general de consolidaciones financieras y conversión de divisas](./financial-consolidations-currency-translation.md).

Para obtener información sobre los escenarios donde puede generar o consolidar informes financieros, consulte [Generar informes financieros consolidados](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
