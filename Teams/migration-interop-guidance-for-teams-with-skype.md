---
title: Migration und Interoperabilität – Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Grundlegende Konzepte für die Verwaltung des Übergangs Ihrer Organisation zu Teams von Skype for Business zu verstehen.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6c8e96c1aeb8fabcbe42ba403c51b4a8d6f4836
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657265"
---
# <a name="coexistence-modes---reference"></a>Koexistenzmodi – Referenz

> [!Important] 
> - Nach der Einstellung von Skype for Business Online am 31. Juli 2021 ist es nicht mehr möglich, einem Benutzer, der in der Cloud verwaltet wird, einen anderen Koexistenzmodus als TeamsOnly zuzuweisen. Wie vor der Einstellung können Benutzern, die in Skype for Business Server lokal verwaltet werden, *andere Modus als* TeamsOnly zugewiesen werden. 

Koexistenzmodi bieten Endbenutzern eine einfache, vorhersehbare Erfahrung, wenn Organisationen von Skype for Business zu Teams wechseln. Für eine Organisation, die zu Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, obwohl nicht allen Benutzern gleichzeitig TeamsOnly (oder ein beliebiger Modus) zugewiesen werden muss. Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern zu gewährleisten, die TeamsOnly sind, und denen, die noch nicht vorhanden sind.

Aus technischer Sicht steuert der Modus eines Benutzers mehrere Aspekte der Benutzererfahrung:

- *Eingehendes Routing*: In welchem Client (Teams oder Skype for Business) landen eingehende Chats und Anrufe? 
- *Veröffentlichung von Anwesenheitsinformationen*: Ist die Anwesenheit des Benutzers, die anderen Benutzern angezeigt wird, basierend auf seiner Aktivität in Teams oder Skype for Business? 
- *Besprechungsplanung*: Welcher Dienst wird verwendet, um neue Besprechungen zu planen und sicherzustellen, dass das richtige Add-In in Outlook vorhanden ist? TeamsUpgradePolicy steuert nicht die Teilnahme an Besprechungen. Benutzer können jederzeit *an* jeder Besprechung teilnehmen, ganz gleich, ob es sich um eine Skype for Business-Besprechung oder eine Teams-Besprechung handelt.
- *Clientumgebung*: Welche Funktionen sind in Teams und/oder Skype for Business Client verfügbar? Können Benutzer Anrufe und Chats in Teams, Skype for Business oder beidem initiieren? Ist die Teams & Channels-Oberfläche verfügbar?  

Weitere Informationen zum Routing- und Anwesenheitsverhalten basierend auf dem Modus finden Sie unter [Koexistenz mit Skype for Business](./coexistence-chat-calls-presence.md).

Aus Erfahrungsperspektive kann der Modus jedoch als Definition der Benutzeroberfläche für Folgendes beschrieben werden:
- *Chat und Anrufe*: Welchen Client verwendet ein Benutzer?
- *Besprechungsplanung*: Planen Benutzer neue Besprechungen als Teams oder Skype for Business Besprechungen?
- *Verfügbarkeit von Funktionen für die Zusammenarbeit im Teams-Client*. Ist die Funktion "Teams & Kanäle und Dateien" verfügbar, während Benutzer noch über Skype for Business verfügen?

Die Modi sind unten aufgeführt. Cloudbenutzer müssen TeamsOnly sein, und Benutzer, die lokal verwaltet werden, müssen einen anderen Modus als TeamsOnly verwenden. 
</br>
</br>

|Modus|Anrufe und Chats|Besprechungsplanung<sup>1</sup>|Teams-&-Kanäle|Anwendungsfall|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Nur möglich, wenn der Benutzer kein lokales Konto in Skype for Business Server*|Teams|Microsoft Teams|Ja|Der endgültige Status des Upgrades. Die Standardeinstellung für neue Mandanten, es sei denn, es wird eine Hybridkonfiguration erkannt.|
|Inselmodus|Entweder|Entweder|Ja|Standardkonfiguration für Hybridorganisationen. Ermöglicht es einem einzelnen Benutzer, beide Clients nebeneinander auszuwerten. Chats und Anrufe können in beiden Clients landen, sodass Benutzer immer beide Clients ausführen müssen. Um eine verwirrende oder zurückgestufte Skype for Business Erfahrung zu vermeiden, werden externe (Verbund-)Kommunikation, PSTN-VoIP-Dienste und Sprachanwendungen, Office-Integration und mehrere andere Integrationen weiterhin von Skype for Business behandelt.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Ja|"Besprechungen zuerst". In erster Linie für lokale Organisationen, die von den Teams-Besprechungsfunktionen profitieren können, wenn sie noch nicht bereit sind, Anrufe in die Cloud zu verschieben.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Ja|Alternativer Ausgangspunkt für komplexe Organisationen, die eine engere administrative Kontrolle benötigen.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Spezielles Szenario für Organisationen mit strengen Anforderungen an die Datensteuerung. Teams wird nur verwendet, um an Besprechungen teilzunehmen, die von anderen geplant werden.|
||||||

</br>
</br>

**Notizen:**

<sup>1</sup> Die Möglichkeit, an einer vorhandenen Besprechung teilzunehmen (ob in Teams geplant oder in Skype for Business), wird nicht durch den Modus gesteuert. Standardmäßig können Benutzer jederzeit an jeder Besprechung teilnehmen, zu der sie eingeladen wurden.

<sup>2</sup> Standardmäßig werden beim Zuweisen von TeamsOnly oder SfbWithTeamsCollabAndMeetings zu einem einzelnen Benutzer alle vorhandenen Skype for Business Besprechungen, die von diesem Benutzer für die Zukunft geplant wurden, in Teams-Besprechungen konvertiert. Wenn gewünscht, können Sie diese Besprechungen als Skype for Business Besprechungen belassen, indem Sie entweder angeben`-MigrateMeetingsToTeams $false`, wann TeamsUpgradePolicy gewährt wird, oder indem Sie das Kontrollkästchen im Teams-Admin-Portal deaktivieren. Die Möglichkeit zum Konvertieren von Besprechungen von Skype for Business in Teams ist nicht verfügbar, wenn TeamsUpgradePolicy mandantenweit gewährt wird. 

<sup>3</sup> Derzeit verfügt Teams nicht über die Möglichkeit, die Teams- und Kanalfunktionen zu deaktivieren, sodass dies vorerst aktiviert bleibt.


## <a name="using-teamsupgradepolicy"></a>Verwenden von TeamsUpgradePolicy

TeamsUpgradePolicy macht zwei wichtige Eigenschaften verfügbar: Mode und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(Standard kursiv)|Beschreibung|
|---|---|---|---|
|Modus|Enum|*Inselmodus*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Gibt den Modus an, in dem der Client ausgeführt werden soll.|
|NotifySfbUsers|Boolescher Wert|*Falsch* oder wahr|Gibt an, ob im Skype for Business Client ein Banner angezeigt werden soll, das den Benutzer darüber informiert, dass Teams Skype for Business bald ersetzen wird. Dies kann nicht wahr sein, wenn Mode=TeamsOnly.|
|||||

Teams stellt alle relevanten Instanzen von TeamsUpgradePolicy über integrierte, schreibgeschützte Richtlinien bereit. Daher sind nur Get- und Grant-Cmdlets verfügbar. Die integrierten Instanzen sind unten aufgeführt.
</br>
</br>

|Identity|Modus|NotifySfbUsers|
|---|---|---|
|Inselmodus|Inselmodus|Falsch|
|IslandsWithNotify|Inselmodus|Wahr|
|SfBOnly|SfBOnly|Falsch|
|SfBOnlyWithNotify|SfBOnly|Wahr|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falsch|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Wahr|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falsch|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Wahr|
|UpgradeToTeams|TeamsOnly|Falsch|
|Global</br>*Standard*|Inselmodus|Falsch|
||||

Diese Richtlinieninstanzen können entweder einzelnen Benutzern oder mandantenweit gewährt werden. Zum Beispiel: 
- Um einen Benutzer ($SipAddress) auf Teams zu aktualisieren, gewähren Sie die "UpgradeToTeams"-Instanz:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um den gesamten Mandanten zu aktualisieren, lassen Sie den Identitätsparameter aus dem Grant-Befehl aus:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Die Benutzererfahrung des Teams-Clients bei Verwendung Skype for Business Modi

Wenn sich ein Benutzer in einem der Skype for Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business Client des Benutzers weitergeleitet. Um Verwirrung bei Endbenutzern zu vermeiden und das ordnungsgemäße Routing sicherzustellen, werden Anruf- und Chatfunktionen im Teams-Client automatisch deaktiviert, wenn sich ein Benutzer in einem der Skype for Business Modi befindet. Ebenso wird die Besprechungsplanung in Teams automatisch deaktiviert, wenn sich Benutzer im SfBOnly- oder SfBWithTeamsCollab-Modus befinden, und automatisch aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet. Ausführliche Informationen finden Sie unter [Teams-Clientumgebung und Konformität mit Koexistenzmodi](./teams-client-experience-and-conformance-to-coexistence-modes.md).

> [!Note] 
> - Vor der Automatischen Erzwingung von Teams und Kanälen verhalten sich die Modi SfbOnly und SfBWithTeamsCollab gleich.


## <a name="detailed-mode-descriptions"></a>Detaillierte Modusbeschreibungen
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inselmodus**</br>(nur lokal)|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Benutzer:</br><ul><li>Kann Chats und VoIP-Anrufe in Skype for Business- oder Teams-Client initiieren. Hinweis: Benutzer mit Skype for Business lokal verwalteten Benutzern können nicht von Teams aus initiieren, um einen anderen Skype for Business Benutzer zu erreichen, unabhängig vom Modus des Empfängers.<li>Empfängt Chats & VoIP-Anrufe, die in Skype for Business von einem anderen Benutzer in ihrem Skype for Business-Client initiiert wurden.<li>Empfängt Chats & VoIP-Anrufe, die in Teams von einem anderen Benutzer in ihrem Teams-Client initiiert werden, wenn er sich im *selben Mandanten befindet*.<li>Empfängt Chats & VoIP-Anrufe, die von einem anderen Benutzer in ihrem Skype for Business-Client in Teams initiiert wurden, wenn er sich in einem *Verbundmandanten befindet*. <li>Verfügt über PSTN-Funktionen wie unten beschrieben:<ul><li>Wenn der Benutzer in Skype for Business lokal verwaltet wird und über Enterprise-VoIP verfügt, werden PSTN-Anrufe immer in Skype for Business initiiert und empfangen.<li>Wenn der Benutzer auf Skype for Business Online verwaltet wird und über das Microsoft-Telefonsystem verfügt, initiiert und empfängt der Benutzer PSTN-Anrufe immer in Skype for Business:<ul><li>Dies geschieht unabhängig davon, ob der Benutzer über einen Microsoft-Anrufplan verfügt oder eine Verbindung mit dem PSTN-Netzwerk über Skype for Business Cloud Connector Edition oder eine lokale Bereitstellung von Skype for Business Server (Hybrid voice) herstellt.<li>**Hinweis: Das Direct Routing des Telefonsystems wird im Inselmodus nicht unterstützt.**</ul></ul><li>Empfängt Microsoft-Anrufwarteschleifen und Anrufe der automatischen Telefonzentrale in Skype for Business:<ul><li>Telefonnummern, die Anrufwarteschleifen und automatischen Telefonzentralen zugewiesen sind, **können im** Inselmodus keine Telefonnummern für das Direkte Routing des Telefonsystems sein.</ul></ul><li>Kann Besprechungen in Teams oder Skype for Business planen (und beide Plug-Ins werden standardmäßig angezeigt).<li>Kann an jeder Skype for Business- oder Teams-Besprechung teilnehmen; die Besprechung wird im jeweiligen Client geöffnet.</ul>|
|**SfBOnly**</br>(nur lokal)|Ein Benutzer führt nur Skype for Business aus. Dieser Benutzer:</br><ul><li>Chats und Anrufe können nur von Skype for Business initiiert werden.<li>Empfängt jeden Chat/Anruf in ihrem Skype for Business Client, unabhängig davon, wo er initiiert wurde, es sei denn, der Initiator ist ein Teams-Benutzer mit Skype for Business lokal verwaltet.*<li> Kann nur Skype for Business Besprechungen planen, aber an Skype for Business oder Teams-Besprechungen teilnehmen.</br>\** Die Verwendung des Inselmodus mit lokalen Benutzern wird in Kombination mit anderen Benutzern im SfBOnly-Modus nicht empfohlen. Wenn ein Teams-Benutzer mit Skype for Business lokal verwaltet wird, einen Anruf oder Chat mit einem SfBOnly-Benutzer initiiert, ist der SfBOnly-Benutzer nicht erreichbar und erhält einen verpassten Chat oder eine Anruf-E-Mail.*|
|**SfBWithTeamsCollab**</br>(nur lokal)|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Benutzer:</br><ul><li>Verfügt über die Funktionalität eines Benutzers im SfBOnly-Modus.<li>Hat Teams nur für die Gruppenzusammenarbeit aktiviert (Kanäle); Chat-/Anruf-/Besprechungsplanung ist deaktiviert.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(nur lokal)|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Benutzer:<ul><li>Verfügt über die Chat- und Anruffunktion des Benutzers im SfBOnly-Modus.<li>Hat Teams für die Gruppenzusammenarbeit aktiviert (Kanäle – umfasst Kanalunterhaltungen); Chat und Anrufe sind deaktiviert.<li>Kann nur Teams-Besprechungen planen, aber an Skype for Business- oder Teams-Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(nur Cloudbenutzer)|Ein Benutzer führt nur Teams aus. Dieser Benutzer:<ul><li>Empfängt Chats und Anrufe in ihrem Teams-Client, unabhängig davon, wo sie initiiert wurden.<li>Chats und Anrufe können nur von Teams initiiert werden.<li>Kann nur Besprechungen in Teams planen, aber an Skype for Business- oder Teams-Besprechungen teilnehmen.<li>Kann weiterhin Skype for Business IP-Telefone verwenden.<br><br>*Die Verwendung des TeamsOnly-Modus in Kombination mit anderen Benutzern im Inselmodus wird erst empfohlen, wenn die Einführung von Teams gesättigt ist. Das heißt, alle Benutzer im Inselmodus verwenden und überwachen aktiv sowohl die Teams- als auch Skype for Business-Clients. Wenn ein TeamsOnly-Benutzer einen Anruf oder Chat mit einem Islands-Benutzer initiiert, wird dieser Anruf oder Chat im Teams-Client des Islands-Benutzers angezeigt. Wenn der Islands-Benutzer Teams nicht verwendet oder überwacht, wird dieser Benutzer offline angezeigt und kann vom TeamsOnly-Benutzer nicht erreicht werden.* <li>In einigen Fällen können Teilnehmer im TeamsOnly-Modus nur mit Skype for Business-Web-App oder der Skype-Besprechungs-App als anonymer Benutzer an Skype for Business Besprechungen teilnehmen. Dieser Fall gilt schließlich für alle Benutzer im TeamsOnly-Modus. Weitere Informationen finden Sie [unter Skype for Business Online-Einstellung](skype-for-business-online-retirement.md#what-to-expect-post-retirement).</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](./coexistence-chat-calls-presence.md)

[Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
