---
title: Migration und Interoperabilität – Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Informieren Sie sich über die grundlegenden Konzepte für die Verwaltung des Umstiegs Ihrer Organisation in Teams von Skype for Business.
localization_priority: Normal
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
ms.openlocfilehash: 7b03a31865504507db1c1b0da0fb9c30eb3e1444
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955922"
---
# <a name="coexistence-modes---reference"></a>Koexistenzmodus – Referenz

Koexistenzmodus bietet Endbenutzern eine einfache, vorhersagbare Erfahrung als Organisationen, die von Skype for Business zu Teams wechseln. Für eine Organisation, die in Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig TeamsOnly (oder ein beliebiger Modus) zugewiesen werden muss. Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen alle Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern, die TeamsOnly sind, und denjenigen, die noch nicht sind, zu gewährleisten.

Aus technischer Sicht regelt der Benutzermodus verschiedene Aspekte der Benutzererfahrung:

- *Eingehendes Routing*: in welchem Client (Teams oder Skype for Business) führen Sie eingehende Chats und Anrufe Land? 
- *Anwesenheits Veröffentlichung*: ist die Anwesenheit des Benutzers, die anderen Benutzern auf der Grundlage ihrer Aktivitäten in Microsoft Teams oder Skype for Business angezeigt wird? 
- *Besprechungsplanung*: welcher Dienst wird für das Planen neuer Besprechungen verwendet, und es wird sichergestellt, dass das richtige Add-in in Outlook vorhanden ist? TeamsUpgradePolicy regelt keine Besprechungsteilnahme. Benutzer können immer *an einer Besprechung teilnehmen* , und zwar unabhängig davon, ob es sich um eine Skype for Business-Besprechung oder eine Teams-Besprechung handelt.
- *Client Experience*: welche Funktionen stehen in Teams und/oder Skype for Business-Client zur Verfügung? Können Benutzer Anrufe und Chats in Teams, Skype for Business oder beides initiieren? Sind Teams & Kanäle verfügbar?  

Weitere Informationen zu Routing und Anwesenheits Verhalten basierend auf dem Modus finden Sie unter [Koexistenz mit Skype for Business](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence).

Im Hinblick auf die Erfahrung kann der Modus jedoch so beschrieben werden, dass die Benutzeroberfläche definiert wird:
- *Chat und Anrufe*: welcher Client wird von einem Benutzer verwendet?
- *Besprechungsplanung*: planen Benutzer neue Besprechungen als Teams oder Skype for Business-Besprechungen?
- *Verfügbarkeit der Funktionen für die Zusammenarbeit im Team-Client*. Sind Teams & Kanal-und Dateifunktionen verfügbar, während Benutzer weiterhin Skype for Business nutzen?

Die Modi sind im folgenden aufgeführt.
</br>
</br>

|Modus|Anrufen und chatten|Besprechungsplanung<sup>1</sup>|Teams & Kanäle|Anwendungsfall|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Erfordert Home in Skype for Business Online*|Microsoft Teams|Microsoft Teams|Ja|Der endgültige Zustand des Upgrades. Auch die Standardeinstellung für neue Mandanten.|
|Inselmodus|Entweder|Entweder|Ja|Standardkonfiguration. Ermöglicht einem einzelnen Benutzer die Auswertung beider Clients nebeneinander. Chats und Anrufe können in einem der beiden Clients erfolgen, sodass Benutzer stets beide Clients ausführen müssen. Um eine verwirrende oder rückläufige Skype for Business-Erfahrung zu vermeiden, werden externe (Verbund-) Kommunikationen, PSTN-Sprachdienste und Sprachanwendungen, Office-Integration und verschiedene andere Integrationen weiterhin von Skype for Business gehandhabt.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Ja|"Besprechungen zuerst". In erster Linie für lokale Organisationen, um von den Funktionen der Teambesprechung zu profitieren, wenn Sie noch nicht bereit sind, Anrufe in die Cloud zu verschieben.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Ja|Alternativer Ausgangspunkt für komplexe Organisationen, die eine strengere administrative Steuerung benötigen.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Spezielles Szenario für Organisationen mit strengen Anforderungen im Hinblick auf die Datensteuerung. Teams wird nur für die Teilnahme an Besprechungen verwendet, die von anderen Personen geplant wurden.|
||||||

</br>
</br>

**Notizen**

<sup>1</sup> die Möglichkeit, an einer vorhandenen Besprechung teilzunehmen (unabhängig davon, ob Sie in Teams oder in Skype for Business geplant ist), wird nicht durch den Modus geregelt. Standardmäßig können Benutzer immer an einer Besprechung teilnehmen, zu der Sie eingeladen wurden.

<sup>2</sup> Wenn Sie einem einzelnen Benutzer entweder TeamsOnly oder SfbWithTeamsCollabAndMeetings zuweisen, werden alle vorhandenen Skype for Business-Besprechungen, die dieser Benutzer für die Zukunft geplant hat, in Teams-Besprechungen umgewandelt. Falls gewünscht, können Sie diese Besprechungen als Skype for Business-Besprechungen belassen, indem Sie entweder angeben, ob Sie  `-MigrateMeetingsToTeams $false` TeamsUpgradePolicy gewähren möchten, oder indem Sie das Kontrollkästchen im Team-Administratorportal deaktivieren. Die Möglichkeit, Besprechungen von Skype for Business in Teams umzuwandeln, steht nicht zur Verfügung, wenn TeamsUpgradePolicy auf Mandantenebene gewährt wird. 

<sup>3</sup> zurzeit hat Teams nicht die Möglichkeit, die Funktionen Teams und Kanäle zu deaktivieren, sodass dies für jetzt aktiviert bleibt.


## <a name="using-teamsupgradepolicy"></a>Verwenden von TeamsUpgradePolicy

TeamsUpgradePolicy macht zwei wichtige Eigenschaften verfügbar: Mode und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(standardmäßig in Kursivschrift)|Beschreibung|
|---|---|---|---|
|Modus|Enumerationswert|*Inselmodus*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Gibt den Modus an, in dem der Client ausgeführt werden soll.|
|NotifySfbUsers|Boolescher Wert|*Falsch* oder wahr|Gibt an, ob ein Banner im Skype for Business-Client angezeigt wird, in dem der Benutzer informiert wird, dass Teams in Kürze Skype for Business ersetzen werden. Dies kann nicht wahr sein, wenn Mode = TeamsOnly.|
|||||

Teams stellt alle relevanten Instanzen von TeamsUpgradePolicy über integrierte, schreibgeschützte Richtlinien bereit. Daher stehen nur Get-und Grant-Cmdlets zur Verfügung. Die integrierten Instanzen sind im folgenden aufgeführt.
</br>
</br>

|Identität |Modus|NotifySfbUsers|
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

Diese Richtlinieninstanzen können entweder einzelnen Benutzern oder auf Mandantenebene gewährt werden. Beispiel:
- Wenn Sie einen Benutzer ($SipAddress) auf Teams aktualisieren möchten, gewähren Sie die "UpgradeToTeams"-Instanz:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um den gesamten Mandanten zu aktualisieren, lassen Sie den Parameter Identity aus dem Befehl Grant aus:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Benutzerfreundlichkeit des Teams-Clients bei Verwendung von Skype for Business-Modi

Wenn sich ein Nutzer in einem der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet. Um die Verwirrung des Endbenutzers zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, werden die Funktionen für Anrufe und Chats im Teams-Client automatisch deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Terminplanung in Teams automatisch deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden, und automatisch aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet. Ausführliche Informationen finden Sie unter [Teams-Clientumgebung und Konformität mit Koexistenzmodus](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Vor der Bereitstellung der automatischen Erzwingung von Teams und Kanälen Verhalten sich der SfbOnly-und der SfBWithTeamsCollab-Modus identisch.


## <a name="detailed-mode-descriptions"></a>Beschreibungen des detaillierten Modus
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inselmodus**</br>Standard|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Nutzer:</br><ul><li>Kann Chats und VoIP-Anrufe in Skype for Business-oder Microsoft Teams-Client initiieren. Hinweis: Benutzer mit Skype for Business, die sich lokal vernetzen, können unabhängig vom Modus des Empfängers nicht aus Teams initiieren, um einen anderen Skype for Business-Benutzer zu erreichen.<li>Empfängt Chats & VoIP-Anrufe, die in Skype for Business von einem anderen Nutzer in seinem Skype for Business-Client initiiert wurden.<li>Empfängt Chats & VoIP-Anrufe, die in Teams von einem anderen Benutzer in seinem Team-Client initiiert wurden, wenn Sie sich im *gleichen Mandanten*befinden.<li>Empfängt Chats & VoIP-Anrufe, die in Teams von einem anderen Benutzer in Ihrem Skype for Business-Client initiiert wurden, wenn Sie sich in einem  *Federated*-Mandanten befinden. <li>Hat die PSTN-Funktionalität wie nachstehend beschrieben:<ul><li>Wenn der Benutzer in Skype for Business lokal beheimatet ist und Enterprise-VoIP hat, werden PSTN-Anrufe immer in Skype for Business initiiert und empfangen.<li>Wenn sich der Benutzer in Skype for Business Online befindet und über ein Microsoft Phone System verfügt, initiiert und empfängt der Benutzer immer PSTN-Anrufe in Skype for Business:<ul><li>Dies geschieht, wenn der Benutzer über einen Microsoft-Anrufplan verfügt oder über Skype for Business Cloud Connector Edition oder eine lokale Bereitstellung von Skype for Business Server (Hybrid-VoIP) eine Verbindung mit dem PSTN-Netzwerk herstellt.<li>**Hinweis: das direkte Routing von Telefonsystemen wird im Modus "Inseln" nicht unterstützt.**</ul></ul><li>Empfängt Microsoft-Anrufwarteschlangen und automatische Telefonzentralen-Anrufe in Skype for Business:<ul><li>Telefonnummern, die Anrufwarteschlangen und automatischen Telefonzentralen zugewiesen sind, können im Modus "Inseln" **keine** direkten Routing Nummern für Telefonsysteme sein.</ul></ul><li>Sie können Besprechungen in Teams oder Skype for Business planen (und beide Plug-ins werden standardmäßig angezeigt).<li>Kann an einer Skype for Business-oder Teams-Besprechung teilnehmen die Besprechung wird im jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein Benutzer führt nur Skype for Business aus. Dieser Nutzer:</br><ul><li>Kann Chats und Anrufe nur über Skype for Business initiieren.<li>Empfängt alle Chats/Anrufe in Ihrem Skype for Business-Client, unabhängig davon, wo Sie initiiert wurden, es sei denn, der Initiator ist ein Team Nutzer, in dem Skype for Business lokal gehostet wird. * <li> Kann nur Skype for Business-Besprechungen planen, kann aber an Skype for Business-oder </br> \* Teams-Besprechungen teilnehmen.* Die Verwendung des Modus "Inseln" mit lokalen Benutzern wird in Verbindung mit anderen Benutzern im SfBOnly-Modus nicht empfohlen. Wenn ein Benutzer von Teams, in dem Skype for Business lokal gehostet wird, einen Anruf oder einen Chat mit einem SfBOnly-Nutzer initiiert, ist der SfBOnly-Nutzer nicht erreichbar und erhält einen verpassten Chat oder eine e-Mail-Verbindung. *|
|**SfBWithTeamsCollab**|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Nutzer:</br><ul><li>Hat die Funktionalität eines Benutzers im SfBOnly-Modus.<li>Hat Teams nur für Gruppenzusammenarbeit (Kanäle) aktiviert; Chat/Anruf-und Besprechungsplanung sind deaktiviert.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Nutzer:<ul><li>Hat die Chat-und Anruffunktion des Benutzers im SfBOnly-Modus.<li>Verfügt über Teams, die für die Gruppenzusammenarbeit aktiviert sind (Kanäle – umfasst Kanal Unterhaltungen); Chat und Anrufe sind deaktiviert.<li>Kann nur Teambesprechungen planen, kann aber an Skype for Business-oder Teams-Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SFB Online-Startseite)|Ein Benutzer führt nur Teams aus. Dieser Nutzer:<ul><li>Empfängt alle Chats und Anrufe in Ihrem Teams-Client, unabhängig davon, wo Sie initiiert wurden.<li>Kann Chats und Anrufe nur von Teams aus initiieren.<li>Sie können Besprechungen nur in Teams planen, aber Sie können an Skype for Business-oder Teams-Besprechungen teilnehmen.<li>Skype for Business-IP-Telefone weiterhin nutzen können.<br><br>*Die Verwendung des TeamsOnly-Modus in Kombination mit anderen Benutzern im Modus "Inseln" wird erst empfohlen, wenn die Einführung von Teams ausgelastet ist. Das bedeutet, dass alle Nutzer des Inseln-Modus sowohl die Teams als auch die Skype for Business-Clients aktiv verwenden und überwachen. Wenn ein TeamsOnly-Benutzer einen Anruf oder Chat mit einem Nutzer der Inselgruppe initiiert, landet dieser Anruf oder Chat im Team-Client der Inseln des Benutzers. Wenn der Benutzer der Inseln keine Teams verwendet oder überwacht, wird dieser Benutzer als offline angezeigt und ist vom TeamsOnly-Benutzer nicht erreichbar.*</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
