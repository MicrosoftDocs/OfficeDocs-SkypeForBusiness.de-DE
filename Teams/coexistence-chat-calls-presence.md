---
title: Koexistenz mit Skype für Unternehmen
author: jambirk
ms.author: francoid
manager: Serdars
ms.date: 11/7/2018
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: Dieses Dokument beschreibt das Verhalten der Chat, Anrufrouting und Anwesenheit zwischen Benutzern, Teams und Skype für Unternehmen, die im Mandanten und Verbundpartner, basierend auf zugewiesenen TeamsUpgrade Modi. Sie umfasst routing Optimierungen, Anwesenheit Verhalten sowie die Änderung TeamsUpgrade Standardmodus aus *Legacy* *Inseln* und die bevorstehende Stilllegung der *Vorversion*.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0d6e4ad171ffc99e1f0aaa1c3b93e0fd61443bc
ms.sourcegitcommit: 42143176c46ba9496a0fd401c8e4774075106b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238106"
---
# <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype für Unternehmen

Koexistenz und Interoperabilität zwischen Skype für Unternehmen und Teams wird definiert, durch TeamsUpgrade Modi, [Migration und Interoperabilität Anleitungen für Organisationen](migration-interop-guidance-for-teams-with-skype.md)mit Teams zusammen mit Skype für Unternehmen beschrieben.

Alle Benutzer werden immer einen TeamsUpgrade-Modus, entweder standardmäßig oder explizit durch den Administrator zugewiesen. Der Standardwert ist *Inseln*. Benutzer, die Teams aktualisiert haben, den Modus der *TeamsOnly*.

> [!NOTE]
> *Legacymodus* wurde als veraltet eingestuft. Benutzer verbleibenden *Legacy* -Modus werden in *Inseln* Modus nach 15 November 2018 konvertiert werden soll.

## <a name="routing-parameters"></a>Routing-Parameter

Der Modus TeamsUpgrade des Empfängers ist Schlüssel bestimmt das Verhalten des Chats, Anrufe und Anwesenheit, sowohl innerhalb einer mandantenstruktur und Verbundpartner konstant.

Wenn der Absender Teams verwendet wird, erfolgt die Routingentscheidung beim Erstellen einer neuen Unterhaltungsthreads. Vorhandene Unterhaltung Threads in Teams behalten immer die routing-Methode festgelegt wird, wenn der Thread erstellt wurde. Teams unterstützt beständige Threads.

 Thread Routingmethoden sind:  
* *systemeigene* für eine Teams, Teams Unterhaltung im Mandanten
* *Interop* für einen Skype-Teams für Business Unterhaltung im Mandanten
* der *Verbund* für einen Verbundpartner Unterhaltung konstant.

Der Parameter, mit die die Routingmethode Thread bestimmt sind:
* Der Modus TeamsUpgrade des Empfängers
* Die vom Absender verwendete client
* Gibt an, ob die Unterhaltung neu oder Teil eines vorhandenen Threads ist
* Gibt an, ob die Unterhaltung im Mandanten oder im Verbund ist
* Gibt an, ob die Unterhaltung möglich ist.
    * Im Mandanten Interoperabilität und Verbund von Teams erfordert, dass der Absender Mandanten ist entweder rein online oder Skype für hybride Business. Rein lokale Mandanten können nicht im Mandanten Interoperabilität oder für den Verbund Teams haben.
    * Wenn die Skype für Business-Konto des Absenders verwaltete am Standort ist, kann nicht der Benutzer der Client Teams für die Interoperabilität in Mandanten und für den Verbund verwenden. Der Benutzer muss die Skype für Business-Client für Interoperabilität und Verbund verwenden.
    * Teams Teams Kommunikation ist immer möglich Mandanten.

# <a name="chat-and-call-routing"></a>Chat und Anrufrouting

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Mandanten Sie routing für neue Chats oder Anrufe 

In der folgenden Tabelle werden die aktuellen Practice für Chat in Mandanten und Anrufrouting erfasst. In dieser Tabelle ist gültig für neue Anrufe oder Chats, die von einem bereits vorhandenen Thread nicht gestartet werden. Es wird beschrieben, an den Client einen neuen Anruf (oder Chat) weitergeleitet werden, wenn von einem Benutzer von links, um eine im Mandanten Zielbenutzer auf der rechten Seite stammt.

An TeamsOnly Benutzer gesendete Nachrichten landen immer in Teams. An SfB * Benutzer gesendete Nachrichten landen immer in Skype für Unternehmen, wenn die Unterhaltung möglich, wie oben beschrieben ist. An Inseln Benutzer gesendete Nachrichten landen immer im-Client, aus denen sie stammen wurden.

**Tabelle 1: Mandanten neue Chat oder Anrufrouting**

| <br/> Modus   | Von&nbsp;Absender <br/> Client | <br/> SfB&nbsp;verwaltet | | <br/> Inseln  | Um&nbsp;Ziel <br/> SfB\*   | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |--- |
| Inseln <br/>Inseln <br/>Inseln <br/>Inseln<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Microsoft Teams<br/>SfB <br/>Microsoft Teams <br/>SfB <br/>SfB <br/>SfB <br/>Microsoft Teams|Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/> Online<br/> Klicken Sie auf prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>|Microsoft Teams <br/> SfB <br/> Microsoft Teams <br/> SfB <br/>  SfB <br/> SfB <br/> Microsoft Teams | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>*SfB* <br/>  | Microsoft Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams* <br/> *Microsoft Teams*  <br/>*Microsoft Teams* <br/>Microsoft Teams <br/> |
|  | | | | | | |

In der Tabelle SfB * stellt einen der folgenden Modi: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Kursiv formatierten Text* in der Tabelle zeigt eine Interop-Unterhaltung an.

**-Stärke** in der Tabelle stellt eine Situation, in denen die Chat oder Anruf nicht möglich ist. Dies liegt daran die Interoperabilität ist nur online verfügbar und erfordert die Skype für Business-Konto zugeordnet ist das Konto Teams aus, um ein online-Konto handeln. Der Absender muss Skype für Business stattdessen in diesen Fällen verwenden. Dies ist einer der Gründe für Microsoft Leitfäden für Kunden Prem/Hybrid verwenden Sie einen anderen Modus als Inseln (in der Regel *SfBWithTeamsCollab*) als Ausgangspunkt für ihre Upgrade Reise Teams.

## <a name="federated-routing-for-new-chats-or-calls"></a>Federated routing für neue Chats oder Anrufe
  
In der folgenden Tabelle werden die aktuelle federated Anruf (und Chat) routing Methoden erfasst. In dieser Tabelle ist für neue Anrufe oder Chats gültig. Es wird beschrieben, an den Client einen neuen Anruf (oder Chat) weitergeleitet werden, wenn von einem Benutzer auf der linken Seite auf einen Verbundpartner Zielbenutzer auf der rechten Seite stammt.

In lässt sich sagen Wenn möglich, wie oben beschrieben, wird die Unterhaltung landen an TeamsOnly Benutzer gesendete Nachrichten immer in Teams; an SfB * Benutzer gesendete Nachrichten landen immer in Skype für Unternehmen; an Inseln Benutzer gesendete Nachrichten landen immer in Skype für Unternehmen unabhängig von den Client aus denen sie stammen wurden. Routing für federated Chats und Anrufe unterscheidet sich von in Mandanten routing, Inseln Benutzer immer eine federated Kommunikation in Skype für Unternehmen erhalten.

Der Grund für diese letzte Punkt ist, dass es wird davon ausgegangen ist nicht möglich, einen Verbundpartner Skype für Geschäftspartner Teams bereits verwendet, wenn sie Inseln Modus werden. Inseln ist der Standardmodus, aber es wird davon ausgegangen ist nicht möglich, dass alle Inseln Benutzer Teams ausführen. Durch das Weiterleiten an Skype für Unternehmen stellen wir sicher, dass keine Kommunikation an einen Benutzer Inseln fällt aus. Wenn wir Teams weitergeleitet, konnte, dass die Kommunikation ausgelassen werden, wenn das Ziel nicht Teams verwendet haben. Routing zu Skype für Unternehmen wird sichergestellt, dass die Nachricht wird immer empfangen werden.  

> [!NOTE]
> Aktuelle Implementierung von Teams Verbund basiert auf Skype für den Verbund Business, daher sie nutzt die Interoperabilität (erfordert den Mandanten des Absenders entweder als reine online oder SfB Hybrid) und bietet eine reduzierte Auswahl an Funktionen im Vergleich zu einem systemeigenen Thread. Wir erwarten systemeigene Teams Teams Verbund in der Zukunft bereitstellen, an welcher Stelle der Thread werden systemeigene und vollständige Funktionen zur Verfügung stellen.

**Tabelle 2: federated neue Chat oder Anrufrouting**

| <br/>Modus   | Vom Absender<br/> Client| <br/>SfB verwaltet| | <br/> Inseln | Ziel<br/> SfB\* | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |---|
| Inseln <br/>Inseln <br/>Inseln <br/>Inseln<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Microsoft Teams<br/>SfB <br/>Microsoft Teams <br/>SfB <br/>SfB <br/>SfB <br/>Microsoft Teams|Online<br/> Online<br/> Klicken Sie auf prem<br/> Klicken Sie auf prem<br/> Online<br/> Klicken Sie auf prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/> | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/>  | Microsoft Teams <br/>Microsoft Teams <br/>**NA** <br/>*Teams <br/>Teams <br/>Teams* <br/>Microsoft Teams <br/> |
|  | | | | | |

In der Tabelle SfB * stellt einen der folgenden Modi: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Kursiv formatierten Text* markiert eine Interop-Unterhaltung.

**-Stärke** stellt eine Situation, in denen die Chat oder Anruf nicht möglich ist. Der Absender muss Skype für Business stattdessen in diesen Fällen verwenden. Dies ist einer der Gründe für Microsoft Leitfäden für Kunden Prem/Hybrid verwenden Sie einen anderen Modus als Inseln (in der Regel SfBWithTeamsCollab) als Ausgangspunkt für ihre Upgrade Reise Teams.

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats und Aufrufen von vorhandenem threads

### <a name="from-teams"></a>Von Teams

Anrufe oder Chats Schritte von einem bereits vorhandenen, für den persistenten Thread in Teams die gleiche Weise wie diesem Thread weitergeleitet werden, wenn diese Option routing noch verfügbar ist. 

Wenn vorhandenem persistent Threads in Teams einem systemeigenen Thread (d. h., Teams weitergeleitet) wurde, werden zusätzliche Chatnachrichten und Anrufe von diesem Thread zu Teams wechseln. Wenn ein Interop-Thread (d. h., Skype für Unternehmen geroutet) war, gehen zusätzliche Chatnachrichten und Anrufe an Skype für Unternehmen (erneut vorausgesetzt, dass Routingoptionen verfügbar sind).

> [!NOTE]
> Vorhandenem Threads im Teams möglicherweise nicht mehr routingfähige. Beispielsweise können auftreten, wenn der Thread ein Interop-Thread zu einem Benutzer war, die nun auf Teams aktualisiert wird. Da es sich um eine Interop-Thread handelt, kann Threads zu Skype für Unternehmen weitergeleitet dieser Benutzer nicht mehr jedoch Skype für Unternehmen für Chat und Aufrufen von. In diesem Fall der Thread deaktiviert sein und weitere Kommunikation nicht zulassen.

### <a name="from-skype-for-business"></a>Von Skype für Unternehmen

Skype für Unternehmen hat keinen Thread Persistenz hinter der SIP-Sitzungstimeout (10 Minuten). Chats und Anrufe aus einem vorhandenen Thread in Skype für Unternehmen vor Ablauf des SIP-Sitzung werden auf die gleiche Weise wie die Thread weitergeleitet werden. Anrufe und Chats aus einem vorhandenen Thread in Skype für Unternehmen über das SIP-Sitzungstimeout werden zu dem Remotebenutzer Skype für Unternehmen, weitergeleitet werden unabhängig von der, die Client der ursprüngliche Thread auf die andere Partei Seite stammt.

## <a name="availability"></a>Verfügbarkeit

Das oben beschriebene Verhalten im Mandanten ist in der Produktion heute verfügbar.

Das oben beschriebene federated Verhalten ist vor allem in der Produktion heute verfügbar. Die folgenden Elemente werden weiterhin eingeführt werden und sind nur für den Mandanten auf frühe Übernahmen verfügbar: 
* Partnerverbund mit einem lokalen Mandanten mit Anwesenheitsinformationen Sichtbarkeit
* Anzeigen von den migrierten Verbundkontakten in der Kontaktliste des Teams client
* Die Möglichkeit, SIP-URI oder SMTP-Adresse verwenden, um einen Partnerkontakt ermitteln.

Einführung für diese hat wird begonnen und allgemeine Verfügbarkeit vor Ende November 2018 erwartet.

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

> [!NOTE]
> Dies ist einer kürzlich vorgenommenen Änderung aus der vorherigen Implementierung (Unified Anwesenheit genannt) der kombinierten, aggregierten Anwesenheitsstatus des Ziels Teams und Skype für Business Clients ergab. Diese vorherigen Ansatz war für Benutzer verwirrend sein, da es häufig angezeigt, die in den genauen Anwesenheitsinformationen, d. h. dass Benutzer nicht erreichbar, obwohl ihre Anwesenheit, die sie online ergab führen würde.

## <a name="in-tenant-presence"></a>Mandanten Anwesenheit

An TeamsOnly Benutzer gesendete Nachrichten landen immer in Teams. Nachrichten an SfB\* Benutzer landen immer in Skype für Unternehmen, wenn die Unterhaltung möglich, wie oben beschrieben ist. An Inseln Benutzer gesendete Nachrichten landen immer im-Client, aus denen sie stammen wurden.

Die Tabelle beschreibt den Herausgeber Anwesenheitsinformationen, die einen Monitor, je nach den Modus des Herausgebers und der Client von der Watcher-Knoten (für einen neuen Thread) angezeigt wird.

**Tabelle 3: im Mandanten Anwesenheit (neuen Threads)**

|Watcher <br/>Client| |<br/>Inseln |Publisher <br/>SfB\* |<br/>Nur Teams|
|--- |--- |--- |--- |---|
|SfB <br/> Microsoft Teams|&boxv;<br/>&boxv;<br/> |SfB <br/>Microsoft Teams | SfB <br/>SfB | Microsoft Teams  <br/> Microsoft Teams |
| | | | |

## <a name="federated-presence"></a>Verbundpartner Anwesenheit

Verbundpartner Anwesenheit basiert auf der Sammelsuche Erreichbarkeit in Tabelle 2 gezeigt.

In der folgenden Tabelle wird beschrieben, die vom Herausgeber Anwesenheitsinformationen, die einen Monitor, je nach den Modus des Herausgebers und der Client von der Watcher-Knoten (für einen neuen Thread) angezeigt wird. Der Client von der Watcher-Knoten spielt keine Rolle im Verbund in dieser Phase, in der Praxis.

**Tabelle 4: federated Anwesenheit (neuen Threads)**

|Watcher <br/> Client | |<br/> Inseln  |Publisher <br/> SfB\* |<br/> Nur Teams  |
|--- |--- |--- |--- |---|
|SfB <br/> Microsoft Teams|&boxv;<br/>&boxv; |SfB <br/> SfB | SfB <br/> SfB | Microsoft Teams <br/> Microsoft Teams |
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Anwesenheitsinformationen in vorhandenem threads

Um ausrichten Anwesenheits- und Erreichbarkeit in vorhandenem Threads, das Ziel Anwesenheit verfügbar gemacht werden, dass Thread mit dem routing des Threads ausgerichtet werden sollen muss, ist es möglich, ausgehend routing.

Insbesondere wenn einen Empfänger Sie zuvor eine beständige interop Unterhaltungsthreads mit hatten wird anschließend aktualisiert, Teams, dass Thread wider präzise Anwesenheit nicht mehr und nicht mehr routingfähig sein. Sie sollten einen neuen Thread starten.
