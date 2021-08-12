---
title: Topologiegrundlagen für Skype for Business Server
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
description: 'Zusammenfassung: Wählen Sie Ihre Topologie für Skype for Business Server aus. Erfahren Sie mehr über die Serverkollokation für Skype for Business Server.'
ms.openlocfilehash: 922bc26ee6eeea720c62cbbc744953aa5edecf4c03a792fac56ee7910806b6e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349867"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Topologiegrundlagen für Skype for Business Server

**Zusammenfassung:** Wählen Sie Ihre Topologie für Skype for Business Server aus. Erfahren Sie mehr über die Serverkollokation für Skype for Business Server.

Bevor Sie etwas anderes vorbereiten, sollten Sie wissen, dass Sie die richtige Topologie für die Bereitstellung von Skype for Business Server planen. Als Erstes müssen Sie entscheiden, ob Sie über eine lokale Bereitstellung von Skype for Business Server verfügen oder ob Sie dies mit einer Skype for Business Server Onlinebereitstellung in einer Hybridbereitstellung kombinieren möchten. In beiden Fällen möchten Sie weiterlesen, da wir die lokalen Topologien hier detailliert beschreiben, aber die Hybriddetails sind in ihrem eigenen Abschnitt dokumentiert.

Sie können auch einige Beispieltopologien in [Referenztopologien für Skype for Business Server](reference-topologies.md)sehen.

## <a name="sites"></a>Websites

In Skype for Business Server definieren Sie Standorte in Ihrem Netzwerk, die Skype for Business Server Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass Skype for Business Server Websites ein separates Konzept von Active Directory Domain Services-Websites und Microsoft Exchange Server Websites sind. Ihre Skype for Business Server-Websites müssen nicht Ihren Active Directory-Websites entsprechen.

Skype for Business Server unterstützt die lokale Bereitstellung eines oder mehrerer Standorte, die gemäß Ihren Anforderungen an hohe Verfügbarkeit und Standort skaliert werden können.

Ihre Bereitstellung verfügt über mindestens einen zentralen Standort (auch als Datencenter bezeichnet, d. h. ein Rechenzentrum für alle darin befindlichen Server), und jeder zentrale Standort in Ihrer Bereitstellung verfügt über einen Standard Edition Server oder mindestens einen Enterprise Edition Front-End-Pool. Sie können die Unterschiede in den einzelnen Optionen unten sehen:

- Standard Edition Server enthält eine SQL Server Express Datenbank.

- Enterprise Edition Der Front-End-Pool umfasst:

  - Ein oder mehrere Front-End-Server (idealerweise mindestens drei, zur Skalierbarkeit), mit maximal zwölf. Für mehrere Server wäre ein Lastenausgleich erforderlich.

  - Ein separater Back-End-Server.

Weitere Informationen zu den verschiedenen Serverrollen finden Sie etwas später in diesem Abschnitt.

Zusätzlich zu Ihren zentralen Standorten können Sie auch eine oder mehrere Zweigstellen haben, die mit Ihrem zentralen Standort verknüpft sind. Sie sind für fast alle Funktionen von der zentralen Website abhängig. Was sind sie also genau?

- Survivable Branch Appliance, die ein PSTN-Gateway (Public Switched Telephone Network) mit einigen Skype for Business Server Funktionen kombiniert.

- Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.

- Eigenständiges PSTN-Gateway (das nicht Teil der Survivable Branch Appliance ist).

- Eigenständiger Vermittlungsserver oder eigenständiger Vermittlungsserverpool (wenn Sie diese Rolle nicht mit der Survivable Branch Appliance verbinden möchten).

## <a name="whats-in-a-skype-for-business-server-site"></a>Was befindet sich auf einer Skype for Business Server Website?

Um mehr details zu erhalten, kann ein zentraler Standort auch Folgendes aufweisen:

- Mehrere Front-End-Pools in derselben Domäne oder in unterschiedlichen Domänen (denken Sie daran, dass sich alle Front-End-Server in einem Front-End-Pool zusammen mit den Back-End-Servern für den Pool in derselben Domäne befinden müssen).

- Mehrere Server der Standard Edition.

- Office Web Apps-Server, der mit Office Web Apps in Skype for Business Server zum Freigeben und Rendern von PowerPoint Präsentationen verwendet wird.

- Edgeserver oder Edgepool (in einem Umkreisnetzwerk). Erforderlich, wenn Ihre Bereitstellung Verbundpartner, Verbindungen mit öffentlichen Chatdiensten, XMPP-Gateway (Extensible Messaging and Presence Protocol) und Remotebenutzerzugriff unterstützen soll. Weitere Informationen finden Sie in der Dokumentation zur Edgeserverplanung.

- Server für beständigen Chat. Hilfreich, wenn Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen sollen, die im Laufe der Zeit bestehen bleiben. Weitere Informationen finden Sie im Thema "Planen des Servers für beständigen Chat".

- Überwachung. Wird verwendet, um die Datensammlung für Audio-/Video (A/V) Quality of Experience (QoE) und Die Aufzeichnung von Kommunikationsdatensätzen (KDS) für Enterprise-VoIP- und A/V-Konferenzen in Ihrer Bereitstellung zu unterstützen. Dies wird im Thema "Planung für die Überwachung" ausführlich behandelt.

- Director- oder Director-Pool. Nicht erforderlich, aber nützlich, wenn Sie die Resilienz verbessern und die Umleitung von Skype for Business Benutzeranforderungen an den Heimpool des Benutzers aktivieren möchten. Wenn Sie Directors bereitstellen möchten, werden maximal 10 pro Pool unterstützt. Wenn Sie dies benötigen, lesen Sie auf jeden Fall weiter im Thema "Planung für Directors".

- Reverse-Proxy. Dies ist keine Skype for Business Server Komponente, aber wenn Sie die Freigabe von Webinhalten für Verbundbenutzer unterstützen möchten, wenn Sie Mobilitätsdatenverkehr unterstützen möchten, wenn Ihre Remotebenutzer das Adressbuch verwenden, an Besprechungen teilnehmen möchten usw., sollten Sie dies in Ihrer Umgebung haben. Es gibt ein Thema zum Einrichten des Reverseproxyservers, das Sie sich ansehen können, um weitere Details zu erhalten, wenn Sie bereit sind.

Weitere Informationen zur Kollokation für diese Server finden Sie unten.

Alle Front-End-Pools und Standard Edition Server, die an Ihrem zentralen Standort bereitgestellt werden, teilen sich Folgendes, vorausgesetzt, Sie haben sie bereitgestellt:

||||
|:-----|:-----|:-----|
|Director oder Director-Pool  <br/> |Eigenständiger Vermittlungsserver oder Vermittlungsserverpool  <br/> |Office Web Apps-Server  <br/> |
|Edgeserver oder Edgepool  <br/> |Server für beständigen Chat oder Serverpool für beständigen Chat  <br/> |Überwachung  <br/> |

Wo befindet sich Exchange Unified Messaging (UM)-Server in dieser Liste? Nun, Sie können es mit Skype for Business Server verwenden, wenn Sie in Exchange UM integriert werden möchten, aber es ist keine Komponente der Skype for Business Server Website, daher wird sie hier nicht erwähnt.

Möglicherweise planen Sie mehrere zentrale Standorte, und wenn dies der Fall ist, können sie die folgenden Server und Rollen freigeben, wenn sie an Ihrem zentralen Standort bereitgestellt werden:

|||
|:-----|:-----|
|Eigenständiger Vermittlungsserver oder Vermittlungsserverpool  <br/> |Edgeserver oder Edgepool  <br/> |
|Server für beständigen Chat oder Serverpool für beständigen Chat  <br/> |Überwachung  <br/> |

Genau wie die letzte Liste fügen wir den Exchange UM-Server hier nicht ein, da er nicht Teil der Skype for Business Server Bereitstellung ist, aber auch hier in die gleiche Kategorie fällt.

Es gibt natürlich einige andere Komponenten und Optionen, die in Bereitstellungen einbezogen werden.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |PSTN-Gateways (wenn Sie Enterprise-VoIP  <br/> |Exchange UM-Server (wenn Sie Exchange UM integrieren möchten)  <br/> |DNS-Lastenausgleich  <br/> |
|Hardwaregeräte zum Lastenausgleich  <br/> |SQL Server-Datenbanken  <br/> |Dateifreigaben  <br/> ||

## <a name="server-roles"></a>Serverrollen

Jeder Server, auf dem Skype for Business Server ausgeführt wird, führt eine oder mehrere Serverrollen aus. Eine Serverrolle ist ein definierter Satz von Skype for Business Server Funktionen, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die erforderliche Funktionalität bereitstellen.

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen Pools mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Für die meisten Arten von Pools in Skype for Business Server müssen Sie ein Lastenausgleichsmodul bereitstellen, um den Datenverkehr zwischen den verschiedenen Servern im Pool zu verteilen. Skype for Business Server unterstützt sowohl DNS-Lastenausgleich (Domain Name System) als auch Hardwaregeräte zum Lastenausgleich.

### <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In Skype for Business Server Enterprise Edition ist der Front-End-Server die Zentrale Serverrolle und führt viele grundlegende Skype for Business Server Funktionen aus. Der Front-End-Server und die Back-End-Server sind die einzigen Serverrollen, die in einer Skype for Business Server Enterprise Edition Bereitstellung erforderlich sind.

Bei einem Front-End-Pool handelt es sich um einen Satz von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server bietet u. a. die folgenden Funktionen:

- Benutzerauthentifizierung und -registrierung.

- Anwesenheitsinformationen und Visitenkartenaustausch.

- Adressbuchdienste und Verteilerlistenerweiterung.

- Chatfunktionen, einschließlich Konferenzen mit mehreren Teilnehmern.

- Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt).

- Anwendungshosting für anwendungen, die in Skype for Business Server enthalten sind (z. B. Konferenzzentrale und Reaktionsgruppenanwendung) und Anwendungen von Drittanbietern.

- Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen enthalten Metriken zur Qualität der Medien (Audio und Video), die Ihr Netzwerk für Enterprise-VoIP Anrufe und A/V-Konferenzen durchlaufen.

- Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

- Optional eine Archivierung der Sofortnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) in der Planungsdokumentation.

    In Lync Server 2010 und früheren Versionen waren Überwachung und Archivierung separate Serverrollen, die nicht auf dem Front-End-Server verbunden waren.

- Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Darüber hinaus führt ein Front-End-Server in der Bereitstellung auch den zentralen Verwaltungsserver aus, der grundlegende Konfigurationsdaten verwaltet und auf allen Servern bereitstellt, auf denen Skype for Business Server ausgeführt wird. Der zentrale Verwaltungsserver bietet auch Lync Server-Verwaltungsshell und Dateiübertragungsfunktionen.

Die Back-End-Server sind Datenbankserver, die Microsoft SQL Server ausgeführt werden, die die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer- und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken, z. B. die Reaktionsgruppendatenbank. Sie können über einen einzelnen Back-End-Server verfügen, die hohe Verfügbarkeit des [Back-End-Servers in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) wird jedoch für Failover empfohlen. Back-End-Server führen keine Skype for Business Server Software aus.

> [!IMPORTANT]
> Es wird nicht empfohlen, Skype for Business Server Datenbanken mit anderen Datenbanken zu verbinden. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

### <a name="edge-server"></a>Edgeserver

Edgeserver ermöglicht Ihren Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Zu diesen externen Benutzern können die eigenen Benutzer der Organisation gehören, die derzeit außerhalb des Standorts arbeiten, Benutzer aus Verbundpartnerorganisationen und externe Benutzer, die zur Teilnahme an Konferenzen eingeladen wurden, die in Ihrer Skype for Business Server Bereitstellung gehostet werden.

Bei der Bereitstellung des Edgeservers werden außerdem die Mobilitätsdienste aktiviert, mit denen die Lync-Funktionalität auf mobilen Geräten unterstützt wird. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen ausführen wie Senden und Empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Das Mobilitätsfeature unterstützt auch Pushbenachrichtigungen für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre Skype for Business Server Benutzer Kontakte von XMPP-basierten Partnern für Chatnachrichten und Anwesenheitsinformationen hinzufügen können.

> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

### <a name="mediation-server"></a>Vermittlungsserver

Der Vermittlungsserver ist eine erforderliche Komponente für die Implementierung von Enterprise-VoIP, Anruf über Arbeit und Einwahlkonferenzen. Der Vermittlungsserver übersetzt Signalisierung und in einigen Konfigurationen Medien zwischen Ihrer internen Skype for Business Server-Infrastruktur und einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SIP-Trunk (Session Initiation Protocol). Sie können den Vermittlungsserver gemeinsam mit dem Front-End-Sever auf demselben Server oder getrennt in einem eigenständigen Vermittlungsserverpool ausführen.

Ausführliche Informationen finden Sie unter ["Vermittlungsserverkomponente" in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)

### <a name="video-interop-server"></a>Video-Interoperabilitätsserver

Der Video-Interoperabilitätsserver ist ab Skype for Business Server 2015 eine neue Rolle. Sie können Ihre Skype for Business Server Bereitstellung in bestimmte VTC-Lösungen (Video Teleconferencing System) von Drittanbietern integrieren. Ein VIS fungiert als Vermittler zwischen einem Drittanbieter-Telekonferenzsystem und einer Skype for Business Server Bereitstellung. Für diese Version konzentriert sich VIS auf die Interoperabilität mit Cisco/Tandberg-Videosystemen.

Ausführliche Informationen finden Sie unter [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Directors können Skype for Business Server Benutzeranforderungen authentifizieren, aber keine Benutzerkonten verwalten oder Anwesenheits- oder Konferenzdienste bereitstellen. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server.

### <a name="persistent-chat-server-roles"></a>Serverrollen für beständigen Chat

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Server, auf denen Skype for Business Server Standard Edition ausgeführt werden, können auch beständigen Chat ausführen, der auf demselben Server verbunden ist. Sie können den Front-End-Server für beständigen Chat nicht mit Enterprise Edition Front-End-Server verbinden.

Ausführliche Informationen finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung

Skype for Business Server bietet hohe Verfügbarkeit durch Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.

Skype for Business Server bietet auch Notfallwiederherstellungsmaßnahmen, indem die Poolpaarung aktiviert wird. Wenn Sie diese Topologie bereitstellen, bestimmen Sie Front-End-Poolpaare, wobei sich jeder Pool in einem Paar in einem separaten Rechenzentrum und in einem separaten geografischen Bereich befindet. Wenn ein Pool oder Standort ausfällt, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool im Paar zu verwenden, mit minimaler Dienstunterbrechung.

Skype for Business Server unterstützt auch mehrere Optionen für hohe Verfügbarkeit von Back-End-Servern. Hierzu gehören:

- Datenbankspiegelung

- AlwaysOn-Verfügbarkeitsgruppen

- AlwaysOn-Failoverclusterinstanzen (FCI)

- SQL Failoverclustering

Ausführliche Informationen zur Poolpaarung und zur hohen Verfügbarkeit von Back-End-Servern finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Serverkollocation in Skype for Business Server

Wir haben den Begriff "Collocate" bereits verwendet, aber was bedeutet dies? Skype for Business Server ermöglicht es Ihnen, einige Serverrollen und -features auf demselben Server zu finden, was kollokiert ist, oder auf verschiedenen Servern, aber es kann verwirrend sein, wenn Sie beginnen, und ob Sie eine Standard Edition oder Enterprise Edition Serverbereitstellung durchführen (sie verfügen jeweils über eigene Regeln). Zur Unterstützung Bei der Planung integrieren wir die Serverkollokation in Standard Edition Serverbereitstellungen und Enterprise Edition Front-End-Poolbereitstellungen (in den meisten Fällen sind diese Informationen identisch und wo sie unterschiedlich sind, werden sie speziell aufgerufen).

### <a name="collocation-of-server-roles"></a>Kollokation von Serverrollen

Auf dem Standard Edition Server ist die folgende Rolle verbunden (zusätzliche Konfiguration ist jedoch erforderlich), während diese Rolle im Enterprise Edition Front-End-Pool verbunden oder auf einem separaten Server bereitgestellt werden kann:

- Mediation

Diese Serverrollen müssen jeweils auf einem separaten Server bereitgestellt werden:

- Director

- Microsoft Edge

- Video-Interoperabilitätsserver

- Office Web Apps

### <a name="databases"></a>Datenbanken

Dies ist der Bereich mit echten Unterschieden zwischen Standard Edition Serverbereitstellungen und Enterprise Edition Bereitstellungen von Serverpools. Daher finden Sie im Folgenden zwei Abschnitte, gefolgt von einigen zusätzlichen Regeln für beide.

#### <a name="standard"></a>Standard

Da SQL Server Express auf dem Standard Edition Server verbunden ist und nicht verschoben werden kann, ist dies ziemlich einfach. Wenn Sie den Server für beständigen Chat auf einem Standard Edition Server bereitstellen, können Sie auch den beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat auf dem Standard Edition Server verbinden, dies ist jedoch nicht erforderlich.

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.

Diese können nicht auf dem Standard Edition Server verbunden werden, sondern können auf einem einzigen Datenbankserver ausgeführt werden:

- Überwachungsdatenbank

- Archivierungsdatenbank

- Jede Back-End-Datenbank für einen Enterprise Edition Front-End-Pool

#### <a name="enterprise"></a>Enterprise

Die folgenden Datenbanken können auf demselben Back-End-SQL Server verbunden werden:

- Back-End-Datenbank

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Konformitätsdatenbank für beständigen Chat

#### <a name="both"></a>In beide Richtungen

Nun sind einige zusätzliche Regeln zu beachten, wenn Sie Skype for Business Server Datenbanken in einer einzelnen SQL Instanz oder in mehreren SQL Instanzen in derselben SQL Server Datenbank verbinden:

- Jede SQL Instanz kann nur eine einzelne Back-End-Datenbank für einen Enterprise Edition Front-End-Pool, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne Datenbank für beständigen Chat und eine einzelne Konformitätsdatenbank für beständigen Chat enthalten.

- Der Datenbankserver kann nicht mehr als einen Enterprise Edition Front-End-Pool, einen Server, auf dem die Archivierung ausgeführt wird, einen Server mit Überwachung, eine einzelne Datenbank für beständigen Chat und eine einzelne Konformitätsdatenbank für beständigen Chat unterstützen. Er kann jedoch einen der beiden Server unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

    > [!NOTE]
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.

### <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann sich auf einem separaten Server befinden, oder Sie können sie auf demselben Server wie einen oder alle der folgenden Server verbinden:

- Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Konformitätsdatenbank für beständigen Chat

> [!CAUTION]
> Beachten Sie, dass Sie zwar die Dateifreigabe auf diesen Servern verbinden können, es jedoch wichtig ist, zu beachten, dass sie nicht empfohlen wird. Wenn Sie die Dateifreigabe mit einer anderen Serverrolle verbinden, stellen Sie sicher, dass Sie regelmäßig Auf Datenträgerspeicher- und Leistungsprobleme überwachen.

### <a name="keep-in-mind"></a>Beachten Sie

- Sie können keinen Reverseproxyserver verbinden, bei dem es sich nicht um eine Skype for Business Server Komponente handelt, und sich möglicherweise nicht einmal in Ihrer Topologie befinden. Sie benötigen einen Reverseproxy, wenn Sie unter anderem die Freigabe von Webinhalten für Verbundbenutzer unterstützen möchten. Falls erforderlich, implementieren Sie reverseproxyunterstützung für Skype for Business Server, indem Sie einen vorhandenen Reverseproxyserver konfigurieren, der sich bereits in Ihrer Organisation befindet und von anderen Anwendungen verwendet wird.

- Sie können keine Exchange UM-Komponente oder SharePoint Serverkomponente mit einer Skype for Business Server Rolle verbinden.

## <a name="see-also"></a>Siehe auch

[Referenztopologien für Skype for Business Server](reference-topologies.md)