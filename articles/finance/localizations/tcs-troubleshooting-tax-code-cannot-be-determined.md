---
title: No se puede determinar el código de impuestos
description: Este artículo explica cómo solucionar el error "No se puede determinar el código de impuestos" del servicio de Cálculo de impuestos.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 6a74724de38cf362900277ab9addc8e6894f7689
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877870"
---
# <a name="tax-code-cannot-be-determined"></a>No se puede determinar el código de impuestos

[!include [banner](../includes/banner.md)]

Este artículo explica los pasos de solución de problemas que puede seguir si recibe el error "No se puede determinar el código de impuestos" en el servicio de Cálculo de impuestos.

## <a name="symptom"></a>Síntoma

Usted recibe el siguiente mensaje de error: "Encabezado/Líneas - 1, no se puede determinar el código de impuestos". Como alternativa, encuentra el error en el archivo de solución de problemas, como se muestra en el siguiente ejemplo. Para obtener más información, consulte [Habilitar modo de depuración para solución de problemas](tcs-troubleshooting-enable-debug-mode.md).

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Causa

Es probable que el problema se deba a que el grupo de impuestos y el grupo de impuestos de artículos no se entrecruzan.

## <a name="troubleshoot"></a>Solucionar problemas

Siga estos pasos para solucionar el problema.

1. En el archivo de solución de problemas, verifique que se hayan determinado el grupo de impuestos y el grupo de impuestos de artículos. Si los valores para **Grupo de impuestos** y **Grupo de impuestos de artículos** están en blanco, el grupo de impuestos y el grupo de impuestos de artículos no se han determinado. Si se han determinado, los resultados pueden ser incorrectos.

    Este es un ejemplo de archivo de solución de problemas.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
                            "Adjustment": null
                        }
                    ],
                    "Measures": {
                        ...
                    },
                    ...
                }
            ]
        },
        ...
    }
    ```

2. Verifique que está habilitada la opción **Anular impuestos** en la pestaña **Configuración** de los detalles de línea de pedido de ventas.

    - Si está habilitada, los códigos de impuestos dependerán de los valores de **Grupo de impuestos** y **Grupo de impuestos del artículo** que ingrese en la línea de transacción. Verifique que estos valores se hayan ingresado correctamente.
    - Si no está habilitado, verifique que se hayan establecido los valores correctos para los campos **Aplicabilidad del grupo de impuestos** y **Aplicabilidad del grupo de impuestos de artículos**. Para más información, vea [No se encontró ningún resultado coincidente](tcs-troubleshooting-no-matching-result.md).

3. Si el grupo de impuestos y el grupo de impuestos de artículos se han determinado correctamente, determine si existe alguna intersección para ellos.

    1. En RCS, vaya a **Características de impuestos** \> **Códigos y grupos de impuestos** \> **Grupo de impuestos**.

        | Línea.Grupo de impuestos | Códigos de impuestos |
        |----------------|-----------|
        | Grupo A        | C         |

    2. Vaya a **Características de impuestos** \> **Códigos y grupos de impuestos** \> **Grupo de impuestos de artículos**.

        | Línea.Grupo de impuestos de artículos | Códigos de impuestos |
        |---------------------|-----------|
        | Grupo B             | mil millones         |

    Si no hay intersección para el grupo de impuestos y el grupo de impuestos de artículos, no se determinará el código de impuestos.

## <a name="mitigation"></a>Mitigación

1. Recorra cada paso en la sección [Solucionar problemas](#troubleshoot) de este artículo y corrija la configuración según sea necesario. Si el grupo de impuestos y el grupo de impuestos de artículos no se han determinado correctamente, consulte [No se encontró ningún resultado coincidente](tcs-troubleshooting-no-matching-result.md).
2. Si no hay intersección para el grupo de impuestos y el grupo de impuestos de artículos, cree una nueva versión de la característica en RCS y corrija la configuración.

    - Vaya a **Características de impuestos** \> **Códigos y grupos de impuestos** > **Grupo de impuestos del artículo**.

        | Línea.Grupo de impuestos de artículos | Códigos impositivos |
        |---------------------|-----------|
        | Grupo B             | A;B       |

    El código de impuestos se determinará como **A**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
