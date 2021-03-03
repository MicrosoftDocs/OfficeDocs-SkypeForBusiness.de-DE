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
ms.openlocfilehash: 3db3641e5b884ef5bca43222fcf001bd4c5a538a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825275"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS-Anforderungen für Skype for Business Server

**Zusammenfassung:** Überprüfen Sie die DNS-Überlegungen in diesem Thema, bevor Sie Skype for Business Server implementieren.

Dieser Artikel befasst sich nur mit der DNS-Planung für Skype for Business Server-Bereitstellungen im lokalen Netzwerk einer Organisation. Informationen zu Skype for Business Online finden Sie unter "Office 365-URLs und IP-Adressbereiche". [https://aka.ms/o365ips](https://aka.ms/o365ips)

Ein Domain Name Service (DNS)-Server ordnet Hostnamen zu (z. B. www. <span></span> contoso <span></span> .com, vermutlich ein Webserver) an IP-Adressen (z. B. 10.10.10.10). Es hilft Clients und voneinander abhängigen Servern, im Netzwerk miteinander zu kommunizieren. Wenn Sie eine Implementierung von Skype for Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung neuer Servernamen (in der Regel mit der Rolle, die sie übernehmen) den zugewiesenen IP-Adressen entspricht.

Dies mag zunächst ein wenig ungerregend erscheinen, aber die schwere Aufgabe für die Planung kann mithilfe des [Skype for Business Server 2015-Planungstools erledigt werden.](https://www.microsoft.com/download/details.aspx?id=50357) Nachdem Sie die Fragen des Assistenten zu den features durchgegangen sind, die Sie verwenden möchten, können Sie für jede von Ihnen festgelegte Website den DNS-Bericht im Edge-Admin-Bericht anzeigen und die dort aufgeführten Informationen verwenden, um Ihre DNS-Einträge zu erstellen. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen. Weitere Informationen finden Sie unter ["Überprüfen des DNS-Berichts".](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report) Denken Sie daran, dass Sie den Edge-Admin-Bericht in eine Excel-Tabelle exportieren können, und der DNS-Bericht ist eines der Arbeitsblätter in der Datei. Obwohl dieses Tool funktionen enthält, die von [Skype for Business Server 2019](../../../SfBServer2019/deprecated.md)veraltet sind, kann es dennoch verwendet werden, um einen anfänglichen Plan zu erstellen, wenn diese Features nicht ausgewählt sind.

Wenn Sie eine neue Implementierung installieren, wie unter "Erstellen von DNS-Einträgen für [Skype for Business Server"](../../deploy/install/create-dns-records.md) beschrieben, und beim Erstellen Ihrer Topologie für Skype for Business Server erkennen wir, dass Sie die in Windows Server 2016 oder einem Drittanbieter-DNS-Paket integrierten DNS-Funktionen verwenden können. Daher werden die Diskussionen in diesem Artikel nicht spezifisch, sondern allgemein behandelt. We're detailing what's needed, and how you meet that need is your decision to make.

Erfahrene Skype for Business-, Lync- und Office Communications Suite-Administratoren finden die folgenden Tabellen wahrscheinlich hilfreich. Wenn die Tabelle für Sie verwirrend ist, werden in den späteren Abschnitten oder Artikeln die folgenden Konzepte erläutert:

## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

In den folgenden Tabellen sind die DNS-Einträge dargestellt, die Skype for Business Server zum Bereitstellen von Diensten für Benutzer verwendet. Einige sind optional, da sie nur zur Unterstützung bestimmter Features benötigt werden, und sie können übersprungen werden, wenn diese Features nicht gewünscht werden. Die dns-Einträge, die nur für den internen Zugriff erforderlich sind, sind in der ersten Tabelle enthalten, und eine Bereitstellung, die internen und externen Zugriff ermöglicht, benötigt Einträge aus beiden Tabellen.

**Interne DNS-Zuordnungen**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN des Front-End-Pools  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |Front-End-Poolserver-IP-Adressen  <br/>  DNS LB bis *192.168.21.122 192.168.21.123 192.168.21.124*   |DNS-Lastenausgleich von Front-End-Pools. Ordnet den Namen des Front-End-Pools einem Satz von IP-Adressen zu.  <br/> Siehe [Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN jedes Front-End-Servers oder Standard Edition-Servers in einem Pool oder eines eigenständigen Servers <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |Entsprechende IP der einzelnen Server  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Ordnet den Servernamen der ip-Adresse zu.   |v   |
|A/AAAA   |Enterprise Pool Internal Web Services Override FQDN  <br/> *Web-Int. <span></span> contoso <span></span> .com*   |HLB-VIP für interne Webdienste des Front-End-Servers  <br/> *192.168.21.120*   |Erforderlich, um Client-zu-Server-Webdatenverkehr zu aktivieren, z. B. das Herunterladen der Skype for Business Web App. Auch für mobile Clients erforderlich.   |v   |
|A/AAAA   |Außerkraftsetzung des FQDN für externe Webdienste für den Unternehmenspool  <br/> *Web ext. <span></span> contoso <span></span> .com*   |HLB-VIP für externe Webdienste des Front-End-Servers  <br/>*68.123.56.90*   |Erforderlich, um Client-zu-Server-Webdatenverkehr zu aktivieren, z. B. das Herunterladen der Skype for Business Web App. Erforderlich, wenn mobile Clients DNS intern auflösen. Kann in die DMZ-Reverseproxy-IP oder Internet-IP aufgelöst werden.   ||
|A/AAAA   | Back-End-Server SQL server-FQDN <br/> *SQL1. <span></span> contoso <span></span> .com*   |Server-IP-Adresse  <br/> *192.168.11.90*   |Ordnet den Servernamen für einen Back-End-SQL, der mit dem Front-End-Pool arbeitet, deren IP-Adresse zu.   ||
|A/AAAA   |Back-End-Serverspiegel SQL Server-FQDN  <br/> *SQL2. <span></span> contoso <span></span> .com*   |Server-IP-Adresse  <br/> *192.168.11.91*   |Ordnet den Servernamen für einen Back-End-SQL, der mit dem Front-End-Pool arbeitet, deren IP-Adresse zu.   ||
|A/AAAA   |FQDN des Directorpools  <br/>**Hinweis:** Bei Verwendung eines eigenständigen Directorservers nicht anwendbar <br/> *DirPool. <span></span> contoso <span></span> .com*   |Directorpool-IP-Adressen  <br/> DNS LB bis *192.168.21.132, 192.168.21.133, 192.168.21.134*   |DNS-Lastenausgleich von Directorpoolservern. Ordnet den Poolnamen für den Directorpool einer IP-Adresse zu. Siehe "Bereitstellen des DNS-Lastenausgleichs für [Front-End-Pools und Directorpools".](load-balancing.md#BK_FE_Dir) <br/> Ein Director kann einen Benutzer authentifizieren und ist optional.   ||
|A/AAAA   |Director-FQDN   |Server-IP-Adresse der einzelnen Directorserver   |Ordnet den Poolnamen für den Director einer IP-Adresse zu. Siehe "Bereitstellen des DNS-Lastenausgleichs [für Front-End-Pools und Directorpools".](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN des Vermittlungsserverpools   |Pool-IP-Adressen   |Die Vermittlungsserverrolle ist optional. Sie können die von einem Vermittlungsserver bereitgestellten Dienste für den Front-End-Server oder -Pool gemeinsam ermitteln. Siehe Verwenden [des DNS-Lastenausgleichs für Vermittlungsserverpools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Vermittlungsserver-FQDN   |Server-IP-Adresse   |Sie können die von einem Vermittlungsserver bereitgestellten Dienste für den Front-End-Server oder -Pool gemeinsam ermitteln. Siehe Verwenden [des DNS-Lastenausgleichs für Vermittlungsserverpools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN des Servers für beständigen Chat   |Server-IP-Adresse für beständigen Chat   |Ein Server für beständigen Chat ist für die Funktion für beständigen Chat erforderlich und ist andernfalls optional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |HLB-Front-End-Pool-VIP oder Director-IP  <br/>  192.168.21.121  |Interner AutoErmittlungsdienst1, erforderlich für Mobilitätsunterstützung. Wenn internes DNS für die Auflösung mobiler Geräte verwendet wird, sollte es auf die externe IP oder DMZ-VIP verweisen.  <br/> Für Webdienste benötigen wir hlB für den Front-End-Pool, da HTTPS DNS nicht nutzen kann. Für Front-End-Pool oder #A0 sollte dies in eine HLB-VIP oder eine normale IP für einen Standard #A1 oder einen eigenständigen #A2 aufgelöst werden.   |v   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |FQDN des HLB-FE-Pools oder Director-FQDN  <br/> Web-Int. <span></span> contoso <span></span> .com   |Interner AutoErmittlungsdienst1 <br/> Sie können dies bei Bedarf als CNAME anstelle eines A-Datensatzes implementieren.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Front-End-Poolserver-IP-Adressen (oder jede Director-IP-Adresse)  <br/>  DNS LB bis *192.168.21.122 192.168.21.123 192.168.21.124*   |Erforderlich für die automatische Konfiguration: Exemplarische Vorgehensweise zum Suchen von Diensten durch [Skype for Business-Clients](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Ein Datensatz, der auf die Front-End-Poolserver oder Directorserver im internen Netzwerk oder auf den Zugriffs-Edgedienst, wenn der Client extern ist, verweisen   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |VIP des HLB-FE-Pools oder Directorpool-HLB-VIP oder SE/Director-Server-IP  <br/>  192.168.21.121  |Die Bereitstellung dieses Eintrags ist optional &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Port 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Port 5061  |FQDN des Front-End-Pools  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Aktiviert die automatische Anmeldung des internen Benutzers 1 beim Front-End-Server/-Pool oder SE-Server/-Pool, der Clientanforderungen für die Anmeldung authentifiziert und umleitiert.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN des Front-End-Pools  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Interne Benutzerzugriffsinformationen &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer-FQDN  <br/> north-america.pool.ntp.org   |Für Lync Phone Edition-Geräte erforderliche NTP-Quelle   |Dies ist erforderlich, um Desktophands zu unterstützen.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN des Zugriffs-Edgediensts <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Erstellen Sie einen SRV-Eintrag für jede SIP-Domäne, die IOS- oder Windows Phone Mobile-Clients hat.   |Unterstützung für mobile Clients   |
|A/AAAA   |Admin-URL  <br/>*Web-Int. <span></span> contoso <span></span> .com*  |VIP des HLB-FE-Pools  <br/> 192.168.21.121   |Skype for Business Server-Systemsteuerung, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Meet-URL  <br/>*Web-Int. <span></span> contoso <span></span> .com*  |VIP des HLB-FE-Pools  <br/> 192.168.21.121   |Onlinebesprechungen, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Einwahl-URL  <br/>*Web-Int. <span></span> contoso <span></span> .com*  |VIP des HLB-FE-Pools  <br/> 192.168.21.121   |Einwahlkonferenzen, siehe [einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Interner Webdienste-FQDN  <br/>*Web-Int. <span></span> contoso <span></span> .com*  |VIP des HLB-FE-Pools  <br/> 192.168.21.121   |Von Skype for Business Web App verwendeter Skype for Business-Webdienst   ||
|A/AAAA   |FQDN des Office Web Apps Server-Pools  <br/> OWA. <span></span> contoso <span></span> .com   | Office Web Apps Server-Pool-VIP-Adresse <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps Server-Pools.   ||
|A/AAAA   | Interner Web-FQDN <br/> Web-Int. <span></span> contoso <span></span> .com   | Front-End-Pool-VIP-Adresse <br/> 192.168.21.121   |Definiert den internen Web-FQDN, der von Skype for Business Web App verwendet wird.  <br/> Wenn Sie für diesen Pool den DNS-Lastenausgleich verwenden, können Der Front-End-Pool und die interne Webfarm nicht denselben FQDN haben.   ||

&#x2776; Wird von einem Client zum Ermitteln des Front-End-Servers oder Front-End-Pools verwendet und als Benutzer authentifiziert und angemeldet. Weitere Informationen dazu finden Sie in [der exemplarischen Vorgehensweise für Skype for Business-Clients, die Dienste suchen.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; Dies ist nur erforderlich, um Legacyclients vor Lync 2013 und Desktophands zu unterstützen.

&#x2778; In dem Fall, dass ein Unified Communications-Gerät aktiviert ist, aber ein Benutzer sich noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag dem Gerät, den Server zu ermitteln, der den Geräteaktualisierungswebdienst hosten, und Updates zu erhalten. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.

Das folgende Diagramm zeigt ein Beispiel, das sowohl interne als auch externe DNS-Einträge sowie viele der in den umgebenden Tabellen angezeigten Einträge enthält:

**Edgenetzwerkdiagramm mit öffentlichen IPv4-Adressen**

![Beispiel für ein DNS-Netzwerkdiagramm](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Umkreisnetzwerk-DNS-Zuordnungen (sowohl interne als auch externe Schnittstellen)**

|Eintragstyp|Value|Auflösung in|Zweck|Erforderlich|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN des internen Edgepools  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Interne Edgepool-IP-Adressen  <br/> 172.25.33.10, 172.25.33.11   |Interne Schnittstellen-IP-Adressen des konsolidierten Edgepools   |v   |
|A/AAAA   |Edgeserver-FQDN  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |Interne Server-IP für einen Server im Edgepool  <br/> 172.25.33.10   |Erstellen Sie einen Eintrag für jeden Server im Pool mit dem Server-FQDN, der auf die interne Serverknoten-IP im Pool verweisen soll. Weitere Informationen finden Sie unter ["DNS Load Balancing" für Edgeserverpools.](load-balancing.md#BK_Edge)   |v   |
|A/AAAA   |FQDN des Zugriffs-Edgedienstpools  <br/>*Access1. <span></span> contoso <span></span> .com*  |Externe IP-Adressen des Zugriffs-Edgedienstpools  <br/> 131.107.16.10, 131.107.16.11   |Der Zugriffs-Edgedienst stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden Sip-Datenverkehr (Session Initiation Protocol) zur Verfügung.   |v   |
|A/AAAA   |FQDN des Webkonferenz-Edgedienst-Pools  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Externe IP-Adressen des Webkonferenz-Edgediensts  <br/> 131.107.16.90, 131.107.16.91   |Der Webkonferenz-Edgedienst ermöglicht externen Benutzern die Teilnahme an Besprechungen, die in Ihrer internen Skype for Business Server-Umgebung gehostet werden.   |v   |
|A/AAAA   |*av.\<sip-domain\>* Pool-FQDN <br/>*AV1. <span></span> contoso <span></span> .com*  |Externe A/V-Edge-IP-Adressen  <br/> 131.107.16.170, 131.107.16.171   |Der A/V-Edgedienst stellt Audio, Video, Anwendungsfreigabe und Dateiübertragung externen Benutzern zur Verfügung.   |v   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN des Edgepools für den externen Zugriff  <br/>*Access1. <span></span> contoso <span></span> .com*  |Sucht den Edgeserverpool. Exemplarische Vorgehensweise zum Suchen von [Diensten durch Skype for Business-Clients](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |Externer Zugriffs-Edge-FQDN  <br/>_Access1. <span></span> contoso <span></span> .com_  |Wird für den Externen Benutzerzugriff verwendet. Exemplarische Vorgehensweise zum Suchen von [Diensten durch Skype for Business-Clients](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |Externer Zugriffs-Edge-FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |Wird für Verbund- und Verbindungen mit öffentlichen Verbindungen verwendet   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |Externer Zugriffs-Edge-FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |Der XMPP-Proxydienst akzeptiert und sendet XMPP (Extensible Messaging and Presence Protocol)-Nachrichten an und von konfigurierten XMPP-Verbundpartnern.   |Y, zum Bereitstellen des Verbunds, andernfalls optional  <br/> Nicht verfügbar in Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |Externer Zugriffs-Edge-FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |Zur Unterstützung des Pushbenachrichtigungsdiensts und des Apple-Pushbenachrichtigungsdiensts erstellen Sie einen SRV-Eintrag für jede SIP-Domäne. &#x2778;  ||
|A/AAAA   |FQDN der Webdienste für externe Front-End-Pools  <br/>*Web ext. <span></span> contoso <span></span> .com*  |Öffentliche Reverseproxy-IP-Adresse, Proxys zur VIP der externen Webdienste für Ihre Front-End-Pool-&#x2776; <br/> 131.107.155.1 Proxy zu 192.168.21.120   |Externe Schnittstelle des Front-End-Pools, die von Skype for Business Web App verwendet wird   |v   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Öffentliche Reverseproxy-IP-Adresse, wird in die VIP der externen Webdienste für den Directorpool aufgelöst, sofern sie einen haben, oder für den Front-End-Pool, wenn Sie nicht über einen Director &#x2777; <br/> 131.107.155.1 Proxy zu 192.168.21.120   | Externer Eintrag für die Client-AutoErmittlung, der auch von Mobility, Skype for Business Web App und der Planer-Web-App verwendet wird und vom Reverseproxyserver aufgelöst wird <br/> Zur Unterstützung des Pushbenachrichtigungsdiensts und des Apple-Pushbenachrichtigungsdiensts erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit Microsoft Lync Mobile-Clients. 3   |v   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Öffentliche Reverseproxy-IP-Adresse, wird in die externe Webschnittstelle für den Front-End-Pool aufgelöst  <br/> 131.107.155.1 Proxy zu 192.168.21.120   |Proxy für Skype for Business Web Service  <br/> Siehe [einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |einwählen.*\<sipdomain\>* <br/> einwählen. *<span></span> contoso <span></span> .com*  |Öffentliche Reverseproxy-IP-Adresse, Proxys an die externe Webschnittstelle für den Front-End-Pool  <br/> 131.107.155.1 Proxy zu 192.168.21.120   |Proxy für Skype for Business Web Service  <br/> Siehe [einfache URLs](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN des Office Web Apps Server-Pools  <br/> OWA. <span></span> contoso <span></span> .com   | Öffentliche Reverseproxy-IP-Adresse, Proxys an die externe Webschnittstelle für den Office Web Apps Server <br/> 131.107.155.1 Proxy zu 192.168.1.5   | Office Web Apps Server-Pool-VIP-Adresse <br/> 192.168.1.5   |Definiert den FQDN des Office Web Apps Server-Pools.   |

&#x2776; Erforderlich zum Bereitstellen des Verbunds, andernfalls optional.

&#x2777; Wird von einem Client zum Ermitteln des Front-End-Servers oder Front-End-Pools verwendet und als Benutzer authentifiziert und angemeldet.

&#x2778; Diese Anforderung gilt nur für Clients auf Apple- oder Microsoft-basierten mobilen Geräten. Android- und Nokia Symbian-Geräte verwenden keine Pushbenachrichtigung.

 Weitere Informationen zu Edgeservern und Umkreisnetzwerken finden Sie im [Edgeserver-DNS-Planungsinhalt.](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)

> [!IMPORTANT]
> Skype for Business Server unterstützt die Verwendung von IPv6-Adressierung. Weitere [Informationen finden Sie unter "Planen von IPv6 in Skype for Business".](ipv6.md)

> [!IMPORTANT]
> Weitere Informationen zu FQDNs finden Sie in den [DNS-Grundlagen.](basics.md)

**Split-Brain-DNS** 
 <a name="BK_split"></a>

Split -Brain-DNS ist eine DNS-Konfiguration, in der Sie zwei DNS-Zonen mit demselben Namespace haben. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet, wie in diesen Tabellen erwähnt. Weitere Informationen dazu finden Sie unter [Split-Brain-DNS.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

## <a name="hybrid-considerations"></a>Überlegungen zur Hybridbereitstellung
<a name="BK_Hybrid"> </a>

Wenn Sie planen, einige Benutzer online und einige lokal zu be homen, lesen Sie den Artikel zur Planung der Hybridkonnektivität [in Skype for Business Server 2019.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) Sie müssen DNS wie gewohnt für Skype for Business Server 2015 konfigurieren und zusätzliche DNS-Einträge hinzufügen.

Sie sollten sich auch unter "Office 365-URLs und -IP-Adressbereiche" vergewissern, dass Ihre Benutzer Zugriff auf die benötigten [https://aka.ms/o365ips](https://aka.ms/o365ips) Onlineressourcen haben.

## <a name="simple-urls"></a>Einfache URLs
<a name="BK_Simple"> </a>

Eine URL (Uniform Resource Locator) ist ein Verweis auf eine Webressource, die ihren Speicherort in einem Computernetzwerk und ein Protokoll zum Abrufen angibt.

Skype for Business Server unterstützt die Verwendung von drei "einfachen" URLs für den Zugriff auf Dienste:

- **"Meet"** wird als Basis-URL für alle Konferenzen am Standort verwendet. Ein Beispiel für eine einfache MEET-URL ist "https: <span></span> // <span></span> meet". <span></span> contoso <span></span> .com. Eine URL für eine bestimmte Besprechung kann https: <span></span> // <span></span> meet sein. <span></span> contoso <span></span> .com/_username_/7322994.

    Mit der einfachen URL "Meet" sind Links zur Teilnahme an Besprechungen leicht verständlich und einfach zu kommunizieren.

- **Die Einwahl ermöglicht** den Zugriff auf die Webseite mit den Einstellungen für Einwahlkonferenzen. Auf dieser Seite werden Einwahlnummern für Konferenzen mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und In-Conference-DTMF-Steuerelementen angezeigt und die Verwaltung der persönlichen Identifikationsnummer (PIN) und zugewiesener Konferenzinformationen unterstützt. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die einfache URL für die Einwahl ist https:// <span></span> Einwahl. <span></span> contoso <span></span> .com.

- **Der** Administrator ermöglicht den schnellen Zugriff auf die Skype for Business Server-Systemsteuerung. Auf jedem Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die Skype for Business Server-Systemsteuerung öffnen, indem er die einfache ADMIN-URL in einen Browser eintippt. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. Ein Beispiel für die einfache Admin-URL ist https:// <span></span> Administrator. <span></span> contoso <span></span> .com.

Einfache URLs werden in den DNS-Anforderungen für [einfache URLs in Skype for Business Server ausführlicher behandelt.](simple-urls.md)

## <a name="dns-by-server-role"></a>DNS nach Serverrolle
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server wie gewünscht festlegen, sie jedoch einprägsam machen und deren Funktion im System widerspiegeln.

### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese allgemeinen Datensatzanforderungen gelten für alle Serverrolle, die von Skype for Business verwendet wird. Ein Pool ist eine Gruppe von Servern, auf denen die gleichen Dienste ausgeführt werden, die zusammenarbeiten, um Clientanforderungen zu verarbeiten, die über einen Lastenausgleich an sie gerichtet werden. Weitere [Informationen finden Sie unter lastenausgleichsanforderungen](load-balancing.md) für Skype for Business

**Anforderungen an den DNS-Eintrag für Server-/Poolrollen (es wird davon ausgegangen, dass der DNS-Lastenausgleich verwendet wird)**

|Bereitstellungsszenario|DNS-Anforderung|
|:-----|:-----|
|Ein Server:  <br/> Beständiger Chat, Director, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Pool:  <br/> Beständiger Chat, Director, Edgeserver, Vermittlungsserver, Front-End   |Ein interner A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes Serverknotens im Pool in seine IP-Adresse aufhebt.  <br/>**Beispiel** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Mehrere interne A-Einträge, die den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools in die IP-Adressen der Serverknoten im Pool auflösen.  <br/>**Beispiel** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Spezielle Edgeserver-DNS-Themen

 Informationen zum Planen der Edgeserverbereitstellung finden Sie unter ["Plan for Edge Server deployments in Skype for Business Server 2015"](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)und ["Advanced Edge Server DNS planning for Skype for Business Server 2015",](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) die die folgenden Abschnitte enthalten.

- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Exemplarische Vorgehensweise zum Suchen von Diensten durch Skype for Business-Clients](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


