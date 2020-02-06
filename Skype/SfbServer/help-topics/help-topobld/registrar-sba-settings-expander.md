---
title: SBA-Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Sie bearbeiten die Einstellungen für die Widerstandsfähigkeit und konfigurieren die folgenden Eigenschaften:'
ms.openlocfilehash: b5c5982dc0a49d1d2002465f4f7a2c6381dd5370
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819347"
---
# <a name="registrar-sba-settings-expander"></a>SBA-Einstellungen der Registrierungsstelle – Erweiterung

Sie bearbeiten die Einstellungen für die **Widerstandsfähigkeit** und konfigurieren die folgenden Eigenschaften:

- Wählen Sie in der Liste **zugeordneter Benutzer Dienst und sicherungsregistrierungspool** aus.

    Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für VoIP** .

    Konfigurieren Sie das **Erkennungsintervall für Sprachfehler (SEK)** und das **sprach-Failback-Intervall (SEK)**. Standardmäßig sind die Intervalle 120 Sekunden für die Sprachfehler Erkennung und 240 Sekunden für sprach-Failback.

    > [!CAUTION]
    > Die Anzahl der Sekunden, die Sie für die Failover-und Failback-Intervalle definieren, sollten sorgfältig getestet werden, um sicherzustellen, dass die Widerstandsfähigkeit wie erwartet funktioniert. Wenn Sie das Intervall auf "gering" (also weniger als 120 Sekunden) oder das Failover und die Failback-Einstellung zu eng festlegen, kann dies zu einem tatsächlichen Failover und Failback führen, die nicht erwartungsgemäß funktionieren.

  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.

  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.

  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.

## <a name="see-also"></a>Siehe auch

[Planung für Enterprise-VoIP-Resilienz](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
