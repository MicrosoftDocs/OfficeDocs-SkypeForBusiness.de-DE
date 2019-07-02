---
title: Grundlagen der Topologie für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Zusammenfassung: Wählen Sie Ihre Topologie für Skype for Business Server aus. Informationen zur Server Zusammenstellung für Skype for Business Server.'
ms.openlocfilehash: 064dc9d4f7f5d2a5ac722b3cfae928501b217822
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418011"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Grundlagen der Topologie für Skype for Business Server

**Zusammenfassung:** Wählen Sie Ihre Topologie für Skype for Business Server aus. Informationen zur Server Zusammenstellung für Skype for Business Server.

Bevor Sie etwas anderes vorbereiten, sollten Sie wissen, dass Sie die richtige Topologie für Ihre Bereitstellung von Skype for Business Server planen. Als erstes müssen Sie entscheiden, ob Sie eine lokale Bereitstellung von Skype for Business Server haben oder ob Sie dies mit einer Online-Bereitstellung von Skype for Business Server in einer Hybrid Bereitstellung kombinieren werden. Wie auch immer, Sie möchten weiter lesen, da wir die lokalen Topologien hier ausführlich erläutern, die Hybrid Details jedoch in einem eigenen Abschnitt dokumentiert sind.

Sie können auch einige Beispiel Topologien in [Referenz Topologien für Skype for Business Server](reference-topologies.md)sehen.

## <a name="sites"></a>Standorte

In Skype for Business Server definieren Sie Websites in Ihrem Netzwerk, die Skype for Business Server-Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass Skype for Business Server-Websites ein separates Konzept von Active Directory-Domänendienst Websites und Microsoft Exchange Server-Websites sind. Ihre Skype for Business Server-Websites müssen Ihren Active Directory-Standorten nicht entsprechen.

Skype for Business Server unterstützt die lokale Bereitstellung von einem oder mehreren Websites, die entsprechend Ihren Anforderungen an Hochverfügbarkeit und Standort skaliert werden können.

Ihre Bereitstellung verfügt über mindestens einen zentralen Standort (auch als Rechenzentrum bezeichnet, dies ist ein Rechenzentrum für alle darin befindlichen Server), und jeder zentrale Standort in Ihrer Bereitstellung verfügt über einen Standard Edition-Server oder mindestens einen Enterprise Edition-Front-End-Pool. Nachfolgend sind die Unterschiede zwischen den Optionen dargelegt:

- Der Standard Edition-Server enthält eine in SQL Server Express enthaltene Datenbank.

- Enterprise Edition-Front-End-Pool umfasst:

  - Einen oder mehrere Front-End-Server (idealerweise mindestens drei für Skalierbarkeit) mit maximal zwölf. Für mehr als einen Server wäre ein Lastenausgleich erforderlich.

  - Ein separater Back-End-Server.

Nähere Einzelheiten über die verschiedenen Serverrollen erfahren Sie im weiteren Verlauf dieses Abschnitts.

Zusätzlich zu Ihren zentralen Websites verfügen Sie möglicherweise auch über eine oder mehrere Zweigstellen, die mit Ihrem zentralen Standort verknüpft sind. Sie sind von der zentralen Website für nahezu alle Funktionen abhängig, und worin bestehen Sie genau?

- Survival-Branch-Appliance, die ein PSTN-Gateway (Public Switched Telephone Network) mit einigen Funktionen für Skype for Business Server kombiniert.

- Survivable-Branch-Server, es ist ein Server mit Windows Server, auf dem die Skype for Business Server-Registrierungs-und Mediationsserver-Software installiert ist.

- Eigenständiges PSTN-Gateway (das nicht Bestandteil der Survivable Branch-Appliance ist).

- Eigenständiger Vermittlungsserver oder eigenständiger vermittlungsserverpool (wenn Sie diese Rolle nicht mit der Survivable Branch Appliance collocate möchten).

## <a name="whats-in-a-skype-for-business-server-site"></a>Was befindet sich in einer Skype for Business Server-Website?

Um mehr Details zu erhalten, kann eine zentrale Website auch Folgendes aufweisen:

- Mehrere Front-End-Pools in der gleichen Domäne oder in verschiedenen Domänen (denken Sie daran, dass sich alle Front-End-Server in einem Front-End-Pool zusammen mit den Back-End-Servern für den Pool in der gleichen Domäne befinden müssen).

- Mehrere Standard Edition-Server.

- Office Web Apps Server, der in Verbindung mit Office Web Apps in Skype for Business Server zum Freigeben und Rendern von PowerPoint-Präsentationen verwendet wird.

- Edge-Server oder Edge-Pool (in einem Umkreisnetzwerk) Wird benötigt, wenn Ihre Bereitstellung Verbundpartner, Verbindung mit öffentlichen Chatdiensten, ein Gateway für XMPP (Extensible Messaging and Presence Protocol ) und den Zugriff durch Remotebenutzer unterstützen soll. Weitere Informationen finden Sie in der Dokumentation zur Edge-Server-Planung.

- Beständiger Chat Server. Nützlich, wenn Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen sollen, die sich über längere Zeiträume erstrecken. Weitere Informationen finden Sie im Thema Planen des beständigen Chat Servers.

- Überwachung. Dient zur Unterstützung der Datensammlung für Audio/Video (A/v) Quality of Experience (QoE) und Anrufdetailaufzeichnung (CDR) für Enterprise-VoIP-und A/v-Konferenzen in Ihrer Bereitstellung. Dies wird im Thema „Überwachungsplanung“ näher erläutert.

- Director-oder Director-Pool Nicht erforderlich, aber hilfreich, wenn Sie die Widerstandsfähigkeit verbessern und die Umleitung von Skype for Business-Benutzeranforderungen an den Home-Pool des Benutzers aktivieren möchten. Wenn Sie Directors bereitstellen möchten, werden maximal 10 pro Pool unterstützt. Wenn dies etwas ist, das Sie benötigen, lesen Sie unbedingt weiter im Thema Planen von Directors.

- Reverseproxy Hierbei handelt es sich nicht um eine Skype for Business-Server Komponente, aber wenn Sie die Freigabe von Webinhalten für verbundene Benutzer unterstützen möchten, wenn Sie den Mobilitäts Datenverkehr unterstützen möchten, wenn Ihre Remotebenutzer das Adressbuch verwenden, an Besprechungen teilnehmen und so weiter suchen möchten, ist dies etwas, das Sie in Ihrer Umgebung haben möchten. Wenn Sie bereit sind, gibt es ein Thema zum Einrichten eines Reverse-Proxyservers, den Sie für weitere Details Auschecken können.

Nachstehend finden Sie weitere Informationen zum Verbinden dieser Server.

Alle Front-End-Pools und Standard Edition-Server, die an Ihrem zentralen Standort bereitgestellt werden, geben Folgendes an, vorausgesetzt, Sie haben Sie bereitgestellt:

||||
|:-----|:-----|:-----|
|Director-oder Director-Pool  <br/> |Eigenständiger Vermittlungsserver oder vermittlungsserverpool  <br/> |Office Web Apps-Server  <br/> |
|Edgeserver oder Edge-Pool  <br/> |Serverpool für beständigen Chat oder beständiger Chat  <br/> |Überwachung  <br/> |

Wo befindet sich der Exchange Unified Messaging (um)-Server in dieser Liste? Nun, Sie können es sicherlich mit Skype for Business Server nutzen, wenn Sie sich in Exchange um integrieren möchten, aber es ist keine Komponente der Skype for Business Server-Website, daher erwähnen wir es hier nicht.

Möglicherweise planen Sie, mehrere zentrale Websites zu verwenden, und wenn dies der Fall ist, können Sie die folgenden Server und Rollen freigeben, wenn Sie auf Ihrem zentralen Standort bereitgestellt werden:

|||
|:-----|:-----|
|Eigenständiger Vermittlungsserver oder vermittlungsserverpool  <br/> |Edgeserver oder Edge-Pool  <br/> |
|Serverpool für beständigen Chat oder beständiger Chat  <br/> |Überwachung  <br/> |

Wie in der letzten Liste wird der Exchange um-Server hier nicht eingeschlossen, da er nicht Teil der Skype for Business Server-Bereitstellung ist, sondern auch hier in die gleiche Kategorie fällt.

Bereitstellungen enthalten aber auch noch weitere Komponenten und Optionen.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |PSTN-Gateways (wenn Sie Enterprise-VoIP bereitstellen)  <br/> |Exchange um-Server (wenn Sie die Integration in Exchange um durchsuchen möchten)  <br/> |DNS-Lastenausgleich  <br/> |
|Hardwaregeräte zum Lastenausgleich  <br/> |SQL Server-Datenbanken  <br/> |Dateifreigaben  <br/> ||

## <a name="server-roles"></a>Serverrollen

Jeder Server, auf dem Skype for Business Server ausgeführt wird, führt mindestens eine Serverrolle aus. Eine Serverrolle ist ein definierter Satz von Skype for Business Server-Funktionen, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die die erforderliche Funktionalität enthalten.

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen Pools mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Für die meisten Arten von Pools in Skype for Business Server müssen Sie ein Lastenausgleichsmodul bereitstellen, um den Datenverkehr zwischen den verschiedenen Servern im Pool zu verbreiten. Skype for Business Server unterstützt sowohl DNS-Load-Balancing (Domain Name System) als auch Hardware-Lastenausgleichsgeräte.

### <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In Skype for Business Server Enterprise Edition ist der Front-End-Server die Hauptserver Rolle und führt viele grundlegende Funktionen von Skype for Business Server aus. Der Front-End-Server ist zusammen mit den Back-End-Servern die einzige Server Rolle, die für die Bereitstellung von Skype for Business Server Enterprise Edition erforderlich ist.

Bei einem Front-End-Pool handelt es sich um einen Satz von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server enthält Folgendes:

- Benutzerauthentifizierung und -registrierung.

- Anwesenheitsinformationen und Visitenkartenaustausch.

- Adressbuchdienste und Verteilerlistenerweiterung.

- Chatnachrichtenfunktionalität, einschließlich Chatnachrichtenkonferenzen mit mehreren Teilnehmern.

- Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt).

- Anwendungs-Hosting, für beide Anwendungen, die in Skype for Business Server enthalten sind (beispielsweise Conferencing Attendant und Response Group-Anwendung) sowie Anwendungen von Drittanbietern.

- Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen enthalten Metriken zur Qualität der Medien (Audio und Video), die in Ihrem Netzwerk für Enterprise-Sprachanrufe und A/V-Konferenzen durchlaufen werden.

- Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

- Optional eine Archivierung der Chatnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in der Planungsdokumentation.

    In lync Server 2010 und früheren Versionen waren Überwachung und Archivierung getrennte Server Rollen, nicht auf dem Front-End-Server.

- Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Darüber hinaus führt ein Front-End-Server in der Bereitstellung auch den zentralen Verwaltungsserver aus, der grundlegende Konfigurationsdaten für alle Server verwaltet und bereitstellt, auf denen Skype for Business Server ausgeführt wird. Der zentrale Verwaltungs Server bietet auch die lync Server-Verwaltungsshell und die Dateiübertragungsfunktionen.

Die Back-End-Server sind Datenbankserver mit Microsoft SQL Server, die die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer-und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken wie die Datenbank der Reaktionsgruppe. Sie können einen einzelnen Back-End-Server haben, aber für Failover wird eine [höhere Verfügbarkeit von Back-End-Servern in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) empfohlen. Back-End-Server führen keine Skype for Business Server-Software aus.

> [!IMPORTANT]
> Es wird nicht empfohlen, abstimmen Skype for Business Server-Datenbanken mit anderen Datenbanken zu verwenden. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.

> [!NOTE]
> Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

### <a name="edge-server"></a>Edgeserver

Edge-Server ermöglicht Ihren Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Diese externen Benutzer können die eigenen Benutzer der Organisation einbeziehen, die derzeit an einem externen Standort arbeiten, Benutzer aus Verbundpartner Organisationen und externe Benutzer, die eingeladen wurden, an Konferenzen teilzunehmen, die in Ihrer Skype for Business Server-Bereitstellung gehostet werden.

Durch die Bereitstellung von Edge Server werden auch Mobilitätsdienste aktiviert, die die lync-Funktionalität auf mobilen Geräten unterstützen. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen wie Senden und Empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit ausführen. Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit anzurufen, eine Rufnummer zu erreichen, Voicemail und verpasste Anrufe zu tätigen. Die Mobilitätsfunktion unterstützt auch Pushbenachrichtigungen für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre Skype for Business Server-Benutzer Kontakte von XMPP-basierten Partnern für Sofortnachrichten und Anwesenheitsinformationen hinzufügen können.

> [!NOTE]
> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>Vermittlungsserver

Der Vermittlungs Server ist eine notwendige Komponente zum Implementieren von Enterprise-VoIP, Anrufen über die Arbeit und Einwahlkonferenzen. Der Vermittlungs Server übersetzt Signalisierungen und in einigen Konfigurationen Medien zwischen Ihrer internen Skype for Business Server-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network), IP-PBX oder einem SIP-Trunk (Session Initiation Protocol). Sie können den Vermittlungsserver auf dem gleichen Server wie dem Front-End-Server ausführen oder in einen eigenständigen vermittlungsserverpool unterteilt.

Ausführliche Informationen finden Sie unter [Mediation Server-Komponente in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Video-Interoperabilität-Server

Video-Interop-Server ist eine neue Rolle in Skype for Business Server 2015. Damit können Sie Ihre Skype for Business Server-Bereitstellung mit bestimmten VTC-Lösungen (Video Teleconferencing System) von Drittanbietern integrieren. Ein VIS fungiert als Vermittler zwischen einem Drittanbieter-Konferenzsystem und einer Skype for Business Server-Bereitstellung. Bei dieser Version konzentriert sich der VIS auf die Interoperabilität mit Videosystemen von Cisco/Tandberg.

Ausführliche Informationen finden Sie unter [Planen des Video-Interop-Servers in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Directors können die Benutzeranforderungen von Skype for Business Server authentifizieren, jedoch keine Benutzerkonten oder Anwesenheits-oder Konferenzdienste. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server.

### <a name="persistent-chat-server-roles"></a>Server Rollen für beständigen Chat

> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Auf Servern mit Skype for Business Server Standard Edition können auch persistente Chats auf demselben Server ausgeführt werden. Der Front-End-Server für beständigen Chat mit Enterprise Edition-Front-End-Server kann nicht collocate werden.

Ausführliche Informationen finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung

Skype for Business Server bietet eine höhere Verfügbarkeit durch Serverredundanz über Pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.

Skype for Business Server bietet auch Disaster Recovery-Maßnahmen, indem es die Pool-Kopplung aktiviert. Wenn Sie diese Topologie bereitstellen, definieren Sie Paare von Front-End-Pools, wobei sich jeder Pool in einem Paar in einem separaten Rechenzentrum und in einem separaten geografischen Bereich befindet. Wenn ein Pool oder eine Website nicht mehr zur Verfügung steht, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool des Paars mit minimaler Dienstunterbrechung zu verwenden.

Skype for Business Server unterstützt auch verschiedene Optionen für die höchst Verfügbarkeit von Back-End-Servern. Diese beinhalten Folgendes:

- Datenbankspiegelung

- AlwaysOn-Verfügbarkeitsgruppen

- AlwaysOn-Failover-Cluster Instanzen (FCI)

- SQL-Failoverclustering

Ausführliche Informationen zur Pool-Kopplung und zur Verfügbarkeit von Back-End-Servern finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Server Zusammenstellung in Skype for Business Server

Wir haben den Begriff collocate bereits verwendet, aber was bedeutet das? Mit Skype for Business Server können Sie einige Serverrollen und-Features auf dem gleichen Server finden, bei denen es sich um eine Zusammenfassung oder auf unterschiedlichen Servern handelt, aber es kann verwirrend sein, wenn Sie beginnen, und ob Sie einen Standard Edition-oder Enterprise Edition-Server ausführen Bereitstellung (beide verfügen über eigene Regeln). Zur Unterstützung bei der Planung sind die Server-Zusammenstellung in Standard Edition-Server Bereitstellungen und Enterprise Edition-Front-End-Pool Bereitstellungen eingeschlossen (in den meisten Fällen sind diese Informationen identisch, und wenn Sie anders sind, werden Sie ausdrücklich aufgerufen).

### <a name="collocation-of-server-roles"></a>Kollokation von Serverrollen

Auf dem Standard Edition-Server ist die folgende Rolle zusammengestellt (es ist jedoch eine zusätzliche Konfiguration erforderlich), während sich diese Rolle im Front-End-Pool der Enterprise Edition auf einem separaten Server befinden kann:

- Vermittlung

Die Serverrollen müssen jeweils auf einem separaten Computer bereitgestellt werden:

- Director

- Edge

- Video-Interoperabilität-Server

- Office Web Apps

### <a name="databases"></a>Datenbanken

Hierbei handelt es sich um den Bereich mit echten unterschieden zwischen Standard Edition-Server Bereitstellungen und Enterprise Edition-Serverpool Bereitstellungen, daher haben wir zwei Abschnitte, gefolgt von einigen zusätzlichen Regeln für beide.

#### <a name="standard"></a>Standard

Da sich SQL Server Express auf dem Standard Edition-Server befindet und nicht verschoben werden kann, ist dies ziemlich einfach. Darüber hinaus können Sie, wenn Sie den beständigen Chat Server auf einem Standard Edition-Server bereitstellen, auch den beständigen Chat und die Compliance-Datenbank für beständigen Chat auf dem Standard Edition-Server collocate.

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

Diese können nicht auf dem Standard Edition-Server, sondern auf einem eigenen Datenbankserver abgelegt werden:

- Überwachungsdatenbank

- Archivierungsdatenbank

- Eine beliebige Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool

#### <a name="enterprise"></a>Enterprise

Die folgenden Datenbankenkönnen auf dem gleichen Back-End-SQL Server gespeichert werden:

- Back-End-Datenbank

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Kompatibilitätsdatenbank für beständigen Chat

#### <a name="both"></a>Both

Nun gibt es einige zusätzliche Regeln, die beim Abstimmen von Skype for Business Server-Datenbanken in einer einzelnen SQL-Instanz oder in mehreren SQL-Instanzen in derselben SQL Server-Datenbank zu beachten sind:

- Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne persistent Chat-Datenbank und eine einzelne Datenbank für beständige Chats enthalten.

- Der Datenbankserver kann nicht mehr als einen Enterprise Edition-Front-End-Pool, einen Server mit Archivierungsfunktion, einen Server mit Überwachung, eine einzelne beständige Chat-Datenbank und eine einzelne Datenbank für beständigen Chats unterstützen, kann aber jeweils eine davon unterstützen. unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

    > [!NOTE]
    > Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.

### <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann auf einem separaten Server oder auf demselben wie einem der folgenden Server ausgeführt werden:

- Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Kompatibilitätsdatenbank für beständigen Chat

> [!CAUTION]
> Beachten Sie, dass die Dateifreigabe auf diesen Servern zwar ausgeführt werden kann, wir dies jedoch nicht empfehlen. Stellen Sie sicher, regelmäßig auf genügend Speicherplatz und Leistungsprobleme zu achten, wenn Sie die Dateifreigabe mit einer beliebigen anderen Serverrolle ausführen.

### <a name="keep-in-mind"></a>Bitte beachten Sie:

- Sie können keinen Reverse-Proxy-Server collocate, der keine Skype for Business-Serverkomponente ist und sich möglicherweise noch nicht in Ihrer Topologie befindet. Sie benötigen einen Reverseproxy, wenn Sie die Freigabe von Webinhalten für Federated-Benutzer unter vielen anderen Dingen unterstützen möchten. Wenn Sie dies benötigen, führen Sie die Reverse-Proxy-Unterstützung für Skype for Business Server aus, indem Sie einen vorhandenen Reverse-Proxy-Server konfigurieren, der sich bereits in Ihrer Organisation befindet und von anderen Anwendungen verwendet wird.

- Sie können keine Exchange um-Komponente oder SharePoint Server-Komponente mit einer Skype for Business-Serverrolle collocate.

## <a name="see-also"></a>Siehe auch

[Referenz Topologien für Skype for Business Server](reference-topologies.md)
