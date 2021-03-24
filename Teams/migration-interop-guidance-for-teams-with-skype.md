---
title: Migration und Interoperabilität – Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Verstehen Sie die grundlegenden Konzepte für die Verwaltung des Übergangs Ihrer Organisation zu Teams von Skype for Business.
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
ms.openlocfilehash: c3a446213a5c10126b9ae42986fe2fa1986bc9e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098331"
---
# <a name="coexistence-modes---reference"></a>Koexistenzmodi – Referenz

Koexistenzmodi bieten Endbenutzern eine einfache, vorhersagbare Benutzererfahrung, während Organisationen von Skype for Business zu Teams wechseln. Für eine Organisation, die zu Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, obwohl nicht allen Benutzern TeamsOnly (oder ein beliebiger Modus) gleichzeitig zugewiesen werden muss. Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern zu gewährleisten, die TeamsOnly sind und denen, die es noch nicht sind.

Aus technischer Sicht bestimmt der Modus eines Benutzers mehrere Aspekte der Benutzererfahrung:

- *Eingehendes Routing:* In welchem Client (Teams oder Skype for Business) werden eingehende Chats und Anrufe an landen? 
- *Anwesenheitsveröffentlichung:* Ist die Anwesenheit des Benutzers, die anderen Benutzern angezeigt wird, basierend auf seinen Aktivitäten in Teams oder Skype for Business? 
- *Besprechungsplanung:* Welcher Dienst wird verwendet, um neue Besprechungen zu planen und sicherzustellen, dass das richtige Add-In in Outlook vorhanden ist? TeamsUpgradePolicy regelt die Teilnahme an Besprechungen nicht. Benutzer können immer *an jeder* Besprechung teilnehmen, ganz gleich, ob es sich um eine Skype for Business-Besprechung oder eine Teams-Besprechung geht.
- *Clienterfahrung:* Welche Funktionen stehen in Teams und/oder skype for Business-Client zur Verfügung? Können Benutzer Anrufe und Chats in Teams, Skype for Business oder beides initiieren? Ist die & von Teams verfügbar?  

Weitere Informationen zum Routing- und Anwesenheitsverhalten basierend auf dem Modus finden Sie unter [Koexistenz mit Skype for Business.](./coexistence-chat-calls-presence.md)

Aus Erfahrungssicht kann der Modus jedoch so beschrieben werden, dass er die Benutzererfahrung für die folgenden Aufgaben definiert:
- *Chat und Anrufe:* Welchen Client verwendet ein Benutzer?
- *Besprechungsplanung:* Planen Benutzer neue Besprechungen als Teams- oder Skype for Business-Besprechungen?
- *Verfügbarkeit der Zusammenarbeitsfunktionalität im Teams-Client*. Steht die & Kanäle und Dateien von Teams zur Verfügung, während Die Benutzer skype for Business weiterhin nutzen?

Die Modi sind unten aufgeführt.
</br>
</br>

|Modus|Anrufe und Chats|Besprechungsplanung<sup>1</sup>|Teams & Kanäle|Use Case|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Erfordert die Startseite in Skype for Business Online*|Microsoft Teams|Microsoft Teams|Ja|Der endgültige Status des Upgrades. Auch die Standardeinstellung für neue Mandanten.|
|Inseln|Eine der beiden|Eine der beiden|Ja|Standardkonfiguration. Ermöglicht es einem einzelnen Benutzer, beide Clients nebeneinander auszuwerten. Chats und Anrufe können in jedem Client landen, sodass Benutzer immer beide Clients ausführen müssen. Um eine verwirrende oder regressierte Skype for Business-Erfahrung zu vermeiden, werden externe (Verbund-) Kommunikationen, PSTN-Sprachdienste und Sprachanwendungen, die Office-Integration und mehrere andere Integrationen weiterhin von Skype for Business behandelt.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Microsoft Teams|Ja|"Besprechungen zuerst". In erster Linie für lokale Organisationen, die von den Funktionen von Teams-Besprechungen profitieren, wenn sie noch nicht bereit sind, Anrufe in die Cloud zu verschieben.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Ja|Alternativer Ausgangspunkt für komplexe Organisationen, die eine engere verwaltungstechnische Kontrolle benötigen.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Spezielles Szenario für Organisationen mit strengen Anforderungen an die Datensteuerung. Teams wird nur verwendet, um an Besprechungen teilzunehmen, die von anderen Personen geplant wurden.|
||||||

</br>
</br>

**Hinweise:**

<sup>1</sup> Die Möglichkeit, an einer vorhandenen Besprechung (unabhängig davon, ob sie in Teams oder In Skype for Business geplant ist) teilnehmen zu können, unterliegt nicht dem Modus. Standardmäßig können Benutzer immer an jeder Besprechung teilnehmen, zu der sie eingeladen wurden.

<sup>2</sup> Standardmäßig werden beim Zuweisen von TeamsOnly oder SfbWithTeamsCollabAndMeetings zu einem einzelnen Benutzer alle vorhandenen Skype for Business-Besprechungen, die von diesem Benutzer für die Zukunft geplant werden, in Teams-Besprechungen konvertiert. Bei Bedarf können Sie diese Besprechungen als Skype for Business-Besprechungen verlassen, indem Sie entweder angeben, wann TeamsUpgradePolicy gewährt wird, oder indem Sie das Kontrollkästchen im Teams Admin-Portal  `-MigrateMeetingsToTeams $false` deaktivieren. Die Möglichkeit, Besprechungen von Skype for Business in Teams zu konvertieren, ist nicht verfügbar, wenn TeamsUpgradePolicy mandantenweit gewährt wird. 

<sup>3</sup> Derzeit ist Teams nicht in der Lage, die Funktionen "Teams" und "Kanäle" zu deaktivieren, daher bleibt dies vorer zeit aktiviert.


## <a name="using-teamsupgradepolicy"></a>Verwenden von TeamsUpgradePolicy

TeamsUpgradePolicy macht zwei wichtige Eigenschaften verfügbar: Modus und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(standard in italic)|Beschreibung|
|---|---|---|---|
|Modus|Aufzählen|*Inseln*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Gibt den Modus an, in dem der Client ausgeführt werden soll.|
|NotifySfbUsers|Boolescher Wert|*Falsch* oder wahr|Gibt an, ob im Skype for Business-Client ein Banner angezeigt werden soll, das den Benutzer darüber informiert, dass Teams Skype for Business bald ersetzen wird. Dies kann nicht zutreffen, wenn Mode=TeamsOnly.|
|||||

Teams stellt alle relevanten Instanzen von TeamsUpgradePolicy über integrierte, schreibgeschützte Richtlinien zur Verf lichung zur Schreibgeschütztkeit zur. Daher sind nur Get- und Grant-Cmdlets verfügbar. Die integrierten Instanzen sind unten aufgeführt.
</br>
</br>

|Identität |Modus|NotifySfbUsers|
|---|---|---|
|Inseln|Inseln|Falsch|
|IslandsWithNotify|Inseln|Wahr|
|SfBOnly|SfBOnly|Falsch|
|SfBOnlyWithNotify|SfBOnly|Wahr|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falsch|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Wahr|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falsch|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Wahr|
|UpgradeToTeams|TeamsOnly|Falsch|
|Global</br>*Standard*|Inseln|Falsch|
||||

Diese Richtlinieninstanzen können entweder einzelnen Benutzern oder mandantenweit gewährt werden. Beispiel:
- Zum Upgrade eines Benutzers ($SipAddress) auf Teams gewähren Sie die Instanz "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Wenn Sie ein Upgrade des gesamten Mandanten durchführen möchten, geben Sie den Identitätsparameter aus dem Befehl "Grant" aus:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Benutzerfreundlichkeit des Teams-Clients bei Verwendung von Skype for Business-Modi

Wenn sich ein Benutzer in einem der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers geroutet. Um Verwirrung beim Endbenutzer zu vermeiden und die ordnungsgemäße Weiterleitung sicherzustellen, werden Anruf- und Chatfunktionen im Teams-Client automatisch deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Besprechungsplanung in Teams automatisch deaktiviert, wenn sich Benutzer im SfBOnly- oder SfBWithTeamsCollab-Modus befinden und automatisch aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet. Details finden Sie unter [Teams-Clienterfahrung und Konformität mit Koexistenzmodi.](./teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!Note] 
> - Vor der Bereitstellung der automatischen Erzwingung von Teams und Kanälen verhalten sich die Modi SfbOnly und SfBWithTeamsCollab gleich.


## <a name="detailed-mode-descriptions"></a>Detaillierte Modusbeschreibungen
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inseln**</br>(Standard)|Ein Benutzer führt Sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Benutzer:</br><ul><li>Kann Chats und VoIP-Anrufe entweder im Skype for Business- oder im Teams-Client initiieren. Hinweis: Benutzer mit lokalen Skype for Business-Heimen können nicht von Teams aus starten, um einen anderen Skype for Business-Benutzer zu erreichen, unabhängig vom Modus des Empfängers.<li>Empfängt Chats & VoIP-Anrufe, die in Skype for Business von einem anderen Benutzer in ihrem Skype for Business-Client initiiert wurden.<li>Empfängt Chats & VoIP-Anrufe, die in Teams von einem anderen Benutzer in ihrem Teams-Client initiiert wurden, wenn sie sich im gleichen *Mandanten befinden.*<li>Empfängt Chats & VoIP-Anrufe, die von einem anderen Benutzer in ihrem Skype for Business-Client in Teams initiiert wurden, wenn sie sich in einem *Verbundclient befinden.* <li>Verfügt über pstN-Funktionen, wie unten angegeben:<ul><li>Wenn der Benutzer in Skype for Business lokal zu Hause ist und über Enterprise-VoIP verfügt, werden in Skype for Business immer PSTN-Anrufe initiiert und empfangen.<li>Wenn der Benutzer in Skype for Business Online zu Hause ist und über Microsoft Phone System verfügt, initiiert und empfängt der Benutzer in Skype for Business immer FESTNETZanrufe:<ul><li>Dies geschieht, unabhängig davon, ob der Benutzer über einen Microsoft-Anrufplan verfügt oder über Skype for Business Cloud Connector Edition oder eine lokale Bereitstellung von Skype for Business Server (Hybrid voice) eine Verbindung mit dem PSTN-Netzwerk herstellt.<li>**Hinweis: Das direkte Routing des Telefonsystems wird im Inselmodus nicht unterstützt.**</ul></ul><li>Empfängt Microsoft-Anrufwarteschlangen und anrufe mit automatischer Telefonkonferenz in Skype for Business:<ul><li>Telefonnummern, die Anrufwarteschlangen und automatischen Telefonwarteschlangen zugewiesen sind, **können** keine Telefonsystem-Direktroutingnummern im Inselmodus sein.</ul></ul><li>Kann Besprechungen in Teams oder Skype for Business planen (und standardmäßig werden beide Plug-Ins angezeigt).<li>Kann an jeder Skype for Business- oder #A0 teilnehmen. die Besprechung im jeweiligen Client geöffnet wird.</ul>|
|**SfBOnly**|Ein Benutzer führt nur Skype for Business aus. Dieser Benutzer:</br><ul><li>Kann nur Chats und Anrufe aus Skype for Business initiieren.<li>Empfängt jeden Chat/Anruf in seinem Skype for Business-Client, unabhängig davon, wo initiiert wurde, es sei denn, der Initiator ist ein Teams-Benutzer, bei dem Skype for Business lokal zuhause ist. *<li> Kann nur Skype for Business-Besprechungen planen, aber </br> \* an Skype for Business- oder Teams-Besprechungen teilnehmen.* Die Verwendung des Inselmodus mit lokalen Benutzern wird nicht in Kombination mit anderen Benutzern im SfBOnly-Modus empfohlen. Wenn ein #A0 mit einem lokalen Skype for #A1 einen Anruf oder Chat mit einem SfBOnly-Benutzer initiiert, ist der SfBOnly-Benutzer nicht erreichbar und empfängt eine verpasste Chat- oder Anruf-E-Mail.*|
|**SfBWithTeamsCollab**|Ein Benutzer führt Sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Benutzer:</br><ul><li>Verfügt über die Funktionalität eines Benutzers im SfBOnly-Modus.<li>Hat Teams nur für die Gruppenzusammenarbeit (Kanäle) aktiviert; Die Chat-/Anruf-/Besprechungsplanung ist deaktiviert.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Ein Benutzer führt Sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Benutzer:<ul><li>Verfügt über die Chat- und Anruffunktionen des Benutzers im SfBOnly-Modus.<li>Hat Teams für die Gruppenzusammenarbeit aktiviert (Kanäle – einschließlich Kanalunterhaltungen); Chat und Anrufe sind deaktiviert.<li>Kann nur Teams-Besprechungen planen, aber an Skype for Business- oder Teams-Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SfB Online Home)|Ein Benutzer führt nur Teams aus. Dieser Benutzer:<ul><li>Empfängt Chats und Anrufe in ihrem Teams-Client, unabhängig davon, wo initiiert wurde.<li>Kann nur Chats und Anrufe von Teams initiieren.<li>Kann Besprechungen nur in Teams planen, aber an Skype for Business- oder Teams-Besprechungen teilnehmen.<li>Kann weiterhin Skype for Business-IP-Telefone verwenden.<br><br>*Die Verwendung des TeamsOnly-Modus in Kombination mit anderen Benutzern im Inselmodus wird erst empfohlen, wenn die #A0 gesättigt ist. Das bedeutet, dass alle Benutzer des Islands-Modus sowohl die Teams- als auch die Skype for Business-Clients aktiv verwenden und überwachen. Wenn ein TeamsOnly-Benutzer einen Anruf oder Chat mit einem #A0 initiiert, landet dieser Anruf oder Chat im #A0 des Islands-Benutzers. wenn der Benutzer "Inseln" Teams nicht verwendet oder überwacht, wird dieser Benutzer offline angezeigt und kann vom TeamsOnly-Benutzer nicht erreicht werden.*</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](./coexistence-chat-calls-presence.md)

[Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)