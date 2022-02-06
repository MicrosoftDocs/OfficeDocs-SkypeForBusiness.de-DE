---
title: SBA-Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Sie bearbeiten die Einstellungen für Flexibilität und konfigurieren die folgenden Eigenschaften:'
---

# <a name="registrar-sba-settings-expander"></a>SBA-Einstellungen der Registrierungsstelle – Erweiterung

Sie bearbeiten die Einstellungen für **Flexibilität** und konfigurieren die folgenden Eigenschaften:

- Wählen Sie in der Liste die Option **Zugeordneter Benutzerdienst und Sicherungsregistrierungsstellen-Pool** aus.

    Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für Sprachdienste**.

    Konfigurieren Sie die Optionen **Erkennungsintervall für Sprachdienstfehler (Sek.)** und **Failbackintervall für Sprache (Sek.)**. Die Standardeinstellungen für die Intervalle lauten 120 Sekunden für die Erkennung von Sprachdienstfehlern und 240 Sekunden für das Failback für Sprache.

    > [!CAUTION]
    > Die Anzahl an Sekunden, die Sie für Failover- und Failbackintervalle definieren, muss sorgfältig getestet werden, um sicherzustellen, dass die Ausfallsicherheit wie gewünscht funktioniert. Wenn das Intervall zu kurz ist (weniger als 120 Sekunden) oder Failover und Failback zu eng festgelegt sind, kann dies dazu führen, dass Failover und Failback nicht wie gewünscht funktionieren.

  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.

  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.

  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.

## <a name="see-also"></a>Siehe auch

[Planen Enterprise-VoIP Ausfallsicherheit](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)