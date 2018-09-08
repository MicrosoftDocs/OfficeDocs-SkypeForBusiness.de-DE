---
title: DNS-Anforderungen für Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Zusammenfassung: Überprüfen Sie die DNS-Aspekten in diesem Thema vor der Implementierung von Skype für Business Server.'
ms.openlocfilehash: d7f1cf424b98700eed7b2474e3c06db6d585fb30
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887890"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>DNS-Anforderungen für Skype für Business Server

**Zusammenfassung:** Überprüfen Sie vor der Implementierung von Skype für Business Server die DNS-Aspekten in diesem Thema.

Dieser Artikel behandelt nur DNS-Planung für Skype für Business Server-Bereitstellungen auf die lokale Netzwerk einer Organisation. Skype für Business Online finden Sie in "-Office 365-URLs und IP-Adressbereichen" unter [https://aka.ms/o365ips](https://aka.ms/o365ips).

Ein Server Domain Name Service (DNS) ordnet Hostnamen (wie Www.<span> </span> Contoso<span></span>.com, vermutlich auf einem Webserver) in IP-Adressen (z. B. 10.10.10.10). Auf diese Weise können Clients und voneinander abhängige Server im Netzwerk miteinander kommunizieren. Wenn Sie eine Implementierung von Skype für Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung der neuen Servernamen (in der Regel die Rolle, die sie für ergreifen können spiegeln) die IP-Adressen entspricht, denen sie zugeordnet sind.

Dies mag ein Bit schwierige zunächst, den schwierigsten für die Planung, dies ist möglich, der [Skype für Business Server 2015 Planungstool](https://www.microsoft.com/en-us/download/details.aspx?id=50357)verwenden. Wenn Sie die Fragen des Assistenten zu den Funktionen, die Sie verwenden möchten, beantwortet haben, können Sie für jeden definierten Standort den DNS-Bericht im Edge-Adminbericht anzeigen und die dort aufgelisteten Informationen zum Erstellen Ihrer DNS-Einträge verwenden. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen. Details hierzu finden Sie unter [Überprüfen des DNS-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Berücksichtigen Sie, dass Sie den Edge-Adminbericht in eine Excel-Tabelle exportieren können. Den DNS-Bericht finden Sie auf einem der Arbeitsblätter in der Datei. Während dieses Tool Features [von Skype für Business Server 2019 veraltet umfasst](../../../SfBServer2019/deprecated.md), können sie weiterhin verwendet werden einen Basisplan erstellen, wenn diese Features nicht aktiviert sind

Wenn Sie eine neue Implementierung wie unter [Erstellen von DNS-Einträge für Skype für Business Server](../../deploy/install/create-dns-records.md) installieren und Erstellen von Ihrer Topologie für Skype für Business Server, wir erkannt wird, können Sie zum Verwenden der DNS-Funktionen in Windows Server integriert 2016 oder einem Drittanbieter-DNS-Paket, damit wir die Diskussionen in diesem Artikel allgemeine anstelle von bestimmten halten. Wir beschreiben, was Sie benötigen, und Sie entscheiden, wie Sie diese Anforderungen erfüllen.

Erfahrene Skype für Unternehmen, Lync und Office Communications-Suite-Administratoren wird wahrscheinlich in den folgenden Tabellen hilfreich sein. Falls die Tabelle verwirrend scheint – in den späteren Abschnitten bzw. Artikeln werden die folgenden Konzepte erörtert:

## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

Die folgende Tabelle enthält die DNS-Einträge, dass Skype für Business Server wird verwendet, um die Dienste für Benutzer bereitzustellen. Einige sind optional, da sie nur zur Unterstützung bestimmter Funktionen benötigt werden. Wenn die entsprechenden Funktionen nicht gewünscht werden, können die DNS-Einträge übersprungen werden. Die DNS-Einträge, die nur für den internen Zugriff benötigt werden, befinden sich in der ersten Tabelle. Bei einer Bereitstellung, die internen und externen Zugriff ermöglicht, werden Einträge aus beiden Tabellen benötigt.

**Interne DNS-Zuordnungen**

|Eintragstyp|Wert|Auflösung in|Verwendungszweck|Erforderlich|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Front-End-Pool-FQDN  <br/> *FE-Pool. <span> </span>Contoso<span></span>.com*   |Front-End-Pool Server IP-Adressen  <br/>  DNS-kg zu *192.168.21.122 192.168.21.123 192.168.21.124*   |DNS-Lastenausgleich von Front-End-Pools. Ordnet den Namen des Front-End-Pools einer Gruppe von IP-Adressen zu.  <br/> Siehe [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir).  |Y   |
|A/AAAA   | FQDN des jedem Front-End-Server oder Standard Edition-Server in einem Pool oder einen eigenständigen server <br/>  *"FE01". <span> </span>Contoso. <span> </span>com FE02. <span> </span>Contoso<span></span>.com FE03. <span> </span>Contoso<span></span>.com*   |Entsprechende IP jedes Servers  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Ordnet den Servernamen seiner IP-Adresse zu.   |Y   |
|A/AAAA   |FQDN des Enterprise-Pools für die interne Webdienstüberschreibung  <br/> *Web-int<span></span>Contoso<span></span>.com*   |Hardwaregeräts zum Lastenausgleich_vip für interne Webdienste der Front-End-Server  <br/> *192.168.21.120*   |Zum Aktivieren der Client-zu-Server-Webdatenverkehr, wie die Skype für Business Web App heruntergeladen erforderlich. Wird auch für mobile Clients benötigt.   |Y   |
|A/AAAA   |FQDN des Enterprise-Pools für die externe Webdienstüberschreibung  <br/> *Web-automatischer<span></span>Contoso<span></span>.com*   |Hardwaregeräts zum Lastenausgleich_vip für externe Webdienste der Front-End-Server  <br/>*68.123.56.90*   |Zum Aktivieren der Client-zu-Server-Webdatenverkehr, wie die Skype für Business Web App heruntergeladen erforderlich. Wird benötigt, wenn mobile Clients DNS intern auflösen. Kann in eine IP eines Reverseproxys in der DMZ oder in eine Internet-IP aufgelöst werden.   ||
|A/AAAA   | Back-End-Server-SQL Server-FQDN <br/> *SQL1. <span> </span>Contoso<span></span>.com*   |IP-Adresse des Servers  <br/> *192.168.11.90*   |Ordnet den Servernamen für einen Back-End-SQL-Server arbeiten mit den Front-End-Pool seiner IP-Adresse   ||
|A/AAAA   |Back-End-Server-Spiegelung-SQL-Server-FQDN  <br/> *SQL2. <span> </span>Contoso<span></span>.com*   |IP-Adresse des Servers  <br/> *192.168.11.91*   |Ordnet den Servernamen für einen Back-End-SQL-Spiegelserver arbeiten mit den Front-End-Pool seiner IP-Adresse   ||
|A/AAAA   |Directorpool-FQDN  <br/>**Hinweis:** Nicht zutreffend, wenn Sie einen eigenständigen Director-Server verwenden <br/> *DirPool. <span> </span>Contoso<span></span>.com*   |Director-Pool-IP-Adressen  <br/> DNS-kg *192.168.21.132, 192.168.21.133* , 192.168.21.134   |DNS-Lastenausgleich von Directorpoolservern. Nennen Sie der Pool für den Director-Pool in einer IP-Adresse Maps finden Sie unter [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir) <br/> Ein Director kann einen Benutzer authentifizieren. Der Director ist optional.   ||
|A/AAAA   |Director-FQDN   |Server-IP-Adresse des einzelnen Director-server   |Nennen Sie der Pool für den Director in eine IP-Adresse Maps finden Sie unter [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |Mediation Serverpool-FQDN   |IP-Adressen des Pools   |Die Rolle des Vermittlungsservers ist optional. Sie können diese von einem Vermittlungsserver für den Front-End-Server oder -Pool bereitgestellten Dienste zusammen mit anderen bereitstellen. Finden Sie unter [Verwenden von DNS-Lastenausgleichs in Vermittlungsserverpools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Vermittlungsserver FQDN   |IP-Adresse des Servers   |Sie können diese von einem Vermittlungsserver für den Front-End-Server oder -Pool bereitgestellten Dienste zusammen mit anderen bereitstellen. Finden Sie unter [Verwenden von DNS-Lastenausgleichs in Vermittlungsserverpools](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Persistent Chat-Server-FQDN   |Persistent Chat-Server-IP-Adresse   |Ein Server für beständigen Chat wird für die Funktion „Beständiger Chat“ benötigt. Andernfalls ist er optional.   ||
|A/AAAA   |Lyncdiscoverinternal. * \<Sipdomain\>* <br/> Lyncdiscoverinternal. * <span> </span>Contoso<span></span>.com*   |Hardwaregeräts zum Lastenausgleich Front-End-Pool-VIP oder Director-IP  <br/>  192.168.21.121  |Interne AutoDiscover Service1, für die Unterstützung der Mobilität erforderlich. Wenn interne DNS aufgelöst für mobile Geräte verwendet wird, sollte er auf die externe IP-Adresse oder DMZ VIP-Adresse verweisen.  <br/> Für Webdienste benötigen wir Hardwaregeräts zum Lastenausgleich, auf dem Front-End-Pool wie HTTPS DNS nutzen können. Für Front-End-Pool oder Director-Pool, sollte in die VIP eines Hardwaregeräts zum Lastenausgleich oder eine reguläre IP-Adresse für einen Standard Edition-Server oder einen eigenständigen Director-Server aufgelöst wird.   |Y   |
|CNAME   |Lyncdiscoverinternal. * \<Sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>.com*   |FQDN des HLB-Front-End-Pools oder des Directors  <br/> Web-int<span></span>Contoso<span></span>.com   |Interne AutoErmittlung Service1 <br/> Dies können Sie bei Bedarf als A-Eintrag anstatt als CNAME-Eintrag implementieren.   ||
|A/AAAA   |SIP. * \<Sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>.com*  |Front-End-Pool Server IP-Adressen (oder an einen einzelnen Director-IP-Adresse)  <br/>  DNS-kg zu *192.168.21.122 192.168.21.123 192.168.21.124*   |Damit die automatische Konfiguration erforderlich, finden Sie unter [Exemplarische Vorgehensweise von Skype für Business Clients suchen Dienste](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Datensätze, die auf den Front-End-Pool-Servern oder Director-Server auf dem internen Netzwerk oder Zugriffs-edgediensts verweist, wenn der Client externe ist oder eines Datensatzes   |& #x 2777;  |
|A/AAAA   |UCUpdates-r2. * \<Sipdomain\>* <br/> UCUpdates-r2. * <span> </span>Contoso<span></span>.com*  |VIP des HLB-Front-End-Pools, VIP des HLB-Directorpools oder IP des SE-Servers/Directorservers  <br/>  192.168.21.121  |Die Bereitstellung dieser Eintrag optional ist & #x 2778;  ||
|A/AAAA   |\_Sipinternaltls. \_Tcp. * \<Sipdomain\> * <br/>Port 5061 <br/>\_Sipinternaltls. \_Tcp. * <span> </span>Contoso<span></span>.com* <br/>Port 5061  |Front-End-Pool-FQDN  <br/>*FE-Pool. <span> </span>Contoso<span></span>.com*  |Ermöglicht die automatische Anmeldung interner Benutzer1 beim Front-End-Server/-Pool oder SE-Server/-Pool, der Anmeldeanforderungen von Clients authentifiziert und umleitet.  |& #x 2777; |
|A/AAAA |\_Sipinternal. * \<Sipdomain\>* <br/>\_Sipinternal. <span> </span> *Contoso<span></span>.com*  |Front-End-Pool-FQDN  <br/>_FE-Pool. <span> </span>Contoso<span></span>.com_  |Zugriff durch interne Benutzer & #x 2776;  |& #x 2777;  |
|SRV   | \_NTP. \_Udp. * \<Sipdomain\> * <br/> \_NTP. \_Udp. <span> </span> *Contoso<span></span>.com*  |FQDN des Zeitservers  <br/> North america.pool.ntp.org   |Für Lync Phone Edition-Geräte erforderliche NTP-Quelle   |Dies ist erforderlich, um desktop Telefone zu unterstützen.   |
|SRV   |\_Sipfederationtls. \_Tcp. * \<Sipdomain\> * <br/>\_Sipfederationtls. \_Tcp. <span> </span> *Contoso<span></span>.com*  | Zugriffs-edgedienst FQDN <br/> EdgePool int<span></span>*Contoso<span></span>.com*  |Erstellen Sie für jede SIP-Domäne, in der sich mobile Clients für iOS oder Windows Phone befinden, einen SRV-Eintrag.   |Für die Unterstützung von mobilen Clients   |
|A/AAAA   |Administrator-URL  <br/>*Web-int<span></span>Contoso<span></span>.com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Skype für Business Server-Systemsteuerung finden Sie unter [Einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Besprechungs-URL  <br/>*Web-int<span></span>Contoso<span></span>.com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Onlinebesprechungen, finden Sie unter [Einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |Einwahl-URL  <br/>*Web-int<span></span>Contoso<span></span>.com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Einwahlkonferenzen, finden Sie unter [Einfache URLs](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN für interne Webdienste  <br/>*Web-int<span></span>Contoso<span></span>.com*  |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121   |Skype für Business-Webdienst wird von Skype für Web-Geschäfts-App   ||
|A/AAAA   |Office Web Apps Server Pool-FQDN  <br/> OWA. <span> </span>Contoso<span></span>.com   | Office Web Apps Server-Pool VIP-Adresse <br/> 192.168.1.5   |Definiert den Office Web Apps Server-Pool-FQDN   ||
|A/AAAA   | Interner Web-FQDN <br/> Web-int<span></span>Contoso<span></span>.com   | Front-End-Pool-VIP-Adresse <br/> 192.168.21.121   |Definiert den internen Web-FQDN wird von Skype für Web-Geschäfts-App  <br/> Wenn Sie für diesen Pool den DNS-Lastenausgleich verwenden, können die FQDNs des Front-End-Pools und der internen Webfarm nicht identisch sein.   ||

& #x 2776; Zum Ermitteln des Front-End-Server oder Front-End-Pools und authentifiziert und werden als Benutzer angemeldet verwendet von einem Client. Weitere Details zu diesem befindet sich in [Exemplarische Vorgehensweise von Skype für Clients Business Services suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

& #x 2777; Dies ist nur erforderlich, zur Unterstützung von Clients von Vorversionen vor dem Lync 2013 und desktop Telefone.

& #x 2778; In der Lage, in dem ein Unified Communications-Gerät eingeschaltet wird, aber ein Benutzer nie in das Gerät angemeldet hat kann der A-Eintrag das Gerät Ermitteln der Hostserver geräteaktualisierungswebdienst und Abrufen von Updates. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.

Das folgende Diagramm zeigt ein Beispiel mit internen und externen DNS-Einträgen sowie vielen der Einträge aus den Tabellen:

**Diagramm eines Edgenetzwerks, in dem öffentliche IPv4-Adressen verwendet werden**

![Beispiel eines DNS-Netzwerkdiagramms](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**DNS-Zuordnungen für das Umkreisnetzwerk (interne und externe Schnittstellen)**

|Eintragstyp|Wert|Auflösung in|Verwendungszweck|Erforderlich|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |Interne Edge-Pool-FQDN  <br/>*EdgePool int<span></span>Contoso<span></span>.com*  |Intern verbundenen Edge-Pool-IP-Adressen  <br/> 172.25.33.10, 172.25.33.11   |Konsolidierte IP-Adressen der internen Schnittstelle des Edgepools   |Y   |
|A/AAAA   |FQDN des Edgeservers  <br/>*Nachteile-1. <span> </span>Contoso<span></span>.com*  |Intern verbundenen Server IP für einen Server in der Edge-pool  <br/> 172.25.33.10   |Erstellen Sie einen Eintrag für jeden Server im Pool mit dem FQDN des Servers in seine interne Server Knoten IP-Adresse im Pool Verweisen finden Sie unter [DNS-Lastenausgleich in Edgeserverpools](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |Zugriffs-edgedienst Pool-FQDN  <br/>*Access1. <span> </span>Contoso<span></span>.com*  |Access-Dienst Pool externe IP-Adressen  <br/> 131.107.16.10, 131.107.16.11   |Zugriffs-edgedienst stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden Datenverkehr von Session Initiation Protocol (SIP) bereit.   |Y   |
|A/AAAA   |Webkonferenz-edgedienst Pool-FQDN  <br/>*Webcon1. <span> </span>Contoso<span></span>.com*  |Web Webkonferenz-Edgeserver Service externe IP-Adressen  <br/> 131.107.16.90, 131.107.16.91   |Der Webkonferenz-edgedienst ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die gehostet werden in Ihrer internen Skype für Business Server-Umgebung.   |Y   |
|A/AAAA   |*av.\<Sip-Domäne\> * Pool-FQDN <br/>*AV1. <span> </span>Contoso<span></span>.com*  |Externe IP-Adressen des A/V-Edgeservers  <br/> 131.107.16.170, 131.107.16.171   |Der A / V-edgedienst stellt audio, Video, Anwendungsfreigabe und File transfer für externe Benutzer.   |Y   |
|CNAME   |SIP. * \<Sipdomain\>* <br/> SIP. * <span> </span>Contoso<span></span>.com*  |Externer FQDN des Zugriffs-Edgepools  <br/>*Access1. <span> </span>Contoso<span></span>.com*  |Sucht nach der Edge-Server-Pool. Finden Sie unter [Exemplarische Vorgehensweise von Skype für Clients Business Services suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_Tls. * \<Sipdomain\> * <br/>\_SIP. \_Tls. <span> </span> *Contoso<span></span>.com*  |FQDN der externen Zugriffs-Edgeservers  <br/>_Access1. <span> </span>Contoso<span></span>.com_  |Wird für den Zugriff durch externe Benutzer verwendet. Finden Sie unter [Exemplarische Vorgehensweise von Skype für Clients Business Services suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_Sipfederationtls. \_Tcp. * \<Sipdomain\> * <br/>\_Sipfederationtls. \_Tcp. <span> </span> *Contoso<span></span>.com*  |FQDN der externen Zugriffs-Edgeservers  <br/>*Access1. <span> </span>Contoso<span></span>.com*  |Wird für Partnerverbunde und die Verbindung mit öffentlichen Chatdiensten verwendet.   |& #x 2776;  |
|SRV   |\_XMPP-Server. \_Tcp. *< Sipdomain\> * <br/>\_XMPP-Server. \_Tcp. * <span> </span>Contoso<span></span>.com*  |FQDN der externen Zugriffs-Edgeservers  <br/>*Access1. <span> </span>Contoso<span></span>.com*  |XMPP-Proxydienst akzeptiert und sendet extensible messaging und Anwesenheit Protocol (XMPP) Nachrichten zu und von konfigurierten XMPP-Verbundpartner.   |Zum Bereitstellen von Partnerverbunden ja, andernfalls optional  <br/> In Skype für Business Server 2019 nicht verfügbar.|
|SRV   |\_Sipfederationtls. \_Tcp. * \<Sipdomain\> * <br/>\_Sipfederationtls. \_Tcp. * <span> </span>Contoso<span></span>.com*  |FQDN der externen Zugriffs-Edgeservers  <br/>*Access1. <span> </span>Contoso<span></span>.com*  |Um Push Notification Service und Apple-pushbenachrichtigungsdienst unterstützen, erstellen Sie einen SRV-Eintrag für jede SIP-Domäne. & #x 2778;  ||
|A/AAAA   |Externe Front-End-Pool FQDN der Webdienste  <br/>*Web-automatischer<span></span>Contoso<span></span>.com*  |Reverseproxys Proxy öffentliche IP-Adresse, an die externe Web Services VIP-Adresse für Ihre Front-End-Pool & #x 2776; <br/> 131.107.155.1 Proxy für 192.168.21.120   |Front-End-Pool externe Schnittstelle wird von Skype für Web-Geschäfts-App   |Y   |
|A/AAAA/CNAME   |Lyncdiscover. * \<Sipdomain\>* <br/> Lyncdiscover. * <span> </span>Contoso<span></span>.com*  |Reverse Proxy öffentliche IP-Adresse aufgelöst wird, an die externe Web Services VIP-Adresse für den Director-Pool, falls vorhanden, oder für den Front-End-Pool, wenn Sie nicht über einen Director & #x 2777 verfügen; <br/> 131.107.155.1 Proxy für 192.168.21.120   | Externer Eintrag für Client aufgelöst AutoErmittlung, auch vom Mobilität, Skype für Business Web App- und Scheduler Web app verwendet den Reverseproxyserver <br/> Um Push Notification Service und Apple-pushbenachrichtigungsdienst unterstützen, erstellen Sie einen SRV-Eintrag für jede SIP-Domäne, Microsoft Lync Mobile-Clients aufweist. 3  |Y   |
|A/AAAA   |erfüllen. * \<Sipdomain\>* <br/> erfüllen. * <span> </span>Contoso<span></span>.com*  |Reverse Proxy öffentliche IP-Adresse, löst die Web-Schnittstelle für den Front-End-pool  <br/> 131.107.155.1 Proxy für 192.168.21.120   |Skype für Business Web Service-Proxy  <br/> Hier finden Sie [einfache URLs](dns.md#BK_Simple)  |Y   |
|A/AAAA   |DFÜ-Zoll*\<Sipdomain\>* <br/> DFÜ-Zoll*<span></span>Contoso<span></span>.com*  |Reverseproxys Proxy öffentliche IP-Adresse, die Web-Schnittstelle für den Front-End-pool  <br/> 131.107.155.1 Proxy für 192.168.21.120   |Skype für Business Web Service-Proxy  <br/> Hier finden Sie [einfache URLs](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps Server Pool-FQDN  <br/> OWA. <span> </span>Contoso<span></span>.com   | Reverseproxys Proxy öffentliche IP-Adresse, die Web-Schnittstelle für die Office Web Apps Server <br/> 131.107.155.1 als Proxy für 192.168.1.5   | Office Web Apps Server-Pool VIP-Adresse <br/> 192.168.1.5   |Definiert den Office Web Apps Server-Pool-FQDN   |

& #x 2776; Verbund, andernfalls optional Bereitstellung erforderlich sind.

& #x 2777; Zum Ermitteln der Front-End-Server oder Front-End-Pool und authentifiziert und werden als Benutzer angemeldet verwendet von einem Client.

& #x 2778; Dies gilt nur für Clients auf Apple oder Microsoft-basierte mobile Geräten. Android- und Nokia Symbian-Geräte verwenden die Pushbenachrichtigung nicht.

 Weitere Informationen über die Edge-Servern und Umkreisnetzwerken finden Sie unter der Edge-Server [DNS-Planung](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) Inhalte.

> [!IMPORTANT]
> Skype für Business Server unterstützt die Verwendung von IPv6-Adressen. Einzelheiten finden Sie unter [Planen für IPv6 in Skype für Unternehmen](ipv6.md) .

> [!IMPORTANT]
> Weitere Informationen über FQDNs finden Sie unter [DNS-Grundlagen](basics.md).

**Split-Brain DNS** 
 <a name="BK_split"> </a>

Split-Brain-DNS ist eine DNS-Konfiguration, bei der Sie zwei DNS-Zonen mit dem gleichen Namespace verwenden. Wie aus den Tabellen hervorgeht, verarbeitet die erste DNS-Zone interne Anforderungen, während die zweite DNS-Zone für externe Anforderungen zuständig ist. Weitere Informationen hierzu finden Sie unter [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Überlegungen zu Hybridbereitstellungen
<a name="BK_Hybrid"> </a>

Wenn Sie planen, einige Benutzer online verwaltet und einige bei vor Ort finden Sie in der hybridkonnektivität [Skype für Business Server 2015](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS) und [Skype für Business Server 2019](../../../SfBServer2019/hybrid/hybrid-solutions.md)Artikel planen. Sie müssen zum Konfigurieren von DNS wie gewohnt für Skype für Business Server 2015 und auch zusätzliche DNS-Datensätze hinzufügen.

Sie sollten auch auf "-Office 365-URLs und IP-Adressbereichen" finden Sie unter [https://aka.ms/o365ips](https://aka.ms/o365ips) zu bestätigen, dass Ihre Benutzer Zugriff auf den online-Ressourcen verfügen sie benötigen.

## <a name="simple-urls"></a>Einfache URLs 
<a name="BK_Simple"> </a>

Bei einer URL (Uniform Resource Locator) handelt es sich um einen Verweis auf eine Webressource, der den Speicherort der Ressource in einem Computernetzwerk und das zum Abrufen verwendete Protokoll angibt.

Skype für Business Server unterstützt die Verwendung von drei "einfache" URLs auf Dienste zuzugreifen:

- 
                Die **Besprechungs**-URL („meet“) dient als Basis-URL für alle Konferenzen, die am Standort abgehalten werden. Ein Beispiel für eine einfache Meet-URL ist Https:<span></span>//<span></span>erfüllen. <span> </span>Contoso<span></span>. com. Eine URL für eine bestimmte Besprechung möglicherweise Https:<span></span>//<span></span>erfüllen. <span> </span>Contoso<span></span>.com /_Username_/7322994.

    Mit der einfachen Besprechungs-URL sind Links für die Teilnahme an Besprechungen einfach zu verstehen und leicht zu kommunizieren.

- 
                Die **Einwahl**-URL („dialin“) ermöglicht den Zugriff auf die Webseite mit den Einstellungen für Einwahlkonferenzen. Auf dieser Seite werden die Konferenzeinwahlnummern mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und die in einer Konferenz verfügbaren MFV-Steuerelemente angezeigt. Darüber hinaus können auf dieser Seite PINs sowie zugewiesene Konferenzinformationen verwaltet werden. Die einfache Einwahl-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die Einwahl einfache URL lautet https://<span></span>Dialin. <span> </span>Contoso<span></span>. com.

- **Admin** ermöglicht schnellen Zugriff auf die Skype Business Server-Systemsteuerung. Von einem beliebigen Computer innerhalb der Firewall Ihres Unternehmens kann ein Administrator die Skype Business Server-Systemsteuerung öffnen, indem Sie die einfache Admin-URL in einem Browser eingeben. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation. Ein Beispiel für die einfache Admin-URL lautet https://<span></span>Admin. <span> </span>Contoso<span></span>. com.

Einfache URLs sind unter [DNS-Anforderungen für einfache URLs in Skype für Business Server](simple-urls.md)ausführlich erläutert.

## <a name="dns-by-server-role"></a>DNS nach Serverrollen
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server beliebig festlegen. Die Namen sollten aber einprägsam sein und Aufschluss über ihre Funktion im System geben.

### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese generische Datensatz Anforderungen gelten für alle Serverrollen von Skype für Unternehmen verwendet. Bei einem Pool handelt es sich um eine Gruppe von Servern, die die gleichen Dienste ausführen und gemeinsam Clientanforderungen verarbeiten, die über einen Lastenausgleich an sie geleitet werden. Einzelheiten finden Sie unter [Lastenausgleich Anforderungen für Skype für Unternehmen](load-balancing.md)

**Anforderungen für DNS-Einträge für Server-/Poolrollen (vorausgesetzt, dass DNS-Lastenausgleich verwendet wird)**

|Bereitstellungsszenario|DNS-Anforderung|
|:-----|:-----|
|Ein Server:  <br/> Beständiger Chat, Director, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> ServerRole. <span> </span>Contoso<span></span>.com 10.10.10.0   |
|Pool:  <br/> Beständiger Chat, Director, Edgeserver, Vermittlungsserver, Front-End-Server   |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) jedes Serverknotens im Pool in die zugehörige IP-Adresse aufgelöst wird  <br/>**Beispiel** <br/> ServerRole01. <span> </span>Contoso<span></span>.com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>.com 10.10.10.2  <br/> Mehrere interne A-Einträge, mit denen der vollqualifizierte Domänenname (FQDN) des Pools in die IP-Adressen der Serverknoten im Pool aufgelöst wird  <br/>**Beispiel** <br/> ServerPool. <span> </span>Contoso<span></span>.com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edgeserverspezifische DNS-Themen

 Informationen zum Planen von Edge-Server-Bereitstellung zu überprüfen, [Planen von Edge-Server-Bereitstellungen in Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)und [Erweiterte Edge Server DNS planen Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , die in den folgenden Abschnitten hat

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


