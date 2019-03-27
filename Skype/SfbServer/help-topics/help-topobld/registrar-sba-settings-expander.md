---
title: SBA-Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Sie bearbeiten die Einstellungen für Flexibilität und konfigurieren Sie die folgenden Eigenschaften:'
ms.openlocfilehash: 118c7e3eda7fc8422483989880f7ae0b31b9842f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896703"
---
# <a name="registrar-sba-settings-expander"></a>SBA-Einstellungen der Registrierungsstelle – Erweiterung

Sie bearbeiten die Einstellungen für **Flexibilität** und konfigurieren Sie die folgenden Eigenschaften:

- Wählen Sie **zugeordneter Benutzerdienst und Sicherungsregistrierungsstellen-Pool** aus der Liste aus.

    Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für VoIP** .

    Konfigurieren der **VoIP-Fehler Erkennung Intervall (s)** und **VoIP Failback Intervall (s)**. Standardmäßig sind die Intervalle 120 für die Erkennung von VoIP-Fehlern und 240 Sekunden für VoIP Failback.

    > [!CAUTION]
    > Die Anzahl der Sekunden an, denen Sie für die Intervalle Failover und Failback definieren sollten sorgfältig getestet werden, um sicherzustellen, dass die Resiliency wie erwartet funktioniert. Festlegen des Intervalls auf Niedrig (d. h., kleiner als 120 Sekunden) oder das Failover und Failback festlegen zu stark möglicherweise in den tatsächlichen Failover und Failback funktioniert nicht wie erwartet.

  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.

  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.

  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.

## <a name="see-also"></a>Siehe auch

[Planen von Enterprise-VoIP-Ausfallsicherheit](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
