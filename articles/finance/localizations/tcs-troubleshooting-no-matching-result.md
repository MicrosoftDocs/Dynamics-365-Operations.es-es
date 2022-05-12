---
title: No se encuentran resultados coincidentes
description: Este tema explica cómo solucionar el error "No se pudo encontrar ningún resultado coincidente" en el servicio de Cálculo de impuestos.
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
ms.openlocfilehash: c1a343b0b74645d40b0a2582749968cc0a56afd7
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645442"
---
# <a name="no-matching-result-could-be-found"></a>No se encuentran resultados coincidentes

[!include [banner](../includes/banner.md)]

Este tema explica los pasos de solución de problemas que puede seguir si recibe el error "No se pudo encontrar ningún resultado coincidente" en el servicio de Cálculo de impuestos.

## <a name="symptom"></a>Síntoma

Recibe el siguiente mensaje de error: "Encabezado/Líneas - 1, Grupo de impuestos, no se pudo encontrar ningún resultado coincidente".

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
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
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

El problema se produce cuando la configuración de la caracerística en Regulatory Configuration Service (RCS) es incorrecta.

## <a name="troubleshoot"></a>Solucionar problemas

1. Descargue el archivo de solución de problemas. Para obtener más información, consulte [Habilitar modo de depuración para solución de problemas](tcs-troubleshooting-enable-debug-mode.md).
2. Compare la entrada de cálculo del servicio de impuestos con la configuración de características para solucionar el problema de configuración.

    El siguiente ejemplo muestra la entrada de cálculo del servicio de impuestos.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    La siguiente tabla enumera la aplicabilidad del grupo de impuestos en RCS.

    | Encabezado.Proceso de negocio | Líneas.Unidad de negocio | Encabezado.Envío de código postal | Grupo de impuestos |
    |-------------------------|---------------------|---------------------------|-----------|
    | Diario                 |                     |                           | Grupo A   |
    | Ventas                   |                     | 30160                     | Grupo B   |

    De acuerdo con la entrada de cálculo del servicio de impuestos, el valor de **Proceso de negocio** en el encabezado es **Ventas**, y el valor de **Envío de código postal** en el encabezado es **30159**. Esta entrada se basa en la configuración de reglas de aplicabilidad en RCS. Dado que no hay una línea coincidente, se produce el error.

    > [!NOTE]
    > Si el valor en la regla de aplicabilidad está en blanco, la regla es aplicable a cualquier valor.

## <a name="mitigation"></a>Mitigación

Siga estos pasos para solucionar el error.

1. En RCS, vaya a **Funciones de globalización** \> **Cálculo de impuestos**.
2. Cree una nueva versión de la característica.
3. Agregue una línea para la información correspondiente.

    | Encabezado.Proceso de negocio | Líneas.Unidad de negocio | Encabezado.Envío de código postal| Grupo de impuestos |
    |-------------------------|---------------------|--------------------------|-----------|
    | Diario                 |                     |                          | Grupo A   |
    | Ventas                   |                     | 30160                    | Grupo B   |
    | Ventas                   |                     | 30159                    | Grupo B   |

4. Publique la versión de configuración de características.
5. En Microsoft Dynamics 365 Finance, vaya a **Impuesto** \> **Configuración** \> **Configuración de impuestos** \> **Parámetros de cálculo de impuestos** y seleccione la nueva versión.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
