---
title: DNS-Anforderungen für Skype for Business Server
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Zusammenfassung: Überprüfen Sie die DNS-Überlegungen in diesem Thema, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: ee69019df0c137fa4cd64260bd804769747ff2a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096239"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS-Anforderungen für Skype for Business Server

**Zusammenfassung:** Überprüfen Sie die DNS-Überlegungen in diesem Thema, bevor Sie Skype for Business Server implementieren.

In diesem Artikel wird nur die DNS-Planung für Skype for Business Server-Bereitstellungen im lokalen Netzwerk einer Organisation behandelt. Informationen zu Skype for Business Online finden Sie unter "Office 365-URLs und IP-Adressbereiche". [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges)

Ein Dns-Server (Domain Name Service) ordnet Hostnamen zu (z. B. www. <span></span> contoso <span></span> .com, vermutlich ein Webserver) an IP-Adressen (z. B. 10.10.10.10). Es hilft Clients und voneinander abhängigen Servern, im Netzwerk miteinander zu kommunizieren. Wenn Sie eine Implementierung von Skype for Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung neuer Servernamen (in der Regel mit der Rolle, die sie übernehmen) den zugewiesenen IP-Adressen entspricht.

Dies mag zunächst etwas bedenklich erscheinen, dies kann jedoch mithilfe des [Skype for Business Server 2015-Planungstools](https://www.microsoft.com/download/details.aspx?id=50357)geplant werden. Nachdem Sie die Fragen des Assistenten zu den features durchgegangen haben, die Sie verwenden möchten, können Sie für jeden von Ihnen definierten Standort den DNS-Bericht im Edge-Admin-Bericht anzeigen und die dort aufgeführten Informationen verwenden, um Ihre DNS-Einträge zu erstellen. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen. Weitere Informationen finden Sie [unter Überprüfen des DNS-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Beachten Sie, dass Sie den Edgeadministratorbericht in eine Excel-Tabelle exportieren können, und der DNS-Bericht ist eines der Arbeitsblätter in der Datei. Obwohl dieses Tool funktionen enthält, die von [Skype for Business Server 2019](../../../SfBServer2019/deprecated.md)veraltet sind, kann es dennoch verwendet werden, um einen anfänglichen Plan zu erstellen, wenn diese Features nicht ausgewählt sind.

Wenn Sie eine neue Implementierung installieren, wie unter Erstellen von DNS-Einträgen für [Skype for Business Server](../../deploy/install/create-dns-records.md) und Erstellen Ihrer Topologie für Skype for Business Server beschrieben, erkennen wir, dass Sie die in Windows Server 2016 oder einem Drittanbieter-DNS-Paket integrierten DNS-Funktionen verwenden können, sodass wir die Diskussionen in diesem Artikel nicht spezifisch, sondern allgemein halten können. Wir erläutern, was erforderlich ist, und wie Sie diese Notwendigkeit erfüllen, ist Ihre Entscheidung.

Erfahrene Skype for Business-, Lync- und Office Communications Suite-Administratoren finden wahrscheinlich die folgenden Tabellen nützlich. Wenn die Tabelle für Sie verwirrend ist, werden in den späteren Abschnitten oder Artikeln die folgenden Konzepte erläutert:

## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

Die folgenden Tabellen zeigen DNS-Einträge, die Skype for Business Server zum Bereitstellen von Diensten für Benutzer verwendet. Einige sind optional, da sie nur zur Unterstützung bestimmter Features benötigt werden, und sie können übersprungen werden, wenn diese Features nicht gewünscht werden. Die nur für den internen Zugriff erforderlichen DNS-Einträge befinden sich in der ersten Tabelle, und eine Bereitstellung, die internen und externen Zugriff ermöglicht, benötigt Datensätze aus beiden Tabellen.

**Interne DNS-Zuordnungen**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN des Front-End-Pools  <br/> *FE-Pool. <span></span> contoso <span></span> .com*   |Front-End-Poolserver-IP-Adressen  <br/>  DNS LB bis *192.168.21.122 192.168.21.123 192.168.21.124*   |DNS-Lastenausgleich von Front-End-Pools. Ordnet den Namen des Front-End-Pools einer Reihe von IP-Adressen zu.  <br/> Weitere [Informationen finden Sie unter Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN jedes Front-End-Servers oder Standard Edition-Servers in einem Pool oder eines eigenständigen Servers <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |Entsprechende IP der einzelnen Server  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Ordnet den Servernamen seiner IP-Adresse zu.   |v   |
|A/AAAA   |Unternehmenspool Interne Webdienste überschreiben FQDN  <br/> *Web-int. <span></span> contoso <span></span> .com*   |#A0 für interne Webdienste des Front-End-Servers  <br/> *192.168.21.120*   |Erforderlich, um client to server web traffic zu aktivieren, z. B. das Herunterladen der Skype for Business Web App. Auch für Mobile-Clients erforderlich.   |v   |
|A/AAAA   |Außerkraftsetzung des FQDN für externe Webdienste im Unternehmenspool  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |#A0 für externe Webdienste des Front-End-Servers  <br/>*68.123.56.90*   |Erforderlich, um client to server web traffic zu aktivieren, z. B. das Herunterladen der Skype for Business Web App. Erforderlich, wenn mobile Clients DNS intern auflösen. Kann in DMZ Reverse Proxy IP oder Internet IP aufgelöst werden.   ||
|A/AAAA   | Back-End-Server SQL FQDN <br/> *SQL1. <span></span> contoso <span></span> .com*   |Server-IP-Adresse  <br/> *192.168.11.90*   |Ordnet den Servernamen für einen Back-End-SQL, der mit dem Front-End-Pool arbeitet, seiner IP-Adresse zu.   ||
|A/AAAA   |Back-End-Serverspiegelung SQL FQDN des Servers  <br/> *SQL2. <span></span> contoso <span></span> .com*   |Server-IP-Adresse  <br/> *192.168.11.91*   |Ordnet den Servernamen für einen Back-End-SQL Spiegelserver, der mit dem Front-End-Pool arbeitet, seiner IP-Adresse zu.   ||
|A/AAAA   |FQDN des Directorpools  <br/>**Hinweis:** Bei Verwendung eines eigenständigen Director-Servers nicht anwendbar <br/> *DirPool. <span></span> contoso <span></span> .com*   |Directorpool-IP-Adressen  <br/> DNS LB bis *192.168.21.132, 192.168.21.133, 192.168.21.134*   |DNS-Lastenausgleich von Director Pool-Servern. Ordnet den Poolnamen für den Directorpool einer IP-Adresse zu, siehe [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir) <br/> Ein Director kann einen Benutzer authentifizieren und ist optional.   ||
|A/AAAA   |Director FQDN   |Server-IP-Adresse der einzelnen Directorserver   |Ordnet den Poolnamen für den Director einer IP-Adresse zu, siehe [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN des Vermittlungsserverpools   |Pool-IP-Adressen   |Die Vermittlungsserverrolle ist optional. Sie können die von einem Vermittlungsserver bereitgestellten Dienste gemeinsam mit dem Front-End-Server oder -Pool suchen. Weitere [Informationen finden Sie unter Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN des Vermittlungsservers   |Server-IP-Adresse   |Sie können die von einem Vermittlungsserver bereitgestellten Dienste gemeinsam mit dem Front-End-Server oder -Pool suchen. Weitere [Informationen finden Sie unter Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN des Servers für beständigen Chat   |Server-IP-Adresse für beständigen Chat   |Ein Server für beständigen Chat ist für das Feature für beständigen Chat erforderlich und ist andernfalls optional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |HLB-Front-End-Pool-VIP oder Director-IP  <br/>  192.168.21.121  |Interner AutoErmittlungsdienst1, erforderlich für die Mobilitätsunterstützung. Wenn internes DNS zum Auflösen für mobile Geräte verwendet wird, sollte es auf die externe IP oder DMZ-VIP verweisen.  <br/> Für Webdienste benötigen wir HLB im Front-End-Pool, da HTTPS DNS nicht nutzen kann. Für Front-End-Pool oder Directorpool sollte dies in eine HLB-VIP oder eine reguläre IP für einen Standard#A0 oder einen eigenständigen #A1 aufgelöst werden.   |v   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |#A0 oder Director-FQDN  <br/> Web-int. <span></span> contoso <span></span> .com   |Interner AutoErmittlungsdienst1 <br/> Sie können dies bei Bedarf als CNAME anstelle eines A-Datensatzes implementieren.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Front-End-Poolserver-IP-Adressen (oder an jede Director-IP-Adresse)  <br/>  DNS LB bis *192.168.21.122 192.168.21.123 192.168.21.124*   |Für die automatische Konfiguration erforderliche Informationen finden Sie unter [Walkthrough of Skype for Business clients locating services.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Ein Datensatz oder Datensätze, der auf die Front-End-Poolserver oder Directorserver im internen Netzwerk oder auf den Access Edge-Dienst zu verweisen, wenn der Client extern ist   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |HLB FE Pool VIP oder Director Pool HLB VIP oder SE/Director Server IP  <br/>  192.168.21.121  |Die Bereitstellung dieses Datensatzes ist optional &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Port 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Port 5061  |FQDN des Front-End-Pools  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Aktiviert die automatische Anmeldung des internen Benutzers 1 beim Front-End-Server/-Pool oder SE-Server/-Pool, der Clientanforderungen für die Anmeldung authentifiziert und umleitt.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN des Front-End-Pools  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Interne Benutzerzugriffsinformationen &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer-FQDN  <br/> north-america.pool.ntp.org   |NTP-Quelle für Lync Phone Edition-Geräte erforderlich   |Dies ist erforderlich, um Desktophandsprecher zu unterstützen.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN des Zugriffs-Edgediensts <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit IOS- oder Windows Phone Mobile-Clients.   |Support für mobile Clients   |
|A/AAAA   |Admin-URL  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype for Business Server-Systemsteuerung, siehe [Einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |meet-URL  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Onlinebesprechungen finden Sie unter [Einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Einwahl-URL  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Einwahlkonferenzen finden Sie unter [Einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN für interne Webdienste  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Von Skype for Business Web App verwendeter Skype for Business-Webdienst   ||
|A/AAAA   |FQDN des Office Web Apps Server-Pools  <br/> OWA. <span></span> contoso <span></span> .com   | Office Web Apps Server Pool-VIP-Adresse <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps Server-Pools   ||
|A/AAAA   | Interner Web-FQDN <br/> Web-int. <span></span> contoso <span></span> .com   | Front-End-Pool-VIP-Adresse <br/> 192.168.21.121   |Definiert den internen Web-FQDN, der von Skype for Business Web App verwendet wird  <br/> Wenn Sie den DNS-Lastenausgleich für diesen Pool verwenden, können Der Front-End-Pool und die interne Webfarm nicht denselben FQDN haben.   ||

&#x2776; Wird von einem Client verwendet, um den Front-End-Server oder den Front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu werden. Weitere Informationen dazu finden Sie unter [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; Dies ist nur erforderlich, um Ältere Clients vor Lync 2013 und Desktophandsprecher zu unterstützen.

&#x2778; In der Situation, in der ein Unified Communications-Gerät aktiviert ist, sich ein Benutzer jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag dem Gerät, den Server zu ermitteln, der den Device Update-Webdienst hosten, und Updates zu erhalten. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.

Das folgende Diagramm zeigt ein Beispiel, das sowohl interne als auch externe DNS-Einträge sowie viele der in den umgebenden Tabellen angezeigten Einträge enthält:

**Edgenetzwerkdiagramm mit öffentlichen IPv4-Adressen**

![Beispiel für ein DNS-Netzwerkdiagramm](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Umkreisnetzwerk-DNS-Zuordnungen (sowohl interne als auch externe Schnittstellen)**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN des internen Edgepools  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Interne Edgepool-IP-Adressen  <br/> 172.25.33.10, 172.25.33.11   |Interne Schnittstellen-IP-Adressen des konsolidierten Edgepools   |v   |
|A/AAAA   |FQDN des Edgeservers  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |Interne Server-IP für einen Server im Edgepool  <br/> 172.25.33.10   |Erstellen Sie einen Datensatz für jeden Server im Pool mit dem Server-FQDN, der auf die interne Serverknoten-IP im Pool verweisen soll. Weitere Informationen finden Sie unter [DNS Load Balancing on Edge Server Pools](load-balancing.md#BK_Edge).   |v   |
|A/AAAA   |FQDN des Zugriffs-Edgedienstpools  <br/>*Access1. <span></span> contoso <span></span> .com*  |Externe IP-Adressen des Zugriffs-Edgedienstpools  <br/> 131.107.16.10, 131.107.16.11   |Der Access-Edgedienst stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) zur Verfügung.   |v   |
|A/AAAA   |FQDN des Webkonferenz-Edgedienstpools  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Externe IP-Adressen des Webkonferenz-Edgediensts  <br/> 131.107.16.90, 131.107.16.91   |Der Webkonferenz-Edgedienst ermöglicht externen Benutzern die Teilnahme an Besprechungen, die in Ihrer internen Skype for Business Server-Umgebung gehostet werden.   |v   |
|A/AAAA   |*av.\<sip-domain\>* Pool-FQDN <br/>*AV1. <span></span> contoso <span></span> .com*  |Externe A/V-Edge-IP-Adressen  <br/> 131.107.16.170, 131.107.16.171   |Der A/V-Edgedienst stellt Audio, Video, Anwendungsfreigabe und Dateiübertragung für externe Benutzer zur Verfügung.   |v   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN des Externen Zugriffs-Edgepools  <br/>*Access1. <span></span> contoso <span></span> .com*  |Sucht den Edgeserverpool . Weitere [Informationen finden Sie unter Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN des externen Zugriffs-Edge  <br/>_Access1. <span></span> contoso <span></span> .com_  |Wird für den externen Benutzerzugriff verwendet. Weitere [Informationen finden Sie unter Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN des externen Zugriffs-Edge  <br/>*Access1. <span></span> contoso <span></span> .com*  |Wird für verbund- und öffentliche Verbindungen mit öffentlichen Verbindungen verwendet   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN des externen Zugriffs-Edge  <br/>*Access1. <span></span> contoso <span></span> .com*  |Der XMPP-Proxydienst akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.   |Y, zum Bereitstellen des Verbunds, andernfalls optional  <br/> In Skype for Business Server 2019 nicht verfügbar.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN des externen Zugriffs-Edge  <br/>*Access1. <span></span> contoso <span></span> .com*  |Zur Unterstützung des Pushbenachrichtigungsdiensts und des Apple-Pushbenachrichtigungsdiensts erstellen Sie einen SRV-Eintrag für jede SIP-Domäne. &#x2778;  ||
|A/AAAA   |FQDN für externe Front-End-Poolwebdienste  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Reverseproxy öffentliche IP-Adresse, Proxys an die VIP für externe Webdienste für Ihren Front-End-Pool &#x2776; <br/> 131.107.155.1-Proxy zu 192.168.21.120   |Externe Front-End-Poolschnittstelle, die von Skype for Business Web App verwendet wird   |v   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Öffentlichen Reverseproxy-IP-Adresse, wird in die VIP für externe Webdienste für Ihren Directorpool aufgelöst, wenn Sie über eine verfügen, oder für Ihren Front-End-Pool, wenn Sie nicht über einen Director-&#x2777; <br/> 131.107.155.1-Proxy zu 192.168.21.120   | Externer Datensatz für die Client-AutoErmittlung, der auch von Mobility, Skype for Business Web App und scheduler Web App verwendet wird und vom Reverseproxyserver aufgelöst wird <br/> Zur Unterstützung des Pushbenachrichtigungsdiensts und des Apple-Pushbenachrichtigungsdiensts erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit Microsoft Lync Mobile-Clients. 3  |v   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Reverseproxy öffentliche IP-Adresse, wird in die externe Webschnittstelle für den Front-End-Pool aufgelöst  <br/> 131.107.155.1-Proxy zu 192.168.21.120   |Proxy für Skype for Business Web Service  <br/> Siehe [Einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |Einwahl.*\<sipdomain\>* <br/> Einwahl. *<span></span> contoso <span></span> .com*  |Öffentliche IP-Adresse des Reverseproxys, Proxys an die externe Webschnittstelle für den Front-End-Pool  <br/> 131.107.155.1-Proxy zu 192.168.21.120   |Proxy für Skype for Business Web Service  <br/> Siehe [Einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN des Office Web Apps Server-Pools  <br/> OWA. <span></span> contoso <span></span> .com   | Reverseproxy öffentliche IP-Adresse, Proxys an die externe Webschnittstelle für den Office Web Apps Server <br/> 131.107.155.1-Proxy zu 192.168.1.5   | Office Web Apps Server Pool-VIP-Adresse <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps Server-Pools   |

&#x2776; Erforderlich für die Bereitstellung des Verbunds, andernfalls optional.

&#x2777; Wird von einem Client verwendet, um den Front-End-Server oder front-End-Pool zu ermitteln und als Benutzer authentifiziert und angemeldet zu werden.

&#x2778; Diese Anforderung gilt nur für Clients auf Apple- oder Microsoft-basierten mobilen Geräten. Android- und Nokia Symbian-Geräte verwenden keine Pushbenachrichtigung.

 Weitere Informationen zu Edgeservern und Umkreisnetzwerken finden Sie unter [Edgeserver-DNS-Planungsinhalt.](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)

> [!IMPORTANT]
> Skype for Business Server unterstützt die Verwendung der IPv6-Adressierung. Weitere [Informationen finden Sie unter Plan for IPv6 in Skype for Business.](ipv6.md)

> [!IMPORTANT]
> Weitere Informationen zu FQDNs finden Sie unter [DNS basics](basics.md).

**Split Brain DNS** 
 <a name="BK_split"></a>

Split Brain DNS ist eine DNS-Konfiguration, in der Sie zwei DNS-Zonen mit demselben Namespace haben. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet, wie in diesen Tabellen erwähnt. Weitere Informationen dazu finden Sie unter [Split-Brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Hybride Überlegungen
<a name="BK_Hybrid"> </a>

Wenn Sie planen, einige Benutzer online und einige lokal zu homed zu haben, lesen Sie den Artikel Zur Planung von Hybridverbindungen [skype for Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Sie müssen DNS für Skype for Business Server 2015 normal konfigurieren und zusätzliche DNS-Einträge hinzufügen.

Sie sollten sich auch auf "Office 365-URLs und IP-Adressbereiche" unter beziehen, um zu bestätigen, dass Ihre Benutzer Zugriff auf die benötigten [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) Onlineressourcen haben.

## <a name="simple-urls"></a>Einfache URLs
<a name="BK_Simple"> </a>

Ein Uniform Resource Locator (URL) ist ein Verweis auf eine Webressource, die ihren Speicherort in einem Computernetzwerk und ein Protokoll zum Abrufen angibt.

Skype for Business Server unterstützt die Verwendung von drei "einfachen" URLs für den Zugriff auf Dienste:

- **Meet** wird als Basis-URL für alle Konferenzen auf der Website verwendet. Ein Beispiel für eine einfache MEET-URL ist https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. Eine URL für eine bestimmte Besprechung kann https: <span></span> // <span></span> meet sein. <span></span> contoso <span></span> .com/_username_/7322994.

    Mit der einfachen URL "Besprechungen" sind Links zum Teilnehmen an Besprechungen einfach zu verstehen und leicht zu kommunizieren.

- **Die Einwahl** ermöglicht den Zugriff auf die Webseite "Einstellungen für Einwahlkonferenzen". Auf dieser Seite werden Konferenz-Einwahlnummern mit ihren verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und DTMF-Steuerelementen in Konferenzen angezeigt und die Verwaltung der persönlichen Identifikationsnummer (PIN) und der zugewiesenen Konferenzinformationen unterstützt. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die einfache Einwahl-URL ist https:// <span></span> Einwahl. <span></span> contoso <span></span> .com.

- **Der** Administrator ermöglicht den schnellen Zugriff auf die Skype for Business Server-Systemsteuerung. Auf jedem Computer in den Firewalls Ihrer Organisation kann ein Administrator die Skype for Business Server-Systemsteuerung öffnen, indem er die einfache Admin-URL in einen Browser eintippt. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. Ein Beispiel für die einfache Admin-URL ist https:// <span></span> Administrator. <span></span> contoso <span></span> .com.

Einfache URLs werden unter DNS-Anforderungen für einfache [URLs in Skype for Business Server ausführlicher erläutert.](simple-urls.md)

## <a name="dns-by-server-role"></a>DNS nach Serverrolle
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server nach Ihren Wünschen festlegen, sie jedoch einprägsam machen und deren Funktion im System widerspiegeln.

### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese allgemeinen Datensatzanforderungen gelten für alle Serverrolle, die von Skype for Business verwendet wird. Ein Pool ist eine Gruppe von Servern, auf denen dieselben Dienste ausgeführt werden, die zusammenarbeiten, um Clientanforderungen zu verarbeiten, die über einen Lastenausgleich an sie gerichtet werden. Weitere [Informationen finden Sie unter Lastenausgleichsanforderungen](load-balancing.md) für Skype for Business

**DNS-Eintrag Anforderungen für Server-Pool-Rollen (vorausgesetzt dns-Lastenausgleich)**

|Bereitstellungsszenario|DNS-Anforderung|
|:-----|:-----|
|Ein Server:  <br/> Beständigen Chat, Director, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Pool:  <br/> Beständigen Chat, Director, Edgeserver, Vermittlungsserver, Front-End   |Ein interner A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes Serverknotens im Pool in seine IP-Adresse aufräumt.  <br/>**Beispiel** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Mehrere interne A-Datensätze, die den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools in die IP-Adressen der Serverknoten im Pool auflösen.  <br/>**Beispiel** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edgeserverspezifische DNS-Themen

 Informationen zum Planen der Edgeserverbereitstellung finden Sie unter [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)und Advanced Edge Server DNS planning for Skype for Business Server [2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) mit den folgenden Abschnitten.

- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Exemplarische Vorgehensweise der Skype for Business-Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)