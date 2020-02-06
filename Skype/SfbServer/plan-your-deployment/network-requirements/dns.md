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
description: 'Zusammenfassung: Überprüfen Sie die DNS-Überlegungen in diesem Thema vor der Implementierung von Skype for Business Server.'
ms.openlocfilehash: 52984c0813fb96c78ff5a1581c0722a691501ccb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802125"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS-Anforderungen für Skype for Business Server

**Zusammenfassung:** Überprüfen Sie die DNS-Überlegungen in diesem Thema vor der Implementierung von Skype for Business Server.

In diesem Artikel wird nur die DNS-Planung für Skype for Business Server-Bereitstellungen im lokalen Netzwerk einer Organisation behandelt. Informationen zu Skype for Business Online finden Sie unter "Office 365-URLs und IP- [https://aka.ms/o365ips](https://aka.ms/o365ips)Adressbereiche".

Ein DNS-Server (Domain Name Service) ordnet Hostnamen (wie www<span> </span> . Contoso<span></span>. com, vermutlich ein Webserver), an IP-Adressen (wie 10.10.10.10). Auf diese Weise können Clients und voneinander abhängige Server im Netzwerk miteinander kommunizieren. Wenn Sie eine Implementierung von Skype for Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung neuer Server Namen (in der Regel die Rolle, die Sie übernehmen werden) den IP-Adressen entspricht, denen Sie zugewiesen sind.

Dies mag zunächst etwas entmutigend erscheinen, aber die schwerwiegende Aufgabe für die Planung kann mit dem [Planning-Tool für Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357)erfolgen. Nachdem Sie die Fragen des Assistenten zu den Features, die Sie verwenden möchten, durchlaufen haben, können Sie für jede von Ihnen definierte Website den DNS-Bericht im Edge-Administrator Bericht anzeigen und die dort aufgelisteten Informationen verwenden, um Ihre DNS-Einträge zu erstellen. Sie können auch Anpassungen an vielen der verwendeten Namen und IP-Adressen vornehmen, um Details finden Sie unter [Überprüfen des DNS-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Beachten Sie, dass Sie den Bericht Edge-Administrator in eine Excel-Tabelle exportieren können, und der DNS-Bericht eines der Arbeitsblätter in der Datei ist. Obwohl dieses Tool Features enthält, die [von Skype for Business Server 2019 veraltet](../../../SfBServer2019/deprecated.md)sind, kann es weiterhin verwendet werden, um einen anfänglichen Plan zu erstellen, wenn diese Features nicht ausgewählt sind.

Wenn Sie eine neue Implementierung installieren, wie unter [Erstellen von DNS-Einträgen für Skype for Business Server und erstellen](../../deploy/install/create-dns-records.md) Ihrer Topologie für Skype for Business Server beschrieben wird, erkennen wir, dass Sie die DNS-Funktionen, die in Windows Server 2016 oder einem Drittanbieter-DNS-Paket integriert sind, verwenden können, damit wir die Diskussionen in diesem Artikel generell und nicht nur in bestimmten Fällen aufbewahren. Wir sind detailliert, was erforderlich ist, und wie Sie diese Anforderung erfüllen, ist Ihre Entscheidung.

Erfahrene Skype for Business-, lync-und Office Communications Suite-Administratoren werden die folgenden Tabellen wahrscheinlich nützlich finden. Wenn die Tabelle für Sie verwirrend ist, werden die folgenden Abschnitte oder Artikel die folgenden Konzepte beleuchten:

## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

In den folgenden Tabellen werden die DNS-Einträge von Skype for Business Server zum Bereitstellen von Diensten für Benutzer angezeigt. Einige sind optional, da Sie nur zur Unterstützung bestimmter Features erforderlich sind, und Sie können übersprungen werden, wenn diese Features nicht erwünscht sind. Die für den internen Zugriff benötigten DNS-Einträge sind nur in der ersten Tabelle vorhanden, und eine Bereitstellung, die internen und externen Zugriff ermöglicht, benötigt Datensätze aus beiden Tabellen.

**Interne DNS-Zuordnungen**

|Eintragstyp|Wert|Auflösung in|Verwendungszweck|Erforderlich|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN des Front-End-Pools  <br/> *FE-Pool. <span> </span>Contoso<span></span>. com*   |IP-Adressen des Front-End-Pool Servers  <br/>  DNS lb to *192.168.21.122 192.168.21.123 192.168.21.124*   |DNS-Lastenausgleich von Front-End-Pools. Ordnet den Namen des Front-End-Pools einer Gruppe von IP-Adressen zu. <br/> Siehe [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir).  |Y   |
|A/AAAA   | FQDN jedes Front-End-Servers oder Standard Edition-Servers in einem Pool oder einem eigenständigen Server <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>Contoso<span></span>. com FE03. <span> </span>Contoso<span></span>. com*   |Entsprechende IP jedes Servers  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Ordnet den Servernamen seiner IP-Adresse zu.   |Y   |
|A/AAAA   |FQDN des Enterprise-Pools für die interne Webdienstüberschreibung  <br/> *Web-int.<span></span>Contoso<span></span>. com*   |HLB VIP für interne Webdienste des Front-End-Servers  <br/> *192.168.21.120*   |Erforderlich zum Aktivieren des Webverkehrs von Client zu Server, beispielsweise zum Herunterladen der Skype for Business-Web-App. Wird auch für mobile Clients benötigt.   |Y   |
|A/AAAA   |FQDN des Enterprise-Pools für die externe Webdienstüberschreibung  <br/> *Web-extern.<span></span>Contoso<span></span>. com*   |HLB VIP für externe Webdienste des Front-End-Servers  <br/>*68.123.56.90*   |Erforderlich zum Aktivieren des Webverkehrs von Client zu Server, beispielsweise zum Herunterladen der Skype for Business-Web-App. Wird benötigt, wenn mobile Clients DNS intern auflösen. Kann in eine IP eines Reverseproxys in der DMZ oder in eine Internet-IP aufgelöst werden.   ||
|A/AAAA   | Back-End-Server-SQL Server-FQDN <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |IP-Adresse des Servers  <br/> *192.168.11.90*   |Ordnet den Servernamen eines Back-End-SQL-Servers, der mit dem Front-End-Pool arbeitet, an dessen IP-Adresse an.   ||
|A/AAAA   |Back-End-Server-Spiegelung des SQL Server-FQDN  <br/> *SQL2. <span> </span>Contoso<span></span>. com*   |IP-Adresse des Servers  <br/> *192.168.11.91*   |Ordnet den Servernamen eines Back-End-SQL-Spiegelservers, der mit dem Front-End-Pool arbeitet, an dessen IP-Adresse an.   ||
|A/AAAA   |FQDN des Director-Pools  <br/>**Hinweis:** Nicht anwendbar bei Verwendung eines Standalone Director-Servers <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |IP-Adressen des Director-Pools  <br/> DNS lb to *192.168.21.132, 192.168.21.133, 192.168.21.134*   |DNS-Lastenausgleich von Director-Pool Servern. Ordnet den Poolnamen des Director-Pools einer IP-Adresse zu, lesen Sie [Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir) . <br/> Ein Director kann einen Benutzer authentifizieren. Der Director ist optional.   ||
|A/AAAA   |Director-FQDN   |Server-IP-Adresse jedes Director-Servers   |Ordnet den Namen des Pools für den Director einer IP-Adresse zu, lesen Sie [Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir) .  ||
|A/AAAA   |FQDN des Mediations Server Pools   |IP-Adressen des Pools   |Die Rolle des Vermittlungsservers ist optional. Sie können diese von einem Vermittlungsserver für den Front-End-Server oder -Pool bereitgestellten Dienste zusammen mit anderen bereitstellen. Siehe [Verwenden des DNS-Lastenausgleichs in Vermittlungs Server Pools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Vermittlungs Server-FQDN   |IP-Adresse des Servers   |Sie können diese von einem Vermittlungsserver für den Front-End-Server oder -Pool bereitgestellten Dienste zusammen mit anderen bereitstellen. Siehe [Verwenden des DNS-Lastenausgleichs in Vermittlungs Server Pools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN des beständigen Chat Servers   |IP-Adresse des beständigen Chat Servers   |Ein Server für beständigen Chat wird für die Funktion „Beständiger Chat“ benötigt. Andernfalls ist er optional.    ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>Contoso<span></span>. com*   |HLB-Front-End-Pool VIP oder Director IP  <br/>  192.168.21.121  |Interner autodiscover Service1, erforderlich für Mobilitätsunterstützung. Wenn für mobile Geräte ein interner DNS aufgelöst wird, sollte es auf die externe IP-Adresse oder die DMZ-VIP-Anwendung verweisen.  <br/> Für Webdienste ist HLB im Front-End-Pool erforderlich, da https DNS nicht nutzen kann. Bei einem Front-End-Pool oder einem Director-Pool sollte dies zu einem HLB-VIP oder einer regulären IP-Adresse für einen Standard Edition-Server oder einen Standalone Director-Server aufgelöst werden.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |FQDN des HLB-Front-End-Pools oder des Directors  <br/> Web-int.<span></span>Contoso<span></span>. com   |Interner Auto Ermittlungs-Service1 <br/> Dies können Sie bei Bedarf als A-Eintrag anstatt als CNAME-Eintrag implementieren.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Server-IP-Adressen des Front-End-Pools (oder die IP-Adresse eines jeden Directors)  <br/>  DNS lb to *192.168.21.122 192.168.21.123 192.168.21.124*   |Erforderlich für die automatische Konfiguration finden Sie unter [Exemplarische Vorgehensweise von Skype for Business-Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Ein Datensatz oder Datensätze, die auf die Front-End-Pool Server oder Director-Server im internen Netzwerk verweisen, oder auf den Access-Edgedienst, wenn der Client extern ist   |&#x2777;  |
|A/AAAA   |ucupdates-r2. * \<sipdomain\>* <br/> ucupdates-r2. * <span> </span>Contoso<span></span>. com*  |VIP des HLB-Front-End-Pools, VIP des HLB-Directorpools oder IP des SE-Servers/Directorservers  <br/>  192.168.21.121  |Die Bereitstellung dieses Eintrags ist optional #a0  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain\> * <br/>Port 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Port 5061  |FQDN des Front-End-Pools  <br/>*FE-Pool. <span> </span>Contoso<span></span>. com*  |Ermöglicht die automatische Anmeldung interner Benutzer1 beim Front-End-Server/-Pool oder SE-Server/-Pool, der Anmeldeanforderungen von Clients authentifiziert und umleitet.    |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>. com*  |FQDN des Front-End-Pools  <br/>_FE-Pool. <span> </span>Contoso<span></span>. com_  |Interner Benutzer Zugriff #a0  |&#x2777;  |
|SRV   | \_NTP. \_UDP. * \<sipdomain\> * <br/> \_NTP. \_UDP. <span> </span> *contoso<span></span>. com*  |FQDN des Zeitservers  <br/> north-america.pool.ntp.org   |NTP-Quelle für lync Phone Edition-Geräte erforderlich   |Dies ist erforderlich, um Desktop-Handsets zu unterstützen.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  | Access Edge Service-FQDN <br/> EdgePool-int.<span></span>*contoso<span></span>. com*  |Erstellen Sie für jede SIP-Domäne, in der sich mobile Clients für iOS oder Windows Phone befinden, einen SRV-Eintrag.   |Für die Unterstützung von mobilen Clients   |
|A/AAAA   |Administrator-URL  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Skype for Business Server-Systemsteuerung, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Besprechungs-URL  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Online Besprechungen, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Einwahl-URL  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Einwahlkonferenzen, siehe [Einfache URLs](dns.md#BK_Simple).  ||
|A/AAAA   |FQDN für interne Webdienste  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Skype for Business-Web-Service, der von Skype for Business Web App verwendet wird   ||
|A/AAAA   |Office Web Apps-Server Pool-FQDN  <br/> OWA. <span> </span>Contoso<span></span>. com   | Office Web Apps-Server Pool-VIP-Adresse <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps-Server Pools   ||
|A/AAAA   |  Interner Web-FQDN <br/> Web-int.<span></span>Contoso<span></span>. com   | VIP-Adresse des Front-End-Pools <br/> 192.168.21.121   |Definiert den internen Web-FQDN, der von Skype for Business Web App verwendet wird.  <br/> Wenn Sie für diesen Pool den DNS-Lastenausgleich verwenden, können die FQDNs des Front-End-Pools und der internen Webfarm nicht identisch sein.   ||

&#x2776; von einem Client verwendet, um den Front-End-Server oder den Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu werden. Weitere Informationen hierzu finden Sie unter [Exemplarische Vorgehensweise von Skype for Business-Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; Dies ist nur erforderlich, um ältere Clients vor lync 2013 und Desktop-Handsets zu unterstützen.

&#x2778; in der Situation, in der ein Unified Communications-Gerät aktiviert ist, sich aber ein Benutzer noch nie beim Gerät angemeldet hat, ermöglicht der a-Eintrag dem Gerät, den Server-Host-Update-Webdienst zu ermitteln und Updates zu erhalten. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.

Das folgende Diagramm zeigt ein Beispiel mit internen und externen DNS-Einträgen sowie vielen der Einträge aus den Tabellen: 

**Diagramm eines Edgenetzwerks, in dem öffentliche IPv4-Adressen verwendet werden**

![Beispiel eines DNS-Netzwerkdiagramms](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**DNS-Zuordnungen für das Umkreisnetzwerk (interne und externe Schnittstellen)**

|Eintragstyp|Wert|Auflösung in|Verwendungszweck|Erforderlich|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN des internen Edge-Pools  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |IP-Adressen für den internen Rand Pool  <br/> 172.25.33.10, 172.25.33.11   |Konsolidierte IP-Adressen der internen Schnittstelle des Edgepools   |Y   |
|A/AAAA   |FQDN des Edge-Servers  <br/>*Nachteile-1. <span> </span>Contoso<span></span>. com*  |Interne IP-Adresse eines Servers im Edge-Pool  <br/> 172.25.33.10   |Erstellen eines Datensatzes für jeden Server im Pool mit dem Server-FQDN, der auf seine interne Serverknoten-IP im Pool zeigt, finden Sie Informationen unter [DNS-Lastenausgleich auf Edgeserver-Pools](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |Access Edge Service Pool-FQDN  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Access Edge Service Pool-externe IP-Adressen  <br/> 131.107.16.10, 131.107.16.11   |Der Access-Edgedienst stellt einen einzelnen vertrauenswürdigen Verbindungspunkt für ausgehende und eingehende SIP-Datenverkehr (Session Initiation Protocol) bereit.   |Y   |
|A/AAAA   |FQDN des Web Conferencing Edge-Service Pools  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Webkonferenz-Edgedienst (externe IP-Adressen)  <br/> 131.107.16.90, 131.107.16.91   |Mit dem Webkonferenz-Edgedienst können externe Benutzer an Besprechungen teilnehmen, die in ihrer internen Skype for Business Server-Umgebung gehostet werden.   |Y   |
|A/AAAA   |*AV.\<SIP-Domäne\> * Pool-FQDN <br/>*AV1. <span> </span>Contoso<span></span>. com*  |Externe IP-Adressen des A/V-Edgeservers  <br/> 131.107.16.170, 131.107.16.171   |Der A/V-Edgedienst ermöglicht externen Benutzern die Bereitstellung von Audio, Video, Anwendungsfreigabe und Dateiübertragung.   |Y   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Externer FQDN des Zugriffs-Edgepools  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Sucht den Edge-Server Pool. Siehe [Exemplarische Vorgehensweise von Skype for Business-Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_TLS. * \<sipdomain\> * <br/>\_SIP. \_TLS. <span> </span> *contoso<span></span>. com*  |FQDN des externen Zugriffs-Edge  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Wird für den Zugriff durch externe Benutzer verwendet. Siehe [Exemplarische Vorgehensweise von Skype for Business-Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  |FQDN des externen Zugriffs-Edge  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Wird für Partnerverbunde und die Verbindung mit öffentlichen Chatdiensten verwendet.   |&#x2776;  |
|SRV   |\_XMPP-Server. \_TCP. *<sipdomain\> * <br/>\_XMPP-Server. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN des externen Zugriffs-Edge  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Der XMPP-Proxy Dienst akzeptiert und sendet Nachrichten zu und von konfigurierten XMPP-Verbundpartnern.   |Zum Bereitstellen von Partnerverbunden ja, andernfalls optional  <br/> In Skype for Business Server 2019 nicht verfügbar.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN des externen Zugriffs-Edge  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Um den Push-Benachrichtigungsdienst und den Apple Push-Benachrichtigungsdienst zu unterstützen, erstellen Sie für jede SIP-Domäne einen SRV-Eintrag. &#x2778;  ||
|A/AAAA   |Externer Front-End-Pool-Webdienste-FQDN  <br/>*Web-extern.<span></span>Contoso<span></span>. com*  |Reverse Proxy Public IP Address, Proxies to the External Web Services VIP für Ihren Front-End-Pool #a0 <br/> 131.107.155.1 Proxy to 192.168.21.120   |Externe Schnittstelle des Front-End-Pools, die von Skype for Business Web App verwendet wird   |Y   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Reverse Proxy Public IP Address, behebt die externen Webdienste VIP für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben #a0 <br/> 131.107.155.1 Proxy to 192.168.21.120   | Externer Eintrag für Client-AutoErmittlung, auch von Mobility, Skype for Business Web App und Scheduler Web App, vom Reverse-Proxy-Server aufgelöst <br/> Um den Push-Benachrichtigungsdienst und den Apple Push-Benachrichtigungsdienst zu unterstützen, erstellen Sie für jede SIP-Domäne mit Microsoft lync Mobile-Clients einen SRV-Eintrag. 3  |Y   |
|A/AAAA   |treffen. * \<sipdomain\>* <br/> treffen. * <span> </span>Contoso<span></span>. com*  |Reverse Proxy Public IP Address, behebt die externe Weboberfläche für den Front-End-Pool  <br/> 131.107.155.1 Proxy to 192.168.21.120   |Proxy für Skype for Business Web Service  <br/> Siehe [Einfache URLs](dns.md#BK_Simple).  |Y   |
|A/AAAA   |Einwahl.*\<sipdomain\>* <br/> Einwahl.*<span></span><span></span>contoso. com*  |Reverse Proxy Public IP Address, Proxies an die externe Weboberfläche für den Front-End-Pool  <br/> 131.107.155.1 Proxy to 192.168.21.120   |Proxy für Skype for Business Web Service  <br/> Siehe [Einfache URLs](dns.md#BK_Simple).  |Y   |
|A/AAAA   |Office Web Apps-Server Pool-FQDN  <br/> OWA. <span> </span>Contoso<span></span>. com   | Reverse Proxy Public IP Address, Proxies to the External Web Interface für den Office Web Apps Server <br/> 131.107.155.1 als Proxy für 192.168.1.5   | Office Web Apps-Server Pool-VIP-Adresse <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps-Server Pools   |

&#x2776; erforderlich, um den Verbund bereitzustellen, andernfalls optional.

&#x2777; von einem Client verwendet, um den Front-End-Server oder den Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu werden.

&#x2778; diese Anforderung gilt nur für Clients auf mobilen Apple-oder Microsoft-basierten Geräten. Android- und Nokia Symbian-Geräte verwenden die Pushbenachrichtigung nicht.

 Weitere Informationen zu Edgeserver und Umkreisnetzwerken finden Sie unter Edge-Server [-DNS-Planning-](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) Inhalt.

> [!IMPORTANT]
> Skype for Business Server unterstützt die Verwendung von IPv6-Adressierung. Weitere Details finden Sie unter [Plan for IPv6 in Skype for Business](ipv6.md).

> [!IMPORTANT]
> Weitere Details zu FQDNs finden Sie unter [DNS basics](basics.md). 

**Brain-DNS-Split** 
 <a name="BK_split"> </a>

Split-Brain-DNS ist eine DNS-Konfiguration, bei der Sie zwei DNS-Zonen mit dem gleichen Namespace verwenden. Wie aus den Tabellen hervorgeht, verarbeitet die erste DNS-Zone interne Anforderungen, während die zweite DNS-Zone für externe Anforderungen zuständig ist. Weitere Informationen hierzu finden Sie unter [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Überlegungen zu Hybridbereitstellungen
<a name="BK_Hybrid"> </a>

Wenn Sie beabsichtigen, einige Benutzer online und teilweise lokal zu verwenden, lesen Sie den Artikel zur Hybriden Verbindungs Planung in [Skype for Business Server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Sie müssen DNS wie gewohnt für Skype for Business Server 2015 konfigurieren und außerdem weitere DNS-Einträge hinzufügen.

Sie sollten auch auf "Office 365-URLs und IP-Adressbereiche" [https://aka.ms/o365ips](https://aka.ms/o365ips) verweisen, um zu bestätigen, dass Ihre Benutzer auf die benötigten Online Ressourcen zugreifen können.

## <a name="simple-urls"></a>Einfache URLs 
<a name="BK_Simple"> </a>

Bei einer URL (Uniform Resource Locator) handelt es sich um einen Verweis auf eine Webressource, der den Speicherort der Ressource in einem Computernetzwerk und das zum Abrufen verwendete Protokoll angibt. 

Skype for Business Server unterstützt die Verwendung von drei "einfachen" URLs für den Zugriff auf Dienste:

- Die **Besprechungs**-URL („meet“) dient als Basis-URL für alle Konferenzen, die am Standort abgehalten werden. Ein Beispiel für eine einfache URL zu erfüllen ist HTTPS<span></span>//<span></span>: Meet. <span> </span>Contoso<span></span>. com. Eine URL für eine bestimmte Besprechung ist möglicherweise<span></span>//<span></span>https: Besprechung. <span> </span>Contoso<span></span>. com/_username_/7322994.

    Mit der einfachen Besprechungs-URL sind Links für die Teilnahme an Besprechungen einfach zu verstehen und leicht zu kommunizieren.

- **Einwahl** ermöglicht den Zugriff auf die Webseite Einstellungen für Einwahlkonferenzen. Auf dieser Seite werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung der persönlichen Identifikationsnummer ( PIN) und zugewiesene Konferenz Informationen. Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können. Ein Beispiel für die einfache URL für Einwahl ist https://<span></span>dialin. <span> </span>Contoso<span></span>. com.

- Der **Administrator** ermöglicht den schnellen Zugriff auf das Skype for Business Server-Control Panel. Von einem beliebigen Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die Skype for Business Server-Systemsteuerung öffnen, indem er die einfache Administrator-URL in einen Browser eingibt. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation. Ein Beispiel für die einfache Administrator-URL ist<span></span>https://-Administrator. <span> </span>Contoso<span></span>. com.

Einfache URLs werden unter [DNS-Anforderungen für einfache URLs in Skype for Business Server](simple-urls.md)ausführlicher erläutert.

## <a name="dns-by-server-role"></a>DNS nach Serverrollen
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server beliebig festlegen. Die Namen sollten aber einprägsam sein und Aufschluss über ihre Funktion im System geben.

### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese generischen Eintrags Anforderungen gelten für alle von Skype for Business verwendeten Serverfunktionen. Bei einem Pool handelt es sich um eine Gruppe von Servern, die die gleichen Dienste ausführen und gemeinsam Clientanforderungen verarbeiten, die über einen Lastenausgleich an sie geleitet werden. Weitere Details finden Sie unter [Load balancing requirements for Skype for Business](load-balancing.md).

**Anforderungen für DNS-Einträge für Server-/Poolrollen (vorausgesetzt, dass DNS-Lastenausgleich verwendet wird)**

|Bereitstellungsszenario|DNS-Anforderung|
|:-----|:-----|
|Ein Server:  <br/> Beständiger Chat, Director, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> ServerRole. <span> </span>Contoso<span></span>. com 10.10.10.0   |
|Pool:  <br/> Beständiger Chat, Director, Edgeserver, Vermittlungsserver, Front-End-Server    |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) jedes Serverknotens im Pool in die zugehörige IP-Adresse aufgelöst wird  <br/>**Beispiel** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>. com 10.10.10.2  <br/> Mehrere interne A-Einträge, mit denen der vollqualifizierte Domänenname (FQDN) des Pools in die IP-Adressen der Serverknoten im Pool aufgelöst wird  <br/>**Beispiel** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edgeserverspezifische DNS-Themen

 Um die Edge-Server-Bereitstellung zu planen, überprüfen Sie den [Plan für Edge-Server-Bereitstellungen in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)und [Advanced Edge Server-DNS-Planung für Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , in dem die folgenden Abschnitte enthalten sind.

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


