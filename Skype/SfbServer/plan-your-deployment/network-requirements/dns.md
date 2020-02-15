---
title: DNS-Anforderungen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Zusammenfassung: Überprüfen Sie die DNS-Überlegungen in diesem Thema vor der Implementierung Skype for Business Server.'
ms.openlocfilehash: 33c5e18c6bc8d5a29b0e4a6fa447fbde02028556
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982810"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS-Anforderungen für Skype for Business Server

**Zusammenfassung:** Lesen Sie die DNS-Überlegungen in diesem Thema, bevor Sie Skype for Business Server implementieren.

In diesem Artikel wird nur die DNS-Planung für Skype for Business Server Bereitstellungen im lokalen Netzwerk einer Organisation behandelt. Informationen zu Skype for Business Online finden Sie unter "Office 365 URLs and IP Address Ranges" unter [https://aka.ms/o365ips](https://aka.ms/o365ips).

Ein DNS-Server (Domain Name Service) ordnet Hostnamen zu (wie<span> </span> www. Contoso<span></span>. com, vermutlich ein Webserver) zu IP-Adressen (beispielsweise 10.10.10.10). Es unterstützt Clients und voneinander abhängige Server miteinander im Netzwerk kommunizieren. Wenn Sie eine Implementierung von Skype for Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung neuer Server Namen (in der Regel die Rolle, die Sie übernehmen) mit den IP-Adressen übereinstimmt, denen Sie zugewiesen sind.

Dies kann zwar zunächst ein wenig entmutigend erscheinen, die Planung kann jedoch mit dem [Skype for Business Server 2015 Planungs Tool](https://www.microsoft.com/download/details.aspx?id=50357)stark angehoben werden. Nachdem Sie die Fragen des Assistenten zu den Funktionen, die Sie verwenden möchten, durchlaufen haben, können Sie für jeden Standort, den Sie definieren, den DNS-Bericht im Edge-Administrator Bericht anzeigen und die dort aufgelisteten Informationen verwenden, um Ihre DNS-Einträge zu erstellen. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen, ausführliche Informationen finden Sie unter [Überprüfen des DNS-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Beachten Sie, dass Sie den Edge-Verwaltungsbericht in ein Excel-Arbeitsblatt exportieren können, und der DNS-Bericht ist eines der Arbeitsblätter in der Datei. Dieses Tool umfasst Features, die [in Skype for Business Server 2019 veraltet](../../../SfBServer2019/deprecated.md)sind, kann jedoch weiterhin verwendet werden, um einen anfänglichen Plan zu erstellen, wenn diese Features nicht ausgewählt sind.

Wenn Sie eine neue Implementierung installieren, wie unter [Create DNS Records for Skype for Business Server und erstellen](../../deploy/install/create-dns-records.md) Ihrer Topologie für Skype for Business Server beschrieben, erkennen wir, dass Sie die DNS-Funktionen, die in Windows Server 2016 oder einem Drittanbieter-DNS-Paket integriert sind, verwenden können, daher halten wir die Diskussionen in diesem Artikel für allgemein und nicht für spezifisch. Wir erläutern, was erforderlich ist, und wie Sie diese Anforderungen erfüllen, ist die Entscheidung, die Sie treffen müssen.

Erfahrene Skype for Business-, lync-und Office Communications Suite-Administratoren werden die folgenden Tabellen wahrscheinlich nützlich finden. Wenn die Tabelle verwirrend für Sie ist, werden die nachfolgenden Abschnitte oder Artikel einiges über die folgenden Konzepte beleuchten:

## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

Die folgenden Tabellen enthalten DNS-Einträge Skype for Business Server verwendet, um Benutzern Dienste bereitzustellen. Einige sind optional, da Sie nur zur Unterstützung bestimmter Features erforderlich sind, und Sie können übersprungen werden, wenn diese Features nicht gewünscht werden. Die für den internen Zugriff erforderlichen DNS-Einträge sind nur in der ersten Tabelle enthalten, und für eine Bereitstellung, die internen und externen Zugriff ermöglicht, sind Datensätze aus beiden Tabellen erforderlich.

**Interne DNS-Zuordnungen**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Front-End-Pool-FQDN  <br/> *FE-Pool. <span> </span>Contoso<span></span>. com*   |Front-End-Pool Server-IP-Adressen  <br/>  DNS lb to *192.168.21.122 Ausgleich 192.168.21.124*   |DNS-Lastenausgleich von Front-End-Pools. Ordnet den Front-End-Pool Namen einer Gruppe von IP-Adressen zu.  <br/> Siehe [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN jeder Front-End-Server oder Standard Edition-Server in einem Pool oder einem eigenständigen Server <br/>  *"Fe01". <span> </span>contoso. <span> </span>com-FE02. <span> </span>Contoso<span></span>. com FE03. <span> </span>Contoso<span></span>. com*   |Entsprechende IP-Adresse der einzelnen Server  <br/> *192.168.21.122 Ausgleich 192.168.21.124*   |Ordnet den Servernamen seiner IP-Adresse zu.   |v   |
|A/AAAA   |Enterprise-Pool interne Webdienste FQDN außer Kraft setzen  <br/> *Internet-int.<span></span>Contoso<span></span>. com*   |HLB-VIP für Front-End-Server interne Webdienste  <br/> *192.168.21.120*   |Erforderlich, um den Webdatenverkehr von Clients auf dem Server zu aktivieren, beispielsweise das Herunterladen der Skype for Business-Webanwendung. Auch für mobile Clients erforderlich.   |v   |
|A/AAAA   |Enterprise-Pool externe Webdienste FQDN außer Kraft setzen  <br/> *Webseite-ext.<span></span>Contoso<span></span>. com*   |HLB-VIP für Front-End-Server externe Webdienste  <br/>*68.123.56.90*   |Erforderlich, um den Webdatenverkehr von Clients auf dem Server zu aktivieren, beispielsweise das Herunterladen der Skype for Business-Webanwendung. Erforderlich, wenn mobile Clients die DNS intern auflösen. Kann in DMZ Reverse Proxy IP oder Internet IP aufgelöst werden.   ||
|A/AAAA   | SQL Server-FQDN des Back-End-Servers <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |Server-IP-Adresse  <br/> *192.168.11.90*   |Ordnet den Servernamen für einen Back-End-SQL-Server an, der mit dem Front-End-Pool an seine IP-Adresse arbeitet.   ||
|A/AAAA   |Back-End-Server-SQL Server-FQDN spiegeln  <br/> *Sql2. <span> </span>Contoso<span></span>. com*   |Server-IP-Adresse  <br/> *192.168.11.91*   |Ordnet den Servernamen eines Back-End-SQL-Spiegelservers an, der mit dem Front-End-Pool an seiner IP-Adresse arbeitet.   ||
|A/AAAA   |Directorpool-FQDN  <br/>**Hinweis:** Nicht zutreffend bei Verwendung eines eigenständigen Director-Servers <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |Directorpool-IP-Adressen  <br/> DNS-lb zu *192.168.21.132, 192.168.21.133, 192.168.21.134*   |DNS-Lastenausgleich von Director-Pool Servern. Ordnet den Namen des Pools für das Directorpool einer IP-Adresse zu, siehe [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir) <br/> Ein Director kann einen Benutzer authentifizieren und ist optional.   ||
|A/AAAA   |Director-FQDN   |Server-IP-Adresse jedes Director-Servers   |Ordnet den Namen des Pools für den Director einer IP-Adresse zu, siehe [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN des Vermittlungsserver Pools   |Pool-IP-Adressen   |Die Vermittlungsserver Rolle ist optional. Sie können die von einem Vermittlungsserver bereitgestellten Dienste für den Front-End-Server oder-Pool zusammenstellen. Siehe [Verwenden des DNS-Lastenausgleichs in Vermittlungsserver Pools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Vermittlungsserver-FQDN   |Server-IP-Adresse   |Sie können die von einem Vermittlungsserver bereitgestellten Dienste für den Front-End-Server oder-Pool zusammenstellen. Siehe [Verwenden des DNS-Lastenausgleichs in Vermittlungsserver Pools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN des Servers für beständigen Chat   |IP-Adresse des Servers für beständigen Chat   |Ein Server für beständigen Chat ist für das Feature für den beständigen Chat erforderlich und ist ansonsten optional.   ||
|A/AAAA   |"lyncdiscoverinternal". * \<sipdomain "\>* <br/> "lyncdiscoverinternal". * <span> </span>Contoso<span></span>. com*   |HLB Front-End-Pool VIP-oder Director-IP  <br/>  192.168.21.121  |Interne AutoErmittlung Service1, erforderlich für Mobilitätsunterstützung. Wenn das Auflösen von internem DNS für mobile Geräte verwendet wird, sollte es auf die externe IP oder DMZ VIP hinweisen.  <br/> Für Webdienste benötigen wir HLB im Front-End-Pool, da https DNS nicht nutzen kann. Für Front-End-Pool oder Directorpool sollte dies zu einem HLB-VIP oder einer regulären IP-Adresse für einen Standard Edition-Server oder einen eigenständigen Director-Server aufgelöst werden.   |v   |
|CNAME   |"lyncdiscoverinternal". * \<sipdomain "\>* <br/> "lyncdiscoverinternal". *<span></span>Contoso<span></span>. com*   |Vollqualifizierter FQDN-oder Director-FQDN des HLB FE-Pools  <br/> Internet-int.<span></span>Contoso<span></span>. com   |Interne AutoErmittlung Service1 <br/> Sie können dies bei Bedarf als CNAME anstelle eines a-Eintrags implementieren.   ||
|A/AAAA   |SIP. * \<sipdomain "\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Front-End-Pool Server-IP-Adressen (oder an eine beliebige Director-IP-Adresse)  <br/>  DNS lb to *192.168.21.122 Ausgleich 192.168.21.124*   |Für die automatische Konfiguration erforderlich, siehe [Exemplarische Vorgehensweise von Skype for Business Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Ein Datensatz oder Datensätze, die auf die Front-End-Pool Server oder Director-Server im internen Netzwerk oder auf die Zugriffs-Edgedienst, wenn der Client extern ist   |&#x2777;  |
|A/AAAA   |ucupdates-r2. * \<sipdomain "\>* <br/> ucupdates-r2. * <span> </span>Contoso<span></span>. com*  |HLB FE Pool VIP oder Director Pool HLB VIP oder SE/Director Server IP  <br/>  192.168.21.121  |Die Bereitstellung dieses Datensatzes ist optional &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain "\> * <br/>Port 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Port 5061  |Front-End-Pool-FQDN  <br/>*FE-Pool. <span> </span>Contoso<span></span>. com*  |Aktiviert die automatische Anmeldung des internen Benutzers 1 für den Front-End-Server/Pool oder SE-Server/-Pool, der Clientanforderungen für die Anmeldung authentifiziert und umleitet.  |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain "\>* <br/>sipinternal. <span> </span> *contoso<span></span>. com*  |Front-End-Pool-FQDN  <br/>_FE-Pool. <span> </span>Contoso<span></span>. com_  |Interner Benutzer Zugriff &#x2776;  |&#x2777;  |
|SRV   | \_NTP. \_UDP. * \<sipdomain "\> * <br/> \_NTP. \_UDP. <span> </span> *contoso<span></span>. com*  |Server-FQDN  <br/> north-america.pool.ntp.org   |Erforderliche NTP-Quelle für lync Phone Edition-Geräte   |Dies ist für die Unterstützung von Desktop-Mobiltelefonen erforderlich.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain "\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  | Zugriffs-Edgedienst-FQDN <br/> EdgePool-int.<span></span>*contoso<span></span>. com*  |Erstellen Sie einen SRV-Eintrag für jede SIP-Domäne, die über IOS-oder Windows Phone Mobile-Clients verfügt.   |Unterstützung für mobile Clients   |
|A/AAAA   |Administrator-URL  <br/>*Internet-int.<span></span>Contoso<span></span>. com*  |HLB FE-Pool – VIP  <br/> 192.168.21.121   |Skype for Business Server der Systemsteuerung finden Sie unter [Simple URLs](dns.md#BK_Simple) .  ||
|A/AAAA   |URL erfüllen  <br/>*Internet-int.<span></span>Contoso<span></span>. com*  |HLB FE-Pool – VIP  <br/> 192.168.21.121   |Online Besprechungen, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Einwahl-URL  <br/>*Internet-int.<span></span>Contoso<span></span>. com*  |HLB FE-Pool – VIP  <br/> 192.168.21.121   |Einwahlkonferenzen, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Interner Webdienste FQDN  <br/>*Internet-int.<span></span>Contoso<span></span>. com*  |HLB FE-Pool – VIP  <br/> 192.168.21.121   |Skype for Business von Skype for Business-Webanwendung verwendete Webdienst   ||
|A/AAAA   |FQDN des Office-webapps-Server Pools  <br/> OWA. <span> </span>Contoso<span></span>. com   | VIP-Adresse des Office-webapps-Server Pools <br/> 192.168.1.5   |Definiert den FQDN des Office-webapps-Server Pools   ||
|A/AAAA   | Interner FQDN des Webs <br/> Internet-int.<span></span>Contoso<span></span>. com   | Front-End-Pool VIP-Adresse <br/> 192.168.21.121   |Definiert den internen webfqdn, der von Skype for Business-Webanwendung verwendet wird.  <br/> Wenn Sie den DNS-Lastenausgleich in diesem Pool verwenden, kann Ihre Front-End-Pool und die interne Webfarm nicht denselben FQDN aufweisen.   ||

&#x2776; wird von einem Client verwendet, um die Front-End-Server oder Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu sein. Weitere Einzelheiten dazu finden Sie unter [Exemplarische Vorgehensweise von Skype for Business Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; Dies ist nur erforderlich, um ältere Clients vor lync 2013 und Desktop-Mobiltelefonen zu unterstützen.

&#x2778; in der Situation, in der ein Unified Communications-Gerät aktiviert ist, sich jedoch ein Benutzer noch nie am Gerät angemeldet hat, ermöglicht der a-Eintrag dem Gerät, den Server, der den Geräte Update-Webdienst hostet, zu ermitteln und Updates zu erhalten. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.

Das folgende Diagramm zeigt ein Beispiel, das sowohl interne als auch externe DNS-Einträge sowie viele der in den umgebenden Tabellen angezeigten Datensätze enthält:

**Edge-Netzwerkdiagramm mit öffentlichen IPv4-Adressen**

![Beispiel für ein DNS-Netzwerkdiagramm](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**DNS-Zuordnungen für Umkreisnetzwerke (sowohl interne als auch externe Schnittstellen)**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |Interner Edgepool FQDN  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |Intern ausgerichtete Edgepool-IP-Adressen  <br/> 172.25.33.10, 172.25.33.11   |Konsolidierte Edge-Pool-IP-Adressen der internen Schnittstelle   |v   |
|A/AAAA   |Edgeserver-FQDN  <br/>*Cons-1. <span> </span>Contoso<span></span>. com*  |Interne Server-IP für einen Server im Edgepool  <br/> 172.25.33.10   |Erstellen Sie einen Eintrag für jeden Server im Pool, wobei der FQDN des Servers auf seine interne Serverknoten-IP im Pool verweist, siehe [DNS-Lastenausgleich in Edgeserver Pools](load-balancing.md#BK_Edge).   |v   |
|A/AAAA   |FQDN des Zugriffs-Edgedienst Pools  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Externe IP-Adressen Zugriffs-Edgedienst Pools  <br/> 131.107.16.10, 131.107.16.11   |Das Zugriffs-Edgedienst stellt einen einzelnen vertrauenswürdigen Verbindungspfad für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.   |v   |
|A/AAAA   |FQDN des Webkonferenz-Edgedienst Pools  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Webkonferenz-Edgedienst externe IP-Adressen  <br/> 131.107.16.90, 131.107.16.91   |Mit dem Webkonferenz-Edgedienst können externe Benutzer an Besprechungen teilnehmen, die in ihrer internen Skype for Business Server Umgebung gehostet werden.   |v   |
|A/AAAA   |*AV.\<SIP-Domäne\> * Pool-FQDN <br/>*AV1. <span> </span>Contoso<span></span>. com*  |A/V-Edge-externe IP-Adressen  <br/> 131.107.16.170, 131.107.16.171   |In der A/V-Edgedienst werden Audio-, Video-, Anwendungsfreigabe und Dateiübertragung für externe Benutzer verfügbar gemacht.   |v   |
|CNAME   |SIP. * \<sipdomain "\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |FQDN des externen Zugriffs-Edge-Pools  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Sucht den Edgeserver Pool. Siehe [Exemplarische Vorgehensweise von Skype for Business Clients zum Auffinden von Diensten](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_SIP. \_TLS. * \<sipdomain "\> * <br/>\_SIP. \_TLS. <span> </span> *contoso<span></span>. com*  |Externer FQDN für den Zugriffs-Edgeserver  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Wird für den Zugriff durch externe Benutzer verwendet. Siehe [Exemplarische Vorgehensweise von Skype for Business Clients zum Auffinden von Diensten](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain "\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  |Externer FQDN für den Zugriffs-Edgeserver  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Wird für Verbund-und öffentliche Instant Messaging-Verbindungen verwendet   |&#x2776;  |
|SRV   |\_XMPP-Server. \_TCP. *<sipdomain "\> * <br/>\_XMPP-Server. \_TCP. * <span> </span>Contoso<span></span>. com*  |Externer FQDN für den Zugriffs-Edgeserver  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Der XMPP-Proxy Dienst akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.   |Y, um einen Partnerverbund bereitzustellen, andernfalls optional  <br/> Nicht verfügbar in Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain "\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |Externer FQDN für den Zugriffs-Edgeserver  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Zur Unterstützung von Push Notification Service und Apple Push Notification Service erstellen Sie einen SRV-Eintrag für jede SIP-Domäne. &#x2778;  ||
|A/AAAA   |Externer Front-End-Pool-Webdienste-FQDN  <br/>*Webseite-ext.<span></span>Contoso<span></span>. com*  |Reverse Proxy Public IP Address, Proxies an die externe Webdienste VIP für Ihre Front-End-Pool &#x2776; <br/> 131.107.155.1-Proxy zu 192.168.21.120   |Front-End-Pool von Skype for Business-Webanwendung verwendete externe Schnittstelle   |v   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain "\>* <br/> lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Reverse Proxy öffentliche IP-Adresse, wird in die externe Webdienste VIP für Ihren Directorpool aufgelöst, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben &#x2777; <br/> 131.107.155.1-Proxy zu 192.168.21.120   | Externer Eintrag für die Client AutoErmittlung, der auch von Mobility, Skype for Business-Webanwendung und der Planer-Webanwendung verwendet wird, aufgelöst durch den Reverse-Proxy Server <br/> Zur Unterstützung von Push Notification Service und Apple Push Notification Service erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit Microsoft lync Mobile-Clients. 3   |v   |
|A/AAAA   |erfüllen. * \<sipdomain "\>* <br/> erfüllen. * <span> </span>Contoso<span></span>. com*  |Reverse Proxy Public IP Address, wird in die externe Weboberfläche für die Front-End-Pool aufgelöst  <br/> 131.107.155.1-Proxy zu 192.168.21.120   |Proxy für Skype for Business-Webdienst  <br/> Siehe [einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |Einwahl.*\<sipdomain "\>* <br/> Einwahl.*<span></span><span></span>contoso. com*  |Reverse Proxy Public IP Address, Proxies an die externe Weboberfläche für die Front-End-Pool  <br/> 131.107.155.1-Proxy zu 192.168.21.120   |Proxy für Skype for Business-Webdienst  <br/> Siehe [einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN des Office-webapps-Server Pools  <br/> OWA. <span> </span>Contoso<span></span>. com   | Reverse Proxy Public IP Address, Proxies an die externe Webschnittstelle für den Office-webapps-Server <br/> 131.107.155.1-Proxy zu 192.168.1.5   | VIP-Adresse des Office-webapps-Server Pools <br/> 192.168.1.5   |Definiert den FQDN des Office-webapps-Server Pools   |

Für die Bereitstellung des Verbunds &#x2776; erforderlich, andernfalls optional.

&#x2777; wird von einem Client verwendet, um den Front-End-Server oder Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu sein.

&#x2778; diese Anforderung gilt nur für Clients auf Apple-oder Microsoft-basierten mobilen Geräten. Android-und Nokia Symbian-Geräte verwenden keine Push-Benachrichtigung.

 Weitere Informationen zu Edgeserver und Umkreisnetzwerken finden Sie unter Edgeserver [-DNS-Planungs](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) Inhalte.

> [!IMPORTANT]
> Skype for Business Server unterstützt die Verwendung der IPv6-Adressierung. Weitere Informationen finden Sie unter [Plan for IPv6 in Skype for Business](ipv6.md) .

> [!IMPORTANT]
> Weitere Details zu FQDNs finden Sie unter [DNS Basics](basics.md).

**Geteilte Gehirn DNS** 
 <a name="BK_split"> </a>

Split Brain DNS ist eine DNS-Konfiguration, in der Sie zwei DNS-Zonen mit dem gleichen Namespace haben. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet, wie in diesen Tabellen erwähnt. Weitere Informationen hierzu finden Sie unter [Split-Brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Hybrid Überlegungen
<a name="BK_Hybrid"> </a>

Wenn Sie Vorhaben, einige Benutzer online und einige lokal verwaltet zu haben, lesen Sie den Artikel zur Planung der Hybrid Konnektivität [Skype for Business Server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Sie müssen DNS als normal für Skype for Business Server 2015 konfigurieren und außerdem zusätzliche DNS-Einträge hinzufügen.

Sie sollten sich auch auf "Office 365-URLs und IP-Adressbereiche [https://aka.ms/o365ips](https://aka.ms/o365ips) " berufen, um zu bestätigen, dass Ihre Benutzer Zugriff auf die Online Ressourcen haben, die für Sie benötigt werden.

## <a name="simple-urls"></a>Einfache URLs
<a name="BK_Simple"> </a>

Bei einem Uniform Resource Locator (URL) handelt es sich um einen Verweis auf eine Webressource, die den Speicherort in einem Computernetzwerk angibt, sowie ein Protokoll, das zum Abrufen verwendet wird.

Skype for Business Server unterstützt die Verwendung von drei einfachen URLs für den Zugriff auf Dienste:

- **Meet** wird als Basis-URL für alle Konferenzen auf der Website verwendet. Ein Beispiel für eine einfache Meet-URL ist HTTPS<span></span>//<span></span>: Meet. <span> </span>Contoso<span></span>. com. Eine URL für eine bestimmte Besprechung ist möglicherweise<span></span>//<span></span>https: Meet. <span> </span>Contoso<span></span>. com/_username_/7322994.

    Mit der einfachen URL "Meet" sind Links für die Teilnahme an Besprechungen leicht nachzuvollziehen und einfach zu kommunizieren.

- Die **Einwahl** ermöglicht den Zugriff auf die Webseite mit den Einstellungen für Einwahlkonferenzen. Auf dieser Seite werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (also für Besprechungen, die nicht geplant werden müssen) und DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung der persönlichen Identifikationsnummer ( PIN) und zugewiesene Konferenz Informationen. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die einfache Einwahl-URL ist https://<span></span>dialin. <span> </span>Contoso<span></span>. com.

- Der **Administrator** ermöglicht den schnellen Zugriff auf die Skype for Business Server-Systemsteuerung. Von einem beliebigen Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die Skype for Business Server-Systemsteuerung öffnen, indem er die einfache admin-URL in einen Browser eingibt. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. Ein Beispiel für die einfache admin-URL ist<span></span>https://admin. <span> </span>Contoso<span></span>. com.

Einfache URLs werden unter [DNS-Anforderungen für einfache URLs in Skype for Business Server](simple-urls.md)ausführlicher erläutert.

## <a name="dns-by-server-role"></a>DNS nach Serverrolle
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server wie gewünscht festlegen, Sie jedoch unvergesslich machen und ihre Funktion im System widerspiegeln.

### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese generischen Daten Satz Anforderungen gelten für alle von Skype for Business verwendeten Serverrollen. Bei einem Pool handelt es sich um eine Gruppe von Servern, auf denen dieselben Dienste durchgeführt werden, die zusammenarbeiten, um Clientanforderungen zu verarbeiten, die über einen Lastenausgleich an Sie gerichtet werden Weitere Informationen finden Sie unter [Lastenausgleichsanforderungen für Skype for Business](load-balancing.md) .

**DNS-Eintrags Anforderungen für Server/Pool-Rollen (vermutet DNS-Lastenausgleich)**

|Bereitstellungsszenario|DNS-Anforderung|
|:-----|:-----|
|Ein Server:  <br/> Beständiger Chat, Director, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> ServerRole. <span> </span>Contoso<span></span>. com 10.10.10.0   |
|Pool  <br/> Beständiger Chat, Director, Edgeserver, Vermittlungsserver, Front-End   |Ein interner A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes Server Knotens im Pool in seine IP-Adresse auflöst.  <br/>**Beispiel** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>. com 10.10.10.2  <br/> Mehrere interne A-Datensätze, die den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools in die IP-Adressen der Serverknoten im Pool auflösen.  <br/>**Beispiel** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edgeserver spezifische DNS-Themen

 Überprüfen Sie den [Plan für Edgeserver Bereitstellungen in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)und [Erweiterte Edgeserver DNS-Planung für Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) mit den folgenden Abschnitten, um die Edgeserver-Bereitstellung zu planen:

- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Exemplarische Vorgehensweise von Skype for Business Clients zum Auffinden von Diensten](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


