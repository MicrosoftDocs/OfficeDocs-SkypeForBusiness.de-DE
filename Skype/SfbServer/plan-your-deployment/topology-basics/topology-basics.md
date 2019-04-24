---
title: Topologiegrundlagen Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Zusammenfassung: Wählen Sie Ihre Topologie für Skype für Business Server. Informationen Sie zu serverausführung für Skype für Business Server.'
ms.openlocfilehash: 566d044defd69dd9ae79bc964c9a587332649b42
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205972"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Topologiegrundlagen Skype für Business Server

**Zusammenfassung:** Wählen Sie Ihre Topologie für Skype für Business Server. Informationen Sie zu serverausführung für Skype für Business Server.

Vor der Vorbereitung sonst noch etwas, möchten Sie wissen, dass Sie für die richtigen Topologie für die Bereitstellung von Skype für Business Server vorab. Erstes müssen Sie entscheiden ist, wenn Sie also eine lokalen Bereitstellung von Skype für Business Server verfügen oder wenn Sie vorhaben, dies mit einer Skype für Business Server Online-Bereitstellung in einer hybridbereitstellung zu kombinieren. In beiden Fällen Sie nun möchten, lesen Sie weiter, wie die lokalen-Topologien erläutert werden, aber die Hybriden Details in einem eigenen Abschnitt dokumentiert sind.

Sie können auch einige Beispieltopologien in [referenztopologien für Skype für Business Server](reference-topologies.md)finden Sie unter.

## <a name="sites"></a>Standorte

In Skype für Business Server definieren Sie Websites in Ihrem Netzwerk, die Skype für Business Server-Komponenten enthalten. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass Skype für Business Server Websites sind unterscheiden sich von Active Directory Domain Services-Websites und Microsoft Exchange Server-Websites. Ihre Skype für Business Server Websites müssen keine Active Directory-Standorte entsprechen.

Skype für Business Server unterstützt die lokale Bereitstellung an einen oder mehrere Websites, die gemäß der hohen Verfügbarkeit und die Anforderungen an den Speicherort skaliert werden kann.

Ihre Bereitstellung müssen Sie mindestens einen zentralen Standort (auch als ein Datencenter bezeichnet, ist dies ein Datencenter für alle darin Server), und jeder zentrale Standort in Ihrer Bereitstellung weist einen Standard Edition-Server oder mindestens einen Enterprise Edition-Front-End-Pool. Nachfolgend sind die Unterschiede zwischen den Optionen dargelegt:

- Standard Edition-Server enthält eine verbundene SQL Server Express-Datenbank.

- Enterprise Edition-Front-End-Pool verwaltet:

  - Eine oder mehrere Front-End-Servern (idealerweise mindestens drei, für die Skalierbarkeit), mit maximal zwölf. Für mehr als einen Server wäre ein Lastenausgleich erforderlich.

  - Eine separate Back End-Server.

Nähere Einzelheiten über die verschiedenen Serverrollen erfahren Sie im weiteren Verlauf dieses Abschnitts.

Zusätzlich zu Ihrer zentralen Standorten und möglicherweise auch am Ende besitzen eine oder mehrere Zweigniederlassungen mit Ihrem zentralen Standort verknüpft ist. Sie richten sich nach den zentralen Standort für fast alle ihre Funktionalität so Was sind sie, genau bestehen aus?

- Survivable Branch Appliance die ein Gateway public switched Telephone Network, (PSTN) mit einigen Skype für Business Server-Funktionalität kombiniert.

- Survivable Branch Server ist es einem Server mit Windows Server, der Skype für Business Server Registrierung und Vermittlungsserver Software installiert wurde.

- Eigenständiges PSTN-Gateway (Dies ist nicht Bestandteil der Survivable Branch Appliance).

- Eigenständiger Vermittlungsserver oder eigenständigen vermittlungsserverpool (sofern Sie nicht dieser Rolle mit der Survivable Branch Appliance zusammengestellt werden möchten).

## <a name="whats-in-a-skype-for-business-server-site"></a>Was ist in einer Skype für Business Server-Website?

Um weitere Details zu speichern, kann ebenfalls ein zentraler Standort haben:

- Mehrere Front-End-Pools, in derselben Domäne oder in unterschiedlichen Domänen (Beachten Sie bei der Planung, dass alle Front-End-Servern in einem Front-End-Pool, zusammen mit den Back End-Servern für den Pool in derselben Domäne sein müssen).

- Mehrere Standard Edition-Server.

- Office Web Apps Server, die mit Office Web Apps in Skype für Business Server verwendet wird, für die Freigabe und Rendern von PowerPoint-Präsentationen.

- Edge-Server oder Edge-Pool (in einem Umkreisnetzwerk). Wird benötigt, wenn Ihre Bereitstellung Verbundpartner, Verbindung mit öffentlichen Chatdiensten, ein Gateway für XMPP (Extensible Messaging and Presence Protocol ) und den Zugriff durch Remotebenutzer unterstützen soll. Weitere Informationen finden Sie in der Edge-Server in der Planungsdokumentation.

- Persistent Chat-Server. Nützlich, wenn Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen sollen, die sich über längere Zeiträume erstrecken. Weitere Informationen finden Sie unter Planning for Persistent Chat Server Thema ist vorhanden.

- Überwachung. Zur Unterstützung der Datensammlung für Audio/Video (A / V) Quality of Experience (QoE), und rufen detail Recording (CDR) für Enterprise Voice und A / V-Konferenzen in Ihrer Bereitstellung. Dies wird im Thema „Überwachungsplanung“ näher erläutert.

- Director oder Director-Pool. Nicht erforderlich, aber nützlich, wenn zur Verbesserung der Flexibilität und aktivieren Sie die Umleitung von Skype für Business Benutzeranfragen zum Homepool des Benutzers werden soll. Wenn Sie den Director-Server bereitstellen möchten, wird ein Maximum von 10 pro Pool unterstützt. Wenn es etwas, die Sie benötigen handelt, auf jeden Fall lesen Sie weiter unter Planning for Directors Thema.

- Reverse-Proxyserver. Dies ist eine Skype für Business Server-Komponente nicht, aber dies ist unterstützt die Freigabe von Webinhalten für Verbundbenutzer, wenn Sie beabsichtigen, die Unterstützung von Mobilität Datenverkehr, wenn Ihre Remotebenutzer zum Adressbuch, Besprechungsteilnahme per usw. verwenden möchten etwas Sie benötigen Möchten Sie in Ihrer Umgebung haben. Es ist eine Einstellung up Reverse Proxy Servers Thema Sie weitere Details können überprüfen Wenn Sie bereit sind.

Nachstehend finden Sie weitere Informationen zum Verbinden dieser Server.

Alle Front-End-Pools und Standard Edition-Server am zentralen Standort bereitgestellt freigeben folgenden, vorausgesetzt, Sie haben diese bereitgestellt:

||||
|:-----|:-----|:-----|
|Director oder Director-pool  <br/> |Eigenständiger Vermittlungsserver oder vermittlungsserverpool  <br/> |Office Web Apps-Server  <br/> |
|Edge-Server oder Edge-pool  <br/> |Persistent Chat-Server oder Persistent Chat Server pool  <br/> |Überwachung  <br/> |

Wo befindet sich Exchange Unified Messaging (UM) Server in dieser Liste? Sie können natürlich es mit Skype für Business Server verwenden, wenn Sie mit Exchange UM integrieren möchten, aber es ist nicht Bestandteil der Skype für Business Server-Website, damit es nicht hier Erwähnung sind.

Planen Sie möglicherweise auf mehrere zentralen Standort haben, und so ist, sie können gemeinsam den folgenden Servern und Rollen, wenn sie auf Ihrem zentralen Standort bereitgestellt haben:

|||
|:-----|:-----|
|Eigenständiger Vermittlungsserver oder vermittlungsserverpool  <br/> |Edge-Server oder Edge-pool  <br/> |
|Persistent Chat-Server oder Persistent Chat Server pool  <br/> |Überwachung  <br/> |

Wie bei der letzten Liste sind nicht wir dem Exchange UM-Server hier einschließlich, da es nicht Bestandteil der Skype für Business Server-Bereitstellung ist, aber es liegt in der gleichen Kategorie hier zu.

Bereitstellungen enthalten aber auch noch weitere Komponenten und Optionen.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |PSTN-Gateways (wenn Sie Enterprise-VoIP bereitstellen)  <br/> |Exchange UM-Servers (Wenn Sie Exchange UM integrieren möchten)  <br/> |DNS-Lastenausgleich  <br/> |
|Hardwaregeräte zum Lastenausgleich  <br/> |SQL Server-Datenbanken  <br/> |Dateifreigaben  <br/> ||

## <a name="server-roles"></a>Serverrollen

Jeder Server mit Skype für Business Server führt eine oder mehrere Serverrollen. Eine Serverrolle ist eine definierte Reihe von Skype für Business Server-Funktionen, die von diesem Server bereitgestellt. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die die erforderliche Funktionalität enthalten.

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen Pools mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Für die meisten Arten von Pools in Skype für Business Server müssen Sie ein System zum Lastenausgleich, um den Datenverkehr zwischen den verschiedenen Servern im Pool verteilt bereitstellen. Skype für Business Server unterstützt Domain Name System (DNS)-Lastenausgleich und Hardwaregeräte zum Lastenausgleich.

### <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In Skype für Business Server Enterprise Edition der Front-End-Server die Server Core-Rolle ist und viele grundlegende Skype für Business Server-Funktionen ausgeführt. Der Front-End-Server zusammen mit den Back End-Servern, sind die einzige Serverrollen in eine beliebige Skype für Business Server Enterprise Edition-Bereitstellung erforderlich.

Ein Front-End-Pool ist eine Reihe von Front-End-Servern identischer Konfiguration, die zum Bereitstellen von Diensten für eine allgemeine Gruppe von Benutzern zusammenarbeiten. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server umfasst Folgendes:

- Benutzerauthentifizierung und -registrierung.

- Anwesenheitsinformationen und Visitenkartenaustausch.

- Adressbuchdienste und Verteilerlistenerweiterung.

- Chatnachrichtenfunktionalität, einschließlich Chatnachrichtenkonferenzen mit mehreren Teilnehmern.

- Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt).

- Anwendungshosting für sowohl Skype für Business Server (beispielsweise die Konferenzzentrale und Reaktionsgruppendienst-Anwendung) enthaltenen Anwendungen und drittanbieteranwendungen.

- Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen bereitstellt, über die Qualität des Mediums (audio und video) Metriken Traversieren Ihr Netzwerk für Enterprise-VoIP-Anrufe und A / V-Konferenzen.

- Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

- Optional eine Archivierung der Chatnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in der Planungsdokumentation.

    In Lync Server 2010 und früheren Versionen wurden die Überwachung und Archivierung separaten Serverrollen nicht auf Front-End-Server verbunden.

- Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Ein Front-End-Server in der Bereitstellung führt darüber hinaus auch den zentralen Verwaltungsserver, die verwaltet und grundlegende Konfigurationsdaten auf allen Servern mit Skype für Business Server bereitgestellt. Den zentralen Verwaltungsserver außerdem Lync Server-Verwaltungsshell und Dateiübertragungsfunktionen Datei.

Die Back-End-Servern sind Datenbankserver mit Microsoft SQL Server, die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server dienen als backup-Speicher für des Pools Benutzer- und Konferenzdaten und befinden sich die primären Speicher für andere Datenbanken, wie die reaktionsgruppendatenbank. Sie können einen einzelnen Back End-Server verfügen wird, [hohe Verfügbarkeit von Back-End-Server in Skype für Business Server](../high-availability-and-disaster-recovery/back-end-server.md) jedoch empfohlen für Failover. Back-End-Servern Skype für Business Server Software nicht ausgeführt werden.

> [!IMPORTANT]
> Zusammenstellen des Skype für Business Server-Datenbanken mit anderen Datenbanken wird nicht empfohlen. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.

> [!NOTE]
> SQL-Spiegelung wird steht in Skype für Business Server 2015 jedoch nicht mehr in unterstützt Skype für Business Server 2019. Die AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL clustering Failovermethoden werden bevorzugt mit Skype für Business Server 2019.

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

### <a name="edge-server"></a>Edgeserver

Edge-Server ermöglicht es Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Diese externen Benutzer können die organisationseigenen Benutzer enthalten, die derzeit sind außerhalb des Betriebsgeländes arbeiten, Benutzer Organisationen Verbundpartner und externe Benutzer, die zur Teilnahme an Konferenzen auf Ihre Skype für Business Server-Bereitstellung eingeladen wurden.

Bereitstellen von Edge-Server auch ermöglicht Mobilitätsdienste, der Lync-Funktionen auf mobilen Geräten unterstützt. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen wie Senden und Empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit ausführen. Mobile Geräte unterstützt darüber hinaus einige Enterprise-VoIP-Features, beispielsweise zum Teilnehmen an einer Konferenz, Anruf über den Arbeitsplatz, Erreichbarkeit unter einer Nummer, Voicemail und verpasste Anrufe klicken. Die Mobilitätsfunktion unterstützt auch Pushbenachrichtigungen für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten, um Ihre Skype für Business Server-Benutzer hinzufügen Kontakte von XMPP-basierten Partnern für instant messaging und Anwesenheit aktivieren konfigurieren.

> [!NOTE]
> XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019. Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>Vermittlungsserver

Mediation Server ist eine erforderliche Komponente für die Implementierung von Enterprise-VoIP, über den Arbeitsplatz anrufen und einwahlkonferenzen. Vermittlungsserver übersetzt Signalisierung, und in einigen Konfigurationen, Medien zwischen Ihrem internen Skype für Business Server-Infrastruktur und eine öffentliche gewechselt, PSTN-Gateway (Telefonfestnetz), IP-Nebenstellenanlage oder einen Trunk Session Initiation Protocol (SIP). Sie können Mediation Server ausführen zusammen auf demselben Server als Front-End-Server oder in einen eigenständigen vermittlungsserverpool aufgeteilt.

Weitere Informationen hierzu finden Sie unter [Mediation Server Component in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Video-Interoperabilität-Server

Interop-Video-Server ist eine neue Rolle ab Skype für Business Server 2015. Sie können Ihre Skype für Business Server-Bereitstellung mit bestimmten VTC (Video Telekonferenzsystem)-Lösungen von Drittanbietern integriert werden soll. Ein gegenüber dient als Vermittlung zwischen einem 3. Partei Telefonkonferenzen System und einen Skype für Business Server-Bereitstellung. Bei dieser Version konzentriert sich der VIS auf die Interoperabilität mit Videosystemen von Cisco/Tandberg.

Weitere Informationen hierzu finden Sie unter [Interop Videoserver in Skype für Business Server planen](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Directors können Skype für Benutzeranfragen Business Server authentifizieren, aber sie nicht privat Benutzerkonten oder Anwesenheit oder Konferenzdienste bereitzustellen. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server.

### <a name="persistent-chat-server-roles"></a>Persistent Chat Server-Rollen

> [!NOTE]
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Servern mit Skype für Business Server Standard Edition auch Persistent Chat ausgeführt werden können, werden auf demselben Server verbunden. Sie können nicht den beständigen Chat Front-End-Server mit Enterprise Edition-Front-End-Server verbinden.

Weitere Informationen hierzu finden Sie unter [Planen von Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung

Skype für Business Server bietet hohe Verfügbarkeit durch Redundanz von Webservern über pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.

Skype für Business Server bietet auch Disaster Recovery Maßnahmen Kopplung von Pools aktivieren. Wenn Sie diese Topologie bereitstellen, werden Sie Paare von Front-End-Pools und mit jeder Pool in einem Paar befindet sich in einem separaten Rechenzentrum und einen separaten geografischen Bereich festlegen. Wenn Sie einen Pool oder Standort ausfällt, können Sie die Benutzer von diesem Pool um Pool in das Paar mit minimaler Unterbrechung der Dienst verwenden umleiten.

Skype für Business Server unterstützt auch mehrere Optionen für hohe Verfügbarkeit von Back-End-Server. Diese beinhalten Folgendes:

- Datenbankspiegelung

- AlwaysOn-Verfügbarkeitsgruppen

- AlwaysOn-Failoverclusterinstanzen (FCI)

- SQL-Failoverclustering

Ausführliche Informationen zur Kopplung von Pools und hohe Verfügbarkeit von Back-End-Server finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Gemeinsame serverausführung in Skype für Business Server

Wir haben verwendet der Begriff bereits zusammenstellen, aber was bedeutet das? Skype für Business Server ermöglicht es Ihnen, suchen einige Serverrollen und Features auf dem gleichen Server, der gemeinsame Ausführung ist, oder auf unterschiedlichen Servern, jedoch können verwirrend sein, wenn Sie neu und beginnen, und ob Sie gerade tun, einen Standard Edition oder Enterprise Edition-server Bereitstellung (beide verfügen über eigene Regeln). Um Hilfe bei der Ihrer Planung sind wir Server verbinden in Bereitstellungen von Standard Edition-Server und Enterprise Edition-Front-End-Pool-Bereitstellungen einschließlich (diese Informationen in den meisten Fällen ist identisch und anderen ist, wird aufgerufen insbesondere).

### <a name="collocation-of-server-roles"></a>Kollokation von Serverrollen

Standard Edition-Servers weist die folgenden Rolle verbunden (zusätzliche Konfiguration ist erforderlich gegenüber), klicken Sie in der Enterprise Edition-Front-End-Pool, diese Rolle kann verbunden oder auf einem separaten Server bereitgestellt:

- Vermittlung

Die Serverrollen müssen jeweils auf einem separaten Computer bereitgestellt werden:

- Director

- Edge

- Video-Interoperabilität-Server

- Office Web Apps

### <a name="databases"></a>Datenbanken

Dies ist der Bereich mit der echten Unterschiede zwischen Standard Edition-Server-Bereitstellungen und Bereitstellungen mit Enterprise Edition-Server-Pools, damit wir zwei Abschnitte weiter unten einige zusätzlichen Regeln für beide gefolgt müssen.

#### <a name="standard"></a>Standard

Da SQL Server Express auf dem Standard Edition-Server verbunden ist, und kann nicht verschoben werden, ist dies recht einfach. Darüber hinaus, wenn Sie Persistent Chat Server auf einem Standard Edition-Server bereitstellen, Sie können auch den beständigen Chat und die Kompatibilitätsdatenbank beständigen Chat auf dem Standard Edition-Server zu verbinden, aber nicht erforderlich.

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

Diese können nicht auf dem Standard Edition-Server ausgeführt werden, jedoch können auf einem einzelnen Datenbankserver eigene wechseln:

- Überwachungsdatenbank

- Archivierungsdatenbank

- Alle Back-End-Datenbank für einen Enterprise Edition-Front-End-pool

#### <a name="enterprise"></a>Enterprise

Die folgenden Datenbanken können auf dem gleichen Back-End-SQL Server kombiniert werden:

- Back-End-Datenbank

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Kompatibilitätsdatenbank für beständigen Chat

#### <a name="both"></a>Both

Nun, es gibt einige zusätzlichen Regeln zu befolgen, wenn Verbindung Skype für Business Server-Datenbanken in einer einzelnen SQL-Instanz oder in mehreren SQL-Instanzen in der gleichen SQL Server-Datenbank:

- Jede SQL-Instanz kann nur eine einzelne Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool, eine Überwachungsdatenbank, eine einzige Archivierungsdatenbank, eine einzelne Datenbank für beständigen Chat und eine einzelne Datenbank für beständigen Chat Compliance enthalten.

- Der Datenbankserver kann nicht mehrere Enterprise Edition-Front-End-Pools, einen Server mit der Archivierung, einen Server mit der Überwachung, eine einzelne Datenbank für beständigen Chat und einer einzelnen Kompatibilitätsdatenbank beständigen Chat unterstützen, aber dies kann eine der einzelnen unterstützen, unabhängig von gibt an, ob die Datenbanken verwenden dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server.

    > [!NOTE]
    > Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.

### <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann auf einem separaten Server oder auf demselben wie einem der folgenden Server ausgeführt werden:

- Datenbankserver, einschließlich des Back-End Servers eines Enterprise Edition-Front-End-Pools

- Überwachungsdatenbank

- Archivierungsdatenbank

- Datenbank für beständigen Chat

- Kompatibilitätsdatenbank für beständigen Chat

> [!CAUTION]
> Beachten Sie, dass die Dateifreigabe auf diesen Servern zwar ausgeführt werden kann, wir dies jedoch nicht empfehlen. Stellen Sie sicher, regelmäßig auf genügend Speicherplatz und Leistungsprobleme zu achten, wenn Sie die Dateifreigabe mit einer beliebigen anderen Serverrolle ausführen.

### <a name="keep-in-mind"></a>Bitte beachten Sie:

- Sie können keinen Reverseproxyserver verbinden, die einen Skype für Business Server-Komponente nicht zur Verfügung, und möglicherweise auch nicht in Ihrer Topologie. Wenn Sie die gemeinsame Nutzung von Webinhalten für Verbundbenutzer, u. a. viele unterstützen möchten, benötigen Sie einen reverse-Proxyserver. Bei Bedarf, fahren Sie fort, und implementieren Sie reverse-Proxy-Unterstützung für Skype für Business Server durch Konfigurieren eines vorhandenen reverse-Proxyservers, der bereits in Ihrer Organisation ist, die von einer anderen Anwendung verwendet wird.

- Sie können keine Exchange UM-Komponente oder SharePoint Server-Komponente Skype für Business Server-Role verbinden.

## <a name="see-also"></a>Siehe auch

[Referenztopologien für Skype für Business Server](reference-topologies.md)
