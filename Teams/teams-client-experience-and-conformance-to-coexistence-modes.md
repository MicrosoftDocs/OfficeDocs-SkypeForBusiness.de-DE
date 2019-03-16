---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Clientumgebung Teams und ASP.NET-Features, Koexistenz Modi
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd2b3f94acfc82e1602f3137ed1e275a03c7b0e
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "30647425"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

> [!NOTE]
> Auf dieser Seite werden wichtige anstehende Änderungen in das Verhalten des Teams Clients sind Benutzer in einer der der Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) beschrieben.


Der Zweck der Koexistenz Modi darin eine einfache und vorhersehbare Erfahrung für Endbenutzer als Organisationen Übergang von Skype für Business Teams bereitzustellen.  Für eine Organisation verschieben, Teams ist der TeamsOnly-Modus der endgültigen Ziel für jeden Benutzer, wenn nicht alle Benutzer sich TeamsOnly (oder einem anderen Modus) zugewiesen werden zur gleichen Zeit müssen.  Vor dem Benutzer TeamsOnly Modus erreichen können Organisationen verwenden die Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), um sicherzustellen, dass vorhersehbare Kommunikation zwischen Benutzern, die TeamsOnly sind und Personen, die noch nicht. 

Wenn ein Benutzer in einer der der Skype für Business Modi ist, werden alle eingehenden Chats und Anrufe an Skype für Business-Client des Benutzers weitergeleitet. Endbenutzer Verwechslungen und die Sicherstellung ordnungsgemäßes routing, Anruf- und Chat Funktionen im Client Teams soll deaktiviert werden, wenn ein Benutzer in einer der der Skype für Business Modi ist. Auf ähnliche Weise ist Besprechung planen in Teams für die direkte Verwendung explizit deaktiviert werden, wenn der Benutzer in den SfBOnly oder SfBWithTeamsCollab Modi sind und explizit aktiviert, wenn ein Benutzer in den Modus SfBWithTeamsCollabAndMeetings ist.  Die Funktionalität automatisch deaktivieren chat und -Funktionen aufrufen sowie Aktivieren/Deaktivieren der Besprechung planen, basierend auf Modus jetzt beginnt, Rollout TAP-Kunden.  

Bevor Sie diese Funktionalität war Microsoft Anleitung die richtige Benutzeroberfläche beitragen, indem Sie die entsprechenden Einstellungen in Messaging, aufrufen und Besprechungsrichtlinien festlegen. Allerdings gab es keine formelle Durchsetzung dieser und da Benutzer standardmäßig vollen Zugriff auf alle Funktionen im Client Teams hatte, einige Benutzer möglicherweise haben beibehalten, Zugriff auf einige oder alle dieser Erfahrungen im Client Teams unabhängig von deren Modus.  Daher während diese Funktionalität stellt, möglicherweise einige Benutzer eine Änderung in ihre Erfahrung im Client Teams angezeigt, wie die Benutzeroberfläche ihrer Modus entsprechen beginnt.  Die folgende Tabelle enthält das neue Verhalten:


|Eine effektive Benutzermodus|Erleben Sie die Teams-Client|
|---|---|
|Skype für Business-Modus|Anruf- und Chat<sup>1</sup> sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechung planen, ist verfügbar|
|SfBWithTeamsCollab oder SfBOnly<sup>2</sup>|Besprechung planen ist nicht verfügbar|
|||

**Hinweise:**
<sup>1</sup> Meeting Chat weiterhin verfügbar ist.

<sup>2</sup> für den Moment SfBwithTeamsCollab und SfBOnly Verhalten sich, aber die Absicht für SfBOnly Modus auch deaktivieren, Kanäle und Dateien Funktonalität Teams; Es ist derzeit keine Einstellung, die mit dieser Funktionalität in Teams deaktiviert werden kann.


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a>Wie können Organisationen auf automatische UX Übereinstimmung mit Modi vorbereiten

Vor dieser Änderung Rollout können Organisationen die gewünschte Erfahrung im Teams Client zusätzliche Richtlinien verwenden, wie in diesem Abschnitt beschrieben erzielen. Dadurch wird sichergestellt, dass die Einführung nahtlos für Endbenutzer ist. Beachten Sie, dass nach die Änderung stellt, diese Richtlinien festlegen nicht erforderlich.  Alternativ können Organisationen, die nicht für Benutzer, die Funktionalität im Client Teams eingeschränkt haben möchten, die Benutzer auf Inseln oder TeamsOnly Modus umschalten, jedoch, die auch routing auswirkt.

Verwenden Sie die manuelle Konfiguration des Endbenutzers Administratoren die folgenden Richtlinien und Einstellungen:


|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechung planen|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


Administratoren sollten für jede dieser Einstellungen auf die folgenden Werte für einen bestimmten Modus festlegen:

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder Inseln|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Vor der Einführung der automatischen Konformität des Benutzererlebnisses basierend auf Modi die `Grant-CsTeamsUpgradePolicy` Cmdlet überprüft die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy bestimmen, ob diese mit den angegebenen Modus kompatibel sind. Wenn eine nicht ordnungsgemäß konfiguriert sind, die Grant wird erfolgreich ausgeführt, aber eine Warnung erhalten in PowerShell, der angibt, welche spezifischen Einstellungen nicht ordnungsgemäß konfiguriert sind. Es folgt ein Beispiel für die PowerShell-Warnung kann folgendermaßen aussehen:


"Grant-CsTeamsUpgradePolicy-Identity user1@contoso.com PolicyName - SfBWithTeamsCollab

Warnung: Der Benutzer "user1@contoso.com" zurzeit Werte für eine effektive Richtlinie aktiviert ist: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In der near-Begriff beim Erteilen von TeamsUpgradePolicy mit Mode = SfBWithTeamsCollab an einen Benutzer müssen Sie auch separat zuweisen Richtlinie, um sicherzustellen, dass der Benutzer hat die Richtlinienwerte für eine effektive deaktiviert: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. Die Funktion berücksichtigt in der Zukunft automatisch TeamsUpgradePolicy. "

Bei sehen eine Warnung ausgegeben, sollte der Administrator die angezeigten Richtlinien, um eine kompatible Endbenutzer Erlebnis in Teams anschließend aktualisieren. Entscheidet der Administrator keine Aktion als Ergebnis der Warnung, können Benutzer weiterhin auf chat, zugreifen aufrufen und/oder meeting Planungsfunktionen in Teams abhängig von den Werten der TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, die möglicherweise etwas verwirrend Endbenutzers.

Sobald automatische-Konformität von den Teams Clientumgebung basierend auf TeamsUpgradePolicy Modus verfügbar ist, wird es nicht mehr erforderlich sind, um diese Richtlinien festgelegt sein. Der Wert der TeamsUpgradePolicy Modus werden die Werte dieser spezifischen Einstellungen Vorrang. Automatische Konformität wird durch die Gruppenrichtlinieninfrastruktur müssen während der Richtlinie Lösung erreicht. Das Verhalten basierend auf Modus gewinnen bei einem Konflikt der anderen Einstellungen über die Werte AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling und AllowChannelMeetingScheduling. Nachdem Automatische Konformität angeboten wird, werden die PowerShell-Warnungen aktualisiert werden, um dem Administrator mitzuteilen, den die Clientumgebung trotz alle Werte von TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy automatisch angewendet wird.







