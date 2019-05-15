---
title: Koexistenz mit Skype for Business
author: kenwith
ms.author: kenwith
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
description: Dieses Dokument beschreibt das Verhalten der Chat, Anrufrouting und Anwesenheit zwischen Benutzern, Teams und Skype für Unternehmen, die im Mandanten und Verbundpartner, basierend auf zugewiesenen TeamsUpgrade Modi. Sie umfasst routing Optimierungen, Anwesenheit Verhalten sowie die Änderung TeamsUpgrade Standardmodus aus *Legacy* *Inseln* und die bevorstehende Stilllegung der *Vorversion*.
ms.openlocfilehash: 3c88bd93805e6c2a33eb2f5c03ee04d4e7d55535
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929105"
---
# <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Koexistenz und Interoperabilität zwischen Benutzern und Skype für Geschäfts- und Teams Clients wird durch TeamsUpgrade Modi, [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Business](migration-interop-guidance-for-teams-with-skype.md)beschriebenen definiert.

Alle Benutzer werden immer einen TeamsUpgrade-Modus, entweder standardmäßig oder explizit durch den Administrator zugewiesen. Der Standardwert ist *Inseln*. Benutzer, die Teams aktualisiert haben, den Modus der *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*und *SfBWithTeamsCollabAndMeetings* sind auch Modi.


## <a name="routing-parameters"></a>Routing-Parameter

Der Modus TeamsUpgrade des Empfängers ist Schlüssel bestimmt das Verhalten des Chats, Anrufe und Anwesenheit, sowohl innerhalb einer mandantenstruktur und Verbundpartner konstant.

Wenn der Absender Teams verwendet wird, erfolgt die Routingentscheidung beim Erstellen einer neuen Unterhaltungsthreads. Vorhandene Unterhaltung Threads in Teams beibehalten immer bei der Erstellung des Threads bestimmt die Routingmethode: Teams persistent Threads unterstützt.

 Thread Routingmethoden sind:  

- *systemeigene* für eine Teams, Teams Unterhaltung im Mandanten
- *Interop* für einen Skype-Teams für Business Unterhaltung im Mandanten
- für eine Unterhaltung federated konstant *Verbund*

Der Parameter, mit die die Routingmethode Thread bestimmt sind:

- Der Modus TeamsUpgrade des Empfängers
- Die vom Absender verwendete client
- Gibt an, ob die Unterhaltung neu oder Teil eines vorhandenen Threads ist
- Gibt an, ob die Unterhaltung im Mandanten oder im Verbund ist
- Gibt an, ob die Unterhaltung möglich ist.
    - Interoperabilität *im Mandanten* erfordert, dass der Mandant entweder ist rein online oder Skype für hybride Business. Rein lokalen Mandanten in Mandanten Interoperabilität haben können.
    - *Cross-Mandanten Verbund* erfordert immer ordnungsgemäße Skype für Business Verbundkonfiguration als auch Teams Verbundkonfiguration aus beiden Mandanten. Skype für hybride Business ist nicht erforderlich, entweder-Mandanten.
    - Wenn die Skype für Business-Konto des Absenders lokal ist, kann nicht der Benutzer der Client Teams für die Interoperabilität in Mandanten oder für den Verbund verwenden. Benutzer kann nur die Skype für Business-Client für Interoperabilität und Verbund verwenden.
    - Teams Teams Kommunikation ist immer möglich Mandanten.

> [!NOTE]
> Derzeit nutzt alle einen Verbund mit Teams die Skype für Business Verbund Pipeline sowie Teams – Skype für die Business-Interoperabilität. Wir sind systemeigene Teams – Teams Verbund planen. Dokuments werden bei der Freigabe der systemeigenen Föderation aktualisiert.

# <a name="chat-and-call-routing"></a>Chat und Anrufrouting

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Mandanten Sie routing für neue Chats oder Anrufe 

In den folgenden Tabellen erfassen routing von im Mandanten Chat und Anrufe und gelten für neue Anrufe oder Chats, die von einem bereits vorhandenen Thread nicht gestartet werden. Beschrieben werden der Clientcomputer erhält einen neuen Anruf oder Chat, wenn ein Benutzer auf der linken Seite an einen Empfänger im Mandanten-Benutzer auf der rechten Seite stammt.

An TeamsOnly Benutzer gesendete Nachrichten werden immer an Teams weiterleiten. Nachrichten an SfB\* Benutzer werden immer Weiterleitung an Skype für Unternehmen, wenn die Unterhaltung möglich, wie oben beschrieben ist. An Inseln Benutzer gesendete Nachrichten leitet immer an den gleichen Client, von denen sie gesendet wurden.

In den Tabellen unten zeigt, welche Client in einem bestimmten Modus erhalten einen Anruf über den Ersteller (drei am weitesten links Spalten), je nach den Ersteller Modus Client ausgewählt, und, wo ihre Skype für Business Client verwaltet wird (auf Prem oder online).

Führen Sie in den Tabellen, die aus: 
- **SfB\* ** stellt einen der folgenden Modi: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Kursiv formatierten Text* markiert eine Interop-Unterhaltung.

- **Nicht möglich,** stellt eine Situation, in denen die Chat oder Anruf nicht möglich ist. Der Absender muss Skype für Business stattdessen in diesen Fällen verwenden. Dies ist eine der die Gründe für die Microsoft Leitfäden für Prem/Hybrid Kunden einen Modus als Inseln (in der Regel SfBWithTeamsCollab) verwenden, als Ausgangspunkt für ihre Upgrade Reise Teams.

**Tabelle 1a: Mandanten neue Chat oder Anrufrouting an einen Empfänger der Inseln-Modus**

| <br/><br/> Modus | Absender <br/><br/> Client | <br/><br/> SfB&nbsp;verwaltet | | Empfänger <br/><br/> Inseln  |
|--- |--- |--- |--- |--- |
| Inseln | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> Klicken Sie auf prem<br/>Klicken Sie auf prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Klicken Sie auf prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabelle 1 b: Mandanten neue Chat oder an einen Empfänger in einer SfB Anrufrouting\* Modus**

| <br/><br/> Modus   | Absender <br/><br/> Client | <br/><br/> SfB&nbsp;verwaltet | |   Empfänger <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Inseln |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Nicht möglich** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Klicken Sie auf prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabelle 1c: Mandanten neue Chat oder Anrufrouting an einen Empfänger der TeamsOnly-Modus**

| <br/><br/> Modus   | Absender <br/><br/> Client | <br/><br/> SfB&nbsp;verwaltet | |   Empfänger <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Inseln   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Microsoft Teams* <br/>Teams <br/>*Microsoft Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> Klicken Sie auf prem<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>Federated routing für neue Chats oder Anrufe
  
Die folgenden Tabellen Erfassen der Sammelsuche Aufrufe und Chats routing und für neue Anrufe oder Chats gültig sind. Beschreiben sie der Clientcomputer erhält einen neuen Anruf oder Chat, wenn ein Benutzer auf der linken Seite auf einen Verbundpartner Zielbenutzer auf der rechten Seite stammt.

In lässt sich sagen Wenn möglich, wie oben beschrieben, wird die Unterhaltung landen an TeamsOnly Benutzer gesendete Nachrichten immer in Teams; Nachrichten an SfB\* Benutzer landen immer in Skype für Unternehmen; an Inseln Benutzer gesendete Nachrichten landen immer in Skype für Unternehmen unabhängig von den Client aus denen sie gesendet wurden. Routing für federated Chats und Anrufe unterscheidet sich von in Mandanten routing, Inseln Benutzer immer eine federated Kommunikation in Skype für Unternehmen erhalten.

Dies ist, da es wird davon ausgegangen ist nicht möglich, einen Verbundpartner Skype für Geschäftspartner Teams bereits verwendet, wenn sie Inseln Modus werden. Inseln ist der Standardmodus, aber es wird davon ausgegangen ist nicht möglich, dass alle Inseln Benutzer Teams ausführen. Durch das Weiterleiten an Skype für Unternehmen stellen wir sicher, dass keine Kommunikation an einen Benutzer Inseln fällt aus. Wenn wir Teams weitergeleitet, konnte, dass die Kommunikation ausgelassen werden, wenn das Ziel nicht Teams verwendet haben. Routing zu Skype für Unternehmen wird sichergestellt, dass die Nachricht wird immer empfangen werden.  

> [!NOTE]
> Aktuelle Implementierung von Teams Verbund basiert auf Skype für den Verbund Business, daher sie nutzt die Interoperabilität (erfordert den Mandanten des Absenders entweder als reine online oder Skype für hybride Business) und bietet eine Reduzierter Satz von Funktionen im Vergleich zu einem systemeigenen Thread. Wir erwarten systemeigene Teams Teams Verbund in der Zukunft bereitstellen, an welcher Stelle der Thread werden systemeigene und vollständige Funktionen zur Verfügung stellen.

Die folgenden Tabellen beschreiben, welcher Client einen Anruf über den Ersteller (drei am weitesten links Spalten), je nach den Ersteller Modus Client ausgewählt, erhält und, wo ihre Skype für Business Client verwaltet wird (auf Prem oder online).

**Tabelle 2a: federated neue Chat oder Anrufrouting an einen Empfänger Inseln**

| <br/><br/>Modus   | Absender<br/><br/> Client| <br/><br/>SfB verwaltet| | Empfänger<br/><br/> Inseln |
|--- |--- |--- |--- |--- |
| Inseln |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Nicht möglich**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> Klicken Sie auf prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabelle 2 b: federated neue Chat oder Anrufrouting an einen Empfänger in einer SfB\* Modus**

| <br/><br/>Modus   | Absender<br/><br/> Client| <br/><br/>SfB verwaltet| |  Empfänger<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Inseln |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Nicht möglich** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> Klicken Sie auf prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabelle 2c: federated neue Chat oder Anrufrouting an einen Empfänger der TeamsOnly-Modus**

| <br/><br/>Modus | Absender<br/><br/> Client| <br/><br/>SfB verwaltet| |  Empfänger<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Inseln  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Microsoft Teams* <br/>**Nicht möglich** <br/>*Microsoft Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> Klicken Sie auf prem| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats und Aufrufen von vorhandenem threads

### <a name="from-teams"></a>Von Teams

Anrufe oder Chats Schritte von einem bereits vorhandenen, für den persistenten Thread in Teams die gleiche Weise wie diesem Thread weitergeleitet werden, wenn diese Option routing noch verfügbar ist.

Wenn vorhandenem persistent Threads in Teams einem systemeigenen Thread (d. h., Teams weitergeleitet) wurde, werden zusätzliche Chatnachrichten und Anrufe von diesem Thread zu Teams wechseln. Wenn ein Interop-Thread (d. h., Skype für Unternehmen geroutet) war, gehen zusätzliche Chatnachrichten und Anrufe an Skype für Unternehmen (erneut vorausgesetzt, dass Routingoptionen verfügbar sind).

> [!NOTE]
> Es ist möglich für vorhandenem Threads in Teams werden nicht mehr routingfähige, beispielsweise wenn Threads ein Interop-Thread zu einem Benutzer wurde, die nun auf Teams aktualisiert wird. Da es als ein Interop-Thread erstellt wurde, der Thread zu Skype für Unternehmen weitergeleitet, aber der Benutzer nicht mehr kann verwenden Skype für Business für Chat und Aufrufen von. In diesem Fall der Thread deaktiviert sein und weitere Kommunikation nicht zulassen.

### <a name="from-skype-for-business"></a>Von Skype für Unternehmen

Skype für Business Threads führen Sie nicht über die 10 min. SIP-Sitzungstimeout bestehen. Chats und Anrufe aus einem vorhandenen Thread in Skype für Unternehmen vor Ablauf des SIP-Sitzung werden auf die gleiche Weise wie die Thread weitergeleitet werden. Anrufe und Chats aus einem vorhandenen Thread in Skype für Unternehmen über das SIP-Sitzungstimeout werden zu dem Remotebenutzer Skype für Unternehmen, weitergeleitet werden unabhängig von der, die Client der ursprüngliche Thread auf die andere Partei Seite stammt.

## <a name="availability"></a>Verfügbarkeit

Sowohl die im Mandanten und Verbundbenutzer Verhaltensweisen oben beschriebenen stehen zur Verfügung, mit der folgenden Einschränkungen:

- Externe Teilnehmer, dessen Mandanten befinden sich in einer anderen GoLocal Bereitstellung oder Geografie, keine Sofortnachrichten angezeigt chatten klicken Sie in einer Besprechung "federated"
- Verbund und die Interoperabilität zwischen Multitenant O365 und souveräne Wolken wird nicht unterstützt.

# <a name="presence"></a>Anwesenheit

Wenn Sie eine Situation, in dem einige Ihrer Benutzer verwenden des Teams Clients und andere Benutzer weiterhin die Skype für Business-Client verwenden können, Sie eine Anzahl von Benutzern möglicherweise, die beide Clients verwenden. Sie möchten jedoch noch Anwesenheitsstatus für alle Benutzer unabhängig von welcher Client freigegeben werden, die ein einzelner Benutzer hat. Wenn dies in der gesamten Organisation freigegeben ist, können Benutzer besser bestimmen, ob es empfiehlt sich, initiiert einen Chat oder tätigen eines Anrufs.

Beispielsweise wenn ein Ersteller Chat oder Anruf auf das Ziel Skype für Business Client sorgt sollten, ist es der Skype für Business-Client-Anwesenheit, die an den Absender angezeigt werden sollen. Wenn sie auf das Ziel Teams Client sorgt sollten, ist es der Teams Client Anwesenheitsinformationen, die angezeigt werden sollen.

Um wissen, welche das zu erwartende Verhalten, benötigen Sie erkennen, dass die Anwesenheit eines Benutzers Koexistenzmodus Grundlage freigegeben werden:

* Wenn ein Benutzer im TeamsOnly-Modus ist, und klicken Sie dann ein anderer Benutzer (, ob in Teams oder Skype für Unternehmen) des Benutzers, TeamsOnly Teams Anwesenheitsinformationen angezeigt werden
* Wenn ein Benutzer in einer der der SfB ist\* Modi (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), und klicken Sie dann auf einem anderen Benutzer (, ob in Teams oder Skype für Unternehmen) sehen, SfB\* Skype Business Vorhandensein des Benutzers
* Wenn ein Benutzer in Inseln (oder Legacy) ist Modus, Anwesenheitsinformationen in Teams und Anwesenheitsinformationen in Skype für Unternehmen sind unabhängige (die Werte nicht übereinstimmen) und andere Benutzer sieht eine oder das Vorhandensein der Benutzer Inseln, je nachdem, ob sie in derselben mandantenorganisation oder in einer Federat sind ED Mandanten und dem Client Verwendung
    * Von Teams wird ein anderer Benutzer innerhalb derselben mandantenorganisation des Benutzers Inseln Teams Anwesenheitsinformationen angezeigt. Dies wird mit der im Mandanten routing-Tabelle oben ausgerichtet.
    * Von Teams wird ein anderer Benutzer in einem Verbundpartner Mandanten des Benutzers Inseln Skype für Business Anwesenheitsinformationen angezeigt. Dies wird mit der Sammelsuche Routingtabelle oben ausgerichtet.
    * Von Skype für Unternehmen wird ein anderer Benutzer des Benutzers Inseln Skype Business Vorhandensein (sowohl im Mandanten und Verbundpartner) angezeigt. Dies wird mit den Routingtabellen oben ausgerichtet.


## <a name="in-tenant-presence"></a>Mandanten Anwesenheit

An TeamsOnly Benutzer gesendete Nachrichten landen immer in Teams. Nachrichten an SfB\* Benutzer landen immer in Skype für Unternehmen, wenn die Unterhaltung möglich, wie oben beschrieben ist. An Inseln Benutzer gesendete Nachrichten landen immer im-Client, aus denen sie stammen wurden.

Die Tabelle beschreibt den Herausgeber Anwesenheitsinformationen, die einen Monitor, je nach den Modus des Herausgebers und der Client von der Watcher-Knoten (für einen neuen Thread) angezeigt wird.

**Tabelle 3: im Mandanten Anwesenheit (neuen Threads)**

|Watcher <br/><br/>Client| |<br/><br/>Inseln |Publisher <br/><br/>SfB\* |<br/>Nur Teams|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Microsoft Teams|
|Microsoft Teams |&boxv; |Microsoft Teams |Skype for Business |Teams |
| | | | |

## <a name="federated-presence"></a>Verbundpartner Anwesenheit

Verbundpartner Anwesenheit basiert auf der Sammelsuche Erreichbarkeit in Tabelle 2 gezeigt.

In der folgenden Tabelle wird beschrieben, die vom Herausgeber Anwesenheitsinformationen, die einen Monitor, je nach den Modus des Herausgebers und der Client von der Watcher-Knoten (für einen neuen Thread) angezeigt wird. Der Client von der Watcher-Knoten spielt keine Rolle im Verbund in dieser Phase, in der Praxis.

**Tabelle 4: federated Anwesenheit (neuen Threads)**

|Watcher <br/><br/> Client | |<br/><br/> Inseln  |Publisher <br/><br/> SfB\* |<br/><br/> Nur Teams |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Microsoft Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Anwesenheitsinformationen in vorhandenem threads

Um ausrichten Anwesenheits- und Erreichbarkeit in vorhandenem Threads, das Ziel Anwesenheit verfügbar gemacht werden, dass Thread mit dem routing des Threads ausgerichtet werden sollen muss, ist es möglich, ausgehend routing.

Insbesondere wenn einen Empfänger Sie zuvor eine beständige interop Unterhaltungsthreads mit hatten wurde aktualisiert, Teams, dass Thread wider präzise Anwesenheit nicht mehr und nicht mehr routingfähig sein. Sie sollten einen neuen Thread starten.

## <a name="related-links"></a>Verwandte Links
[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Video: Verwalten von Koexistenz und Interoperabilität zwischen SfB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
