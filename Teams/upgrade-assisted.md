---
title: Unterstützte | Skype Business Online für Teams Upgrade
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Übersicht über unterstützte Upgrades von Skype for Business Online zu Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a162a9151413137282d80e47f8f2b08c841e171a
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456888"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Unterstützte Upgrades von Skype for Business Online zu Microsoft Teams

Microsoft hat Skype for Business Online am 31. Juli 2021 eingestellt.  Microsoft stellt einen unterstützten Upgradeprozess zur Verfügung, damit Organisationen die verbleibenden Skype for Business Online-Benutzer ausschließlich auf Teams verschieben können.  Von Microsoft unterstützte Upgrades verringern die Anzahl der technischen Aufgaben und vereinfachen den Umstieg auf eine Welt, ohne Skype for Business Online zu verwenden, unabhängig davon, ob Ihre Organisation:
 - Eine reine Onlineorganisation, die ein Upgrade von *Skype for Business Online* durchführen muss, um zu einem reinen Teams werden, oder
 - Eine Hybridorganisation mit Benutzern sowohl in *Skype for Business Online*  als auch in einer lokalen *Skype for Business Server-Umgebung*, für die nur der Skype for Business *Online-Benutzer* auf "Nur für Teams aktualisieren muss.

Wir empfehlen, dass Sie sich vor [dem Upgrade einen Überblick](https://aka.ms/SkypeToTeams) über unsere Upgradeanleitungen machen. Unser Upgradeleitfaden enthält empfohlene Aktivitäten und hilfreiche Ressourcen für den Abschluss eines Upgrades von Skype for Business Online auf Teams. Dieser Leitfaden gilt für alle Organisationen, die ein Upgrade auf Teams planen, ganz gleich, ob sie alle Aspekte des Upgrades verwalten oder den unterstützten Prozess verwenden.

## <a name="the-assisted-upgrade-experience"></a>Die Upgrade-Unterstützung
Skype for Business Online-Kunden, die für unterstützte Upgrades auf Teams geplant sind, erhalten verschiedene Arten von Benachrichtigungen *: Planen* der Änderung von Beiträgen im Microsoft 365-Nachrichtencenter, Upgrade von Dashboardbenachrichtigungen im Teams Admin Center und In-App-Kennzeichnungen für Endbenutzer. Die Upgradebenachrichtigung im Nachrichtencenter und Teams Admin Center enthält das geplante Datum des unterstützten Upgrades sowie einen Link zu Upgraderessourcen und Schulungen, um die Einführung und Nutzung des Upgrades zu Teams.

Die Umgebung für das unterstützte Upgrade unterscheidet sich geringfügig, je nachdem, ob in Ihrer Organisation Benutzer in einer lokalen Umgebung Skype for Business Server sind:
- **Reine Onlineorganisationen:** Für Organisationen *ohne* lokales Konto Skype Busineess Server-Benutzer `TeamsUpgradeOverridePolicy` wendet der unterstützte Upgradeprozess die Richtlinie auf Ihre Organisation an. Wenn diese Richtlinie angewendet wird, werden alle Benutzer Skype for Business Online im TeamsOnly-Modus platziert.
- **Hybridorganisationen mit lokalen Skype for Business:** Dies umfasst Organisationen mit allen in Skype for Business Server be hauseten Benutzern, unabhängig davon, ob hybrid konfiguriert wurde. Diese Organisationen haben möglicherweise Benutzer, die in eine der folgenden Kategorien fallen:

  - Lokale Benutzer, die auf einem lokalen Skype for Business Server sind (die Benutzer Teams verwenden können oder nicht, Teams sind)
  - TeamsOnly-Benutzer, die in Skype for Business Online Skype for Business wurden
  - Nicht-TeamsOnly-Benutzer, die in Ihrer Skype for Business Online

Der unterstützte Upgradeprozess wirkt sich nur auf die letzte Benutzerkategorie aus: Nicht Teams Nur in Skype for Business Online unterstützte Benutzer werden auf den Teams Modus aktualisiert. Lokale Skype for Business und vorhandene TeamsOnly-Benutzer sind vom unterstützten Upgradeprozess nicht betroffen.

> [!NOTE]
> Ihre Organisation kann Skype for Business Online weiterhin verwenden, bis das Upgrade abgeschlossen ist. Wenn für Sie ein unterstütztes Upgrade auf Teams geplant ist, können Sie vor dem Datum des geplanten Upgrades ein eigenes Upgrade von Skype for Business Online durchführen. Weitere Informationen zum manuellen Upgrade auf die Teams finden Sie in unseren [Upgradeanleitungen](https://aka.ms/SkypeToTeams).

Die Dauer des Upgrades variiert je nach Benutzervolumen und Den Merkmalen der Bereitstellung. In den meisten Fällen wird für Benutzer innerhalb eines Mandanten das Upgrade innerhalb von 24 Stunden nach dem Start des Upgrades durchgeführt. Während dieser Zeit haben Endbenutzer weiterhin Zugriff auf die Skype for Business Online-Funktionen. Sobald das Upgrade abgeschlossen ist und sich die Benutzer von Skype for Business Online abmelden, verwenden sie die Teams für Messaging, Besprechungen und Anrufe.

## <a name="the-post-upgrade-experience"></a>Die Benutzererfahrung nach dem Upgrade

Nach Abschluss des unterstützten Upgrades wird der **Koexistenzmodus** für aktualisierte Benutzer auf Nur Teams festgelegt. Es wird empfohlen, vor Teams [nur Überlegungen zum](teams-only-mode-considerations.md) Modus zu lesen. In der folgenden Tabelle finden Sie eine Übersicht über die Teams Nur die Benutzerfreundlichkeit.

:::row:::
    :::column span="1":::
        **Chat und Anrufe**
    :::column-end:::
    :::column span="3":::
        - Alle Anrufe und Chats werden in einem Teams
        - Benutzer können mit jedem Ihrer Benutzer (Chat/Anruf) Skype for Business kommunizieren
        - Organisationen können es Teams Benutzern ermöglichen, mit Benutzern des Skype zu kommunizieren, indem sie [externe Zugriffsberechtigungen verwalten.](manage-external-access.md)
        - Teams Benutzer, die sich bei Skype for Business Online anmelden, werden an Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Besprechungen**
    :::column-end:::
    :::column span="3":::
        - Benutzer planen alle neuen Besprechungen in Teams (Plug-In ersetzt)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Migrierte Daten**
    :::column-end:::
    :::column span="3":::
        - Vorhandene Kontakte aus Skype for Business Online einschließlich Verbundkontakten (aber keine Verteilerlisten)
        - Kontakte werden migriert, wenn sich Benutzer Teams zum ersten Mal anmelden.
            > [!IMPORTANT]
            >Kontakte müssen innerhalb von 90 Tagen nach Abschluss des Upgrades migriert werden.
        - Vorhandene Skype for Business Onlinebesprechungen werden in Besprechungen Teams konvertiert
            > [!IMPORTANT]
            > Kunden mit reinen Skype for Business Online-Konfigurationen müssen Meeting Migration Service (MMS) verwenden, um vorhandene Skype for Business Online-Besprechungen zu Teams migrieren. Wir empfehlen die Verwendung von MMS vor dem Datum des unterstützten Upgrades. Weitere Informationen zu MMS finden Sie unter [Verwenden des Meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Wenn Sie über eine hybride Skype for Business Server verfügen und ein Upgrade auf Teams durchführen, können Sie Benutzer nach Abschluss des Upgrades zwischen Skype for Business Server und Teams verschieben.

## <a name="related-content"></a>Verwandter Inhalt

- [Erste Schritte beim Upgrade auf Microsoft Teams](upgrade-start-here.md)
- [Einstellung von Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Überlegungen zum Teams Only-Modus](teams-only-mode-considerations.md)
