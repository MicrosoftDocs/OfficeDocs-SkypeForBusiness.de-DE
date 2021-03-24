---
title: Topologiegrunddaten für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Zusammenfassung: Wählen Sie Ihre Topologie für Skype for Business Server aus. Erfahren Sie mehr über die Serverkollocation für Skype for Business Server.'
ms.openlocfilehash: 39a75de6162f51d5d838ace557a546db3500ac01
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103991"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Topologiegrunddaten für Skype for Business Server

**Zusammenfassung:** Wählen Sie Ihre Topologie für Skype for Business Server aus. Erfahren Sie mehr über die Serverkollocation für Skype for Business Server.

Bevor Sie etwas anderes vorbereiten, sollten Sie wissen, dass Sie die richtige Topologie für Ihre Bereitstellung von Skype for Business Server planen. Als Erstes müssen Sie entscheiden, ob Sie eine lokale Bereitstellung von Skype for Business Server haben oder ob Sie dies mit einer Skype for Business Server Online-Bereitstellung in einer Hybridbereitstellung kombinieren möchten. So oder so möchten Sie weiter lesen, da wir hier die lokalen Topologien detailliert erläutern, aber die Hybriddetails sind in ihrem eigenen Abschnitt dokumentiert.

Sie können auch einige Beispieltopologien in [Referenztopologien für Skype for Business Server sehen.](reference-topologies.md)

## <a name="sites"></a>Websites

In Skype for Business Server definieren Sie Websites in Ihrem Netzwerk, die Skype for Business Server-Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass Skype for Business Server-Websites ein separates Konzept von Active Directory Domain Services-Websites und Microsoft Exchange Server sind. Ihre Skype for Business Server-Websites müssen nicht Ihren Active Directory-Websites entsprechen.

Skype for Business Server unterstützt die lokale Bereitstellung eines oder mehrerer Websites, die entsprechend Ihren Anforderungen an hohe Verfügbarkeit und Standort skaliert werden können.

Ihre Bereitstellung verfügt über mindestens einen zentralen Standort (auch als Rechenzentrum bezeichnet, dies ist ein Datencenter für alle Server, die sich dort befinden), und jeder zentrale Standort in Ihrer Bereitstellung verfügt über einen Standard Edition-Server oder mindestens einen Enterprise Edition-Front-End-Pool. Die Unterschiede in den einzelnen Optionen sind unten aufgeführt:

- Standard Edition server includes a collocated SQL Server Express database.

- Der Enterprise Edition-Front-End-Pool umfasst:

  - Mindestens ein Front-End-Server (idealerweise mindestens drei für skalierbarkeit), mit maximal zwölf. Der Lastenausgleich wäre für mehrere Server erforderlich.

  - Ein separater Back-End-Server.

Weitere Informationen zu den verschiedenen Serverrollen finden Sie etwas später in diesem Abschnitt.

Zusätzlich zu Ihren zentralen Standorten können Sie auch einen oder mehrere Zweigstellenstandorte ihrem zentralen Standort zugeordnet haben. Sie sind für fast alle Funktionen vom zentralen Standort abhängig. Was besteht also genau aus ihnen?

- Survivable Branch Appliance, die ein Public Switched Telephone Network (PSTN)-Gateway mit einigen Skype for Business Server-Funktionen kombiniert.

- Survivable Branch Server ist ein Server mit Windows Server, auf dem Die Skype for Business Server-Registrierungs- und Vermittlungsserversoftware installiert ist.

- Eigenständiges PSTN-Gateway (das nicht Teil der Survivable Branch Appliance ist).

- Eigenständiger Vermittlungsserver oder eigenständiger Vermittlungsserverpool (wenn Sie diese Rolle nicht mit der Survivable Branch Appliance verbinden möchten).

## <a name="whats-in-a-skype-for-business-server-site"></a>Was ist auf einer Skype for Business Server-Website?

Um ausführlicher zu werden, kann ein zentraler Standort auch über:

- Mehrere Front-End-Pools in derselben Domäne oder unterschiedlichen Domänen (denken Sie bei der Planung daran, dass sich alle Front-End-Server in einem Front-End-Pool zusammen mit den Back-End-Servern für den Pool in derselben Domäne befinden müssen).

- Mehrere Server der Standard Edition.

- Office Web Apps Server, der zusammen mit Office Web Apps in Skype for Business Server zum Teilen und Rendern von PowerPoint-Präsentationen verwendet wird.

- Edgeserver oder Edgepool (in einem Umkreisnetzwerk). Erforderlich, wenn Ihre Bereitstellung Verbundpartner, Verbindungen mit öffentlichen Chatnachrichten, XMPP-Gateway (Extensible Messaging and Presence Protocol) und Remotebenutzerzugriff unterstützen soll. Weitere Details finden Sie in der Edgeserverplanungsdokumentation.

- Server für beständigen Chat. Nützlich, wenn Benutzer an mehrteiligen, themabasierten Unterhaltungen teilnehmen können sollen, die im Laufe der Zeit beibehalten werden. Weitere Informationen finden Sie im Thema Planning for Persistent Chat Server.

- Überwachung. Wird verwendet, um die Datensammlung für Audio/Video (A/V) Quality of Experience (QoE) und Die Aufzeichnung von Anrufdetails (CdR) für Enterprise-VoIP- und A/V-Konferenzen in Ihrer Bereitstellung zu unterstützen. Im Thema Planning for Monitoring wird dies ausführlich erläutert.

- Director- oder Directorpool. Nicht erforderlich, aber nützlich, wenn Sie die Ausfallsicherheit verbessern und die Umleitung von Skype for Business-Benutzeranforderungen an den Startpool des Benutzers aktivieren möchten. Wenn Sie Directors bereitstellen möchten, werden maximal 10 pro Pool unterstützt. Wenn Sie dies benötigen, lesen Sie unbedingt weiter im Thema Planning for Directors.

- Reverse-Proxy. Dies ist keine Skype for Business Server-Komponente, aber wenn Sie die Freigabe von Webinhalten für Verbundbenutzer unterstützen möchten, wenn Sie Mobilitätsverkehr unterstützen möchten, wenn Ihre Remotebenutzer das Adressbuch verwenden, an Besprechungen teilnehmen möchten, ist dies etwas, was Sie in Ihrer Umgebung haben möchten. Im Thema Einrichten des Reverseproxyservers finden Sie weitere Informationen, wenn Sie bereit sind.

Weitere Informationen zur Kollokation für diese Server finden Sie unten.

Alle Front-End-Pools und Standard Edition-Server, die am zentralen Standort bereitgestellt werden, teilen sich Folgendes, vorausgesetzt, Sie haben sie bereitgestellt:

||||
|:-----|:-----|:-----|
|Director oder Director-Pool  <br/> |Eigenständiger Vermittlungsserver oder Vermittlungsserverpool  <br/> |Office Web Apps-Server  <br/> |
|Edgeserver oder Edgepool  <br/> |Server für beständigen Chat oder Serverpool für beständigen Chat  <br/> |Überwachung  <br/> |

Wo befindet sich exchange Unified Messaging (UM) Server in dieser Liste? Nun, Sie können es mit Sicherheit mit Skype for Business Server verwenden, wenn Sie in Exchange UM integrieren möchten, aber es ist keine Komponente der Skype for Business Server-Website, daher wird es hier nicht erwähnt.

Möglicherweise planen Sie mehrere zentrale Standorte, und wenn ja, können sie die folgenden Server und Rollen gemeinsam nutzen, wenn sie an Ihrem zentralen Standort bereitgestellt werden:

|||
|:-----|:-----|
|Eigenständiger Vermittlungsserver oder Vermittlungsserverpool  <br/> |Edgeserver oder Edgepool  <br/> |
|Server für beständigen Chat oder Serverpool für beständigen Chat  <br/> |Überwachung  <br/> |

Wie bei der letzten Liste werden wir hier nicht den Exchange UM Server enthalten, da er nicht Teil der Skype for Business Server-Bereitstellung ist, aber er fällt auch hier in die gleiche Kategorie.

Es gibt natürlich einige andere Komponenten und Optionen, die in Bereitstellungen gehen.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |PSTN-Gateways (wenn Sie Enterprise-VoIP  <br/> |Exchange UM Server (wenn Sie in Exchange UM integrieren möchten)  <br/> |DNS-Lastenausgleich  <br/> |
|Hardwaregeräte zum Lastenausgleich  <br/> |SQL Server-Datenbanken  <br/> |Dateifreigaben  <br/> ||

## <a name="server-roles"></a>Serverrollen

Auf jedem Server, auf dem Skype for Business Server ausgeführt wird, werden mindestens eine Serverrolle ausgeführt. Eine Serverrolle ist ein definierter Satz von Skype for Business Server-Funktionen, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die erforderliche Funktionalität bereitstellen.

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen Pools mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Für die meisten Arten von Pools in Skype for Business Server müssen Sie einen Lastenausgleich bereitstellen, um den Datenverkehr zwischen den verschiedenen Servern im Pool zu verteilen. Skype for Business Server unterstützt sowohl den Dns-Lastenausgleich (Domain Name System) als auch Hardwaregeräte zum Lastenausgleich.

### <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In Skype for Business Server Enterprise Edition ist der Front-End-Server die zentrale Serverrolle und führt viele grundlegende Skype for Business Server-Funktionen aus. Der Front-End-Server und die Back-End-Server sind die einzigen Serverrollen, die in einer Skype for Business Server Enterprise Edition-Bereitstellung vorhanden sein müssen.

Bei einem Front-End-Pool handelt es sich um einen Satz von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server bietet u. a. die folgenden Funktionen:

- Benutzerauthentifizierung und -registrierung.

- Anwesenheitsinformationen und Visitenkartenaustausch.

- Adressbuchdienste und Verteilerlistenerweiterung.

- Funktionen für A/S, einschließlich Konferenzen mit mehreren Konferenzkonferenzen.

- Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt).

- Anwendungshosting sowohl für Anwendungen, die in Skype for Business Server enthalten sind (z. B. Konferenz attendant und Response Group-Anwendung), als auch für Anwendungen von Drittanbietern.

- Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen enthalten Metriken zur Qualität der Medien (Audio und Video), die Ihr Netzwerk sowohl für Enterprise-VoIP als auch für A/V-Konferenzen durchlaufen.

- Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

- Optional eine Archivierung der Sofortnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) in der Planungsdokumentation.

    In Lync Server 2010 und früheren Versionen waren Überwachung und Archivierung separate Serverrollen, nicht auf Front-End-Server.

- Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Darüber hinaus wird auf einem Front-End-Server in der Bereitstellung auch der zentrale Verwaltungsserver ausgeführt, der grundlegende Konfigurationsdaten auf allen Servern verwaltet und bereitgestellt, auf denen Skype for Business Server ausgeführt wird. Der zentrale Verwaltungsserver bietet außerdem Lync Server-Verwaltungsshell und Dateiübertragungsfunktionen.

Die Back-End-Server sind Datenbankserver mit Microsoft SQL Server, die die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer- und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken wie die Reaktionsgruppe-Datenbank. Sie können über einen einzelnen Back-End-Server verfügen, aber die hohe Verfügbarkeit von [Back-End-Servern in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) wird für failover empfohlen. Auf Back-End-Servern wird keine Skype for Business Server-Software ausgeführt.

> [!IMPORTANT]
> Es wird nicht empfohlen, Skype for Business Server-Datenbanken mit anderen Datenbanken zu verbinden. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

### <a name="edge-server"></a>Edgeserver

Edgeserver ermöglicht Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Zu diesen externen Benutzern können die eigenen Benutzer der Organisation gehören, die derzeit außerhalb der Website arbeiten, Benutzer aus Partnerorganisationen und externe Benutzer, die eingeladen wurden, an Konferenzen teilzunehmen, die in Ihrer Skype for Business Server-Bereitstellung gehostet werden.

Bei der Bereitstellung des Edgeservers werden außerdem die Mobilitätsdienste aktiviert, mit denen die Lync-Funktionalität auf mobilen Geräten unterstützt wird. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen ausführen wie Senden und Empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Das Mobilitätsfeature unterstützt auch Pushbenachrichtigungen für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre Skype for Business Server-Benutzer Kontakte von XMPP-basierten Partnern für Chat und Anwesenheit hinzufügen können.

> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter Migrieren des [XMPP-Verbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

### <a name="mediation-server"></a>Vermittlungsserver

Vermittlungsserver ist eine erforderliche Komponente für die Implementierung von Enterprise-VoIP, Anruf über Arbeit und Einwahlkonferenzen. Der Vermittlungsserver übersetzt Die Signalisierung und in einigen Konfigurationen Medien zwischen Ihrer internen Skype for Business Server-Infrastruktur und einem PstN-Gateway (Public Switched Telephone Network), IP-PBX oder einem Sip-Trunk (Session Initiation Protocol). Sie können den Vermittlungsserver gemeinsam mit dem Front-End-Sever auf demselben Server oder getrennt in einem eigenständigen Vermittlungsserverpool ausführen.

Weitere Informationen finden Sie unter [Vermittlungsserverkomponente in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Video-Interoperabilitätsserver

Video Interop Server ist eine neue Rolle ab Skype for Business Server 2015. Sie können Ihre Skype for Business Server-Bereitstellung in bestimmte VTC-Lösungen (Video Teleconferencing System) von Drittanbietern integrieren. Ein VIS fungiert als Vermittler zwischen einem Drittanbieter-Telekonferenzsystem und einer Skype for Business Server-Bereitstellung. Für diese Version konzentriert sich VIS auf die Interoperabilität mit Cisco/Tandberg-Videosystemen.

Weitere Informationen finden Sie unter [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Directors können Skype for Business Server-Benutzeranforderungen authentifizieren, aber keine Benutzerkonten erstellen oder Anwesenheits- oder Konferenzdienste bereitstellen. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server.

### <a name="persistent-chat-server-roles"></a>Serverrollen für beständigen Chat

> [!NOTE]
> Beständigen Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden.

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Server, auf denen Skype for Business Server Standard Edition ausgeführt wird, können auch beständigen Chat auf demselben Server ausführen. Sie können den Front-End-Server für beständigen Chat nicht mit dem Enterprise Edition-Front-End-Server verbinden.

Weitere Informationen finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung

Skype for Business Server bietet hohe Verfügbarkeit durch Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.

Skype for Business Server bietet auch Notfallwiederherstellungsmaßnahmen, indem die Poolkopplung aktiviert wird. Wenn Sie diese Topologie bereitstellen, legen Sie Paare von Front-End-Pools mit jedem Pool in einem Paar in einem separaten Rechenzentrum und in einem separaten geografischen Bereich vor. Wenn ein Pool oder Standort aus ist, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool im Paar zu verwenden, mit minimaler Dienstunterbrechung.

Skype for Business Server unterstützt auch mehrere Optionen für back-End Server-Hochverfügbarkeit. Hierzu gehören:

- Datenbankspiegelung

- AlwaysOn-Verfügbarkeitsgruppen

- AlwaysOn Failover Cluster Instances (FCI)

- SQL Failoverclustering

Weitere Informationen zur Poolkopplung und zur Hohen Verfügbarkeit von Back-End-Servern finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Serverkolokation in Skype for Business Server

Wir haben den Begriff bereits verwendet, aber was bedeutet dies? Mit Skype for Business Server können Sie einige Serverrollen und -features auf demselben Server, bei dem es sich um eine Kollokation handelt, oder auf unterschiedlichen Servern suchen, es kann jedoch verwirrend sein, wenn Sie beginnen und ob Sie eine Standard Edition- oder Enterprise Edition-Serverbereitstellung (sie verfügen jeweils über eigene Regeln) verwenden. Zur Unterstützung Ihrer Planung werden Serverkollocation in Standard Edition-Serverbereitstellungen und Enterprise Edition-Front-End-Poolbereitstellungen hinzugefügt (in den meisten Fällen sind diese Informationen identisch, und wo sie sich unterscheiden, werden sie speziell bezeichnet).

### <a name="collocation-of-server-roles"></a>Kollokation von Serverrollen

Der Standard Edition-Server hat die folgende Rolle (allerdings ist eine zusätzliche Konfiguration erforderlich), während diese Rolle im Enterprise Edition-Front-End-Pool zusammengeknallt oder auf einem separaten Server bereitgestellt werden kann:

- Vermittlung

Diese Serverrollen müssen jeweils auf einem separaten Server bereitgestellt werden:

- Director

- Microsoft Edge

- Video-Interoperabilitätsserver

- Office Web Apps

### <a name="databases"></a>Datenbanken

Dies ist der Bereich mit echten Unterschieden zwischen Standard Edition-Serverbereitstellungen und Enterprise Edition-Serverpoolbereitstellungen, sodass wir zwei Abschnitte unten haben, gefolgt von einigen zusätzlichen Regeln für beide.

#### <a name="standard"></a>Standard

Da SQL Server Express auf dem Standard Edition-Server zusammengeknallt ist und nicht verschoben werden kann, ist dies recht einfach. Wenn Sie den Server für beständigen Chat auf einem Standard Edition-Server bereitstellen, können Sie außerdem auch den Beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat auf dem Standard Edition-Server verbinden, aber Sie müssen dies nicht.

> [!NOTE]
> Beständigen Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden.

Diese können nicht auf dem Standard Edition-Server, sondern auf einem einzelnen Datenbankserver verwendet werden:

- Überwachungsdatenbank

- Archivierungsdatenbank

- Alle Back-End-Datenbanken für einen Enterprise Edition-Front-End-Pool

#### <a name="enterprise"></a>Unternehmen

Die folgenden Datenbanken können am gleichen Back-End-SQL Server:

- Back-End-Datenbank

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Compliancedatenbank für beständigen Chat

#### <a name="both"></a>In beide Richtungen

Nun müssen einige zusätzliche Regeln beim Verbinden von Skype for Business Server-Datenbanken in einer einzelnen SQL-Instanz oder in mehreren SQL-Instanzen in derselben SQL Server werden:

- Jede SQL-Instanz kann nur eine einzelne Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne Datenbank für beständigen Chat und eine einzelne Compliancedatenbank für beständigen Chat enthalten.

- Der Datenbankserver kann nicht mehr als einen Enterprise Edition-Front-End-Pool, einen Server mit Archivierung, einen Server mit Überwachung, eine einzelne Datenbank für beständigen Chat und eine einzelne Kompatibilitätsdatenbank für beständigen Chat unterstützen, aber er kann einen einzelnen Pool unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

    > [!NOTE]
    > Beständigen Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden.

### <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann sich auf einem separaten Server befinden, oder Sie können sie auf demselben Server wie einen oder alle der folgenden Server verbinden:

- Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Compliancedatenbank für beständigen Chat

> [!CAUTION]
> Beachten Sie, dass Die Dateifreigabe auf diesen Servern zwar gemeinsam verwendet werden kann, sie jedoch nicht empfohlen wird. Wenn Sie die Dateifreigabe mit einer anderen Serverrolle verbinden, stellen Sie sicher, dass Sie regelmäßig auf Speicherplatz- und Leistungsprobleme achten.

### <a name="keep-in-mind"></a>Beachten Sie

- Sie können keinen Reverseproxyserver verbinden, der keine Skype for Business Server-Komponente ist und sich möglicherweise nicht einmal in Ihrer Topologie befindet. Sie benötigen einen Reverseproxy, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer unterstützen möchten, unter anderem. Gehen Sie bei Bedarf voran und implementieren Sie die Reverseproxyunterstützung für Skype for Business Server, indem Sie einen vorhandenen Reverseproxyserver konfigurieren, der bereits in Ihrer Organisation vorhanden ist und von anderen Anwendungen verwendet wird.

- Sie können keine Exchange UM- oder SharePoint Server-Komponente mit einer Skype for Business Server-Rolle verbinden.

## <a name="see-also"></a>Siehe auch

[Referenztopologien für Skype for Business Server](reference-topologies.md)