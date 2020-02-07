---
title: Automatisierte Upgrades | Upgrade für Skype Business to Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Übersicht über automatisierte Upgrades von Skype for Business in Teams
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
ms.openlocfilehash: 1ed959f74be1074ab8ed60b3fe54f06384b7990a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836167"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Automatisierte Upgrades von Skype for Business Online auf Microsoft Teams

Microsoft bietet automatisierte Upgrades für Teams an, um kleine Unternehmen dabei zu unterstützen, den erfolgreichen Übergang von Skype for Business Online vor dem 31. Juli 2021 des Service zu ermöglichen. Das automatisierte Upgrade reduziert die Anzahl der technischen Aufgaben, die von Kunden benötigt werden, und ermöglicht eine stärkere Fokussierung auf organisatorische Vorbereitung, Benutzer Bekanntheit und Teams-Schulung.

Für ein erfolgreiches Upgrade von Skype for Business zu Microsoft Teams ist eine Planung der technischen und Benutzer Bereitschaft erforderlich. Wenn Sie bereit für die ersten Schritte sind, bietet Microsoft einen [Upgrade-Aktionsplan](upgrade-basic.md) mit den wichtigsten empfohlenen Aktivitäten und zugehörigen Ressourcen für die Implementierung eines erfolgreichen Umstiegs von Skype for Business in Teams.

## <a name="notifications-for-scheduled-customers"></a>Benachrichtigungen für geplante Kunden

Skype for Business Online-Kunden, die für automatisierte Upgrades an Teams berechtigt sind, erhalten eine Reihe von Aktualisierungsbenachrichtigungen, die 30 Tage vor dem geplanten Upgrade-Datum beginnen. Diese Benachrichtigungen werden als *Plan für Änderungs* Beiträge im Admin-Nachrichten Center bereitgestellt, aktualisieren e-Mails an den globalen Administrator und in-App-Flags für Endbenutzer.

Diese Benachrichtigungen übermitteln das geplante Datum des automatisierten Upgrades, führen Links zu Ressourcen und Schulungen für Upgrades, um die Einführung und Nutzung von Teams zu fördern, und geben Kunden die Möglichkeit, ihr automatisches Upgrade auf weitere 30 Tage zu verschieben. das Ereignis, das Sie nicht zum geplanten Datum aktualisieren können.

## <a name="the-automated-upgrade-experience"></a>Das automatisierte Upgrade

Automatisierte Upgrades werden nach dem geplanten Aktualisierungsdatum ausgeführt, das in den Benachrichtigungs-e-Mails, im Nachrichten Center und im Team-Admin-Portal mitgeteilt wird. Das Upgrade dauert etwa 15 Minuten, während die Endbenutzer weiterhin Zugriff auf Skype for Business Online-Funktionen haben. Nach Abschluss des Upgrades und dem Abmelden von Benutzern von Skype for Business Online können Benutzer nur Teams für Nachrichten, Besprechungen und Anrufe verwenden.

## <a name="the-post-upgrade-experience"></a>Die Erfahrung nach dem Upgrade

Nach Abschluss des automatisierten Upgrades ist der **Koexistenzmodus** nur auf Teams eingestellt und kann nur in einen anderen Koexistenzmodus von Microsoft geändert werden. Administratoren sollten vor dem Upgrade [nur die Überlegungen im Modus "Teams"](teams-only-mode-considerations.md) überprüfen. In der folgenden Tabelle finden Sie eine allgemeine Übersicht über die Benutzerfreundlichkeit der Teams.


|  |  |
|---------|---------|
|**Chat und Anrufe**     | <UL><LI>Alle Anrufe und Chats werden in Teams initiiert und empfangen.<LI>Benutzer können mit Skype for Business-Benutzern Interop (Chat/Anruf) verwenden.<LI>Benutzer können nicht mit Nutzern kommunizieren, die Skype für Verbraucher verwenden<LI>Benutzer werden zu Teams umgeleitet, wenn Sie sich bei Skype for Business anmelden.      </UL>  |
|**Besprechungen**     |  <UL><LI>Benutzer planen alle neuen Besprechungen in Teams (Plugin ersetzt)    </UL>   |
|**Migrierte Daten**     |<UL><LI>Vorhandene Kontakte aus Skype for Business einschließlich Federated (aber keine Verteilerlisten)<LI>Vorhandene Skype for Business-Besprechungen (sowohl auf-Prem als auch online) werden in Teams-Besprechungen konvertiert</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Verschieben Ihres automatisierten Upgrades

Erfolgreiche Übergänge von Skype for Business Online zu Microsoft Teams erfordern technische Planung und Benutzer Bereitschaft, um sicherzustellen, dass Ihre Organisation bereit ist, die erweiterte Funktionalität und Leistung von Teams zu nutzen. Bei der Planung Ihres Upgrades können Sie jedoch feststellen, dass Ihre Organisation derzeit noch nicht bereit ist, auf Teams zu aktualisieren.

Wenn Sie eine Benachrichtigung bezüglich Ihres geplanten automatisierten Upgrades für Teams erhalten und Sie auf einen späteren Termin verschieben möchten, kann sich der globale Administrator von Office 365 beim Team-Administratorportal anmelden und auf die Schaltfläche " *verschieben* " klicken. Auf diese Weise wird der automatisierte Upgrade-Termin 30 Tage lang verdrängt. Wenn Sie das Team-Administratorportal nach dem Verschieben aktualisieren, wird eine Benachrichtigung angezeigt, die Ihr neues automatisches Aktualisierungsdatum enthält.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Anforderungen für ein Downgrade auf Skype for Business

Wir ermöglichen einmaliges Herunterstufen von Teams zu SfBO, um es den Mietern zu ermöglichen, sich auf Ihr Upgrade auf Teams vorzubereiten. Mandanten, die heruntergestuft wurden, werden für das automatisierte Upgrade 60 Tage ab Ihrem Downgrade-Datum erneut aktiviert.

## <a name="related-content"></a>Verwandter Inhalt

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Einstellung von Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Überlegungen zum Teams Only-Modus](teams-only-mode-considerations.md)

