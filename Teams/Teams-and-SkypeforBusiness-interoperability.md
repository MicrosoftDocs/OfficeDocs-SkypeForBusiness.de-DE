---
title: "Interoperabilität von Microsoft Teams und Skype for Business"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Hier erhalten Sie Informationen zur Interoperabilität zwischen Microsoft Teams und Skype for Business sowie zu den Auswirkungen auf die Verwendung von Chats und Anrufen."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8eca9f18d02d76fe1ab1b754ecf8a49b6b20aec3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Interoperabilität von Microsoft Teams und Skype for Business
=======================================================

Wenn Ihre Organisation zurzeit Skype for Business einsetzt und Sie Microsoft Teams verwenden möchten, müssen Sie verstehen, wie die beiden Anwendungen für die gemeinsame Verwendung konfiguriert werden.

> [!IMPORTANT]
> Dieses Dokument wird für die frühzeitige Bewertung von Anrufplänen für Microsoft Teams bereitgestellt. Die Details zu den Interop-Richtlinien für Microsoft Teams werden sich voraussichtlich in Zukunft ändern.

Dank der Interoperabilität (kurz „Interop“) ist die flüssige Kommunikation in der gesamten Organisation gewährleistet, das heißt, Benutzer von Skype for Business und Microsoft Teams können miteinander chatten und einander anrufen. Wir haben eine neue Interop-Richtlinie für Microsoft Teams bereitgestellt, um IT-Spezialisten das Verwalten der Einführung von Microsoft Teams zu erleichtern. Die Richtlinie wird über eine Windows PowerShell-Remotesitzung mit Skype for Business mithilfe von [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)-Cmdlets verwaltet. Mit dieser Richtlinie können Sie die Funktionen von Microsoft Teams gemäß den Anforderungen Ihrer Organisation konfigurieren.


> [!TIP]
> Die für Interop benötigten PowerShell-Cmdlets finden Sie, indem Sie „CsTeamsInteropPolicy“ in das Feld **Filter** in der [Dokumentation zu den PowerShell-Cmdlets für Skype for Business](https://docs.microsoft.com/powershell/module/skype) eingeben.

Mit der Interop-Richtlinie für Microsoft Teams können IT-Spezialisten die von einem Benutzer bevorzugte Anwendung für den Empfang von Chats und Anrufen festlegen. Die Richtlinie kann so konfiguriert werden, dass die Kommunikation in Microsoft Teams und Skype for Business in Silos stattfindet. Sie können sie aber auch so konfigurieren, dass die Benutzer anwendungsübergreifend kommunizieren können.

Die Interop-Richtlinie für Microsoft Teams kann auf Mandanten- oder Benutzerebene definiert werden. Sie kann sogar so konfiguriert werden, dass die Benutzer auswählen können, welche Anwendung sie für den Empfang von Chats und Anrufen verwenden möchten.

Diese integrierte Flexibilität soll Ihrer Organisation das Testen und Bewerten sowie die Migration zu Microsoft Teams erleichtern. Dabei bestimmen Sie das Tempo und die optimale Vorgehensweise für Ihre Organisation.

> [!NOTE]
> Interoperabilität zwischen Microsoft Teams und Skype for Business wird unterstützt zwischen Benutzern, die ausschließlich online verwaltet werden (in Skype for Business Online und Microsoft Teams), und Benutzern, die in einer lokalen Skype for Business-Bereitstellung in einer gemischten (hybriden) Bereitstellungstopologie verwaltet werden.

## <a name="what-interoperability-means"></a>Was bedeutet Interoperabilität?
Interop bedeutet, dass Microsoft Teams- und Skype for Business-Benutzer in beiden Anwendungen miteinander chatten und einander anrufen können.

Wenn eine Organisation die Reise von Skype for Business zu Microsoft Teams beginnt, verwenden die Benutzer vermutlich verschiedene Clients.

Um kontinuierliche Produktivität zu gewährleisten, bietet Microsoft Teams den Benutzern die Möglichkeit, unabhängig von der jeweils verwendeten Anwendung (Microsoft Teams oder Skype for Business) miteinander zu kommunizieren.

Unter anderem werden die folgenden Interop-Funktionen unterstützt:
- Skype for Business-Benutzer, die Microsoft Teams nicht verwenden, können mit Microsoft Teams-Benutzern chatten und umgekehrt.<p>
![Interop-Chats in Microsoft Teams](media/Interop_chat_experience_from_Teams.png)<br>
- Skype for Business-Benutzer können Sprach- und Videoanrufe mit Microsoft Teams-Benutzern tätigen und umgekehrt. Erweiterte Anrufoptionen, wie beispielsweise Anrufdurchstellung und Anrufweiterleitung, funktionieren weiterhin, auch bei Interop-Anrufen.<p>
![Interop-Anrufe in Microsoft Teams](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> Aus der Sicht von Skype for Business-Benutzern werden Chats und Anrufe von und an Microsoft Teams als Standardchats und -anrufe in Skype for Business wahrgenommen. Details hierzu finden Sie im Abschnitt [Einschränkungen der Interop-Funktionen](#interop-experiences-limitations).

> [!IMPORTANT]
> Einheitliche Anwesenheitsstatus in Microsoft Teams und Skype for Business werden zurzeit nicht unterstützt, das heißt, Microsoft Teams und Skype for Business zeigen ihre eigenen unabhängigen Anwesenheitsstatus an. Wenn Sie wissen möchten, wann die Unterstützung für einheitliche Anwesenheitsstatus verfügbar sein wird, lesen Sie [Von Skype for Business zu Microsoft Teams: Roadmap der Funktionen](https://aka.ms/skype2teamsroadmap).

## <a name="interop-requirements"></a>Interop-Anforderungen
Damit die Interop-Funktionen aktiviert werden können, müssen die Benutzer die folgenden Kriterien erfüllen:
- Die Benutzer müssen für Microsoft Teams aktiviert (und/oder lizenziert) sein.
- Die Benutzer müssen für Skype for Business Online aktiviert (und/oder lizenziert) sein.
    - Dies gilt für Benutzer, die nur Microsoft Teams verwenden möchten oder die Microsoft Teams als primäre Chat- und Anrufanwendung verwenden möchten.
- In einer hybriden Skype for Business-Bereitstellung gilt Folgendes:
    - Benutzer, die in einer lokalen Skype for Business-Bereitstellung (oder einer beliebigen zurzeit für die hybride Skype for Business-Bereitstellung unterstützten Lync Server-Version) verwaltet werden, können über Microsoft Teams mit Cloudbenutzern kommunizieren.
    - Cloudbenutzer, die Microsoft Teams als primäre Chat- und Anrufanwendung verwenden möchten, müssen für Skype for Business Online aktiviert (und/oder lizenziert) sein.

## <a name="supported-topologies-for-interop"></a>Unterstützte Topologien für Interop
Interop zwischen Microsoft Teams und Skype for Business wird primär für die folgenden Skype for Business-Bereitstellungstopologien unterstützt:
- Reine Skype for Business Online-Bereitstellung
- Hybride Skype for Business-Bereitstellung (gemischte Bereitstellung von Skype for Business Online und einer lokalen Version von Skype for Business)

### <a name="skype-for-business-online-only-topology"></a>Reine Skype for Business Online-Topologie
Organisationen mit einer reinen Skype for Business Online-Bereitstellung können von Unterstützung für Interop-Chats und -Anrufe zwischen Skype for Business Online-Benutzern und Microsoft Teams-Benutzern profitieren.

In dieser Topologie müssen Benutzer, für die Microsoft Teams als primäre Chat- und Anrufanwendung konfiguriert ist, auch für Skype for Business Online aktiviert sein, damit Interop möglich ist.

![Interop in einer reinen Skype for Business Online-Bereitstellungstopologie](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Hybride Skype for Business-Bereitstellungstopologie
Organisationen mit einer Bereitstellung, die aus einer gemischten Bereitstellung von Skype for Business Online und Skype for Business Server (lokal) in einer hybriden Bereitstellungstopologie besteht, können von Unterstützung für Interop-Chats und -Anrufe zwischen Skype for Business-Benutzern (online oder lokal verwaltet) und Microsoft Teams-Benutzern profitieren.

Wie in der reinen Skype for Business Online-Bereitstellungstopologie müssen Benutzer, für die Microsoft Teams als primäre Chat- und Anrufanwendung konfiguriert ist, auch für Skype for Business Online aktiviert sein und dort verwaltet werden, damit Interop möglich ist.

![Interop in einer hybriden Skype for Business-Bereitstellungstopologie](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> Die Interop-Unterstützung für hybride Skype for Business-Bereitstellungen umfasst keine Hybridtelefoniefunktionen, die über CCE (Cloud Connector Edition) oder lokale PSTN-Anbindung mithilfe einer vorhandenen Bereitstellung bereitgestellt werden – dies wird allgemein auch als OPCH (On Prem Config Hybrid, hybride lokale Konfiguration) bezeichnet. Microsoft Teams-Benutzer können nicht für PSTN-Anruffunktionen mit CCE oder OPCH aktiviert werden.

### <a name="interop-experiences-limitations"></a>Einschränkungen der Interop-Funktionen
Zurzeit fehlen nicht nur einheitliche Anwesenheitsstatus in Microsoft Teams und Skype for Business, was zu eigenen unabhängigen Anwesenheitsstatus in Microsoft Teams und Skype for Business führt, sondern es gibt auch Funktionen, die für Interop-Chats und -Anrufe zwischen Microsoft Teams und Skype for Business nicht verfügbar sind.

Für Interop bei Chats gelten zurzeit die folgenden Einschränkungen:
- Bei Unterhaltungen mit mehreren Teilnehmern (Gruppen-Chats) in Microsoft Teams müssen alle Teilnehmer Microsoft Teams verwenden.
- Unterhaltungen mit mehreren Teilnehmern (Chats) in Skype for Business sind nur mit Teilnehmern möglich, die Skype for Business verwenden.
- Dateiübertragungen in Chatunterhaltungen mit zwei Teilnehmern oder Dateianlagen in Unterhaltungen zwischen Microsoft Teams und Skype for Business mit mehreren Teilnehmern (und umgekehrt) werden nicht unterstützt.
- Interop-Chats sind in Microsoft Teams nicht beständig.
- Markdown, Rich-Text, sämtliche Emoticons usw. aus Microsoft Teams werden in Interop-Chats nicht unterstützt.

Für Interop bei Anrufen gelten zurzeit die folgenden Einschränkungen:
- Bildschirmübertragung (Desktop- oder App-Freigabe) zwischen Microsoft Teams und Skype for Business wird nicht unterstützt.
- Die Eskalation von laufenden Peer-zu-Peer-Sprachanrufen (P2P) und -Videoanrufen zu Anrufen mit mehreren Teilnehmern, an denen Microsoft Teams- und Skype for Business-Benutzer beteiligt sind, wird nicht unterstützt.

## <a name="managing-interoperability"></a>Verwalten der Interoperabilität
Für die Verwaltung der Interoperabilität zwischen Microsoft Teams und Skype for Business können Sie eine neue Richtlinie nutzen – die Interop-Richtlinie für Microsoft Teams. Mit dieser können Sie steuern, wohin Chats gesendet und Anrufe weitergeleitet werden sollen (Microsoft Teams oder Skype for Business). Die Richtlinie kann für alle Benutzer in der Organisation konfiguriert werden (globale Richtlinie) oder pro Benutzer angewendet werden. Sie können sie über eine Windows PowerShell-Remotesitzung mit Skype for Business mithilfe von [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)-Cmdlets verwalten.

Standardmäßig ist die Richtlinie so konfiguriert, dass Microsoft Teams und Skype for Business mit minimaler Interop parallel genutzt werden können. Dieser Ansatz soll sicherstellen, dass die Einführung von Microsoft Teams nicht zu Störungen der aktuellen Geschäftsprozesse und der Kommunikation in Ihrer Organisation führt.

### <a name="interop-policy-overview"></a>Übersicht über die Interop-Richtlinie
Die Interop-Richtlinie für Microsoft Teams enthält die folgenden Parameter:

|Parameter                    |Mögliche Werte      |Beschreibung  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | „Default“ (Standard), „SfB“, „Teams“ (Microsoft Teams) | Dieser Parameter legt die Standard-App für Chats fest.        |
|`CallingDefaultClient`       | „Default“ (Standard), „SfB“, „Teams“ (Microsoft Teams) | Dieser Parameter legt die Standard-App für Anrufe fest.        |
|`AllowEndUserClientOverride` | „True“ (Wahr), „False“ (Falsch)         | Dieser Parameter legt fest, ob Benutzer die Standard-App für Chats und Anrufe außer Kraft setzen können.         |

> [!WARNING]
> Zurzeit können Sie eine Interop-Richtlinie für Microsoft Teams mit voneinander unabhängigen Werten für die Parameter `ChatDefaultClient` und `CallingDefaultClient` erstellen. Dies wird sich aber voraussichtlich in Zukunft ändern. Achten Sie zurzeit darauf, für beide Parameter den gleichen Wert zu verwenden.

#### <a name="chat-default-client"></a>Standardclient für Chats
Der Parameter `ChatDefaultClient` definiert, wie Chats zwischen Microsoft Teams und Skype for Business weitergeleitet werden. Der globale Standardwert für den Parameter ist auf **Default** (Standard) festgelegt.

> [!IMPORTANT]
> Der Parameter `ChatDefaultClient` wird zurzeit von Microsoft Teams nicht berücksichtigt. Wir aktualisieren diese Dokumentation mit einer Beschreibung des erwarteten Verhaltens, sobald der Parameter von Microsoft Teams berücksichtigt wird. Vorhandene Chat-Interop-Funktionen zwischen Microsoft Teams und Skype for Business, die auf Mandantenebene gesteuert werden, werden so wie bisher funktionieren.

#### <a name="calling-default-client"></a>Standardclient für Anrufe
Der Parameter `CallingDefaultClient` definiert, wie Anrufe zwischen Microsoft Teams und Skype for Business weitergeleitet werden. Der globale Standardwert für den Parameter ist auf **Default** (Standard) festgelegt.

In der folgenden Tabelle wird im Detail erläutert, wie die einzelnen Einstellungen dieses Parameters das Verhalten von Microsoft Teams- und Skype for Business-Clients beeinflussen.

|Anrufer aus  |Einstellung: „Default“ (Standard), Empfang des Anrufs in  |Einstellung: „Teams“ (Microsoft Teams), Empfang des Anrufs in  |Einstellung: „SfB“ (Skype for Business), Empfang des Anrufs in  |
|---------|---------|---------|---------|
|**Skype for Business**     |Skype for Business         |Microsoft Teams        |Skype for Business         |
|**Microsoft Teams**     |Microsoft Teams         |Microsoft Teams         |Skype for Business         |
|**PSTN**   |Skype for Business        |Microsoft Teams        |Skype for Business         |
|**Skype for Business-Verbund**     |Skype for Business         |Skype for Business         |Skype for Business         |

> [!IMPORTANT]
> Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus. Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients. Weitere Informationen zu vorhandenen zertifizierten SIP-Telefonen finden Sie unter [Von Skype for Business zu Microsoft Teams: Roadmap der Funktionen](https://aka.ms/skype2teamsroadmap).

#### <a name="allowing-user-choice"></a>Zulassen der Auswahl durch die Benutzer
Der Parameter `AllowEndUserClientOverride` akzeptiert boolesche Werte (**TRUE** (Wahr) oder **FALSE** (Falsch)). Wenn **TRUE** (Wahr) festgelegt ist, können Benutzer auswählen, wo sie ihre Anrufe empfangen möchten – in Microsoft Teams oder in Skype for Business. Außerdem können die Benutzer ihre primäre Anwendung jederzeit ändern.

![Option „Bevorzugte Anrufanwendung“](media/Preferred_calling_application_option.png)

Der globale Standardwert für diesen Parameter lautet **FALSE** (Falsch), das heißt, Benutzer können ihre primäre Anwendung nicht ohne Eingriff des Administrators auswählen.

## <a name="teams-interop-policy-special-cases"></a>Sonderfälle der Interop-Richtlinie für Microsoft Teams
Beim Zuweisen der Interop-Richtlinie für Microsoft Teams gelten Benutzer, die weiterhin lokal in Skype for Business verwaltet werden – in einer gemischten (hybriden) Bereitstellungstopologie –, Benutzer mit Hybridtelefonie (über CCE oder OPCH) und Benutzer mit spezialisierten Skype for Business-Workflows als Sonderfälle. Widmen Sie der Richtlinie, die Sie diesen Benutzern zuweisen, besondere Aufmerksamkeit.

### <a name="policy-for-skype-for-business-on-premises-users"></a>Richtlinie für lokale Skype for Business-Benutzer
In einer gemischten (hybriden) Bereitstellungstopologie sollten die Parameter `ChatDefaultClient` und `CallingDefaultClient` in der Richtlinie für Benutzer, die in Skype for Business lokal verwaltet werden, nie auf Microsoft Teams festgelegt werden. Wenn die Parameter so festgelegt werden, können die Benutzer keine Chats und Anrufe empfangen. Verwenden Sie für lokale Benutzer die folgende Richtliniendefinition:

|Parameter  |Wert  |
|---------|---------|
|`ChatDefaultClient`    |„Default“ (Standard) oder „SfB“         |
|`CallingDefaultClient`     |„Default“ (Standard) oder „SfB“         |
|`AllowEndUserClientOverride`     |Falsch         |

> [!IMPORTANT]
> Wenn Sie Benutzer von Skype for Business Online auf eine lokale Version von Skype for Business umstellen (oder umgekehrt), müssen Sie sicherstellen, dass die den Benutzern zugewiesene Interop-Richtlinie für Microsoft Teams auf das Verhalten abgestimmt ist, das erzwungen werden soll. Denken Sie daran, dass lokale Benutzer nicht für die Verwendung von Microsoft Teams als primäre Chat- und Anrufanwendung konfiguriert werden können.

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>Richtlinie für Hybridtelefoniebenutzer (CCE oder OPCH)
Skype for Business Online-Benutzer, die für das Telefonsystem mit Hybridtelefonie (über CCE oder OPCH) aktiviert sind, können keine PSTN-Anrufe in Microsoft Teams empfangen. Verwenden Sie die folgende Richtliniendefinition, wenn Sie Hybridtelefoniebenutzern eine Interop-Richtlinie für Microsoft Teams zuweisen.

|Parameter  |Wert  |
|---------|---------|
|`ChatDefaultClient`    |„Default“ (Standard), „SfB“ oder „Teams“ (Microsoft Teams)         |
|`CallingDefaultClient`     |„Default“ (Standard) oder „SfB“         |
|`AllowEndUserClientOverride`     |Falsch         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>Richtlinie für Benutzer mit spezialisierten Skype for Business-Workflows
Es kann Fälle geben, in denen eine Gruppe von Benutzern Drittanbieteranwendungen verwendet, die auf Skype for Business angewiesen sind (z. B. Callcenter, Rezeptionsmitarbeiter usw.). In diesen Fällen sollten Sie sicherstellen, dass die Benutzer in Skype for Business bleiben, bis ihnen in Microsoft Teams gleichwertige Funktionen zur Verfügung stehen. Verwenden Sie für diese Benutzer die folgende Richtliniendefinition:

|Parameter  |Wert  |
|---------|---------|
|`ChatDefaultClient`    |„Default“ (Standard) oder „SfB“         |
|`CallingDefaultClient`     |„Default“ (Standard) oder „SfB“         |
|`AllowEndUserClientOverride`     |Falsch         |