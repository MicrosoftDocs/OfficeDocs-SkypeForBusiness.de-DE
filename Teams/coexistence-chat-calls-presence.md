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
description: Koexistenz-Verhalten zwischen Teams & Skype for Business, einschließlich Routing Parametern, Chat & Anrufweiterleitung, Chats & von bereits vorhandenen Threads, & Anwesenheit.
ms.openlocfilehash: 9dd2baa717466b0f414168356256b6d78ce33f6a
ms.sourcegitcommit: e5e60079cf9d62627de6b26dd4badd353bcc190c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48661347"
---
# <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Die Koexistenz und Interoperabilität zwischen Skype for Business-und Microsoft Teams-Clients und-Benutzern wird durch die TeamsUpgrade-Modi definiert, die unter [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md), beschrieben sind.

Jedem angegebenen Benutzer wird immer ein TeamsUpgrade-Modus zugewiesen, entweder standardmäßig oder explizit durch den Administrator. Der Standardwert ist " *Islands*". Für Benutzer, die auf Teams aktualisiert wurden, ist der Modus *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*und *SfBWithTeamsCollabAndMeetings* sind ebenfalls mögliche Modi.


## <a name="routing-parameters"></a>Routing Parameter

Der TeamsUpgrade-Modus des Empfängers ist ein entscheidender Faktor für das Verhalten von Chats, anrufen und Anwesenheitsinformationen, sowohl innerhalb eines Mandanten als auch über alle Föderations Mandanten.

Wenn der Absender Teams verwendet, wird beim Erstellen eines neuen Konversations Fadens die Routingentscheidung getroffen. Vorhandene Konversations Threads in Teams behalten immer die beim Erstellen des Threads festgelegte Routingmethode bei: Teams unterstützen persistente Threads.

 Die Methoden für das Thread Routing lauten wie folgt:  

- *systemeigene* für Teams, die Unterhaltungen im Mandanten führen
- *Interop* für ein Team für die Skype for Business-Unterhaltung im Mandanten
- *Federated* für eine Federated-Konversation über Mandanten hinweg

Die Parameter, die die Thread Routingmethode bestimmen, sind:

- Der TeamsUpgrade-Modus des Empfängers
- Der vom Absender verwendete Client
- Ob es sich um eine neue Konversation oder um einen Teil eines vorhandenen Threads handelt
- Ob es sich um eine Unterhaltung in einem Mandanten oder einer Föderation handelt
- Ob die Unterhaltung möglich ist
    - *Bei der Mandanten bezogenen* Interoperabilität muss der Mandant entweder Pure Online-oder Skype for Business-Hybrid sein. Rein lokale Mandanten können keine Mandantenübergreifende Interoperabilität aufweisen.
    - Für Mandanten *übergreifende Föderation* ist immer eine ordnungsgemäße Konfiguration von Skype for Business Federation sowie eine ordnungsgemäße Konfiguration des Teams für beide Mandanten erforderlich. Skype for Business-Hybrid ist für beide Mandanten nicht erforderlich.
    - Wenn das Skype for Business-Konto des Erstellers lokal gehostet wird, kann der Benutzer den Teams-Client nicht für die Mandanten Interoperabilität oder für die Föderation verwenden. Dieser Benutzer kann nur den Skype for Business-Client für Interoperabilität und Föderation verwenden.
    - Teams für die Kommunikation in Teams sind in-Mandanten immer möglich.

> [!NOTE]
> Wenn sich der Empfänger und der Absender im TeamsOnly-Aktualisierungsmodus befinden, ist die Unterhaltung ein systemeigener Chat, in dem alle Rich-Messaging-und Anruffunktionen enthalten sind. Weitere Informationen finden Sie unter [systemeigene Chat-Erfahrung für externe (Verbund-) Benutzer in Teams](native-chat-for-external-users.md). Befindet sich einer der Konversationsteilnehmer nicht im TeamsOnly-Upgrademodus, bleibt die Unterhaltung eine Interoperabilitäts Funktion mit nur-Text-Nachrichten.

## <a name="chat-and-call-routing"></a>Chat und Anrufweiterleitung

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Mandanten übergreifendes Routing für neue Chats oder Anrufe 

Die folgenden Tabellen erfassen das Routing von in-Tenant-Chats und-anrufen und gelten für neue Anrufe oder Chats, die nicht aus einem bereits vorhandenen Thread gestartet werden. Es wird beschrieben, welcher Client einen neuen Anruf oder Chat erhält, wenn er von einem Benutzer auf der linken Seite zu einem in-Tenant-Empfänger auf der rechten Seite stammt.

Nachrichten, die an TeamsOnly-Benutzer gesendet werden, werden immer an Teams weitergeleitet. Nachrichten, die an SFB \* -Nutzer gesendet werden, werden immer an Skype for Business weitergeleitet, wenn die Unterhaltung wie oben beschrieben möglich ist. Nachrichten, die an Inseln-Benutzer gesendet werden, werden immer an denselben Client weitergeleitet, von dem Sie gesendet wurden.

In den folgenden Tabellen wird angezeigt, welcher Client in einem bestimmten Modus einen Anruf vom Absender (drei ganz links) erhält, je nach dem Modus des Erstellers, dem ausgewählten Client und dem Aufenthaltsort des Skype for Business-Clients (auf-Prem oder Online).

In den folgenden Tabellen: 
- **SFB \* * _ steht für einen der folgenden Modi: _SfBOnly *, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Kursiver Text* hebt eine Interop-Unterhaltung hervor.

- **Nicht möglich** stellt eine Situation dar, in der der Chat oder Anruf nicht möglich ist. Der Urheber muss stattdessen Skype for Business in diesen Fällen verwenden. Dies ist einer der Gründe, warum die normativen Anleitungen von Microsoft für Kunden mit dem Namen "on-Prem/Hybrid" darin liegen, einen anderen Modus als "Inseln" (normalerweise SfBWithTeamsCollab) als Ausgangspunkt für die Upgrade-Reise zu Teams zu verwenden.

**Tabelle 1a: in-Tenant-neuer Chat oder Anrufweiterleitung an einen Empfänger im Modus "Inseln"**

| <br/><br/> Modus | Urheber <br/><br/> Client | <br/><br/> SFB &nbsp; Homed |<br/><br/>Route – >| Empfänger <br/><br/> Inselmodus  |
|--- |--- |--- |--- |--- |
| Inselmodus | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> Auf-Prem<br/>Auf-Prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SFB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Auf-Prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabelle 1B: in-Tenant-neuer Chat oder Anrufweiterleitung an einen Empfänger im SFB- \* Modus**

| <br/><br/> Modus   | Urheber <br/><br/> Client | <br/><br/> SFB &nbsp; Homed |<br/><br/>Route – > |   Empfänger <br/><br/> SFB\*   |
|--- |--- |--- |---   |--- |
| Inselmodus |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Auf-Prem<br/> Auf-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Nicht möglich** <br/>Skype for Business<br/> |
|SFB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Auf-Prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabelle 1C: in-Tenant-neuer Chat oder Anrufweiterleitung an einen Empfänger im TeamsOnly-Modus**

| <br/><br/> Modus   | Urheber <br/><br/> Client | <br/><br/> SFB &nbsp; Homed |<br/><br/>Route – >|   Empfänger <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Inselmodus   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> Auf-Prem<br/> Auf-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams*  |
|SFB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> Auf-Prem<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Federated-Routing für neue Chats oder Anrufe
  
In den folgenden Tabellen wird das Routing von verbundenen anrufen und Chats erfasst und für neue Anrufe oder Chats gültig. Sie beschreiben, welcher Client einen neuen Anruf oder Chat erhält, wenn er von einem Benutzer auf der linken Seite zu einem verbundenen Zielbenutzer auf der rechten Seite stammt.

Zusammengefasst: Wenn die Unterhaltung wie oben beschrieben möglich ist, werden Nachrichten, die an TeamsOnly-Benutzer gesendet werden, immer in Teams landen; Nachrichten, die an SFB- \* Nutzer gesendet werden, werden immer in Skype for Business landen; Nachrichten, die an Inseln-Benutzer gesendet werden, werden immer in Skype for Business landen, unabhängig vom Kunden, von dem Sie gesendet wurden. Das Routing für verbundene Chats und Anrufe unterscheidet sich vom in-Tenant-Routing, in dem die Benutzer immer eine Föderations Kommunikation in Skype for Business erhalten.

Dies liegt daran, dass wir nicht davon ausgehen können, dass ein Partner von Skype for Business bereits Teams verwendet, wenn Sie sich im Modus "Inseln" befinden. Inseln ist der Standardmodus, aber wir können nicht davon ausgehen, dass alle Inseln-Benutzer Teams ausführen. Durch Routing zu Skype for Business stellen wir sicher, dass keine Kommunikation mit einem Insel Nutzer fehlschlägt. Wenn wir an Teams weitergeleitet werden, könnte diese Kommunikation übersehen werden, wenn das Ziel keine Teams verwendet hat. Durch das Routing zu Skype for Business wird sichergestellt, dass die Nachricht immer empfangen wird.  

> [!NOTE]
> Die aktuelle Implementierung des Teams Federation basiert auf der Skype for Business-Föderation, daher nutzt Sie die Interoperabilitäts Infrastruktur (die den Mandanten des Erstellers als pure Online-oder Skype for Business-hybride benötigt) und bietet einen reduzierten Satz an Funktionen im Vergleich zu einem nativen Thread. Wir gehen davon aus, dass Native Teams in Zukunft für Teams in der Föderation bereitgestellt werden, wobei der Thread systemeigen ist und vollständige Funktionen bietet.

In den folgenden Tabellen wird beschrieben, welcher Client einen Anruf vom Absender erhält (drei Spalten ganz links), je nach dem Modus des Erstellers, dem ausgewählten Client und dem Aufenthaltsort des Skype for Business-Clients (auf-Prem oder Online).

**Tabelle 2a: Föderation des neuen Chats oder Anrufweiterleitung zu einem Insel Empfänger**

| <br/><br/>Modus   | Urheber<br/><br/> Client| <br/><br/>SFB Homed|<br/><br/>Route – > | Empfänger<br/><br/> Inselmodus |
|--- |--- |--- |--- |--- |
| Inselmodus |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Auf-Prem<br/> Auf-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Nicht möglich**   <br/> Skype for Business |
| SFB\* |Skype for Business <br/>Skype for Business |Online<br/> Auf-Prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabelle 2B: Föderation des neuen Chats oder Anrufweiterleitung an einen Empfänger im SFB- \* Modus**

| <br/><br/>Modus   | Urheber<br/><br/> Client| <br/><br/>SFB Homed|<br/><br/>Route – >|  Empfänger<br/><br/> SFB\* |  
|--- |--- |--- |--- |--- |
| Inselmodus |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Auf-Prem<br/> Auf-Prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Nicht möglich** <br/>Skype for Business <br/> |  
| SFB\* |Skype for Business <br/>Skype for Business  |Online<br/> Auf-Prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabelle 2C: Föderation des neuen Chats oder Anrufweiterleitung zu einem TeamsOnly-Modus-Empfänger**

| <br/><br/>Modus | Urheber<br/><br/> Client| <br/><br/>SFB Homed|<br/><br/>Route – >|  Empfänger<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Inselmodus  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Auf-Prem<br/> Auf-Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Microsoft Teams* <br/>**Nicht möglich** <br/>*Microsoft Teams* |
| SFB\* |Skype for Business <br/>Skype for Business  | Online<br/> Auf-Prem| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats und Anrufe von bereits vorhandenen Threads

### <a name="from-teams"></a>Aus Teams

Anrufe oder Chats, die von einem bereits vorhandenen beständigen Thread in Teams gestartet wurden, werden auf die gleiche Weise wie dieser Thread weitergeleitet, wenn diese Routing Option weiterhin verfügbar ist.

Wenn es sich bei dem bereits vorhandenen beständigen Thread in Microsoft Teams um einen systemeigenen Thread (d. h. Weiterleitung an Teams) handelt, werden zusätzliche Chatnachrichten und Anrufe von diesem Thread an Teams weitergeleitet. Wenn es sich um einen Interop-Thread (d. h. Weiterleitung an Skype for Business) handelt, gehen zusätzliche Chat-Nachrichten und Anrufe an Skype for Business (auch wenn die Routingoptionen verfügbar sind).

> [!NOTE]
> Es ist möglich, dass bereits vorhandene Threads in Teams nicht mehr geroutet werden können, beispielsweise wenn es sich bei dem Thread um einen Interop-Thread für einen Benutzer handelt, der nun auf Teams aktualisiert wird. Da es als Interop-Thread erstellt wurde, würde der Thread zu Skype for Business weiterleiten, aber dieser Benutzer kann Skype for Business für Chats und Anrufe nicht mehr verwenden. In diesem Fall wird der Thread deaktiviert und ermöglicht keine weitere Kommunikation.

### <a name="from-skype-for-business"></a>Von Skype for Business

Skype for Business-Threads bleiben nicht über das Timeout von 10 min. SIP-Sitzungen hinaus. Chats und Anrufe von einem vorhandenen Thread in Skype for Business vor Ablauf der SIP-Sitzung werden auf die gleiche Weise wie der Thread weitergeleitet. Anrufe und Chats von einem vorhandenen Thread in Skype for Business über das Timeout der SIP-Sitzung hinaus werden an das Skype for Business der Remote-Partei weitergeleitet, unabhängig davon, von welchem Client der ursprüngliche Thread auf der Seite der anderen Partei kam.

### <a name="availability"></a>Verfügbarkeit

Sowohl das in-Tenant-als auch das Federated-Verhalten, das oben beschrieben wird, ist mit den folgenden Einschränkungen verfügbar:

- Externe Teilnehmer, deren Mandanten sich in einer anderen GoLocal-Bereitstellung befinden, werden im Chat nicht angezeigt, während Sie sich in einer "Föderations Besprechung" befinden
- Föderation und Interoperabilität zwischen Mandanten Office 365 und souveränen Wolken werden nicht unterstützt

## <a name="presence"></a>Anwesenheit

Wenn Sie eine Situation haben, in der einige Ihrer Benutzer den Microsoft Teams-Client verwenden und andere weiterhin den Skype for Business-Client verwenden, haben Sie möglicherweise eine Reihe von Benutzern, die beide Clients verwenden. Sie möchten, dass die Anwesenheitsstatus für alle Benutzer freigegeben werden, und zwar unabhängig davon, welchen Client ein einzelner Benutzer hat. Wenn dies in der gesamten Organisation freigegeben ist, können Benutzer besser feststellen, ob es angemessen ist, einen Chat zu initiieren oder einen Anruf zu tätigen.

Wenn beispielsweise der Chat oder Anruf eines Absenders auf dem Skype for Business-Client des Ziels landet, ist der Skype for Business-Client vorhanden, der dem Absender angezeigt werden sollte. Wenn Sie auf dem Team Client des Ziels landet, sollte die Anwesenheit des Teams-Clients angezeigt werden.

Um zu erfahren, welches Verhalten zu erwarten ist, müssen Sie wissen, dass die Anwesenheitsfunktion basierend auf dem Koexistenzmodus eines Benutzers freigegeben wird:

* Wenn sich ein Benutzer im TeamsOnly-Modus befindet, wird jeder andere Benutzer (ob in Teams oder Skype for Business) sehen, dass der TeamsOnly-Benutzer die Team Anwesenheit erhält.
* Wenn sich ein Nutzer in einem der SFB- \* Modi befindet (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), wird jeder andere Nutzer (in Teams oder Skype for Business) sehen, dass der SFB \* -Nutzer Skype for Business-Anwesenheitsinformationen hat.
* Wenn sich ein Benutzer im Modus "Inseln" (oder "Legacy") befindet, ist die Anwesenheit in Teams und die Anwesenheit in Skype for Business unabhängig (die Werte müssen nicht übereinstimmen), und andere Benutzer sehen je nachdem, ob Sie sich im gleichen Mandanten oder in einem Verbund Mandanten befinden und welchen Client Sie verwenden
    * In Teams sehen alle anderen Benutzer innerhalb desselben Mandanten die Anwesenheitsinformationen des Teams für die Inseln des Benutzers. Diese wird mit der in-Tenant-Routingtabelle oben ausgerichtet.
    * In Teams sehen alle anderen Benutzer in einem Verbund Mandanten die Skype for Business-Anwesenheit der Inseln-Benutzer. Diese wird an der oben aufgeführten Federated-Routingtabelle ausgerichtet.
    * Bei Skype for Business sehen alle anderen Nutzer die Skype for Business-Anwesenheit des Nutzers (sowohl im Mandanten als auch im Verbund). Diese wird an den oben angegebenen Routingtabellen ausgerichtet.


### <a name="in-tenant-presence"></a>Anwesenheit in einem Mandanten

Nachrichten, die an TeamsOnly-Benutzer gesendet werden, landen immer in Teams. Nachrichten, die an SFB \* -Nutzer gesendet werden, werden immer in Skype for Business landen, wenn die Unterhaltung wie oben beschrieben möglich ist. Nachrichten, die an Inseln-Benutzer gesendet werden, landen immer in dem Client, aus dem Sie stammen.

In der Tabelle wird die Anwesenheit des Herausgebers beschrieben, die von einem Watcher abhängig vom Modus des Herausgebers und dem Client des Watcher (für einen neuen Thread) angezeigt wird.

**Tabelle 3: Anwesenheit im Mandanten (neuer Thread)**

|Überwachungselement <br/><br/>Client|<br/><br/>Route – > |<br/><br/>Inselmodus |Publisher <br/><br/>SFB\* |<br/>Nur für Teams|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Microsoft Teams|
|Microsoft Teams |&boxv; |Microsoft Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>Verbund Anwesenheit

Die Verbund Anwesenheit basiert auf der in Tabelle 2 gezeigten Federated-Erreichbarkeit.

In der folgenden Tabelle wird die Anwesenheit des Herausgebers beschrieben, die je nach dem Modus des Herausgebers und dem Client des Watcher (für einen neuen Thread) von einem Watcher-Element angezeigt wird. In der Praxis macht der Kunde des Watcher in dieser Phase keinen Unterschied in der Föderation.

**Tabelle 4: Verbund Anwesenheit (neuer Thread)**

|Überwachungselement <br/><br/> Client |<br/><br/>Route – >|<br/><br/> Inselmodus  |Publisher <br/><br/> SFB\* |<br/><br/> Nur für Teams |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Microsoft Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Anwesenheit in bereits vorhandenen Threads

Um die Anwesenheits-und Erreichbarkeit in bereits vorhandenen Threads auszurichten, muss die in diesem Thread verfügbar gemachte Anwesenheit des Ziels mit dem Routing des Threads ausgerichtet werden, vorausgesetzt, das Routing ist möglich.

Insbesondere, wenn ein Empfänger, für den Sie zuvor einen beständigen Interop-konversationsthread hatten, auf Teams aktualisiert wurde, reflektiert dieser Thread nicht mehr die genaue Anwesenheit und ist nicht mehr routingfähig. Beginnen Sie einen neuen Thread.

## <a name="related-links"></a>Verwandte Links
[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Video: Verwalten der Koexistenz und Interoperabilität zwischen SFB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
