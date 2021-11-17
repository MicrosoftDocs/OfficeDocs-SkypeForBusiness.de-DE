---
title: Koexistenz mit Skype for Business
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Koexistenzverhalten zwischen Teams & Skype for Business, einschließlich Routingparametern, Chat- & Anrufrouting, Chats & Anrufen aus bereits vorhandenen Threads, & Anwesenheitsinformationen.
ms.openlocfilehash: 5c32e99ad7cd74966cc7d8f22bd19a2520249b85
ms.sourcegitcommit: a5b80ad33b4ee9505ea2be1a37f5ec2d8bf5ba76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2021
ms.locfileid: "61042366"
---
# <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Die Koexistenz und Interoperabilität zwischen Skype for Business und Teams Clients wird durch Modi für die Koexistenz gesteuert. Weitere Informationen finden Sie unter [Migrations- und Interoperabilitätsleitfade](migration-interop-guidance-for-teams-with-skype.md)für Organisationen, die Teams mit Skype for Business. Nach dem Ende von Skype for Business Online am 31. Juli 2021 sind in der Cloud gespeicherte Benutzer immer TeamsOnly-Benutzer. Es ist nicht mehr möglich, einem Onlinebenutzer einen anderen Koexistenzmodus als TeamsOnly zuzuordnen. Andere Koexistenzmodi als TeamsOnly sind nur für Organisationen mit lokalen Bereitstellungen von Skype for Business Server oder Lync Server 2013 relevant. In diesem Artikel gilt jeder Verweis auf "Skype for Business Server" auch für Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Ermitteln des Koexistenzmodus eines Benutzers
Alle Benutzer in Organisationen ohne lokale Bereitstellung von Skype for Business Server sind TeamsOnly-Modus, und der effektive Modus des Mandanten ist auch TeamsOnly. Dies kann bestätigt werden, indem Sie die Eigenschaft TeamsUpgradeEffectiveMode für den Mandanten oder den Benutzer mit Teams PowerShell sehen.   Vor der Ende von Skype for Business Online am 31. Juli 2021 hatten Organisationen die Möglichkeit, den Koexistenzmodus für den Benutzer oder den Mandanten zu ändern. Dies ist nicht mehr möglich, außer bei Organisationen mit einer lokalen Bereitstellung von Skype for Business Server, die keinen mandantenweiten Modus von TeamsOnly haben darf. Sie können bestätigen, dass der Koexistenzmodus nicht mehr geändert werden kann, wenn TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" für den Benutzer oder Mandanten verwendet wird.  (TeamsUpgradePolicyIsReadOnly für jeden Benutzer hat denselben Wert wie der Wert des Mandanten.)  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

In einer Organisation mit einer lokalen Bereitstellung von Skype for Business Server kann die globale Mandantenrichtlinie für TeamsUpgradePolicy einen beliebigen anderen Modus als *TeamsOnly haben.* Die zulässigen Modi sind: *SfBOnly,* *SfBWithTeamsCollab* und *SfBWithTeamsCollabAndMeetings.* Benutzern kann auch direkt eine Instanz von TeamsUpgradePolicy zugewiesen werden, die die globale Mandantenrichtlinie ersetzt.  In der Cloud gespeicherte Benutzer müssen TeamsOnly sein, und lokal gespeicherte Benutzer müssen einen beliebigen anderen Modus als TeamsOnly verwenden.  Wenn einem Benutzer keine Instanz von TeamsUpgradePolicy zugewiesen ist, erhält der Benutzer den Wert aus der globalen Mandantenrichtlinie. 

## <a name="routing-parameters"></a>Routingparameter

Der Koexistenzmodus des Empfängers bestimmt das Verhalten von Chats, Anrufen und Anwesenheitspräsenzen, und dies sowohl innerhalb eines Mandanten als auch innerhalb der Partner mandantenübergreifend. Wenn der Absender einen Unterhaltungsthread Teams, wird die Routingentscheidung beim Erstellen eines neuen Unterhaltungsthreads getroffen. Sobald ein Unterhaltungsthread erstellt wurde, ändert sich sein Routing nicht, und es wird die Routingmethode beibehalten, die beim Erstellen des Threads bestimmt wurde.

Threadroutingmethoden sind:

- *systemeigene* für eine Teams, um Teams Unterhaltung im Mandanten zu führen
- *In interop* for a Teams to Skype for Business conversation in-tenant
- *Nativer Partner partnerated* for a federated conversation across tenants when both users have TeamsOnly mode. 
- *Zusammenarbeit für eine* Mandanten-Partnerhaltung, die auf Inaktivität zwischen Skype for Business und Teams.

> [!NOTE]
> - Systemeigene Unterhaltungen (unabhängig davon, ob sie sich im gleichen Mandanten- oder Partnerteamszenario befinden) treten auf, wenn sowohl der Empfänger als auch der Absender über den TeamsOnly-Modus verfügen. Bei der Unterhaltung wird es sich um einen systemeigenen Chat mit sämtlichen Funktionen für Chats und Anrufe. Weitere Informationen finden Sie unter Native Chaterfahrung für [externe Benutzer (Partnerbenutzer) in Teams.](native-chat-for-external-users.md) 
> - Wenn einer der Unterhaltungsteilnehmer NICHT über den TeamsOnly-Modus verfügen, ist die Unterhaltung eine In interop-Erfahrung mit Nur-Text-Nachrichten.
> - Verbundkommunikation zwischen TeamsOnly-Benutzer in Cloud-Wolken mit mehreren Mandanten und speziellen Cloudumgebungen (z. B. Government Clouds) werden als Inop-Partnerchats angezeigt.


Beim Erstellen einer neuen Unterhaltung sind die Faktoren, die bestimmen, wie der Thread geroutet wird:

- Der Koexistenzmodus des Empfängers
- Der vom Absender verwendete Client
- Ob es sich um eine Mandanten- oder Partner-Unterhaltung handelt
- Ob die Unterhaltung möglich ist. Wenn ein Benutzer über ein lokal Skype for Business-Konto verfügt, kann dieser Benutzer den Teams-Client nicht für in-Mandant-Interoperabilität oder für einen Verbund verwenden. Dieser Benutzer kann den Skype for Business nur für Interoperabilität und Verbund verwenden. Beachten Sie Teams dass Teams Kommunikation im Mandanten immer möglich ist.

## <a name="chat-and-call-routing"></a>Weiterleitung von Chats und Anrufen
Die folgenden Tabellen zeigen, welcher Client in einem bestimmten Modus einen Anruf vom Ermittler erhält (drei Spalten ganz links). Welche Benutzer den Anruf erhalten, hängt vom Modus des Ermittlers, vom ausgewählten Client und davon ab, wo das Skype for Business-Konto (lokal oder online) privat ist.

In den folgenden Tabellen:

- **Skype for Business** _ stellt einen der folgenden Modi dar: _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings*.
- *Der italische Text* hebt eine Inaktivität hervor.
- **Nicht möglich** steht für eine Situation, in der der Chat oder Anruf nicht möglich ist. Der Erzähler muss stattdessen Skype for Business in diesen Fällen verwenden. Dies ist einer der Gründe, warum die von Microsoft für lokale und Hybridkunden bestimmten Anweisungen in der Verwendung eines anderen Modus als Islands (normalerweise SfBWithTeamsCollab) als Ausgangspunkt für ihre Upgrade-Reise zu Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Mandanten-Routing für neue Chats oder Anrufe

In den Tabellen unten wird das Routing von In-Mandant-Chats und -Anrufen erfasst. Sie gelten für neue Anrufe oder Chats, die nicht aus einem bereits vorhandenen Thread gestartet werden. Er beschreibt, welcher Client einen neuen Anruf oder Chat erhält (sofern er von einem Benutzer auf der linken Seite stammt) an einen Benutzer im Mandanten auf der rechten Seite.  An TeamsOnly-Benutzer gesendete Nachrichten werden immer an andere Teams. Nachrichten, die an Skype for Business gesendet werden, werden immer an andere Skype for Business. Nachrichten, die an Inseln gesendet werden, werden immer an den Client geroutet, von dem aus sie gesendet wurden.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabelle 1a: Routing neuer Chats oder Anrufe im Mandanten an einen TeamsOnly-Modusempfänger

<br>

|<br><br>Modus|Originator<br><br>Client|<br><br>Skype for Business &nbsp; homed|<br><br>Route -->|TeamsOnly Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;|Teams <br> *Microsoft Teams*|
|Skype for Business | Skype for Business | Lokal|&boxv;|*Microsoft Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabelle 1b: Routing neuer Chats oder Anrufe im Mandanten an einen Empfänger im Islands-Modus

<br>

|<br><br>Modus|Originator<br><br>Client|<br><br>Skype for Business &nbsp; homed|<br><br>Route -->|Islands Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Inselmodus| Teams <br> Skype for Business|Lokal<br>Lokal|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | Lokal|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabelle 1c: Weiterleitung neuer Chats oder Anrufe im Mandantenmodus an einen Skype for Business

<br>

|<br><br>Modus|Originator<br><br>Client|<br><br>Skype for Business &nbsp; homed|<br><br>Route -->|Skype for Business Empfänger|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;| **Nicht möglich** <br> Skype for Business|
|Skype for Business | Skype for Business| Lokal|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Verbundrouting für neue Chats oder Anrufe

In den Tabellen unten wird das Routing von Partneranrufen und Chats erfasst, die für neue Anrufe oder Chats gültig sind. Sie beschreiben, welcher Client einen neuen Anruf oder Chat erhält (falls er von einem Benutzer auf der linken Seite stammt) an einen Partnerzielbenutzer auf der rechten Seite. Zusammenfassung: Wenn die Unterhaltung wie oben beschrieben möglich ist, landen Nachrichten an TeamsOnly-Benutzer immer im Teams; Nachrichten, die an Benutzer des Skype for Business-Modus gesendet wurden, landen immer im Skype for Business; Nachrichten, die an Islands-Benutzer gesendet wurden, landen immer Skype for Business  unabhängig vom Client, von dem sie gesendet wurden. 

Das Routing für Partnerchats und Anrufe unterscheidet sich von der In-Tenant-Weiterleitung, da Islands-Benutzer in einer Partnerkommunikation immer eine Skype for Business. Der Grund dafür ist, dass der Partnerpartner die Daten möglicherweise noch nicht Teams. Routing to Skype for Business for any islands mode recipeint stellt sicher, dass Nachrichten immer empfangen werden.  Das Routing an Teams kann zu einer verpassten Kommunikation führen, wenn der beabsichtigte Empfänger keine Daten Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabelle 2a: Routing neuer Chats oder Anrufe im Partnermodus an einen TeamsOnly-Modusempfänger

<br>

|<br><br>Modus|Originator<br><br>Client|<br><br>Skype for Business homed|<br><br>Route -->|TeamsOnly Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Inselmodus|Teams <br> Skype for Business|Lokal <br> Lokal|&boxv;<br>&boxv;|**Nicht möglich** <br> *Microsoft Teams*|
|Skype for Business |Skype for Business|Lokal|&boxv;| *Microsoft Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabelle 2b: Routing neuer Chats oder Anrufe im Partnering an einen Islands-Empfänger

<br>

|<br><br>Modus|Originator<br><br>Client|<br><br>Skype for Business homed|<br><br>Route -->|Islands Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;| **Nicht möglich** <br> Skype for Business|
|Skype for Business |Skype for Business| Lokal|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabelle 2c: Routing neuer Chats oder Anrufe im Partner-Modus an einen Skype for Business

<br>

|<br><br>Modus|Originator<br><br>Client|<br><br>Skype for Business homed|<br><br>Route -->|Skype for Business Empfänger|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;|**Nicht möglich** <br> Skype for Business|
|Skype for Business |Skype for Business|Lokal|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats und Anrufe aus bereits vorhandenen Threads

### <a name="from-teams"></a>Von Teams

Anrufe oder Chats, die aus einem bereits vorhandenen Unterhaltungsthread in Teams gestartet werden, werden auf die gleiche Weise wie der Thread geroutet. Wenn der bereits vorhandene Thread in Teams ein systemeigener Thread war (d. h. an Teams geroutet wurde), werden zusätzliche Chatnachrichten und Aufrufe von diesem Thread an Teams. Wenn es sich um einen Inop-Thread handelte (d. h. an Skype for Business geroutet), werden zusätzliche Chatnachrichten und Anrufe an Skype for Business (vorausgesetzt, es sind Routingoptionen verfügbar).

> [!NOTE]
> Es ist möglich, dass bereits vorhandene Threads in Teams nicht mehr routingfähig sind, z. B. wenn der Thread ein Inopthread für einen Benutzer war, für den inzwischen ein Upgrade auf eine Teams. Da er als Inopthread erstellt wurde, wird der Thread an Skype for Business geroutet, aber dieser Benutzer kann Skype for Business nicht mehr für Chats und Anrufe verwenden. In diesem Fall wird der Thread deaktiviert, und es ist keine weitere Kommunikation möglich.

### <a name="from-skype-for-business"></a>Von Skype for Business

Skype for Business Threads werden nach dem 10-minütigen SIP-Sitzungstimeout nicht beibehalten. Chats und Anrufe aus einem vorhandenen Thread in Skype for Business vor Ablauf der SIP-Sitzung werden auf die gleiche Weise wie der Thread geroutet. Anrufe und Chats aus einem vorhandenen Thread in Skype for Business, der über das SIP-Sitzungstimeout hinaus geht, werden an das Skype for Business der Remoteseite geroutet, unabhängig davon, von welchem Client der ursprüngliche Thread auf der Seite der anderen Partei stammt.

## <a name="presence"></a>Anwesenheit

In Situationen, in denen einige Benutzer den Teams-Client und andere den Skype for Business-Client verwenden, können einige dieser Benutzer beide Clients verwenden. Es ist wichtig zu verstehen, dass die Anwesenheitsinformationen basierend auf dem Koexistenzmodus eines Benutzers veröffentlicht werden. Wenn beispielsweise der Chat oder Anruf eines Erzählers auf dem Skype for Business-Client des Ziels landen sollte, sollte die Anwesenheit des Skype for Business-Clients für den Erzähler angezeigt werden. Sollte der Client auf dem Zielclient Teams, sollte die Anwesenheit des Teams-Clients angezeigt werden.

Die Anwesenheitsinformationen werden basierend auf dem Koexistenzmodus eines Benutzers freigegeben, wie nachstehend beschrieben:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sieht jeder andere Benutzer (ob in Teams oder Skype for Business) die Anwesenheit von TeamsOnly-Teams
- Wenn sich ein Benutzer in einem der Skype for Business-Modi (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings) befindet, kann jeder andere Benutzer (ob in Teams oder Skype for Business) die Skype for Business-Daten des Skype for Business Anwesenheit
- Wenn sich ein Benutzer im Islands-Modus befindet, sind die Anwesenheitsinformationen in Teams und die Anwesenheit in Skype for Business unabhängig (die Werte müssen nicht übereinstimmen), und anderen Benutzern wird je nachdem, ob sie sich im gleichen Mandanten oder in einem Partner-Mandanten befinden und welchen Client sie verwenden, das eine oder die andere Anwesenheit des Islands-Benutzers angezeigt.
  - Von Teams alle anderen Benutzer innerhalb desselben Mandanten sehen die Anwesenheitsinformationen des Islands-Benutzers Teams. Dies ist an der oben angegebenen Routingtabelle für Mandanten ausgerichtet.
  - Von Teams anderen Benutzern in einem Partner mandant wird die Anwesenheit des Islands-Benutzers Skype for Business angezeigt. Dies ist an der obigen Verbundroutingtabelle ausgerichtet.
  - Von Skype for Business können alle anderen Benutzer die Anwesenheitsinformationen des Benutzers auf den Inseln Skype for Business sehen (sowohl im Mandanten als auch im Verbund). Dies ist an den oben angegebenen Routingtabellen ausgerichtet.

### <a name="in-tenant-presence"></a>Anwesenheitspräsenz in Mandanten

An Teams Gesendete NachrichtenOnly-Benutzer landen immer Teams. Nachrichten, die an Skype for Business-Modus gesendet werden, werden immer Skype for Business, wenn die Unterhaltung wie oben beschrieben möglich ist. An Inseln gesendete Nachrichten landen immer in dem Client, aus dem sie stammen.

In der Tabelle wird Publisher Anwesenheitsmodus beschrieben, der von einer Watcher abhängig vom Modus der Publisher und dem Client der Watcher (für einen neuen Thread) angezeigt wird.

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabelle 3: Anwesenheit in Mandanten (neuer Thread)

<br>

|Zusehen<br><br>Client|<br><br>Route->|<br><br>Inselmodus|Publisher<br><br>Skype for Business|<br>Nur Teams|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Microsoft Teams|&boxv;|Microsoft Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Verbundpräsenz

Die Verbundpräsenz basiert auf der in Tabelle 2 gezeigten Erreichbarkeit im Verbund.  In der folgenden Tabelle wird Publisher-Anwesenheitsmodus beschrieben, der von einem Watcher abhängig vom Modus der Publisher und dem Client der Watcher (für einen neuen Thread) angezeigt wird. In der Praxis macht der Client von Watcher in dieser Phase keinen Unterschied beim Verbund.

#### <a name="table-4-federated-presence-new-thread"></a>Tabelle 4: Verbundpräsenz (neuer Thread)

<br>

|Zusehen<br><br>Client|<br><br>Route->|<br><br>Inselmodus|Publisher<br><br>Skype for Business|<br><br>Nur Teams|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Microsoft Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Anwesenheit in bereits vorhandenen Threads

Um die Anwesenheit und Erreichbarkeit in bereits vorhandenen Threads auszurichten, muss die Anwesenheit des Ziels, die in diesem Thread verfügbar gemacht wird, an das Routing des Threads angepasst werden, sofern Routing möglich ist.  Insbesondere wenn ein Empfänger, mit dem Sie zuvor einen dauerhaften Inop-Unterhaltungsthread hatten, auf Teams aktualisiert wurde, spiegelt dieser Thread keine präzise Anwesenheit mehr wider und kann nicht mehr routingfähig sein. Sie sollten einen neuen Thread starten.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Verbund und Inaktivität mit Office 365 21Vianet

Der Verbund und die Inaktivität zwischen mehr mandantenübergreifenden Office 365 und Office 365, betrieben von 21Vianet, werden unterstützt, wenn sich die Office 365-Benutzer mit mehreren Mandanten im Teams-Modus befinden. In einem solchen Szenario können Skype for Business Online-Benutzer in Office 365, betrieben von 21Vianet, über Chats und Anrufe nur mit Teams Nur Benutzer mit mehreren Mandanten Office 365 kommunizieren. Die folgende Tabelle zeigt die unterstützten Szenarien in dieser Konfiguration:
 
|Szenario|Origin|Empfänger|Unterstützt?|
|---|---|---|---|
|Anwesenheit|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja<br>Ja|
|Chat|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja (nur 1:1)<br>Ja(nur 1:1)|
|Audioanrufe|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja (nur 1:1)<br>Ja (nur 1:1)|
|Videoanrufe|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja (nur 1:1)<br>Ja (nur 1:1)|
|Bildschirmfreigabe|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Ja (durch eine heraufgestufte Teams Besprechung)<br>Ja (durch eine heraufgestufte Skype for Business Besprechung)|
|||||


## <a name="related-links"></a>Verwandte Links
[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)

[Video: Verwalten der Koexistenz und Interoperabilität Skype for Business und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
