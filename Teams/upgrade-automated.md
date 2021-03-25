---
title: Automatische Upgrades| Upgrade von Skype Business auf Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Übersicht über automatisierte Upgrades von Skype for Business auf Teams
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
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120541"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Automatische Upgrades von Skype for Business Online auf Microsoft Teams

Microsoft bietet automatisierte Upgrades für Teams an, damit kleine Unternehmen vor dem 31. Juli 2021 den erfolgreichen Übergang von Skype for Business Online durchführen können. Das automatisierte Upgrade reduziert die Anzahl der technischen Aufgaben, die von Kunden benötigt werden, und ermöglicht eine größere Konzentration auf die Vorbereitung der Organisation, die Benutzererfahrung und die Teams-Schulung.

Ein erfolgreiches Upgrade von Skype for Business auf Microsoft Teams erfordert die Planung der technischen und Benutzerbereitschaft. Wenn Sie bereit für die ersten [](upgrade-basic.md) Schritte sind, bietet Microsoft einen Upgradeaktionsplan mit den wichtigsten empfohlenen Aktivitäten und zugehörigen Ressourcen für die Implementierung eines erfolgreichen Wechsels von Skype for Business zu Teams.

## <a name="notifications-for-scheduled-customers"></a>Benachrichtigungen für geplante Kunden

Skype for Business Online-Kunden, die für automatisierte Upgrades auf Teams berechtigt sind, erhalten eine Reihe von Upgradebenachrichtigungen, die 30 Tage vor dem geplanten Upgradedatum beginnen. Diese Benachrichtigungen werden als *Plan for Change-Beiträge* im Admin Message Center übermittelt, E-Mails an den globalen Administrator und In-App-Kennzeichnungen für Endbenutzer aktualisiert.

Diese Benachrichtigungen kommunizieren das geplante Datum des automatisierten Upgrades, verknüpfen mit Upgraderessourcen und Schulungen, um die Einführung und Nutzung von Teams zu verbessern, und bieten Kunden die Möglichkeit, ihr automatisiertes Upgrade um weitere 30 Tage zu verschieben, wenn sie nicht bereit sind, ein Upgrade bis zum geplanten Datum zu durchführen.

## <a name="the-automated-upgrade-experience"></a>Die automatische Upgradeerfahrung

Automatische Upgrades werden am geplanten Upgradedatum ausgeführt, das in den Benachrichtigungs-E-Mails, dem Nachrichtencenter und dem Teams Admin-Portal mitgeteilt wird. Das Upgrade dauert ungefähr 15 Minuten, während der Endbenutzer weiterhin Zugriff auf die Skype for Business Online-Funktionen haben. Nach Abschluss des Upgrades und der Anmeldung von Skype for Business Online können Benutzer Teams nur noch für Nachrichten, Besprechungen und Anrufe verwenden.

## <a name="the-post-upgrade-experience"></a>Die Nachaktualisierungserfahrung

Nach Abschluss des automatisierten Upgrades ist der **Koexistenzmodus** auf Teams Only festgelegt und kann von Microsoft nur in einen anderen Koexistenzmodus geändert werden. Administratoren sollten die [Überlegungen zum Modus "Nur teams" vor](teams-only-mode-considerations.md) dem Upgrade überprüfen. Die nachstehende Tabelle bietet eine Übersicht über die Benutzerfreundlichkeit nur von Teams auf hoher Ebene.


|  |  |
|---------|---------|
|**Chatten und Anrufen**     | <UL><LI>Alle Anrufe und Chats werden in Teams initiiert und empfangen<LI>Benutzer können mit jedem Skype for Business-Benutzer in Kontakt (Chat/Anruf)<LI>Benutzer können nicht mit Benutzern kommunizieren, die Skype for Consumer verwenden<LI>Benutzer werden an Teams umgeleitet, wenn sie versuchen, sich bei Skype for Business zu anmelden.      </UL>  |
|**Besprechungen**     |  <UL><LI>Benutzer planen alle neuen Besprechungen in Teams (Plug-In ersetzt)    </UL>   |
|**Migrierte Daten**     |<UL><LI>Vorhandene Kontakte aus Skype for Business einschließlich Verbund (aber keine Verteilerlisten)<LI>Vorhandene Skype for Business-Besprechungen (sowohl vorab als auch online) werden in Teams-Besprechungen konvertiert</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Verschieben des automatisierten Upgrades

Erfolgreiche Übergänge von Skype for Business Online zu Microsoft Teams erfordern technische Planung und Benutzerbereitschaft, um sicherzustellen, dass Ihre Organisation bereit ist, die erweiterten Funktionen und die Leistung von Teams zu nutzen. Während Sie ihr Upgrade planen, können Sie jedoch feststellen, dass Ihre Organisation derzeit noch nicht bereit ist, ein Upgrade auf Teams zu unternehmen.

Wenn Sie eine Benachrichtigung zu Ihrem geplanten automatisierten Upgrade auf Teams erhalten und auf einen späteren Zeitpunkt verschieben möchten, kann sich der globale Administrator beim Teams Admin-Portal anmelden und auf die Schaltfläche Verschieben *klicken.* Dadurch wird das automatische Upgradedatum auf 30 Tage vertagt. Wenn Sie das Teams Admin-Portal nach dem Verschieben aktualisieren, wird eine Benachrichtigung angezeigt, die Ihr neues automatisiertes Upgradedatum enthält.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Anforderungen zum Downgrade auf Skype for Business

Wir erlauben Einmalabstufungen von Teams auf SfBO, um Mandanten die weitere Vorbereitung auf ihr Upgrade auf Teams zu ermöglichen. Mandanten, die ein Downgrade erhalten haben, werden 60 Tage nach dem Downgradedatum erneut für das automatisierte Upgrade engagiert.

## <a name="related-content"></a>Verwandter Inhalt

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Einstellung von Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Überlegungen zum Teams Only-Modus](teams-only-mode-considerations.md)