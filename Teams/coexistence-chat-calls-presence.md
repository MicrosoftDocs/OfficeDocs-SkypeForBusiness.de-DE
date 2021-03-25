---
title: Koexistenz mit Skype for Business
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Koexistenzverhalten zwischen Teams & Skype for Business, einschließlich Routingparametern, Chats & Anrufrouting, Chats & Anrufen aus bereits vorhandenen Threads, & Anwesenheit.
ms.openlocfilehash: 603356df5e6f5006ea67f6a84141acf1347c1235
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122339"
---
# <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Die Koexistenz und Interoperabilität zwischen Skype for Business- und Teams-Clients und -Benutzern wird durch teamsUpgrade-Modi definiert, die unter Migrations- und Interoperabilitätsleitfäden für Organisationen beschrieben werden, die Teams zusammen mit [Skype for Business verwenden.](migration-interop-guidance-for-teams-with-skype.md)

Jedem bestimmten Benutzer wird immer ein TeamsUpgrade-Modus zugewiesen, entweder standardmäßig oder explizit vom Administrator. Der Standardwert ist *"Inseln".* Benutzer, die ein Upgrade auf Teams durchgeführt haben, haben den *Modus "TeamsOnly".* *SfBOnly,* *SfBWithTeamsCollab* und *SfBWithTeamsCollabAndMeetings* sind ebenfalls mögliche Modi.


## <a name="routing-parameters"></a>Routingparameter

Der Modus "TeamsUpgrade" des Empfängers ist entscheidend für die Ermittlung des Verhaltens von Chats, Anrufen und Anwesenheitsverhalten, sowohl innerhalb eines Mandanten als auch innerhalb von Verbund-Mandanten.

Wenn der Absender Teams verwendet, wird die Routingentscheidung beim Erstellen eines neuen Unterhaltungsthreads getroffen. Vorhandene Unterhaltungsthreads in Teams behalten immer die Routingmethode bei, die beim Erstellen des Threads bestimmt wurde: Teams unterstützt persistente Threads.

 Threadroutingmethoden sind:  

- *Systemeigene* Für eine In-Mandant-Unterhaltung zwischen Teams und Teams
-  In-Mandant-In-App für eine Unterhaltung zwischen Teams und Skype for Business
- *Partnerated* for a federated conversation across tenants

Die Parameter, die die Threadroutingmethode bestimmen, sind:

- Der Modus "TeamsUpgrade" des Empfängers
- Der vom Absender verwendete Client
- Ob die Unterhaltung neu oder Teil eines vorhandenen Threads ist
- Unabhängig davon, ob es sich bei der Unterhaltung um eine In-Mandant- oder Eine-Partner-Unterhaltung handelt
- Ob die Unterhaltung möglich ist
    - *Die In-Mandant-Interoperabilität* setzt voraus, dass der Mandant entweder reine Online- oder Skype for Business-Hybrid ist. Rein lokale Mandanten können keine in-Mandant-Interoperabilität haben.
    - *Mandantenübergreifender Verbund* erfordert immer die richtige Skype for Business-Verbundkonfiguration sowie die richtige Konfiguration des Teams-Verbunds von beiden Mandanten. Skype for Business-Hybrid ist für keinen der Mandanten erforderlich.
    - Wenn das Skype for Business-Konto des Originators lokal zu Hause ist, kann dieser Benutzer den Teams-Client nicht für in-Mandant-Interoperabilität oder für einen Verbund verwenden. Dieser Benutzer kann den Skype for Business-Client nur für Interoperabilität und Verbund verwenden.
    - Die Kommunikation zwischen Teams und Teams ist immer im Mandanten möglich.

> [!NOTE]
> Wenn sich Empfänger und Absender beide im TeamsOnly-Upgrademodus befinden, handelt es sich bei der Unterhaltung um eine systemeigene Chaterfahrung, die alle reichhaltigen Nachrichten- und Anruffunktionen umfasst. Weitere Informationen finden Sie unter [Native Chaterfahrung für externe (Verbundbenutzer) in Teams.](native-chat-for-external-users.md) Wenn sich einer der Unterhaltungsteilnehmer NICHT im TeamsOnly-Upgrademodus befindet, bleibt die Unterhaltung eine Inopoperfahrung mit nur Textnachrichten.

## <a name="chat-and-call-routing"></a>Routing von Chats und Anrufen

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>In-Mandant-Routing für neue Chats oder Anrufe 

Die nachstehenden Tabellen erfassen das Routing von In-Mandant-Chats und -Anrufen und gelten für neue Anrufe oder Chats, die nicht aus einem bereits vorhandenen Thread gestartet werden. Es wird beschrieben, welcher Client einen neuen Anruf oder Chat erhält, wenn er von einem Benutzer auf der linken Seite an einen Empfänger im Mandanten auf der rechten Seite gesendet wird.

Nachrichten, die an TeamsOnly-Benutzer gesendet werden, werden immer an Teams gesendet. Nachrichten, die an SfB-Benutzer gesendet werden, werden immer an Skype for Business gesendet, wenn die Unterhaltung \* wie oben beschrieben möglich ist. Nachrichten, die an Benutzer von Inseln gesendet werden, werden immer an den Client gesendet, von dem sie gesendet wurden.

Die nachstehenden Tabellen zeigen, welcher Client in einem bestimmten Modus einen Anruf vom Originator (drei Spalten ganz links) erhält, je nach dem Modus des Er originators, dem ausgewählten Client und dem Ort, an dem der Skype for Business-Client zu Hause ist (on-prem oder online).

In den folgenden Tabellen: 
- **SfB \** _ steht für einen der folgenden Modi: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Der italische Text hebt* eine In-Interop-Unterhaltung hervor.

- **Nicht möglich** stellt eine Situation dar, in der der Chat oder Anruf nicht möglich ist. In diesen Fällen muss der Originator stattdessen Skype for Business verwenden. Dies ist einer der Gründe, warum Microsofts richtlinienpflichtige Anleitung für Lokale/Hybridkunden die Verwendung eines anderen Modus als Islands (in der Regel SfBWithTeamsCollab) als Ausgangspunkt für die Upgradereise zu Teams ist.

**Tabelle 1a: Neuer Chat oder Anrufrouting an einen Empfänger im Inselmodus**

| <br/><br/> Modus | Originator <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Route– >| Empfänger <br/><br/> Inseln  |
|--- |--- |--- |--- |--- |
| Inseln | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> On-Prem<br/>On-Prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-Prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Microsoft Teams| Online<br/>|&boxv;<br/>|Microsoft Teams|
| | | | | |

**Tabelle 1b: Neuer Chat oder Anrufrouting an einen Empfänger im \* SfB-Modus**

| <br/><br/> Modus   | Originator <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Route– > |   Empfänger <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Inseln |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Nicht möglich** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-Prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Microsoft Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabelle 1c: Neuer Chat- oder Anrufrouting in einem Mandanten an einen Empfänger im TeamsOnly-Modus**

| <br/><br/> Modus   | Originator <br/><br/> Client | <br/><br/> SfB &nbsp; homed |<br/><br/>Route– >|   Empfänger <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Inseln   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Microsoft Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-Prem<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Microsoft Teams | Online |  &boxv; |Microsoft Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Verbundrouting für neue Chats oder Anrufe
  
Die nachstehenden Tabellen erfassen das Routing von Verbundanrufen und Chats und gelten für neue Anrufe oder Chats. Sie beschreiben, welcher Client einen neuen Anruf oder Chat erhält, wenn er von einem Benutzer auf der linken Seite an einen Partnerzielbenutzer auf der rechten Seite gesendet wird.

Zusammengefasst: Wenn die Unterhaltung wie oben beschrieben möglich ist, werden nachrichten, die an TeamsOnly-Benutzer gesendet werden, immer in Teams angezeigt. Nachrichten, die an #A0 gesendet werden, werden immer in Skype for Business landen. Nachrichten, die an Benutzer von Inseln gesendet werden, werden unabhängig vom Client, von dem sie gesendet wurden, immer \* in Skype for Business landen. Das Routing für Verbundchats und Anrufe unterscheidet sich von der In-Mandant-Routing, da Benutzer von Inseln immer eine Verbundkommunikation in Skype for Business erhalten.

Dies liegt daran, dass wir nicht davon ausgehen können, dass ein Skype for Business-Partner, der eine Partnergruppe ist, teams bereits verwendet, wenn er sich im Inselmodus befindet. Inseln ist der Standardmodus, es kann jedoch nicht davon ausgegangen werden, dass teams von allen Benutzern der Inseln ausgeführt wird. Durch das Routing zu Skype for Business stellen wir sicher, dass keine Kommunikation mit einem Benutzer auf Inseln fehlschlägt. Wenn wir zu Teams geroutet haben, kann diese Kommunikation verpasst werden, wenn das Ziel Teams nicht verwendet hat. Das Routing zu Skype for Business stellt sicher, dass die Nachricht immer empfangen wird.  

> [!NOTE]
> Die aktuelle Implementierung des Teams-Verbunds basiert auf dem Skype for Business-Verbund und nutzt daher die Interoperabilitätsinfrastruktur (die erfordert, dass der Mandant des Originators entweder reine Online- oder Skype for Business-Hybridfunktionen ist) und stellt eine reduzierte Gruppe von Funktionen im Vergleich zu einem systemeigenen Thread bereit. Wir erwarten, in Zukunft systemeigene Teams für den Teams-Verbund bereitstellen zu können. Zu diesem Zeitpunkt wird der Thread systemeigener sein und vollständige Funktionen bereitstellen.

In den nachstehenden Tabellen wird beschrieben, welcher Client einen Anruf vom Originator (drei Spalten ganz links) erhält, je nach Dem Modus des Originators, dem ausgewählten Client und dem Ort, an dem der Skype for Business-Client zu Hause ist (on-prem oder online).

**Tabelle 2a: Neue Chat- oder Anrufrouting für einen Islands-Empfänger**

| <br/><br/>Modus   | Originator<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Route– > | Empfänger<br/><br/> Inseln |
|--- |--- |--- |--- |--- |
| Inseln |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Nicht möglich**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> On-Prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Microsoft Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabelle 2b: Neue Chat- oder Anrufrouting für einen Empfänger im \* SfB-Modus**

| <br/><br/>Modus   | Originator<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Route– >|  Empfänger<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Inseln |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> On-Prem<br/> On-Prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Nicht möglich** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> On-Prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Microsoft Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabelle 2c: Verbundneuer Chat oder Anrufrouting an einen Empfänger im TeamsOnly-Modus**

| <br/><br/>Modus | Originator<br/><br/> Client| <br/><br/>SfB homed|<br/><br/>Route– >|  Empfänger<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Inseln  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> On-Prem<br/> On-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Microsoft Teams <br/>*Microsoft Teams* <br/>**Nicht möglich** <br/>*Microsoft Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> On-Prem| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Microsoft Teams |Online |&boxv; |Microsoft Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats und Anrufe aus bereits vorhandenen Threads

### <a name="from-teams"></a>Aus Teams

Anrufe oder Chats, die aus einem bereits vorhandenen beständigen Thread in Teams gestartet wurden, werden auf die gleiche Weise wie dieser Thread geroutet, wenn diese Routingoption weiterhin verfügbar ist.

Wenn der bereits vorhandene beständigen Thread in Teams ein systemeigener Thread war (d. h. an Teams geroutet wurde), werden weitere Chatnachrichten und Anrufe aus diesem Thread an Teams gesendet. Wenn es sich um einen In-Op-Thread handelte (d. h. an Skype for Business gesendet), werden weitere Chatnachrichten und Anrufe an Skype for Business gesendet (wiederum unter der Annahme, dass Routingoptionen verfügbar sind).

> [!NOTE]
> Es ist möglich, dass bereits vorhandene Threads in Teams nicht mehr routierbar sind, z. B. wenn der Thread ein Inopthread für einen Benutzer war, der jetzt auf Teams aktualisiert wird. Da er als Inop-Thread erstellt wurde, wird der Thread zu Skype for Business weitergeroutet, aber dieser Benutzer kann Skype for Business nicht mehr für Chats und Anrufe verwenden. In diesem Fall wird der Thread deaktiviert und keine weitere Kommunikation zulassen.

### <a name="from-skype-for-business"></a>Aus Skype for Business

Skype for Business-Threads werden nicht über das 10 Min. SIP-Sitzungstimeout hinaus beibehalten. Chats und Anrufe aus einem vorhandenen Thread in Skype for Business vor Ablauf der SIP-Sitzung werden auf die gleiche Weise wie der Thread geroutet. Anrufe und Chats aus einem vorhandenen Thread in Skype for Business über das Timeout für die SIP-Sitzung hinaus werden an skype for Business der Remoteparty gesendet, unabhängig davon, von welchem Client der ursprüngliche Thread auf der Seite der anderen Partei stammt.

### <a name="availability"></a>Verfügbarkeit

Sowohl das oben beschriebene In-Mandant- als auch das Verbundverhalten sind mit den folgenden Einschränkungen verfügbar:

- Externe Teilnehmer, deren Mandanten sich in einer anderen GoLocal-Bereitstellung oder Geographie befinden, sehen in einer "Verbund"-Besprechung keinen Chat im Chat.
- Verbund und In-Beziehung zwischen Multitenant O365 und Sovereign Clouds werden nicht unterstützt

## <a name="presence"></a>Anwesenheit

Wenn Sie eine Situation haben, in der einige Ihrer Benutzer den Teams-Client verwenden und andere weiterhin den Skype for Business-Client verwenden, haben Sie möglicherweise eine Reihe von Benutzern, die beide Clients verwenden. Sie möchten weiterhin, dass Anwesenheitszustände für alle Benutzer freigegeben werden, unabhängig davon, über welchen Client ein einzelner Benutzer verfügt. Wenn dies in der gesamten Organisation freigegeben wird, können Die Benutzer besser bestimmen, ob es sinnvoll ist, einen Chat zu initiieren oder einen Anruf zu starten.

Wenn beispielsweise der Chat oder Anruf eines Ermittlers auf dem Skype for Business-Client des Ziels landen sollte, sollte die Anwesenheit des Skype for Business-Clients dem Originator angezeigt werden. Wenn er auf dem Teams-Client des Ziels landen sollte, sollte die Anwesenheit des Teams-Clients angezeigt werden.

Um zu wissen, welches Verhalten sie erwarten, müssen Sie verstehen, dass Anwesenheitsinformationen basierend auf dem Koexistenzmodus eines Benutzers freigegeben werden:

* Wenn sich ein Benutzer im TeamsOnly-Modus befindet, wird jedem anderen Benutzer (unabhängig davon, ob er sich in Teams oder Skype for Business befindet) die Anwesenheit von TeamsOnly der Teams angezeigt.
* Wenn sich ein Benutzer in einem der SfB-Modi \* befindet (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), wird jedem anderen Benutzer (ob in Teams oder Skype for Business) die Skype for Business-Anwesenheit des SfB-Benutzers angezeigt. \*
* Wenn sich ein Benutzer im Islands(oder Legacy)-Modus befindet, sind die Anwesenheit in Teams und die Anwesenheit in Skype for Business unabhängig (die Werte müssen nicht übereinstimmen), und anderen Benutzern wird die eine oder andere Anwesenheit des Islands-Benutzers angezeigt, je nachdem, ob sie sich im gleichen Mandanten oder in einem Verbundclient befinden und welchen Client sie verwenden.
    * In Teams wird jedem anderen Benutzer innerhalb desselben Mandanten die #A0 des Islands-Benutzers angezeigt. dies ist an der oben angegebenen Routingtabelle im Mandanten ausgerichtet.
    * In Teams sieht jeder andere Benutzer in einem Verbund-Mandanten die Skype for #A0 des Islands-Benutzers. dies ist an der oben angegebenen Verbundroutingtabelle ausgerichtet.
    * In Skype for Business sieht jeder andere Benutzer die Skype for Business-Anwesenheit des Islands-Benutzers (sowohl im Mandanten als auch im Verbund); dies ist an den oben angegebenen Routingtabellen ausgerichtet.


### <a name="in-tenant-presence"></a>In-Tenant-Anwesenheit

Nachrichten, die an TeamsOnly-Benutzer gesendet werden, werden immer in Teams angezeigt. Nachrichten, die an SfB-Benutzer gesendet werden, werden immer in Skype for Business angezeigt, wenn die Unterhaltung \* wie oben beschrieben möglich ist. Nachrichten, die an Benutzer von Inseln gesendet werden, landen immer im Client, von dem sie stammen.

In der Tabelle wird die Anwesenheit des Herausgebers beschrieben, der je nach Modus des Herausgebers und Client der Watcher (für einen neuen Thread) von einem Watcher angezeigt wird.

**Tabelle 3: Anwesenheit in Mandanten (neuer Thread)**

|Watcher <br/><br/>Client|<br/><br/>Route– > |<br/><br/>Inseln |Publisher <br/><br/>SfB\* |<br/>Nur Teams|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Microsoft Teams|
|Microsoft Teams |&boxv; |Microsoft Teams |Skype for Business |Microsoft Teams |
| | | | |

### <a name="federated-presence"></a>Verbundpräsenz

Die Verbundpräsenz basiert auf der in Tabelle 2 gezeigten Verbundverfügbarkeit.

In der nachstehenden Tabelle wird die Anwesenheit des Herausgebers beschrieben, der je nach Modus des Publishers und client des Watcher (für einen neuen Thread) von einem Watcher angezeigt wird. In der Praxis macht der Client des Watcher in dieser Phase keinen Unterschied im Verbund.

**Tabelle 4: Verbundpräsenz (neuer Thread)**

|Watcher <br/><br/> Client |<br/><br/>Route– >|<br/><br/> Inseln  |Publisher <br/><br/> SfB\* |<br/><br/> Nur Teams |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Microsoft Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Microsoft Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Anwesenheit in bereits vorhandenen Threads

Um die Anwesenheits- und Erreichbarkeitsinformationen in bereits vorhandenen Threads auszurichten, muss die in diesem Thread verfügbar gemachte Anwesenheit des Ziels am Routing des Threads ausgerichtet werden, vorausgesetzt, routing ist möglich.

Insbesondere wenn ein Empfänger, mit dem Sie zuvor über einen dauerhaften Unterhaltungsthread für In-In-Verbindungen berichtet haben, auf Teams aktualisiert wurde, spiegelt dieser Thread nicht mehr die genaue Anwesenheit wider und ist nicht mehr routierbar. Sie sollten einen neuen Thread starten.

## <a name="related-links"></a>Verwandte Links
[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)

[Video: Verwalten der Koexistenz und Interoperabilität zwischen SfB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)