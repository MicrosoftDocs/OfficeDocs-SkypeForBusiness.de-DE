---
title: Koexistenz mit Skype for Business
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Koexistenzverhalten zwischen Teams & Skype for Business, einschließlich Routingparametern, Chat & Anrufweiterleitung, Chats & Anrufen aus bereits vorhandenen Threads, & Anwesenheit.
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562394"
---
# <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Koexistenz und Interoperabilität zwischen Skype for Business und Teams-Clients werden durch Koexistenzmodi gesteuert. Weitere Informationen finden Sie unter [Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md). Nach der Einstellung von Skype for Business Online am 31. Juli 2021 sind Benutzer, die in der Cloud verwaltet werden, immer TeamsOnly-Benutzer. Es ist nicht mehr möglich, einem Onlinebenutzer einen anderen Koexistenzmodus als TeamsOnly zuzuweisen. Andere Koexistenzmodi als TeamsOnly sind nur für Organisationen mit lokalen Bereitstellungen von Skype for Business Server oder Lync Server 2013 relevant. In diesem Artikel gilt jeder Verweis auf "Skype for Business Server" auch für Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Bestimmen des Koexistenzmodus eines Benutzers
Alle Benutzer in Organisationen ohne lokale Bereitstellung von Skype for Business Server sind teamsonly-Modus, und der effektive Modus des Mandanten ist auch TeamsOnly. Dies kann bestätigt werden, indem Sie sich die TeamsUpgradeEffectiveMode-Eigenschaft des Mandanten oder des Benutzers mithilfe von Teams PowerShell ansehen.   Vor der Einstellung von Skype for Business Online am 31. Juli 2021 hatten Organisationen die Möglichkeit, den Koexistenzmodus für den Benutzer oder den Mandanten zu ändern. Dies ist nicht mehr möglich, mit Ausnahme von Organisationen mit einer lokalen Bereitstellung von Skype for Business Server, die nicht über den mandantenweiten Modus von TeamsOnly verfügen dürfen. Sie können bestätigen, dass der Koexistenzmodus nicht mehr geändert werden kann, wenn TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" für den Benutzer oder Mandanten vorhanden ist.  (TeamsUpgradePolicyIsReadOnly für jeden Benutzer hat denselben Wert wie der Wert des Mandanten.)  


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

In einer Organisation mit einer lokalen Bereitstellung von Skype for Business Server kann die globale Mandantenrichtlinie für TeamsUpgradePolicy über einen *anderen Modus als TeamsOnly verfügen*. Die zulässigen Modi sind: *SfBOnly*, *SfBWithTeamsCollab* und *SfBWithTeamsCollabAndMeetings*. Benutzern kann auch direkt eine Instanz von TeamsUpgradePolicy zugewiesen werden, wodurch die globale Mandantenrichtlinie ersetzt würde.  Benutzer, die in der Cloud verwaltet werden, müssen TeamsOnly sein, und benutzer, die lokal verwaltet werden, müssen einen anderen Modus als TeamsOnly haben.  Wenn einem Benutzer keine Instanz von TeamsUpgradePolicy zugewiesen ist, erhält der Benutzer den Wert aus der globalen Mandantenrichtlinie. 

## <a name="routing-parameters"></a>Routingparameter

Der Koexistenzmodus des Empfängers bestimmt das Verhalten von Chats, Anrufen und Anwesenheitsinformationen sowohl innerhalb eines Mandanten als auch über Verbundmandanten hinweg. Wenn der Absender Teams verwendet, wird die Routingentscheidung beim Erstellen eines neuen Unterhaltungsthreads getroffen. Nachdem ein Unterhaltungsthread erstellt wurde, ändert sich das Routing nicht mehr und behält die Routingmethode bei, die beim Erstellen des Threads bestimmt wurde.

Threadroutingmethoden sind:

- *nativ* für eine Teams-zu-Teams-Unterhaltung im Mandanten
- *Interoperabilität* für ein Teams zum Skype for Business Unterhaltung im Mandanten
- *Nativer Verbund* für eine Mandantenverbundunterhaltung, wenn beide Benutzer den TeamsOnly-Modus haben. 
- *Interoperabilitätsverbund* für eine mandantenübergreifende Verbundunterhaltung, die auf der Interoperabilität zwischen Skype for Business und Teams basiert.

> [!NOTE]
> - Native Unterhaltungen, unabhängig davon, ob sie sich im gleichen Mandanten- oder Verbundszenario befinden, treten auf, wenn sowohl der Empfänger als auch der Absender über den TeamsOnly-Modus verfügen. Die Unterhaltung wird eine native Chaterfahrung sein, die alle umfassenden Messaging- und Anruffunktionen umfasst. Weitere Informationen finden Sie [in der nativen Chaterfahrung für externe Benutzer (Verbundbenutzer) in Teams](native-chat-for-external-users.md). 
> - Wenn einer der Unterhaltungsteilnehmer NICHT über den TeamsOnly-Modus verfügen, ist die Unterhaltung eine Interoperabilitätserfahrung mit Nur-Text-Nachrichten.
> - Die Verbundkommunikation zwischen TeamsOnly-Benutzern in mehrinstanzenfähigen Clouds und speziellen Cloudumgebungen (z. B. Government Clouds) wird als Interop-Verbundchats angezeigt.


Beim Erstellen einer neuen Unterhaltung sind die Faktoren, die bestimmen, wie der Thread weitergeleitet wird:

- Der Koexistenzmodus des Empfängers
- Der vom Absender verwendete Client
- Gibt an, ob es sich bei der Unterhaltung um eine Mandantenunterhaltung oder einen Verbund handelt.
- Gibt an, ob die Unterhaltung möglich ist. Wenn ein Benutzer über ein Skype for Business Konto verfügt, das lokal verwaltet wird, kann dieser Benutzer den Teams-Client weder für Interoperabilität im Mandanten noch für Partnerverbund verwenden. Dieser Benutzer kann den Skype for Business-Client nur für Interoperabilität und Verbund verwenden. Beachten Sie, dass die Kommunikation zwischen Teams und Teams immer im Mandanten möglich ist.

## <a name="chat-and-call-routing"></a>Chat und Anrufweiterleitung
Die folgenden Tabellen zeigen, welcher Client in einem bestimmten Modus einen Anruf vom Absender erhält (drei Spalten ganz links). Welcher Cient den Anruf erhält, hängt vom Modus des Absenders, dem ausgewählten Client und dem Speicherort des Skype for Business Kontos (lokal oder online) ab.

In den folgenden Tabellen:

- **Skype for Business** _ stellt einen der folgenden Modi dar: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *Kursiv hervorgehobener Text* hebt eine Interoperabilitätsunterhaltung hervor.
- **"Nicht möglich** " stellt eine Situation dar, in der der Chat oder Anruf nicht möglich ist. Der Absender muss in diesen Fällen stattdessen Skype for Business verwenden. Dies ist einer der Gründe, warum microsofts richtlinienorientierte Anleitung für lokale und Hybridkunden darin besteht, einen anderen Modus als Islands (in der Regel SfBWithTeamsCollab) als Ausgangspunkt für ihre Upgrade-Reise zu Teams zu verwenden.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Mandantenspezifisches Routing für neue Chats oder Anrufe

Die folgenden Tabellen erfassen das Routing von In-Tenant-Chats und -Anrufen und gelten für neue Anrufe oder Chats, die nicht aus einem bereits vorhandenen Thread gestartet werden. Es beschreibt, welcher Client einen neuen Anruf oder Chat erhält, wenn er von einem Benutzer auf der linken Seite stammt, an einen In-Tenant-Empfängerbenutzer auf der rechten Seite.  Nachrichten, die an TeamsOnly-Benutzer gesendet werden, werden immer an Teams weitergeleitet. Nachrichten, die an Skype for Business Benutzer gesendet werden, werden immer an Skype for Business weitergeleitet. Nachrichten, die an Inselbenutzer gesendet werden, werden immer an denselben Client weitergeleitet, von dem aus sie gesendet wurden.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabelle 1a: Neuer Chat im Mandanten oder Anrufweiterleitung an einen Empfänger im TeamsOnly-Modus

<br>

|<br><br>Modus|Urheber<br><br>Client|<br><br>&nbsp;Skype for Business gehomed|<br><br>Route – >|TeamsOnly-Empfänger|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;|Teams <br> *Microsoft Teams*|
|Skype for Business | Skype for Business | Lokal|&boxv;|*Microsoft Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabelle 1b: Neuer Chat im Mandanten oder Anrufweiterleitung an einen Empfänger im Inselmodus

<br>

|<br><br>Modus|Urheber<br><br>Client|<br><br>&nbsp;Skype for Business gehomed|<br><br>Route – >|Empfänger der Inseln|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Inselmodus| Teams <br> Skype for Business|Lokal<br>Lokal|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | Lokal|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabelle 1c: Neuer Chat im Mandanten oder Anrufweiterleitung an einen Empfänger in einem Skype for Business-Modus

<br>

|<br><br>Modus|Urheber<br><br>Client|<br><br>&nbsp;Skype for Business gehomed|<br><br>Route – >|Skype for Business Empfänger|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;| **Nicht möglich** <br> Skype for Business|
|Skype for Business | Skype for Business| Lokal|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Verbundrouting für neue Chats oder Anrufe

Die folgenden Tabellen erfassen das Routing von Verbundanrufen und Chats und sind für neue Anrufe oder Chats gültig. Sie beschreiben, welcher Client einen neuen Anruf oder Chat erhält, wenn er von einem Benutzer auf der linken Seite stammt, an einen Partnerzielbenutzer auf der rechten Seite. Zusammenfassend lässt sich feststellen, dass Nachrichten, die an TeamsOnly-Benutzer gesendet werden, immer in Teams landen, wenn die Unterhaltung wie oben beschrieben möglich ist. Nachrichten, die an Benutzer im Skype for Business-Modus gesendet werden, landen immer in Skype for Business. Nachrichten, die an Benutzer von Inseln gesendet werden, landen unabhängig vom Client, von dem sie gesendet wurden, immer in Skype for Business. 

Das Routing für Verbundchats und Anrufe unterscheidet sich vom Mandantenrouting darin, dass Benutzer von Inseln immer eine Verbundkommunikation in Skype for Business erhalten. Dies liegt daran, dass der Verbundpartner Teams möglicherweise noch nicht verwendet. Durch das Routing an Skype for Business für alle Inseln wird sichergestellt, dass Nachrichten immer empfangen werden.  Das Weiterleiten an Teams kann zu einer verpassten Kommunikation führen, wenn der beabsichtigte Empfänger Teams nicht verwendet. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabelle 2a: Neuer Partnerchat oder Anrufweiterleitung an einen Empfänger im TeamsOnly-Modus

<br>

|<br><br>Modus|Urheber<br><br>Client|<br><br>Skype for Business verwaltet|<br><br>Route – >|TeamsOnly-Empfänger|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Inselmodus|Teams <br> Skype for Business|Lokal <br> Lokal|&boxv;<br>&boxv;|**Nicht möglich** <br> *Microsoft Teams*|
|Skype for Business |Skype for Business|Lokal|&boxv;| *Microsoft Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabelle 2b: Neuer Partnerchat oder Anrufweiterleitung an einen Empfänger der Inseln

<br>

|<br><br>Modus|Urheber<br><br>Client|<br><br>Skype for Business verwaltet|<br><br>Route – >|Empfänger der Inseln|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;| **Nicht möglich** <br> Skype for Business|
|Skype for Business |Skype for Business| Lokal|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabelle 2c: Neuer Partnerchat oder Anrufweiterleitung an einen Empfänger in einem Skype for Business-Modus

<br>

|<br><br>Modus|Urheber<br><br>Client|<br><br>Skype for Business verwaltet|<br><br>Route – >|Skype for Business Empfänger|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Inselmodus|Teams <br> Skype for Business| Lokal <br> Lokal|&boxv;<br>&boxv;|**Nicht möglich** <br> Skype for Business|
|Skype for Business |Skype for Business|Lokal|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats und Anrufe aus bereits vorhandenen Threads

### <a name="from-teams"></a>Von Teams

Anrufe oder Chats, die aus einem bereits vorhandenen Unterhaltungsthread in Teams gestartet wurden, werden auf die gleiche Weise wie dieser Thread weitergeleitet. Wenn es sich bei dem bereits vorhandenen Thread in Teams um einen nativen Thread handelte (d. h. an Teams weitergeleitet), werden zusätzliche Chatnachrichten und Anrufe aus diesem Thread an Teams weitergeleitet. Wenn es sich um einen Interoperabilitätsthread handelte (d. h. an Skype for Business weitergeleitet), werden zusätzliche Chatnachrichten und Anrufe an Skype for Business weitergeleitet (vorausgesetzt, Routingoptionen sind verfügbar).

> [!NOTE]
> Es ist möglich, dass bereits vorhandene Threads in Teams nicht mehr routingfähig sind, z. B. wenn der Thread ein Interoperabilitätsthread für einen Benutzer war, der inzwischen auf Teams aktualisiert wurde. Da er als Interoperabilitätsthread erstellt wurde, würde der Thread an Skype for Business weitergeleitet, aber dieser Benutzer kann Skype for Business nicht mehr für Chats und Anrufe verwenden. In diesem Fall wird der Thread deaktiviert und lässt keine weitere Kommunikation zu.

### <a name="from-skype-for-business"></a>Von Skype for Business

Skype for Business Threads werden nicht über das 10-minütige SIP-Sitzungstimeout hinaus beibehalten. Chats und Anrufe aus einem vorhandenen Thread in Skype for Business vor Ablauf der SIP-Sitzung werden auf die gleiche Weise wie der Thread weitergeleitet. Anrufe und Chats aus einem vorhandenen Thread in Skype for Business außerhalb des SIP-Sitzungstimeouts werden an die Skype for Business der Remotepartei weitergeleitet, unabhängig davon, von welchem Client der ursprüngliche Thread auf der Seite der anderen Partei stammt.

## <a name="presence"></a>Anwesenheit

In Situationen, in denen einige Benutzer den Teams-Client verwenden und andere den Skype for Business-Client verwenden, ist es möglich, dass einige dieser Benutzer beide Clients verwenden. Es ist wichtig zu wissen, dass die Anwesenheit basierend auf dem Koexistenzmodus eines Benutzers veröffentlicht wird. Wenn beispielsweise der Chat oder Anruf eines Absenders auf dem Skype for Business Client des Ziels landen soll, sollte dem Absender die Anwesenheit des Skype for Business Kunden angezeigt werden. Wenn es auf dem Teams-Client des Ziels landen sollte, sollte die Anwesenheit des Teams-Clients angezeigt werden.

Die Anwesenheit wird basierend auf dem Koexistenzmodus eines Benutzers freigegeben, wie unten beschrieben:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, wird jedem anderen Benutzer (ob in Teams oder Skype for Business) die Anwesenheit des TeamsOnly-Benutzers angezeigt.
- Wenn sich ein Benutzer in einem der Skype for Business Modi befindet (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), wird jedem anderen Benutzer (ob in Teams oder Skype for Business) angezeigt, dass Skype for Business Skype for Business Anwesenheitsstatus des Benutzers
- Wenn sich ein Benutzer im Inselmodus befindet, sind die Anwesenheit in Teams und die Anwesenheit in Skype for Business unabhängig (die Werte müssen nicht übereinstimmen), und andere Benutzer sehen die eine oder andere Anwesenheit des Islands-Benutzers, je nachdem, ob er sich im selben Mandanten oder in einem Verbundmandanten befindet und welchen Client er verwendet.
  - Von Teams aus sieht jeder andere Benutzer innerhalb desselben Mandanten die Teams-Anwesenheit des Islands-Benutzers. dies ist mit der oben aufgeführten Tabelle für das Mandantenrouting ausgerichtet.
  - In Teams sieht jeder andere Benutzer in einem Verbundmandanten die anwesenheitsinformationen des Islands-Benutzers Skype for Business. Dies ist mit der obigen Verbundroutingtabelle ausgerichtet.
  - Von Skype for Business aus sieht jeder andere Benutzer die anwesenheitsinformationen des Islands-Benutzers Skype for Business (sowohl im Mandanten als auch im Verbund); dies ist mit den oben aufgeführten Routingtabellen ausgerichtet.

### <a name="in-tenant-presence"></a>In-Tenant-Anwesenheit

Nachrichten, die an TeamsOnly-Benutzer gesendet werden, landen immer in Teams. Nachrichten, die an Skype for Business Modus gesendet werden, landen immer in Skype for Business, wenn die Unterhaltung wie oben beschrieben möglich ist. Nachrichten, die an Benutzer von Inseln gesendet werden, landen immer in dem Client, von dem sie stammen.

In der Tabelle wird die Anwesenheit des Herausgebers beschrieben, die von einem Watcher abhängig vom Modus des Herausgebers und dem Client des Watchers (für einen neuen Thread) angezeigt wird.

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabelle 3: Mandantenin-Anwesenheit (neuer Thread)

<br>

|Watcher<br><br>Client|<br><br>Route – >|<br><br>Inselmodus|Publisher<br><br>Skype for Business|<br>Nur Teams|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Microsoft Teams|&boxv;|Microsoft Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Verbundpräsenz

Die Verbundpräsenz basiert auf der in Tabelle 2 dargestellten Erreichbarkeit des Verbunds.  In der folgenden Tabelle wird die Anwesenheit des Herausgebers beschrieben, die von einem Watcher angezeigt wird, abhängig vom Modus des Herausgebers und dem Client des Watchers (für einen neuen Thread). In der Praxis macht der Kunde des Watcher in dieser Phase keinen Unterschied im Verbund.

#### <a name="table-4-federated-presence-new-thread"></a>Tabelle 4: Verbundpräsenz (neuer Thread)

<br>

|Watcher<br><br>Client|<br><br>Route – >|<br><br>Inselmodus|Publisher<br><br>Skype for Business|<br><br>Nur Teams|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Microsoft Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Anwesenheit in bereits vorhandenen Threads

Um die Anwesenheit und Erreichbarkeit in bereits vorhandenen Threads auszurichten, muss die Anwesenheit des Ziels, die in diesem Thread verfügbar gemacht wird, an der Weiterleitung des Threads ausgerichtet werden, vorausgesetzt, das Routing ist möglich.  Insbesondere wenn ein Empfänger, mit dem Sie zuvor einen Thread für beständige Interoperabilitätsunterhaltungen hatten, auf Teams aktualisiert wurde, spiegelt dieser Thread keine genaue Anwesenheit mehr wider und ist nicht mehr routingfähig. Sie sollten einen neuen Thread starten.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Verbund und Interoperabilität mit Office 365, betrieben von 21Vianet

Partnerverbund und Interop zwischen mehrinstanzenfähigen Office 365 und Office 365, die von 21Vianet betrieben werden, werden unterstützt, wenn sich die Benutzer mit mehreren Mandanten Office 365 im Modus "Nur Teams" befinden. In einem solchen Szenario können Skype for Business Onlinebenutzer in Office 365, die von 21Vianet betrieben werden, nur mit Teams-Benutzern in mehrinstanzenfähigen Office 365 über Chats und Anrufe kommunizieren. Die folgende Tabelle zeigt die unterstützten Szenarien in dieser Konfiguration:
 
|Szenario|Ursprung|Empfänger|Unterstützt?|
|---|---|---|---|
|Anwesenheit|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja<br>Ja|
|Chat|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja (nur 1:1)<br>Ja(nur 1:1)|
|Audioanrufe|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja (nur 1:1)<br>Ja (nur 1:1)|
|Videoanrufe|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Ja (nur 1:1)<br>Ja (nur 1:1)|
|Bildschirmfreigabe|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Ja (über eine höhergestufte Teams-Besprechung)<br>Ja (durch eine höhergestufte Skype for Business Besprechung)|
|||||


## <a name="related-links"></a>Verwandte Links
[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)

[Video: Verwalten der Koexistenz und Interoperabilität zwischen Skype for Business und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
