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
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Sie bearbeiten die Einstellungen für die Widerstandsfähigkeit und konfigurieren die folgenden Eigenschaften:'
ms.openlocfilehash: 3fd2ea5a1ea2f0621a4df840a6e2af7581d39e9f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696740"
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
