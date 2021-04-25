---
title: Unterstützte Upgrades | Upgrade von Skype Business Online auf Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Übersicht über unterstützte Upgrades von Skype for Business Online auf Teams
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995196"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams

Microsoft bietet assistierte Upgrades für Teams an, damit Organisationen einen erfolgreichen Übergang von Skype for Business Online durchführen können, da der Dienst am 31. Juli 2021 in Den Ruhestand geht. Unterstützte Upgrades verringern die Anzahl der technischen Aufgaben, die Sie ausführen müssen, und ermöglichen eine größere Konzentration auf die Vorbereitung der Organisation, das Benutzerbewusstsein und die Teams-Schulung.

Wir empfehlen, dass Sie unsere [Upgradeleitfäden vor](https://aka.ms/SkypeToTeams) dem Upgrade lesen. Unser Upgradeleitfaden enthält empfohlene Aktivitäten und hilfreiche Ressourcen zum Abschließen eines Upgrades von Skype for Business Online auf Teams. Dieser Leitfaden gilt für jede Organisation, die ein Upgrade auf Teams plant, unabhängig davon, ob sie alle Aspekte des Upgrades verwalten oder den unterstützten Prozess verwenden.

> [!NOTE]
> Wenn Sie ein assistiertes Upgrade auf Teams geplant haben, können Sie vor dem geplanten Upgradedatum ein eigenes Upgrade von Skype for Business Online durchführen. Weitere Informationen zum manuellen Upgrade auf Teams finden Sie in unseren [Upgradeleitfäden](https://aka.ms/SkypeToTeams).
>
> Ein unterstütztes Upgrade ist für lokale Bereitstellungen von Skype for Business Server nicht verfügbar.

## <a name="notifications-for-scheduled-customers"></a>Benachrichtigungen für geplante Kunden

Skype for Business Online-Kunden, die für unterstützte Upgrades auf Teams geplant sind, erhalten eine Reihe von Upgradebenachrichtigungen. Diese Benachrichtigungen beginnen 90 Tage vor dem geplanten Upgradedatum. Diese Benachrichtigungen werden als *Plan for Change-Beiträge* im Microsoft 365 Message Center, Upgrade-Dashboardbenachrichtigungen im Teams Admin Center und In-App-Kennzeichnungen für Endbenutzer übermittelt.

Upgradebenachrichtigungen enthalten das geplante Datum des unterstützten Upgrades und werden mit Upgraderessourcen und Schulungen verknüpfen, um die Einführung und Nutzung von Teams zu unterstützen.

## <a name="the-assisted-upgrade-experience"></a>Die unterstützte Upgradeerfahrung

Unterstützte Upgrades beginnen im August 2021 mit mandantenspezifischen Datumsangaben, die in den oben genannten Terminplanungsbenachrichtigungen geteilt werden.

Die Dauer des Upgrades variiert je nach Benutzervolumen und den Merkmalen der Bereitstellung. In den meisten Fällen werden Benutzer innerhalb eines Mandanten jedoch innerhalb von 24 Stunden nach dem Start des Upgrades aktualisiert. Während dieser Zeit haben Endbenutzer weiterhin Zugriff auf Skype for Business Online-Funktionen. Sobald das Upgrade abgeschlossen ist und sich Benutzer bei Skype for Business Online abmelden, verwenden sie Teams für Messaging, Besprechungen und Anrufe.

## <a name="the-post-upgrade-experience"></a>Die Nachaktualisierungserfahrung

Nach Abschluss des unterstützten Upgrades ist der **Koexistenzmodus** für aktualisierte Benutzer auf Teams Only festgelegt und kann von Microsoft nur in einen anderen Koexistenzmodus geändert werden. Wir empfehlen, vor dem Upgrade Überlegungen zum [Modus "Nur teams"](teams-only-mode-considerations.md) zu überprüfen. Die nachstehende Tabelle bietet eine Übersicht über die Benutzerfreundlichkeit nur von Teams auf hoher Ebene.

:::row:::
    :::column span="1":::
        **Chatten und Anrufen**
    :::column-end:::
    :::column span="3":::
        - Alle Anrufe und Chats werden in Teams gestartet und empfangen
        - Benutzer können mit jedem Skype for Business-Benutzer kommunizieren (Chat/Anruf).
        - Organisationen können Teams-Benutzern die Kommunikation mit Benutzern des Skype-Verbraucherdienstes ermöglichen, indem sie [Berechtigungen für den externen Zugriff verwalten.](manage-external-access.md)
        - Teams-Benutzer, die sich bei Skype for Business Online anmelden, werden an Teams weitergeleitet
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
        - Vorhandene Kontakte aus Skype for Business Online einschließlich Verbund (aber keine Verteilerlisten)
        - Vorhandene Skype for Business Online-Besprechungen werden in Teams-Besprechungen konvertiert
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>Verwandter Inhalt

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Einstellung von Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Überlegungen zum Teams Only-Modus](teams-only-mode-considerations.md)
