---
title: Migration und Interoperabilität – Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Machen Sie sich mit den grundlegenden Konzepten für die Verwaltung des Übergangs Ihrer Organisation Teams Geschäfts Skype for Business.
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

Koexistenzmodi bieten eine einfache, vorhersehbare Erfahrung für Endbenutzer, wenn Organisationen von einem Skype for Business zu Teams. Für eine Organisation, die zu Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, obwohl nicht allen Benutzern TeamsOnly (oder ein beliebiger Modus) gleichzeitig zugewiesen werden muss. Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersehbare Kommunikation zwischen Benutzern zu gewährleisten, die TeamsOnly sind und personen, die es noch nicht sind.

Aus technischer Sicht bestimmt der Benutzermodus verschiedene Aspekte der Benutzererfahrung:

- *Eingehendes Routing:* In welchem Client (Teams oder Skype for Business) werden eingehende Chats und Anrufe landen? 
- *Veröffentlichung der* Anwesenheitsinformationen: Werden die Anwesenheitsinformationen des Benutzers für andere Benutzer basierend auf ihren Aktivitäten in Teams oder Skype for Business? 
- *Besprechungsplanung:* Welcher Dienst wird verwendet, um neue Besprechungen zu planen und sicherzustellen, dass das richtige Add-In in der Besprechung vorhanden Outlook? Der Beitritt zur Besprechung wird von TeamsUpgradePolicy nicht geregelt. Benutzer können jederzeit *an jeder* Besprechung teilnehmen, ganz gleich, ob es sich um Skype for Business Besprechung oder Teams Besprechungssitzungen geht.
- *Clienterfahrung:* Welche Funktionen sind in Teams und/oder im Skype for Business verfügbar? Können Benutzer Anrufe und Chats in einer Teams, einer Skype for Business oder in beiden Richtungen initiieren? Steht Teams & Kanälen zur Verfügung?  

Weitere Informationen zum Routing und Anwesenheitsverhalten basierend auf dem Modus finden Sie unter [Koexistenz mit Skype for Business.](./coexistence-chat-calls-presence.md)

Aus Erfahrungssicht lässt sich der Modus jedoch so beschreiben, dass er die Erfahrung für die folgenden Aufgaben definiert:
- *Chat und Anrufe:* Welchen Client verwendet ein Benutzer?
- *Besprechungsplanung:* Planen Benutzer neue Besprechungen Teams Besprechungen Skype for Business Besprechungen?
- *Verfügbarkeit der Zusammenarbeitsfunktionalität im Teams Client.* Sind Teams & Kanäle und Dateien verfügbar, während Benutzer weiterhin über Skype for Business?

Die Modi sind unten aufgeführt.
</br>
</br>

|Modus|Anrufe und Chats|Besprechungsplanung<sup>1</sup>|Teams & Channels|Use Case|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Erfordert die Startseite in Skype for Business Online*|Microsoft Teams|Microsoft Teams|Ja|Der endgültige Status des Upgrades. Auch die Standardeinstellung für neue Mandanten.|
|Inselmodus|Eine der beiden|Eine der beiden|Ja|Standardkonfiguration. Ermöglicht es einem einzelnen Benutzer, beide Clients nebeneinander auszuwerten. Chats und Anrufe können in beiden Clients landen, sodass Benutzer immer beide Clients ausführen müssen. Um verwirrende oder regressierte Skype for Business-Benutzererfahrungen zu vermeiden, werden externe Kommunikation (Verbundkommunikation), PSTN-Sprachdienste und -Sprachanwendungen, Office-Integration und mehrere andere Integrationen weiterhin von der Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Microsoft Teams|Ja|"Besprechungen zuerst". In erster Linie für lokale Organisationen, die von Teams Besprechungsfunktionen profitieren können, wenn sie noch nicht bereit sind, Anrufe in die Cloud zu verschieben.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Ja|Alternativer Ausgangspunkt für komplexe Organisationen, die eine engere administrative Kontrolle benötigen.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Spezielles Szenario für Organisationen, die strenge Anforderungen im Bereich der Datensteuerung haben. Teams wird nur für die Teilnahme an Besprechungen verwendet, die von anderen personen geplant wurden.|
||||||

</br>
</br>

**Hinweise:**

<sup>1</sup> Die Möglichkeit zur Teilnahme an einer vorhandenen Besprechung (unabhängig davon, ob sie in Teams oder Skype for Business geplant ist) wird nicht vom Modus bestimmt. Standardmäßig können Benutzer immer an jeder Besprechung teilnehmen, zu der sie eingeladen wurden.

<sup>2</sup> Standardmäßig werden bei der Zuweisung von TeamsOnly oder SfbWithTeamsCollabAndMeetings zu einem einzelnen Benutzer alle vorhandenen Skype for Business-Besprechungen, die von diesem Benutzer für die Zukunft geplant werden, in Teams konvertiert. Bei Bedarf können Sie diese Besprechungen als Skype for Business-Besprechungen be lassen, indem Sie entweder angeben, wenn Sie TeamsUpgradePolicy gewähren, oder indem Sie das Kontrollkästchen im `-MigrateMeetingsToTeams $false` Teams-Verwaltungsportal deaktivieren. Die Möglichkeit zum Konvertieren von Besprechungen von Skype for Business in Teams ist nicht verfügbar, wenn TeamsUpgradePolicy mandantenweit gewährt wird. 

<sup>3</sup> Derzeit Teams nicht über die Möglichkeit, die Funktionen "Teams" und "Kanäle" zu deaktivieren, daher bleibt dies vorer zeit aktiviert.


## <a name="using-teamsupgradepolicy"></a>Verwenden von TeamsUpgradePolicy

TeamsUpgradePolicy macht zwei wichtige Eigenschaften verfügbar: Modus und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(standardmäßig in "Italic" (Standardformat)|Beschreibung|
|---|---|---|---|
|Modus|Enumeration|*Inselmodus*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Gibt den Modus an, in dem der Client ausgeführt werden soll.|
|NotifySfbUsers|Boolescher Wert|*FALSCH* oder WAHR|Gibt an, ob im Client des Skype for Business ein Banner angezeigt werden soll, das den Benutzer darüber informiert, dass Teams in Kürze die Skype for Business. Dies kann nicht zutreffen, wenn "Mode=TeamsOnly" verwendet wird.|
|||||

Teams bietet alle relevanten Instanzen von TeamsUpgradePolicy über integrierte, schreibgeschützte Richtlinien. Daher sind nur Get- und Grant-Cmdlets verfügbar. Die integrierten -Instanzen sind nachfolgend aufgeführt.
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

Diese Richtlinieninstanzen können entweder einzelnen Benutzern oder mandantenweit gewährt werden. Beispiel:
- Um einen Benutzer ($SipAddress) auf eine Teams zu aktualisieren, erteilen Sie die Instanz "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um ein Upgrade für den gesamten Mandanten auszuführen, geben Sie im Befehl "Erteilen" den Identitätsparameter aus:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Die Teams client-Benutzererfahrung bei Der Verwendung Skype for Business Modi

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers geroutet. Um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäßes Routing zu sorgen, werden Anruf- und Chatfunktionen im Teams-Client automatisch deaktiviert, wenn sich ein Benutzer in einem der Skype for Business befindet. Ebenso wird die Besprechungsplanung in Teams automatisch deaktiviert, wenn sich Benutzer im Modus SfBOnly oder SfBWithTeamsCollab befinden, und wird automatisch aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet. Details finden Sie unter [Teams und Konformität mit Koexistenzmodi.](./teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!Note] 
> - Vor der Bereitstellung der automatischen Erzwingung von Teams und Kanälen verhalten sich die Modi SfbOnly und SfBWithTeamsCollab gleich.


## <a name="detailed-mode-descriptions"></a>Detaillierte Modusbeschreibungen
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inselmodus**</br>(Standard)|Ein Benutzer führt Skype for Business und Teams nebeneinander aus. Dieser Benutzer:</br><ul><li>Sie können Chats und VoIP-Anrufe entweder im Skype for Business oder im Teams einleiten. Hinweis: Benutzer mit lokal Skype for Business einem Konto können unabhängig vom Modus des Empfängers nicht Teams, um einen anderen Skype for Business-Benutzer zu erreichen.<li>Empfängt Chats & VoIP-Anrufen, die in einer Skype for Business von einem anderen Benutzer in ihrem Skype for Business initiiert wurden.<li>Empfängt Chats & VoIP-Anrufen, die in Teams von einem anderen Benutzer in ihrem Teams-Client initiiert wurden, wenn sie sich im *gleichen Mandanten befinden.*<li>Empfängt Chats & VoIP-Anrufen, die in Teams von einem anderen Benutzer in ihrem Skype for Business-Client initiiert wurden, wenn er sich in einem *Partner-Mandanten befinden.* <li>Die PSTN-Funktionalität ist wie nachstehend beschrieben:<ul><li>Wenn der Benutzer lokal Skype for Business wird und über Enterprise-VoIP verfügt, werden PSTN-Anrufe immer in der lokalen Skype for Business.<li>Wenn der Benutzer auf Skype for Business Online gespeichert ist und über Microsoft-Telefon System verfügt, initiiert und empfängt der Benutzer pstN-Anrufe immer in Skype for Business:<ul><li>Dies geschieht, unabhängig davon, ob der Benutzer über einen Microsoft-Anrufplan verfügt oder über Skype for Business Cloud Connector Edition oder eine lokale Bereitstellung von Skype for Business Server (Hybrid Voice) eine Verbindung mit dem PSTN-Netzwerk herstellt.<li>**Hinweis: Telefonsystem direktes Routing wird im Islands-Modus nicht unterstützt.**</ul></ul><li>Empfängt Anrufe in Microsoft-Anrufwarteschleifen und anrufe der automatischen Telefon Skype for Business:<ul><li>Telefon Nummern, die Anrufwarteschleifen und  automatischen Telefonkonferenzen zugewiesen sind, können nicht Telefonsystem Direktroutingnummern im Islands-Modus zugewiesen werden.</ul></ul><li>Kann Besprechungen in Teams oder Skype for Business (standardmäßig werden beide Plug-Ins angezeigt).<li>Kann an einer beliebigen Skype for Business oder Teams teilnehmen; wird die Besprechung im jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein Benutzer führt nur Skype for Business. Dieser Benutzer:</br><ul><li>Sie können nur Chats und Anrufe von Skype for Business initiieren.<li>Empfängt unabhängig vom initiierten Ziel Chat/Anruf in seinem Skype for Business-Client, es sei denn, es handelt sich um einen Teams-Benutzer mit lokal Skype for Business homed. *<li> Kann nur Skype for Business Besprechungen planen, kann aber an Besprechungen Skype for Business </br> \* oder Teams teilnehmen.* Die Verwendung des Islands-Modus mit lokalen Benutzern wird nicht in Kombination mit anderen Benutzern im SfBOnly-Modus empfohlen. Wenn ein Teams-Benutzer mit Skype for Business lokal heimisch ist, einen Anruf oder Chat mit einem SfBOnly-Benutzer initiiert, ist der SfBOnly-Benutzer nicht erreichbar und erhält eine verpasste Chat- oder Anruf-E-Mail.*|
|**SfBWithTeamsCollab**|Ein Benutzer führt Skype for Business und Teams nebeneinander aus. Dieser Benutzer:</br><ul><li>Verfügt über die Funktionalität eines Benutzers im SfBOnly-Modus.<li>Ist Teams nur für die Gruppenzusammenarbeit (Kanäle) aktiviert; Chat/Anrufe/Besprechungsplanung sind deaktiviert.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Ein Benutzer führt Skype for Business und Teams nebeneinander aus. Dieser Benutzer:<ul><li>Verfügt über die Chat- und Anruffunktion eines Benutzers im SfBOnly-Modus.<li>Hat Teams für die Gruppenzusammenarbeit aktiviert (Kanäle – einschließlich Kanalunterhaltungen); Chat und Anrufe sind deaktiviert.<li>Kann nur Teams Besprechungen planen, kann aber an Besprechungen Skype for Business oder Teams teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SfB Online Home)|Ein Benutzer führt nur Teams. Dieser Benutzer:<ul><li>Empfängt alle Chats und Anrufe in Teams-Client, unabhängig davon, wo initiiert wird.<li>Sie können nur Chats und Anrufe von Teams initiieren.<li>Kann Besprechungen nur in Teams Besprechungen planen, kann aber an Besprechungen Skype for Business oder Teams teilnehmen.<li>Sie können weiterhin Skype for Business IP-Telefone verwenden.<br><br>*Die Verwendung des TeamsOnly-Modus in Kombination mit anderen Benutzern im Islands-Modus wird erst empfohlen, wenn Teams übernahme gesättigt ist. d. h., alle Benutzer des Islands-Modus verwenden und überwachen Teams Skype for Business Clients. Wenn ein TeamsOnly-Benutzer einen Anruf oder Chat mit einem Islands-Benutzer initiiert, landet dieser Anruf oder Chat im Client des Islands-Teams- Wenn der Islands-Benutzer die Daten nicht Teams überwacht, wird dieser Benutzer offline angezeigt und ist für den TeamsOnly-Benutzer nicht erreichbar.*</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](./coexistence-chat-calls-presence.md)

[Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)