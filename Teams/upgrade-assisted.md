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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c19a0569fe56e9bf8c822b1418ac2fe0685532b
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855934"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Unterstützte Upgrades von Skype for Business Online zu Microsoft Teams

Microsoft bietet Supportupgrades für Teams an, damit Organisationen erfolgreich von Skype for Business Online umstiegen können, wenn der Dienst am 31. Juli 2021 aus der Dienstzeit geht. Unabhängig davon, ob Ihre Organisation ein Upgrade von *Skype for Business Online* oder *Skype for Business Online* mit Hybridumgebung (Benutzer in der Skype for Business **Online-** und Skype for Business Server)-Umgebung vornimmt, verringern die von Ihnen unterstützten Upgrades die Anzahl der technischen Aufgaben, die Sie ausführen müssen, und ermöglichen eine bessere Konzentration auf die Vorbereitung der Organisation, benutzerfreundliche Informationen und Teams Schulungen.

Wir empfehlen, dass Sie sich vor [dem Upgrade einen Überblick](https://aka.ms/SkypeToTeams) über unsere Upgradeanleitungen machen. Unser Upgradeleitfaden enthält empfohlene Aktivitäten und hilfreiche Ressourcen für den Abschluss eines Upgrades von Skype for Business Online zu Teams. Dieser Leitfaden gilt für alle Organisationen, die ein Upgrade auf Teams planen, ganz gleich, ob sie alle Aspekte des Upgrades verwalten oder den unterstützten Prozess verwenden.

> [!NOTE]
> Wenn für Sie ein unterstütztes Upgrade auf Teams geplant ist, können Sie vor dem Datum des geplanten Upgrades ein eigenes Upgrade von Skype for Business Online durchführen. Weitere Informationen dazu, wie Sie ein manuelles Upgrade auf ihre Teams, finden Sie in unserer [Anleitung zum Upgrade.](https://aka.ms/SkypeToTeams)
>
> Unterstützte Upgrades sind für lokale Bereitstellungen von Skype for Business Server.

## <a name="notifications-for-scheduled-customers"></a>Benachrichtigungen für geplante Kunden

Skype for Business Online-Kunden, die für unterstützte Upgrades auf Teams geplant sind, erhalten eine Reihe von Upgradebenachrichtigungen. Diese Benachrichtigungen beginnen 90 Tage vor dem Datum des geplanten Upgrades. Diese Benachrichtigungen werden als Plan *für* Änderungen an Beiträgen im Microsoft 365-Nachrichtencenter, Upgrade von Dashboardbenachrichtigungen im Teams Admin Center und In-App-Flags für Endbenutzer übermittelt.

Upgradebenachrichtigungen enthalten das geplante Datum des unterstützten Upgrades und werden links zu Upgraderessourcen und Schulungen angezeigt, um die Einführung und Verwendung von Ressourcen zu Teams.

## <a name="the-assisted-upgrade-experience"></a>Die Upgrade-Unterstützung

Unterstützte Upgrades beginnen im August 2021 mit mandantenspezifischen Daten, die in den oben genannten Planungsbenachrichtigungen geteilt werden.

Ihre Umgebung für das unterstützte Upgrade unterscheidet sich geringfügig, je nachdem, ob Sie über eine Skype for Business Online- oder eine Skype for Business Online mit Hybridumgebung verfügen:

- **Skype for Business nur online verfügbar** Beim unterstützten Upgradeprozess wird die Richtlinie `TeamsUpgradeOverridePolicy` auf Ihre Organisation angewendet. Wenn diese Richtlinie angewendet wird, werden alle Ihre Skype for Business Online-Benutzer in den Teams Modus gesetzt.
- **Skype for Business Online mit Hybrid** Hybridumgebungen können Benutzer enthalten, die in eine der folgenden Kategorien fallen:

  - Lokale Benutzer, die auf einem Skype for Business Server
  - Skype for Business Onlinebenutzer, die sich im Teams modus befinden
  - Skype for Business Onlinebenutzer, die **sich nicht** im Teams befinden

  Wenn Sie über eine Mischung von Benutzern in jeder der oben aufgeführten Kategorien verfügen, wird beim unterstützten Upgradeprozess nur dann von Skype for Business Online-Benutzern in den Teams Only-Modus umgeschaltet, wenn sie sich noch nicht in diesem Modus befinden. Lokale Skype for Business sind von dem unterstützten Upgradeprozess nicht betroffen.

> [!NOTE]
> Machen Sie sich keine Sorgen, wenn Ihr unterstütztes Upgrade für ein Datum nach dem 31. Juli 2021 geplant ist. Ihre Organisation kann Skype for Business Online verwenden, bis das Upgrade abgeschlossen ist.

Die Dauer des Upgrades variiert je nach Benutzervolumen und Den Merkmalen der Bereitstellung. In den meisten Fällen wird für Benutzer innerhalb eines Mandanten das Upgrade innerhalb von 24 Stunden nach dem Start des Upgrades durchgeführt. Während dieser Zeit haben Endbenutzer weiterhin Zugriff auf die Skype for Business Onlinefunktionen. Sobald das Upgrade abgeschlossen ist und sich Benutzer von Skype for Business Online abmelden, verwenden sie Teams für Nachrichten, Besprechungen und Anrufe.

## <a name="the-post-upgrade-experience"></a>Die Benutzererfahrung nach dem Upgrade

Nach Abschluss des unterstützten Upgrades ist der **Koexistenzmodus** für aktualisierte Benutzer auf Teams festgelegt. Es wird empfohlen, vor Teams [nur Überlegungen zum](teams-only-mode-considerations.md) Modus zu lesen. In der folgenden Tabelle finden Sie eine Übersicht über die Teams Nur Benutzerfreundlichkeit.

:::row:::
    :::column span="1":::
        **Chat und Anrufe**
    :::column-end:::
    :::column span="3":::
        - Alle Anrufe und Chats werden gestartet und in Teams
        - Benutzer können mit jedem Ihrer Benutzer kommunizieren (chatten Skype for Business anrufen)
        - Organisationen können es Teams Benutzern ermöglichen, mit Benutzern des Verbraucherdienstes Skype zu kommunizieren, indem sie [externe Zugriffsberechtigungen verwalten.](manage-external-access.md)
        - Teams Benutzer, die versuchen, sich bei Skype for Business Online anmelden, werden an Teams
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
            > Kunden mit reinen Skype for Business Online-Konfigurationen müssen Meeting Migration Service (MMS) verwenden, um vorhandene Skype for Business Online-Besprechungen zu Teams migrieren. Wir empfehlen die Verwendung von MMS vor dem Datum des unterstützten Upgrades. Weitere Informationen zu MMS finden Sie unter [Verwenden von Meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Wenn Sie über eine hybride Skype for Business Server verfügen und ein Upgrade auf Teams durchführen, können Sie Benutzer nach Abschluss des Upgrades zwischen Skype for Business Server und Teams verschieben.

## <a name="related-content"></a>Verwandter Inhalt

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Einstellung von Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Überlegungen zum Teams Only-Modus](teams-only-mode-considerations.md)
