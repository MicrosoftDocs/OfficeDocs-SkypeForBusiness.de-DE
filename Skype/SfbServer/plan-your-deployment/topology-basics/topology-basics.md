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
description: 'Zusammenfassung: Wählen Sie Ihre Topologie für Skype for Business Server aus. Erfahren Sie mehr über die Serverkollokation für Skype for Business Server.'
ms.openlocfilehash: 9b0dbe6a74a5982c2816c022e5ea7a99ba2abf07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831755"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Topologiegrunddaten für Skype for Business Server

**Zusammenfassung:** Wählen Sie Ihre Topologie für Skype for Business Server aus. Erfahren Sie mehr über die Serverkollokation für Skype for Business Server.

Bevor Sie etwas anderes vorbereiten, sollten Sie wissen, dass Sie die richtige Topologie für Ihre Bereitstellung von Skype for Business Server planen. Als Erstes müssen Sie entscheiden, ob Sie über eine lokale Bereitstellung von Skype for Business Server verfügen oder ob Sie dies mit einer Skype for Business Server Online-Bereitstellung in einer Hybridbereitstellung kombinieren möchten. In beiden Abschnitten sollten Sie weitere Informationen lesen, da wir hier die lokalen Topologien detailliert erläutern, aber die Hybriddetails sind in ihrem eigenen Abschnitt dokumentiert.

Sie können auch einige Beispieltopologien in [Referenztopologien für Skype for Business Server sehen.](reference-topologies.md)

## <a name="sites"></a>Websites

In Skype for Business Server definieren Sie Standorte in Ihrem Netzwerk, die Skype for Business Server-Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass Skype for Business Server-Websites ein separates Konzept von Active Directory Domain Services-Standorten und -Microsoft Exchange Server sind. Ihre Skype for Business Server-Standorte müssen nicht Ihren Active Directory-Standorten entsprechen.

Skype for Business Server unterstützt die lokale Bereitstellung eines oder mehrerer Standorte, die entsprechend Ihren Anforderungen an hohe Verfügbarkeit und Standorte skaliert werden können.

Ihre Bereitstellung verfügt über mindestens einen zentralen Standort (auch als Datencenter bezeichnet, dies ist ein Datencenter für alle Server, die sich dort befinden), und jeder zentrale Standort in Ihrer Bereitstellung verfügt über einen Standard Edition-Server oder mindestens einen Front-End-Pool der Enterprise Edition. Sie können die Unterschiede in den einzelnen Optionen unten sehen:

- Standard Edition server includes a collocated SQL Server Express database.

- Der Front-End-Pool der Enterprise Edition umfasst:

  - Ein oder mehrere Front-End-Server (idealerweise mindestens drei, um Skalierbarkeit zu gewährleisten), mit maximal zwölf. Für mehrere Server wäre ein Lastenausgleich erforderlich.

  - Ein separater Back-End-Server.

Weitere Informationen zu den verschiedenen Serverrollen finden Sie etwas später in diesem Abschnitt.

Zusätzlich zu Ihren zentralen Standorten kann es auch zu einer oder mehreren Zweigstellenstandorten kommen, die ihrem zentralen Standort zugeordnet sind. Sie sind für fast alle Funktionen vom zentralen Standort abhängig. Was besteht also genau aus ihnen?

- Survivable Branch Appliance, die ein PstN-Gateway (Public Switched Telephone Network) mit einigen Skype for Business Server-Funktionen kombiniert.

- Survivable Branch Server ist ein Server unter Windows Server, auf dem die Skype for Business Server-Registrierungs- und Vermittlungsserversoftware installiert ist.

- Eigenständiges PSTN-Gateway (das nicht Teil der Survivable Branch Appliance ist).

- Eigenständiger Vermittlungsserver oder eigenständiger Vermittlungsserverpool (wenn Sie diese Rolle nicht mit der Survivable Branch Appliance verbinden möchten).

## <a name="whats-in-a-skype-for-business-server-site"></a>Was ist an einer Skype for Business Server-Website?

Um genauer zu gehen, kann ein zentraler Standort auch über:

- Mehrere Front-End-Pools in derselben Domäne oder in unterschiedlichen Domänen (denken Sie bei der Planung daran, dass sich alle Front-End-Server in einem Front-End-Pool zusammen mit den Back-End-Servern für den Pool in derselben Domäne befinden müssen).

- Mehrere Server der Standard Edition.

- Office Web Apps Server, der mit Office Web Apps in Skype for Business Server zum Teilen und Rendern von PowerPoint-Präsentationen verwendet wird.

- Edgeserver oder Edgepool (in einem Umkreisnetzwerk). Erforderlich, wenn Ihre Bereitstellung Verbundpartner, Verbindungen mit öffentlichen Instant Messaging-Verbindungen, XMPP-Gateway (Extensible Messaging and Presence Protocol) und Remotebenutzerzugriff unterstützen soll. Weitere Informationen finden Sie in der Dokumentation zur Edgeserverplanung.

- Server für beständigen Chat. Hilfreich, wenn Benutzer an themenbasierten Unterhaltungen mit mehrerenPartys teilnehmen können sollen, die im Laufe der Zeit bestehen bleiben. Weitere Informationen finden Sie im Thema "Planen des Servers für beständigen Chat".

- Überwachung. Wird verwendet, um die Datenerfassung für Audio/Video (A/V) Quality of Experience (QoE) und die Aufzeichnung von Anrufdetaildaten (Call Detail Recording, CDR) für Enterprise-VoIP- und A/V-Konferenzen in Ihrer Bereitstellung zu unterstützen. Dies wird im Thema "Planen der Überwachung" ausführlich erläutert.

- Director oder Directorpool. Nicht erforderlich, aber hilfreich, wenn Sie die Ausfallsicherheit verbessern und die Umleitung von Skype for Business-Benutzeranforderungen an den Homepool des Benutzers aktivieren möchten. Wenn Sie Directors bereitstellen möchten, werden maximal 10 pro Pool unterstützt. Wenn Sie dies benötigen, lesen Sie unbedingt weiter im Thema "Planning for Directors".

- Reverseproxy. Dies ist keine Skype for Business Server-Komponente, aber wenn Sie die Freigabe von Webinhalten für Partnerbenutzer unterstützen möchten, wenn Sie mobilitätsgesteuerten Datenverkehr unterstützen möchten, wenn Ihre Remotebenutzer das Adressbuch verwenden, an Besprechungen teilnehmen möchten, ist dies etwas, was Sie in Ihrer Umgebung wünschen. Es gibt ein Thema zum Einrichten des Reverseproxyservers, in dem Sie weitere Details finden können, wenn Sie bereit sind.

Weitere Informationen zur Kollokation für diese Server finden Sie unten.

Alle Front-End-Pools und Standard Edition-Server, die an Ihrem zentralen Standort bereitgestellt werden, teilen sich Folgendes, vorausgesetzt, Sie haben sie bereitgestellt:

||||
|:-----|:-----|:-----|
|Director oder Director-Pool  <br/> |Eigenständiger Vermittlungsserver oder Vermittlungsserverpool  <br/> |Office Web Apps-Server  <br/> |
|Edgeserver oder Edgepool  <br/> |Server für beständigen Chat oder Serverpool für beständigen Chat  <br/> |Überwachung  <br/> |

Wo befindet sich der Exchange Unified Messaging (UM)-Server in dieser Liste? Nun, Sie können es mit Skype for Business Server verwenden, wenn Sie in Exchange UM integrieren möchten, aber es ist keine Komponente der Skype for Business Server-Website, daher erwähnen wir es hier nicht.

Möglicherweise planen Sie mehrere zentrale Standorte, und in diesem Falls können sie die folgenden Server und Rollen gemeinsam nutzen, wenn sie an Ihrem zentralen Standort bereitgestellt werden:

|||
|:-----|:-----|
|Eigenständiger Vermittlungsserver oder Vermittlungsserverpool  <br/> |Edgeserver oder Edgepool  <br/> |
|Server für beständigen Chat oder Serverpool für beständigen Chat  <br/> |Überwachung  <br/> |

Wie bei der letzten Liste wird hier der Exchange UM Server nicht berücksichtigt, da er nicht Teil der Skype for Business Server-Bereitstellung ist, aber auch hier in die gleiche Kategorie fällt.

Es gibt natürlich einige andere Komponenten und Optionen für Bereitstellungen.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |PSTN-Gateways (wenn Sie Enterprise-VoIP  <br/> |Exchange UM Server (wenn Sie in Exchange UM integrieren möchten)  <br/> |DNS-Lastenausgleich  <br/> |
|Hardwaregeräte zum Lastenausgleich  <br/> |SQL Server-Datenbanken  <br/> |Dateifreigaben  <br/> ||

## <a name="server-roles"></a>Serverrollen

Auf jedem Server mit Skype for Business Server wird mindestens eine Serverrolle ausgeführt. Eine Serverrolle ist ein definierter Satz von Skype for Business Server-Funktionen, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die erforderliche Funktionalität bereitstellen.

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen Pools mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Für die meisten Pooltypen in Skype for Business Server müssen Sie einen Lastenausgleich bereitstellen, um den Datenverkehr auf die verschiedenen Server im Pool zu verteilen. Skype for Business Server unterstützt sowohl den Dns-Lastenausgleich (Domain Name System) als auch Hardwaregeräte zum Lastenausgleich.

### <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In Skype for Business Server Enterprise Edition ist der Front-End-Server die zentrale Serverrolle und führt viele grundlegende Skype for Business Server-Funktionen aus. Der Front-End-Server und die Back-End-Server sind die einzigen Serverrollen, die in einer Skype for Business Server Enterprise Edition-Bereitstellung erforderlich sind.

Bei einem Front-End-Pool handelt es sich um einen Satz von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server bietet u. a. die folgenden Funktionen:

- Benutzerauthentifizierung und -registrierung.

- Anwesenheitsinformationen und Visitenkartenaustausch.

- Adressbuchdienste und Verteilerlistenerweiterung.

- Funktionen für Imitierung, einschließlich Konferenzen mit mehreren Konferenzpartys.

- Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt).

- Anwendungshosting, sowohl für Anwendungen, die in Skype for Business Server enthalten sind (z. B. Konferenz attendant und Reaktionsgruppe-Anwendung), als auch für Anwendungen von Drittanbietern.

- Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen enthalten Metriken zur Qualität der Medien (Audio und Video), die Ihr Netzwerk sowohl für Enterprise-VoIP als auch für A/V-Konferenzen durchlaufen.

- Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

- Optional eine Archivierung der Sofortnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in der Planungsdokumentation.

    In Lync Server 2010 und früheren Versionen waren Überwachung und Archivierung separate Serverrollen, die nicht auf dem Front-End-Server ausgeführt wurden.

- Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Darüber hinaus wird auf einem Front-End-Server in der Bereitstellung auch der zentrale Verwaltungsserver ausgeführt, der grundlegende Konfigurationsdaten verwaltet und auf allen Servern mit Skype for Business Server bereitgestellt. Der zentrale Verwaltungsserver bietet außerdem Lync Server Management Shell und Dateiübertragungsfunktionen.

Die Back-End-Server sind Datenbankserver, auf denen Microsoft SQL Server, die die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer- und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken wie die Reaktionsgruppesdatenbank. Sie können über einen einzelnen Back-End-Server verfügen, die hohe Verfügbarkeit von [Back-End-Servern in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) wird jedoch für failover empfohlen. Auf Back-End-Servern wird keine Skype for Business Server-Software ausgeführt.

> [!IMPORTANT]
> Es wird nicht empfohlen, Skype for Business Server-Datenbanken mit anderen Datenbanken zu verbinden. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL-Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

### <a name="edge-server"></a>Edgeserver

Der Edgeserver ermöglicht Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Zu diesen externen Benutzern können die eigenen Benutzer der Organisation gehören, die derzeit extern arbeiten, Benutzer aus Verbundpartnerorganisationen und externe Benutzer, die zur Teilnahme an Konferenzen eingeladen wurden, die in Ihrer Skype for Business Server-Bereitstellung gehostet werden.

Bei der Bereitstellung des Edgeservers werden außerdem die Mobilitätsdienste aktiviert, mit denen die Lync-Funktionalität auf mobilen Geräten unterstützt wird. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen ausführen wie Senden und Empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Das Mobilitätsfeature unterstützt auch Pushbenachrichtigungen für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre Skype for Business Server-Benutzer Kontakte von XMPP-basierten Partnern für Chat und Anwesenheit hinzufügen können.

> [!NOTE]
> XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

### <a name="mediation-server"></a>Vermittlungsserver

Der Vermittlungsserver ist eine erforderliche Komponente für Enterprise-VoIP, Anruf über Arbeit und Einwahlkonferenzen. Der Vermittlungsserver übersetzt Signaldaten und in einigen Konfigurationen Medien zwischen Ihrer internen Skype for Business Server-Infrastruktur und einem PSTN-Gateway( Public Switched Telephone Network), einer IP-PBX-Anlage oder einem Session Initiation Protocol (SIP)-Trunk. Sie können den Vermittlungsserver gemeinsam mit dem Front-End-Sever auf demselben Server oder getrennt in einem eigenständigen Vermittlungsserverpool ausführen.

Weitere Informationen finden Sie unter [Vermittlungsserverkomponente in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Video-Interoperabilitätsserver

Video Interop Server ist eine neue Rolle ab Skype for Business Server 2015. Sie können Ihre Skype for Business Server-Bereitstellung mit bestimmten VTC(Video Teleconferencing System)-Lösungen von Drittanbietern integrieren. Ein VIS fungiert als Vermittler zwischen einem Drittanbietertelekonferenzsystem und einer Skype for Business Server-Bereitstellung. Für diese Version konzentriert sich der VIS auf die Interoperabilität mit Cisco/Tandberg-Videosystemen.

Weitere Informationen finden Sie unter [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Directors können Skype for Business Server-Benutzeranforderungen authentifizieren, aber sie verwalten keine Benutzerkonten oder stellen Anwesenheits- oder Konferenzdienste zur Verfügung. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server.

### <a name="persistent-chat-server-roles"></a>Serverrollen für beständigen Chat

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Server, auf denen Skype for Business Server Standard Edition ausgeführt wird, können den beständigen Chat auch auf demselben Server ausführen. Sie können den Front-End-Server für beständigen Chat nicht mit dem Front-End-Server der Enterprise Edition verbinden.

Weitere Informationen finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung

Skype for Business Server bietet hohe Verfügbarkeit durch Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.

Skype for Business Server bietet auch Maßnahmen zur Notfallwiederherstellung, indem die Poolpaarung aktiviert wird. Wenn Sie diese Topologie bereitstellen, legen Sie Paare von Front-End-Pools mit jedem Pool in einem Paar in einem separaten Rechenzentrum und in einem separaten geografischen Bereich. Wenn ein Pool oder Standort aus fällt, können Sie die Benutzer dieses Pools so umleiten, dass sie den anderen Pool in dem Paar verwenden, mit minimaler Dienstunterbrechung.

Skype for Business Server unterstützt auch mehrere Optionen für die hohe Verfügbarkeit von Back-End-Servern. Hierzu gehören:

- Datenbankspiegelung

- AlwaysOn-Verfügbarkeitsgruppen

- AlwaysOn Failover Cluster Instances (FCI)

- SQL Failoverclustering

Details zur Poolpaarung und zur hohen Verfügbarkeit von Back-End-Servern finden Sie unter "Planen der hohen Verfügbarkeit und Notfallwiederherstellung [in Skype for Business Server".](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

## <a name="server-collocation-in-skype-for-business-server"></a>Serverkollokation in Skype for Business Server

Wir haben den Begriff "Collocate" bereits verwendet, aber was bedeutet das? Mit Skype for Business Server können Sie einige Serverrollen und -features auf demselben Server suchen, bei dem es sich um eine Kollokation handelt, oder auf unterschiedlichen Servern. Es kann jedoch verwirrend sein, wenn Sie beginnen und ob Sie eine Standard Edition- oder Enterprise Edition-Serverbereitstellung (die jeweils eigene Regeln haben) verwenden. Als Unterstützung bei der Planung verwenden wir Serverkollokation in Standard Edition-Serverbereitstellungen und Enterprise Edition-Front-End-Poolbereitstellungen (in den meisten Fällen sind diese Informationen identisch, und wenn sie anders sind, werden sie speziell bezeichnet).

### <a name="collocation-of-server-roles"></a>Kollokation von Serverrollen

Auf dem Standard Edition-Server ist die folgende Rolle ausgeführt (zusätzliche Konfiguration ist jedoch erforderlich), während diese Rolle im Front-End-Pool der Enterprise Edition mit einem separaten Server ausgeführt oder bereitgestellt werden kann:

- Vermittlung

Diese Serverrollen müssen jeweils auf einem separaten Server bereitgestellt werden:

- Director

- Microsoft Edge

- Video-Interoperabilitätsserver

- Office Web Apps

### <a name="databases"></a>Datenbanken

Dies ist der Bereich mit echten Unterschieden zwischen Standard Edition-Serverbereitstellungen und Enterprise Edition-Serverpoolbereitstellungen. Es folgen also zwei Abschnitte, gefolgt von einigen zusätzlichen Regeln für beide.

#### <a name="standard"></a>Standard

Da SQL Server Express auf dem Standard Edition-Server ausgeführt wird und nicht verschoben werden kann, ist dies ziemlich einfach. Wenn Sie den Server für beständigen Chat auf einem Standard Edition-Server bereitstellen, können Sie darüber hinaus auch die Konformitätsdatenbank für beständigen Chat und den beständigen Chat auf dem Standard Edition-Server verbinden, dies ist jedoch nicht erforderlich.

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.

Diese können nicht auf dem Standard Edition-Server, sondern auf einem einzigen Datenbankserver ausgeführt werden:

- Überwachungsdatenbank

- Archivierungsdatenbank

- Back-End-Datenbank für einen Front-End-Pool der Enterprise Edition

#### <a name="enterprise"></a>Enterprise

Die folgenden Datenbanken können auf demselben Back-End-Server SQL Server:

- Back-End-Datenbank

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Konformitätsdatenbank für beständigen Chat

#### <a name="both"></a>In beide Richtungen

Beim Verbinden von Skype for Business Server-Datenbanken in einer einzelnen SQL-Instanz oder in mehreren SQL-Instanzen in derselben SQL Server müssen nun einige zusätzliche Regeln SQL Server werden:

- Jede SQL kann nur eine einzelne Back-End-Datenbank für einen Front-End-Pool der Enterprise Edition, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne Datenbank für beständigen Chat und eine einzige Konformitätsdatenbank für beständigen Chat enthalten.

- Der Datenbankserver kann nicht mehr als einen Front-End-Pool der Enterprise Edition, einen Server mit Archivierung, einen Server mit Überwachung, eine einzelne Datenbank für den beständigen Chat und eine einzelne Konformitätsdatenbank für beständigen Chat unterstützen, kann jedoch einen davon unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

    > [!NOTE]
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.

### <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann sich auf einem separaten Server befinden, oder Sie können sie auf demselben Server verbinden wie eine oder alle der folgenden:

- Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Konformitätsdatenbank für beständigen Chat

> [!CAUTION]
> Beachten Sie, dass die Dateifreigabe auf diesen Servern zwar gemeinsam ausgeführt werden kann, sie jedoch nicht empfohlen wird. Wenn Sie die Dateifreigabe mit einer anderen Serverrolle verbinden, stellen Sie sicher, dass Sie regelmäßig auf Speicherplatz- und Leistungsprobleme achten.

### <a name="keep-in-mind"></a>Beachten Sie

- Sie können keinen Reverseproxyserver verbinden, der keine Skype for Business Server-Komponente ist und sich möglicherweise nicht einmal in Ihrer Topologie befindet. Sie benötigen unter anderem einen Reverseproxy, wenn Sie die Freigabe von Webinhalten für Partnerbenutzer unterstützen möchten. Falls erforderlich, implementieren Sie die Reverseproxyunterstützung für Skype for Business Server, indem Sie einen vorhandenen Reverseproxyserver konfigurieren, der bereits in Ihrer Organisation vorhanden ist und von anderen Anwendungen verwendet wird.

- Sie können keine Exchange -UM- oder SharePoint Server-Komponente mit einer Skype for Business Server-Rolle verbinden.

## <a name="see-also"></a>Siehe auch

[Referenztopologien für Skype for Business Server](reference-topologies.md)
