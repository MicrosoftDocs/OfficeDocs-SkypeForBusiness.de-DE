---
title: DNS-Anforderungen für Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Zusammenfassung: Überprüfen Sie die DNS-Überlegungen in diesem Thema, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: 7637a1842c9ebc96eee95aa9e4fac6d3db376240
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400259"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS-Anforderungen für Skype for Business Server

**Zusammenfassung:** Überprüfen Sie die DNS-Überlegungen in diesem Thema, bevor Sie Skype for Business Server implementieren.

Dieser Artikel befasst sich nur mit der DNS-Planung für Skype for Business Server Bereitstellungen im lokalen Netzwerk einer Organisation. For Skype for Business Online refer to "Office 365 URLs and IP address ranges" at [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges).

Ein DNS-Server (Domain Name Service) ordnet Hostnamen zu (z. B. www.<span></span> contoso.com<span></span>, vermutlich ein Webserver) an IP-Adressen (z. B. 10.10.10.10). Es hilft Clients und voneinander abhängigen Servern, miteinander im Netzwerk zu kommunizieren. Wenn Sie eine Implementierung von Skype for Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung neuer Servernamen (in der Regel die Rolle, die sie übernehmen) den IP-Adressen entspricht, denen sie zugewiesen sind.

Obwohl dies zunächst etwas entmutigend erscheinen mag, kann dies mit dem [Skype for Business Server 2015-Planungstool](https://www.microsoft.com/download/details.aspx?id=50357) durchgeführt werden. Nachdem Sie die Fragen des Assistenten zu den Features, die Sie verwenden möchten, durchgegangen sind, können Sie für jeden Standort, den Sie definieren, den DNS-Bericht im Edge-Administratorbericht anzeigen und die dort aufgeführten Informationen verwenden, um Ihre DNS-Einträge zu erstellen. Sie können auch anpassungen an vielen der verwendeten Namen und IP-Adressen vornehmen. Ausführliche Informationen finden Sie unter ["Überprüfen des DNS-Berichts"](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Beachten Sie, dass Sie den Edgeadministratorbericht in eine Excel Tabellenkalkulation exportieren können, und der DNS-Bericht ist eines der Arbeitsblätter in der Datei. Obwohl dieses Tool Features enthält, die [ab Skype for Business Server 2019](../../../SfBServer2019/deprecated.md) veraltet sind, kann es weiterhin verwendet werden, um einen ursprünglichen Plan zu erstellen, wenn diese Features nicht ausgewählt sind.

Wenn Sie eine neue Implementierung wie unter [Erstellen von DNS-Einträgen für Skype for Business Server](../../deploy/install/create-dns-records.md) beschrieben installieren und Ihre Topologie für Skype for Business Server erstellen, wissen wir, dass Sie die für Windows Server 2016 integrierten DNS-Funktionen verwenden können.  oder ein DNS-Paket eines Drittanbieters, daher werden wir die Diskussionen in diesem Artikel nicht spezifisch, sondern allgemein behandeln. Wir beschreiben, was erforderlich ist, und wie Sie diese Anforderung erfüllen, ist Ihre Entscheidung.

Erfahrene Skype for Business-, Lync- und Office Communications Suite-Administratoren werden wahrscheinlich die folgenden Tabellen hilfreich finden. Wenn die Tabelle für Sie verwirrend ist, werden in den späteren Abschnitten oder Artikeln die folgenden Konzepte erläutert:

## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

In den folgenden Tabellen sind DNS-Einträge aufgeführt, Skype for Business Server dienste für Benutzer bereitstellen. Einige sind optional, da sie nur zur Unterstützung bestimmter Features benötigt werden, und sie können übersprungen werden, wenn diese Features nicht gewünscht sind. Die dns-Einträge, die nur für den internen Zugriff benötigt werden, befinden sich in der ersten Tabelle, und eine Bereitstellung, die internen und externen Zugriff ermöglicht, benötigt Einträge aus beiden Tabellen.

**Interne DNS-Zuordnungen**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Front-End-Pool-FQDN  <br/> *FE-Pool.<span></span> contoso.com <span></span>*   |IP-Adressen des Front-End-Pools  <br/>  DNS LB bis *192.168.21.122 192.168.21.123 192.168.21.124*   |DNS-Lastenausgleich für Front-End-Pools. Karten den Namen des Front-End-Pools an eine Reihe von IP-Adressen an.  <br/> Siehe [Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN jedes Front-End-Servers oder Standard Edition-Servers in einem Pool oder eines eigenständigen Servers <br/>  *FE01.<span></span> Contoso.<span></span> com FE02.<span></span> contoso.com <span></span> FE03.<span></span> contoso.com <span></span>*   |Entsprechende IP der einzelnen Server  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Karten den Servernamen an seine IP-Adresse an.   |J   |
|A/AAAA   |Enterprise Internen Webdienste des Pools überschreiben FQDN  <br/> *Web-int.<span></span> contoso.com <span></span>*   |HLB-VIP für interne Webdienste des Front-End-Servers  <br/> *192.168.21.120*   |Erforderlich, um Webdatenverkehr zwischen Clients und Servern zu aktivieren, z. B. das Herunterladen der Skype for Business-Web-App. Auch für Mobile-Clients erforderlich.   |J   |
|A/AAAA   |Enterprise Externe Webdienste des Pools überschreiben den FQDN  <br/> *Web-ext.<span></span> contoso.com <span></span>*   |HLB-VIP für externe Webdienste des Front-End-Servers  <br/>*68.123.56.90*   |Erforderlich, um Webdatenverkehr zwischen Clients und Servern zu aktivieren, z. B. das Herunterladen der Skype for Business-Web-App. Erforderlich, wenn mobile Clients DNS intern auflösen. Kann in DMZ Reverseproxy-IP oder Internet-IP aufgelöst werden.   ||
|A/AAAA   | Back-End-Server SQL Server-FQDN <br/> *SQL1.<span></span> contoso.com <span></span>*   |Server-IP-Adresse  <br/> *192.168.11.90*   |Karten den Servernamen für einen Back-End-SQL-Server, der mit dem Front-End-Pool arbeitet, an seine IP-Adresse an.   ||
|A/AAAA   |Back-End-Serverspiegel SQL Server-FQDN  <br/> *SQL2.<span></span> contoso.com <span></span>*   |Server-IP-Adresse  <br/> *192.168.11.91*   |Karten den Servernamen für einen Back-End-SQL-Spiegelserver, der mit dem Front-End-Pool arbeitet, an seine IP-Adresse an.   ||
|A/AAAA   |Directorpool-FQDN  <br/>**Hinweis:** Nicht anwendbar bei Verwendung eines eigenständigen Directorservers <br/> *DirPool.<span></span> contoso.com <span></span>*   |IP-Adressen des Directorpools  <br/> DNS LB zu *192.168.21.132, 192.168.21.133, 192.168.21.134*   |DNS-Lastenausgleich von Directorpoolservern. Karten den Poolnamen für den Directorpool an eine IP-Adresse an. Weitere Informationen finden Sie unter [Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir). <br/> Ein Director kann einen Benutzer authentifizieren und ist optional.   ||
|A/AAAA   |Director-FQDN   |Server-IP-Adresse der einzelnen Directorserver   |Karten des Poolnamens für den Director an eine IP-Adresse, siehe [Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN des Vermittlungsserverpools   |Pool-IP-Adressen   |Die Rolle "Vermittlungsserver" ist optional. Sie können die von einem Vermittlungsserver bereitgestellten Dienste gemeinsam mit dem Front-End-Server oder -Pool suchen. Siehe ["Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools"](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Vermittlungsserver-FQDN   |Server-IP-Adresse   |Sie können die von einem Vermittlungsserver bereitgestellten Dienste gemeinsam mit dem Front-End-Server oder -Pool suchen. Siehe ["Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools"](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN des Servers für beständigen Chat   |IP-Adresse des Servers für beständigen Chat   |Ein Server für beständigen Chat ist für das Feature für beständigen Chat erforderlich und andernfalls optional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso.com <span></span>*   |VIP oder Director-IP des HLB-Front-End-Pools  <br/>  192.168.21.121  |Interner AutoErmittlungsdienst1, erforderlich für Mobilitätsunterstützung. Wenn das interne DNS für mobile Geräte aufgelöst wird, sollte es auf die externe IP oder DMZ-VIP verweisen.  <br/> Für Webdienste benötigen wir HLB im Front-End-Pool, da HTTPS DNS nicht nutzen kann. Für Front-End-Pools oder Directorpools sollte dies in eine HLB-VIP oder eine normale IP für einen Standard edition-Server oder einen eigenständigen Directorserver aufgelöst werden.   |v   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso.com <span></span>*   |FQDN des HLB-FE-Pools oder Director-FQDN  <br/> Web-int.<span></span> contoso.com<span></span>   |Interner AutoErmittlungsdienst1 <br/> Sie können dies bei Bedarf als CNAME anstelle eines A-Eintrags implementieren.   ||
|A/AAAA   |Sip.*\<sipdomain\>* <br/> Sip. *<span></span>contoso.com <span></span>*  |IP-Adressen des Front-End-Pools (oder für jede Director-IP-Adresse)  <br/>  DNS LB bis *192.168.21.122 192.168.21.123 192.168.21.124*   |Erforderlich für die automatische Konfiguration: [Exemplarische Vorgehensweise für Skype for Business Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Ein Datensatz oder Datensätze, der auf die Front-End-Poolserver oder Director-Server im internen Netzwerk oder den Zugriffs-Edgedienst verweist, wenn der Client extern ist   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span>contoso.com <span></span>*  |HLB FE Pool VIP oder Director Pool HLB VIP oder SE/Director Server IP  <br/>  192.168.21.121  |Die Bereitstellung dieses Datensatzes ist optional &#x2778;  ||
|SRV   |\_sipinternaltls.\_ Tcp.*\<sipdomain\>* <br/>Port 5061 <br/>\_sipinternaltls.\_ Tcp. *<span></span>contoso.com <span></span>* <br/>Port 5061  |Front-End-Pool-FQDN  <br/>*FE-Pool.<span></span> contoso.com <span></span>*  |Aktiviert die automatische Anmeldung des internen Benutzers 1 beim Front-End-Server/-Pool oder SE-Server/-Pool, der Clientanforderungen für die Anmeldung authentifiziert und umleitet.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal.<span></span> *contoso.com <span></span>*  |Front-End-Pool-FQDN  <br/>_FE-Pool.<span></span> contoso.com <span></span>_  |Interner Benutzerzugriff &#x2776;  |&#x2777;  |
|SRV   | \_Ntp.\_ Udp.*\<sipdomain\>* <br/> \_Ntp.\_ Udp.<span></span> *contoso.com <span></span>*  |TimeServer-FQDN  <br/> north-america.pool.ntp.org   |FÜR Lync Telefon Edition-Geräte erforderliche NTP-Quelle   |Dies ist erforderlich, um Desktop-Handsets zu unterstützen.   |
|SRV   |\_sipfederationtls.\_ Tcp.*\<sipdomain\>* <br/>\_sipfederationtls.\_ Tcp.<span></span> *contoso.com <span></span>*  | Zugriffs-Edgedienst-FQDN <br/> EdgePool-int.<span></span> *contoso.com <span></span>*  |Erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit IOS- oder Windows Mobile-Telefonclients.   |Unterstützung mobiler Clients   |
|A/AAAA   |Admin-URL  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype for Business Server Systemsteuerung finden Sie unter ["Einfache URLs"](dns.md#BK_Simple)  ||
|A/AAAA   |Besprechungs-URL  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Onlinebesprechungen, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Einwahl-URL  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Einwahlkonferenzen finden Sie unter ["Einfache URLs"](dns.md#BK_Simple)  ||
|A/AAAA   |Interner Webdienst-FQDN  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype for Business Webdienst, der von Skype for Business-Web-App verwendet wird   ||
|A/AAAA   |FQDN für Office Web Apps-Serverpool  <br/> OWA.<span></span> contoso.com<span></span>   | Office VIP-Adresse des Web Apps-Serverpools <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps-Serverpools   ||
|A/AAAA   | Interner Web-FQDN <br/> Web-int.<span></span> contoso.com<span></span>   | VIP-Adresse des Front-End-Pools <br/> 192.168.21.121   |Definiert den internen Web-FQDN, der von Skype for Business-Web-App  <br/> Wenn Sie den DNS-Lastenausgleich für diesen Pool verwenden, können Ihr Front-End-Pool und ihre interne Webfarm nicht über denselben FQDN verfügen.   ||

&#x2776; von einem Client verwendet, um den Front-End-Server oder Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu werden. Weitere Details hierzu finden Sie in [exemplarischer Vorgehensweise für Skype for Business Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; Dies ist nur erforderlich, um Legacyclients vor Lync 2013 und Desktophandsets zu unterstützen.

&#x2778; In der Situation, dass ein Unified Communications-Gerät aktiviert ist, sich aber noch nie bei dem Gerät angemeldet hat, ermöglicht der A-Eintrag dem Gerät, den Server zu ermitteln, der den Geräteaktualisierungswebdienst hostet, und Updates abzurufen. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.

Das folgende Diagramm zeigt ein Beispiel, das sowohl interne als auch externe DNS-Einträge sowie viele der in den umgebenden Tabellen angezeigten Einträge enthält:

**Edgenetzwerkdiagramm mit öffentlichen IPv4-Adressen**

![Beispiel für ein DNS-Netzwerkdiagramm.](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**DNS-Zuordnungen für Umkreisnetzwerke (interne und externe Schnittstellen)**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |Interner Edgepool-FQDN  <br/>*EdgePool-int.<span></span> contoso.com <span></span>*  |Ip-Adressen des internen Edgepools  <br/> 172.25.33.10, 172.25.33.11   |Konsolidierte IP-Adressen der internen Schnittstelle des Edgepools   |v   |
|A/AAAA   |Edgeserver-FQDN  <br/>*Konstante 1.<span></span> contoso.com <span></span>*  |Interne Server-IP für einen Server im Edgepool  <br/> 172.25.33.10   |Erstellen Sie einen Eintrag für jeden Server im Pool mit dem Server-FQDN, der auf die interne Serverknoten-IP im Pool verweist. Siehe [DNS-Lastenausgleich in Edgeserverpools](load-balancing.md#BK_Edge).   |v   |
|A/AAAA   |FQDN des Zugriffs-Edgedienstpools  <br/>*Access1.<span></span> contoso.com <span></span>*  |Zugreifen auf externe IP-Adressen des Edgedienstpools  <br/> 131.107.16.10, 131.107.16.11   |Der Zugriffs-Edgedienst stellt einen einzelnen vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.   |J   |
|A/AAAA   |Webkonferenz-Edgedienstpool-FQDN  <br/>*Webcon1.<span></span> contoso.com <span></span>*  |Externe IP-Adressen des Webkonferenz-Edgediensts  <br/> 131.107.16.90, 131.107.16.91   |Der Webkonferenz-Edgedienst ermöglicht externen Benutzern die Teilnahme an Besprechungen, die in Ihrer internen Skype for Business Server umgebung gehostet werden.   |J   |
|A/AAAA   |*Av.\<sip-domain\>* Pool-FQDN <br/>*AV1.<span></span> contoso.com <span></span>*  |Externe A/V-Edge-IP-Adressen  <br/> 131.107.16.170, 131.107.16.171   |Der A/V-Edgedienst stellt externen Benutzern Audio, Video, Anwendungsfreigabe und Dateiübertragung zur Verfügung.   |J   |
|CNAME   |Sip.*\<sipdomain\>* <br/> Sip. *<span></span>contoso.com <span></span>*  |Externer Zugriffs-Edgepool-FQDN  <br/>*Access1.<span></span> contoso.com <span></span>*  |Sucht den Edgeserverpool. Weitere Informationen [finden Sie unter Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |J   |
|SRV   |\_Sip.\_ Tls.*\<sipdomain\>* <br/>\_Sip.\_ Tls.<span></span> *contoso.com <span></span>*  |Externer Zugriffs-Edge-FQDN  <br/>_Access1.<span></span> contoso.com <span></span>_  |Wird für den Zugriff durch externe Benutzer verwendet. Weitere Informationen [finden Sie unter Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls.\_ Tcp.*\<sipdomain\>* <br/>\_sipfederationtls.\_ Tcp.<span></span> *contoso.com <span></span>*  |Externer Zugriffs-Edge-FQDN  <br/>*Access1.<span></span> contoso.com <span></span>*  |Wird für Partnerverbund- und Verbindungen mit öffentlichen Chatdiensten verwendet   |&#x2776;  |
|SRV   |\_xmpp-server.\_ Tcp. *<sipdomain\>* <br/>\_xmpp-server.\_ Tcp. *<span></span>contoso.com <span></span>*  |Externer Zugriffs-Edge-FQDN  <br/>*Access1.<span></span> contoso.com <span></span>*  |Der XMPP-Proxydienst akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.   |Y, zum Bereitstellen des Partnerverbunds, andernfalls optional  <br/> In Skype for Business Server 2019 nicht verfügbar.|
|SRV   |\_sipfederationtls.\_ Tcp.*\<sipdomain\>* <br/>\_sipfederationtls.\_ Tcp. *<span></span>contoso.com <span></span>*  |Externer Zugriffs-Edge-FQDN  <br/>*Access1.<span></span> contoso.com <span></span>*  |Um den Pushbenachrichtigungsdienst und den Apple-Pushbenachrichtigungsdienst zu unterstützen, erstellen Sie einen SRV-Eintrag für jede SIP-Domäne. &#x2778;  ||
|A/AAAA   |FQDN für externe Front-End-Poolwebdienste  <br/>*Web-ext.<span></span> contoso.com <span></span>*  |Öffentliche IP-Adresse des Reverseproxys, Proxys an die VIP für externe Webdienste für Ihren Front-End-Pool &#x2776; <br/> 131.107.155.1 proxy to 192.168.21.120   |Von Skype for Business-Web-App verwendete externe Front-End-Poolschnittstelle   |J   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span>contoso.com <span></span>*  |Öffentliche IP-Adresse des Reverseproxys wird in die VIP für externe Webdienste für Ihren Directorpool aufgelöst, sofern vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director &#x2777; <br/> 131.107.155.1 proxy to 192.168.21.120   | Externer Datensatz für die Client-AutoErmittlung, der auch von Mobilitäts-, Skype for Business-Web-App- und Scheduler-Web-App verwendet wird und vom Reverseproxyserver aufgelöst wird <br/> Um den Pushbenachrichtigungsdienst und den Apple-Pushbenachrichtigungsdienst zu unterstützen, erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit Microsoft Lync Mobile-Clients. 3  |J   |
|A/AAAA   |Treffen.*\<sipdomain\>* <br/> Treffen. *<span></span>contoso.com <span></span>*  |Öffentliche IP-Adresse des Reverseproxys wird in die externe Webschnittstelle für den Front-End-Pool aufgelöst.  <br/> 131.107.155.1 proxy to 192.168.21.120   |Proxy an Skype for Business Webdienst  <br/> Siehe [einfache URLs](dns.md#BK_Simple)  |J   |
|A/AAAA   |Einwahl.*\<sipdomain\>* <br/> Einwahl. *<span></span>contoso.com <span></span>*  |Öffentliche IP-Adresse des Reverseproxys, Proxys an die externe Webschnittstelle für den Front-End-Pool  <br/> 131.107.155.1 proxy to 192.168.21.120   |Proxy an Skype for Business Webdienst  <br/> Siehe [einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN für Office Web Apps-Serverpool  <br/> OWA.<span></span> contoso.com<span></span>   | Öffentliche IP-Adresse des Reverseproxys, Proxys an die externe Webschnittstelle für den Office Web Apps-Server <br/> 131.107.155.1 proxy to 192.168.1.5   | Office VIP-Adresse des Web Apps-Serverpools <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps-Serverpools   |

&#x2776; Erforderlich, um den Partnerverbund bereitzustellen, andernfalls optional.

&#x2777; wird von einem Client verwendet, um den Front-End-Server oder Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu sein.

&#x2778; Diese Anforderung gilt nur für Clients auf Apple- oder Microsoft-basierten mobilgeräten. Android- und Nokia Symbian-Geräte verwenden keine Pushbenachrichtigung.

 Weitere Informationen zu Edgeservern und Umkreisnetzwerken finden Sie unter den [DNS-Planungsinhalten](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) des Edgeservers.

> [!IMPORTANT]
> Skype for Business Server unterstützt die Verwendung von IPv6-Adressen. Weitere Informationen finden Sie [unter Plan for IPv6 in Skype for Business](ipv6.md).

> [!IMPORTANT]
> Weitere Informationen zu FQDNs finden Sie unter [DNS-Grundlagen](basics.md).

**Split-Brain-DNS**
 <a name="BK_split"></a>

Split Brain DNS ist eine DNS-Konfiguration, bei der Sie zwei DNS-Zonen mit demselben Namespace haben. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet, wie in diesen Tabellen erwähnt. Weitere Informationen hierzu finden Sie unter [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Überlegungen zur Hybridbereitstellung
<a name="BK_Hybrid"> </a>

Wenn Sie beabsichtigen, einige Benutzer online und einige lokal zu verwalten, lesen Sie den Artikel zur Planung der Hybridkonnektivität [Skype for Business Server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Sie müssen DNS für Skype for Business Server 2015 normal konfigurieren und zusätzliche DNS-Einträge hinzufügen.

Sie sollten sich auch unter "Office 365 URLs und IP-Adressbereiche" [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) informieren, um zu bestätigen, dass Ihre Benutzer Zugriff auf die benötigten Onlineressourcen haben.

## <a name="simple-urls"></a>Einfache URLs
<a name="BK_Simple"> </a>

Ein URL (Uniform Resource Locator) ist ein Verweis auf eine Webressource, die den Speicherort in einem Computernetzwerk und ein Protokoll zum Abrufen angibt.

Skype for Business Server unterstützt die Verwendung von drei "einfachen" URLs für den Zugriff auf Dienste:

- **"Meet** " wird als Basis-URL für alle Konferenzen auf der Website verwendet. Ein Beispiel für eine einfache Besprechungs-URL ist https:<span></span>//<span></span>meet.<span></span> contoso.com<span></span>. Eine URL für eine bestimmte Besprechung kann https:<span></span>//<span></span>meet sein.<span></span> contoso.com <span></span>/_username_/7322994.

    Mit der einfachen URL "Besprechungen" sind Links zur Teilnahme an Besprechungen leicht verständlich und leicht zu kommunizieren.

- **Die Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzen Einstellungen. Auf dieser Seite werden Einwahlnummern für Konferenzen mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in konferenzinternen Konferenzen angezeigt und die Verwaltung der persönlichen Identifikationsnummer (PIN) und der zugewiesenen Konferenzinformationen unterstützt. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die einfache EINwahl-URL ist https://<span></span> Dialin.<span></span> contoso.com<span></span>.

- **Der Administrator** ermöglicht den schnellen Zugriff auf die Skype for Business Server Systemsteuerung. Von jedem Computer in den Firewalls Ihrer Organisation aus kann ein Administrator die Skype for Business Server Systemsteuerung öffnen, indem er die einfache Admin-URL in einen Browser eingibt. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. Ein Beispiel für die einfache Admin-URL ist https://<span></span> admin.<span></span> contoso.com<span></span>.

Einfache URLs werden unter [DNS-Anforderungen für einfache URLs in Skype for Business Server](simple-urls.md) ausführlicher erläutert.

## <a name="dns-by-server-role"></a>DNS nach Serverrolle
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server nach Belieben festlegen, sie jedoch einprägsam machen und ihre Funktion im System widerspiegeln.

### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese allgemeinen Datensatzanforderungen gelten für alle Serverrollen, die von Skype for Business verwendet werden. Ein Pool ist eine Gruppe von Servern, auf denen dieselben Dienste ausgeführt werden, die zusammenarbeiten, um Clientanforderungen zu verarbeiten, die über ein Lastenausgleichsmodul an sie weitergeleitet werden. Weitere Informationen finden Sie unter ["Load balancing requirements for Skype for Business" (Anforderungen für den Lastenausgleich) für Skype for Business](load-balancing.md).

**DNS-Eintragsanforderungen für Server-/Poolrollen (setzt DNS-Lastenausgleich voraus)**

|Bereitstellungsszenario|DNS-Anforderung|
|:-----|:-----|
|Ein Server:  <br/> Beständiger Chat, Director, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> Serverrole.<span></span> contoso.com<span></span> 10.10.10.0   |
|Pool:  <br/> Beständiger Chat, Director, Edgeserver, Vermittlungsserver, Front-End   |Ein interner A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes Serverknotens im Pool in seine IP-Adresse auflöst.  <br/>**Beispiel** <br/> ServerRole01.<span></span> contoso.com<span></span> 10.10.10.1  <br/> ServerRole02.<span></span> contoso.com<span></span> 10.10.10.2  <br/> Mehrere interne A-Einträge, die den vollqualifizierten Domänennamen (FQDN) des Pools in die IP-Adressen der Serverknoten im Pool auflösen.  <br/>**Beispiel** <br/> ServerPool.<span></span> contoso.com<span></span> 10.10.10.1  <br/> ServerPool.<span></span> contoso.com<span></span> 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edgeserverspezifische DNS-Themen

 Informationen zum Planen der Edgeserverbereitstellung finden Sie [unter "Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)" und "[Advanced Edge Server DNS planning for Skype for Business Server 2015"](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) (Planen von Edgeserverbereitstellungen in Skype for Business Server 2015) mit den folgenden Abschnitten.

- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Exemplarische Vorgehensweise für Skype for Business Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)