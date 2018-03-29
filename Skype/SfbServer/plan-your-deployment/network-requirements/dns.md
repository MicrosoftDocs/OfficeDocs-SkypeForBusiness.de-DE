---
title: DNS-Anforderungen für Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Zusammenfassung: Überprüfen Sie die DNS-Aspekten in diesem Thema vor der Implementierung von Skype für Business Server 2015.'
ms.openlocfilehash: 2f19e6dbd040a7f553331b6bcb0d7074a30fd0ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>DNS-Anforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Überprüfen Sie die DNS-Aspekten in diesem Thema vor der Implementierung von Skype für Business Server 2015.
  
In diesem Artikel werden nur die DNS-Planung für Skype für Business Server 2015 Bereitstellungen in einer Organisation am Standort Netzwerk. Skype für Business Online finden Sie in "-Office 365-URLs und IP-Adressbereichen" unter [http://aka.ms/o365ips](http://aka.ms/o365ips). 
  
Ein DNS-Server (Domain Name Service) ordnet Hostnamen (wie „www.contoso.com“, mutmaßlich ein Webserver) IP-Adressen zu (z. B. „10.10.10.10“). Auf diese Weise können Clients und voneinander abhängige Server im Netzwerk miteinander kommunizieren. Wenn Sie eine Implementierung von Skype für Business Server 2015 einrichten, müssen Sie sicherstellen, dass die Zuordnung der neuen Servernamen (in der Regel die Rolle, die sie für ergreifen können spiegeln) die IP-Adressen entspricht, denen sie zugeordnet sind.
  
Dies mag ein Bit schwierige zunächst, den schwierigsten für die Planung, dies ist möglich, der [Skype für Business Server 2015 Planungstool](https://www.microsoft.com/en-us/download/details.aspx?id=50357)verwenden. Wenn Sie die Fragen des Assistenten zu den Funktionen, die Sie verwenden möchten, beantwortet haben, können Sie für jeden definierten Standort den DNS-Bericht im Edge-Adminbericht anzeigen und die dort aufgelisteten Informationen zum Erstellen Ihrer DNS-Einträge verwenden. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen. Details hierzu finden Sie unter [Überprüfen des DNS-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Berücksichtigen Sie, dass Sie den Edge-Adminbericht in eine Excel-Tabelle exportieren können. Den DNS-Bericht finden Sie auf einem der Arbeitsblätter in der Datei. 
  
Wenn Sie eine neue Implementierung wie unter [Erstellen von DNS-Einträge für Skype für Business Server 2015](../../deploy/install/create-dns-records.md) installieren und Erstellen von Ihrer Topologie für Skype für Business Server 2015, wir erkannt wird, können Sie zum Verwenden der DNS-Funktionen in Windows integriert Server 2016 oder einem Drittanbieter-DNS-Paket, damit wir die Diskussionen in diesem Artikel allgemeine anstelle von bestimmten halten. Wir beschreiben, was Sie benötigen, und Sie entscheiden, wie Sie diese Anforderungen erfüllen.
  
Erfahrene Skype für Unternehmen, Lync und Office Communications-Suite-Administratoren wird wahrscheinlich in den folgenden Tabellen hilfreich sein. Falls die Tabelle verwirrend scheint – in den späteren Abschnitten bzw. Artikeln werden die folgenden Konzepte erörtert: 
  
- [Zusammenfassenden Tabellen](dns.md#BK_Summary)
    
- [DNS-Grundlagen](basics.md)
    
- [Hybrid-Aspekte](dns.md#BK_Hybrid)
    
- [Split-Brain-DNS](dns.md#BK_split)
    
- [Einfache URLs](dns.md#BK_Simple)
    
- [DNS nach Serverrollen](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>Zusammenfassungstabellen
<a name="BK_Summary"> </a>

Die folgende Tabelle enthält die DNS-Einträge, dass Skype für Business Server 2015 wird verwendet, um die Dienste für Benutzer bereitzustellen. Einige sind optional, da sie nur zur Unterstützung bestimmter Funktionen benötigt werden. Wenn die entsprechenden Funktionen nicht gewünscht werden, können die DNS-Einträge übersprungen werden. Die DNS-Einträge, die nur für den internen Zugriff benötigt werden, befinden sich in der ersten Tabelle. Bei einer Bereitstellung, die internen und externen Zugriff ermöglicht, werden Einträge aus beiden Tabellen benötigt.
  
**Interne DNS-Zuordnungen**

|**Eintragstyp**|**Wert**|**In aufgelöst wird**|**Zweck**|**Erforderlich**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |Front-End-Pool-FQDN  <br/>  *FE-pool.contoso.com*  <br/> |Front-End-Pool Server IP-Adressen  <br/>  DNS-kg zu *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |DNS-Lastenausgleich von Front-End-Pools. Ordnet den Namen des Front-End-Pools einer Gruppe von IP-Adressen zu.  <br/> Siehe [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Directorpools](load-balancing.md#BK_FE_Dir). <br/> |Y  <br/> |
|A/AAAA  <br/> | FQDN des jedem Front-End-Server oder Standard Edition-Server in einem Pool oder einen eigenständigen server <br/>  * FE01.contoso.com, FE02.contoso.com, FE03.contoso.com*  <br/> |Entsprechende IP jedes Servers  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Ordnet den Servernamen seiner IP-Adresse zu.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN des Enterprise-Pools für die interne Webdienstüberschreibung  <br/>  *Web-int.contoso.com*  <br/> |Hardwaregeräts zum Lastenausgleich_vip für interne Webdienste der Front-End-Server  <br/>  * 192.168.21.120 *  <br/> |Zum Aktivieren der Client-zu-Server-Webdatenverkehr, wie die Skype für Business Web App heruntergeladen erforderlich. Wird auch für mobile Clients benötigt.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN des Enterprise-Pools für die externe Webdienstüberschreibung  <br/>  *Web-ext.contoso.com*  <br/> |Hardwaregeräts zum Lastenausgleich_vip für externe Webdienste der Front-End-Server  <br/>  *68.123.56.90*  <br/> |Zum Aktivieren der Client-zu-Server-Webdatenverkehr, wie die Skype für Business Web App heruntergeladen erforderlich. Wird benötigt, wenn mobile Clients DNS intern auflösen. Kann in eine IP eines Reverseproxys in der DMZ oder in eine Internet-IP aufgelöst werden.  <br/> ||
|A/AAAA  <br/> | Back-End-Server-SQL Server-FQDN <br/>  *SQL1.contoso.com*  <br/> |IP-Adresse des Servers  <br/>  *192.168.11.90*  <br/> |Ordnet den Servernamen für einen Back-End-SQL-Server arbeiten mit den Front-End-Pool seiner IP-Adresse  <br/> ||
|A/AAAA  <br/> |Back-End-Server-Spiegelung-SQL-Server-FQDN  <br/>  *SQL2.contoso.com*  <br/> |IP-Adresse des Servers  <br/>  *192.168.11.91*  <br/> |Ordnet den Servernamen für einen Back-End-SQL-Spiegelserver arbeiten mit den Front-End-Pool seiner IP-Adresse  <br/> ||
|A/AAAA  <br/> |Directorpool-FQDN  <br/> **Hinweis:** Nicht zutreffend, wenn Sie einen eigenständigen Director-Server verwenden <br/>  *DirPool.contoso.com*  <br/> |Director-Pool-IP-Adressen  <br/> DNS-kg *192.168.21.132, 192.168.21.133* , 192.168.21.134  <br/> |DNS-Lastenausgleich von Directorpoolservern. Nennen Sie der Pool für den Director-Pool in einer IP-Adresse Maps finden Sie unter [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir) <br/> Ein Director kann einen Benutzer authentifizieren. Der Director ist optional.  <br/> ||
|A/AAAA  <br/> |Director-FQDN  <br/> |Server-IP-Adresse des einzelnen Director-server  <br/> |Nennen Sie der Pool für den Director in eine IP-Adresse Maps finden Sie unter [Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |Mediation Serverpool-FQDN  <br/> |IP-Adressen des Pools  <br/> |Die Rolle des Vermittlungsservers ist optional. Sie können diese von einem Vermittlungsserver für den Front-End-Server oder -Pool bereitgestellten Dienste zusammen mit anderen bereitstellen. Finden Sie unter [Verwenden von DNS-Lastenausgleichs in Vermittlungsserverpools](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |Vermittlungsserver FQDN  <br/> |IP-Adresse des Servers  <br/> |Sie können diese von einem Vermittlungsserver für den Front-End-Server oder -Pool bereitgestellten Dienste zusammen mit anderen bereitstellen. Finden Sie unter [Verwenden von DNS-Lastenausgleichs in Vermittlungsserverpools](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |Persistent Chat-Server-FQDN  <br/> |Persistent Chat-Server-IP-Adresse  <br/> |Ein Server für beständigen Chat wird für die Funktion „Beständiger Chat“ benötigt. Andernfalls ist er optional.  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> Lyncdiscoverinternal. *"contoso.com"*  <br/> |Hardwaregeräts zum Lastenausgleich Front-End-Pool-VIP oder Director-IP  <br/>  192.168.21.121 <br/> |Interne AutoDiscover Service1, für die Unterstützung der Mobilität erforderlich. Wenn interne DNS aufgelöst für mobile Geräte verwendet wird, sollte er auf die externe IP-Adresse oder DMZ VIP-Adresse verweisen.  <br/> Für Webdienste benötigen wir Hardwaregeräts zum Lastenausgleich, auf dem Front-End-Pool wie HTTPS DNS nutzen können. Für Front-End-Pool oder Director-Pool, sollte in die VIP eines Hardwaregeräts zum Lastenausgleich oder eine reguläre IP-Adresse für einen Standard Edition-Server oder einen eigenständigen Director-Server aufgelöst wird.  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *"contoso.com"*  <br/> |FQDN des HLB-Front-End-Pools oder des Directors  <br/> Web-int.contoso.com  <br/> |Interne AutoErmittlung Service1 <br/> Dies können Sie bei Bedarf als A-Eintrag anstatt als CNAME-Eintrag implementieren.  <br/> ||
|A/AAAA  <br/> |sip. _\<sipdomain\>_ <br/> sip. _"contoso.com"_ <br/> |Front-End-Pool Server IP-Adressen (oder an einen einzelnen Director-IP-Adresse)  <br/>  DNS-kg zu *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Damit die automatische Konfiguration erforderlich, finden Sie unter [Exemplarische Vorgehensweise von Skype für Business Clients suchen Dienste](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Datensätze, die auf den Front-End-Pool-Servern oder Director-Server auf dem internen Netzwerk oder Zugriffs-edgediensts verweist, wenn der Client externe ist oder eines Datensatzes  <br/> |2 <br/> |
|A/AAAA  <br/> |ucupdates-r2. _\<sipdomain\>_ <br/> ucupdates-r2. _"contoso.com"_ <br/> |VIP des HLB-Front-End-Pools, VIP des HLB-Directorpools oder IP des SE-Servers/Directorservers  <br/>  192.168.21.121 <br/> |Bereitstellen von dieser Eintrag ist optional 3 <br/> ||
|SRV  <br/> |_sipinternaltls. _ \<Sipdomain\> _ Port 5061 <br/> _sipinternaltls. _"contoso.com"_ Port 5061 <br/> |Front-End-Pool-FQDN  <br/>  _FE-Pool.contoso.com_ <br/> |Ermöglicht es internen Benutzer automatische Anmeldung 1 auf den Front-End-Server/Pool oder SE-Server/Pool, die authentifiziert und weiterleitet Clientanforderungen für die Anmeldung. <br/> |2 <br/> |
|SRV  <br/> |_sipinternal. _\<sipdomain\>_ <br/> _sipinternal. _"contoso.com"_ <br/> |Front-End-Pool-FQDN  <br/>  _FE-Pool.contoso.com_ <br/> |Zugriff durch interne Benutzer 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp. _\<sipdomain\>_ <br/> _ntp._udp. _"contoso.com"_ <br/> |FQDN des Zeitservers  <br/> North america.pool.ntp.org  <br/> |Für Lync Phone Edition-Geräte erforderliche NTP-Quelle  <br/> |Dies ist erforderlich, um desktop Telefone zu unterstützen.  <br/> |
|SRV  <br/> |_sipfederationtls.  _\<sipdomain\>_ <br/> _sipfederationtls.  _"contoso.com"_ <br/> | Zugriffs-edgedienst FQDN <br/> EdgePool int _"contoso.com"_ <br/> |Erstellen Sie für jede SIP-Domäne, in der sich mobile Clients für iOS oder Windows Phone befinden, einen SRV-Eintrag.  <br/> |Für die Unterstützung von mobilen Clients  <br/> |
|A/AAAA  <br/> |Administrator-URL  <br/>  _Web-int.contoso.com_ <br/> |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121  <br/> |Skype für Business Server-Systemsteuerung finden Sie unter [Einfache URLs](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |Besprechungs-URL  <br/>  _Web-int.contoso.com_ <br/> |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121  <br/> |Onlinebesprechungen, finden Sie unter [Einfache URLs](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |Einwahl-URL  <br/>  _Web-int.contoso.com_ <br/> |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121  <br/> |Einwahlkonferenzen, finden Sie unter [Einfache URLs](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |FQDN für interne Webdienste  <br/>  _Web-int.contoso.com_ <br/> |VIP des HLB-Front-End-Pools  <br/> 192.168.21.121  <br/> |Skype für Business-Webdienst wird von Skype für Web-Geschäfts-App  <br/> ||
|A/AAAA  <br/> |Office Web Apps Server Pool-FQDN  <br/> OWA.contoso.com  <br/> | Office Web Apps Server-Pool VIP-Adresse <br/> 192.168.1.5  <br/> |Definiert den Office Web Apps Server-Pool-FQDN  <br/> ||
|A/AAAA  <br/> | Interner Web-FQDN <br/> Web-int.contoso.com  <br/> | Front-End-Pool-VIP-Adresse <br/> 192.168.21.121  <br/> |Definiert den internen Web-FQDN wird von Skype für Web-Geschäfts-App  <br/> Wenn Sie für diesen Pool den DNS-Lastenausgleich verwenden, können die FQDNs des Front-End-Pools und der internen Webfarm nicht identisch sein.  <br/> ||
   
 **1** wird von einem Client zum Ermitteln des Front-End-Server oder Front-End-Pools und authentifiziert und werden als Benutzer angemeldet verwendet. Weitere Details zu diesem befindet sich in [Exemplarische Vorgehensweise von Skype für Clients Business Services suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).
  
 **2** Dies ist nur erforderlich, zur Unterstützung von Clients von Vorversionen vor dem Lync 2013 und desktop Telefone.
  
 **3** -A-Eintrag kann in die Lage, in dem ein Unified Communications-Gerät eingeschaltet wird, aber ein Benutzer nie in das Gerät angemeldet hat, das Gerät zum Ermitteln der Hostserver geräteaktualisierungswebdienst und Abrufen von Updates. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.
  
Das folgende Diagramm zeigt ein Beispiel mit internen und externen DNS-Einträgen sowie vielen der Einträge aus den Tabellen: 
  
**Öffentliche IPv4-Adressen mit Edge-Netzwerkdiagramm**

![Beispiel eines DNS-Netzwerkdiagramms](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**Perimeter Network DNS-Zuordnungen (interne und externe Schnittstellen)**

|**Eintragstyp**|**Wert**|**In aufgelöst wird**|**Zweck**|**Erforderlich**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |Interne Edge-Pool-FQDN  <br/>  _EdgePool int.contoso.com_ <br/> |Intern verbundenen Edge-Pool-IP-Adressen  <br/> 172.25.33.10, 172.25.33.11  <br/> |Konsolidierte IP-Adressen der internen Schnittstelle des Edgepools  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN des Edgeservers  <br/>  _Nachteile 1.contoso.com_ <br/> |Intern verbundenen Server IP für einen Server in der Edge-pool  <br/> 172.25.33.10  <br/> |Erstellen Sie einen Eintrag für jeden Server im Pool mit dem FQDN des Servers in seine interne Server Knoten IP-Adresse im Pool Verweisen finden Sie unter [DNS-Lastenausgleich in Edgeserverpools](load-balancing.md#BK_Edge).  <br/> |Y  <br/> |
|A/AAAA  <br/> |Zugriffs-edgedienst Pool-FQDN  <br/>  _Access1.contoso.com_ <br/> |Access-Dienst Pool externe IP-Adressen  <br/> 131.107.16.10, 131.107.16.11  <br/> |Zugriffs-edgedienst stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden Datenverkehr von Session Initiation Protocol (SIP) bereit.  <br/> |Y  <br/> |
|A/AAAA  <br/> |Webkonferenz-edgedienst Pool-FQDN  <br/>  _Webcon1.contoso.com_ <br/> |Web Webkonferenz-Edgeserver Service externe IP-Adressen  <br/> 131.107.16.90, 131.107.16.91  <br/> |Der Webkonferenz-edgedienst ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die gehostet werden in Ihrer internen Skype für Business Server-Umgebung.  <br/> |Y  <br/> |
|A/AAAA  <br/> | _av.\<Sip-Domäne\> _ Pool-FQDN <br/>  _AV1.contoso.com_ <br/> |Externe IP-Adressen des A/V-Edgeservers  <br/> 131.107.16.170, 131.107.16.171  <br/> |Der A / V-edgedienst stellt audio, Video, Anwendungsfreigabe und File transfer für externe Benutzer.  <br/> |Y  <br/> |
|CNAME  <br/> |sip. _\<sipdomain\>_ <br/> sip. _"contoso.com"_ <br/> |Externer FQDN des Zugriffs-Edgepools  <br/>  _Access1.contoso.com_ <br/> |Sucht nach der Edge-Server-Pool. Finden Sie unter [Exemplarische Vorgehensweise von Skype für Clients Business Services suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip. _\<sipdomain\>_ <br/> _sip. _"contoso.com"_ <br/> |FQDN der externen Zugriffs-Edgeservers  <br/>  _Access1.contoso.com_ <br/> |Wird für den Zugriff durch externe Benutzer verwendet. Finden Sie unter [Exemplarische Vorgehensweise von Skype für Clients Business Services suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls. _\<sipdomain\>_ <br/> _sipfederationtls. _"contoso.com"_ <br/> |FQDN der externen Zugriffs-Edgeservers  <br/>  _Access1.contoso.com_ <br/> |Wird für Partnerverbunde und die Verbindung mit öffentlichen Chatdiensten verwendet.  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-Server._tcp. _\<sipdomain\>_ <br/> _xmpp-Server._tcp. _"contoso.com"_ <br/> |FQDN der externen Zugriffs-Edgeservers  <br/>  _Access1.contoso.com_ <br/> |XMPP-Proxydienst akzeptiert und sendet extensible messaging und Anwesenheit Protocol (XMPP) Nachrichten zu und von konfigurierten XMPP-Verbundpartner.  <br/> |Zum Bereitstellen von Partnerverbunden ja, andernfalls optional  <br/> |
|SRV  <br/> |_sipfederationtls.  _\<sipdomain\>_ <br/> _sipfederationtls.  _"contoso.com"_ <br/> |FQDN der externen Zugriffs-Edgeservers  <br/>  _Access1.contoso.com_ <br/> |Um Push Notification Service und Apple-pushbenachrichtigungsdienst unterstützen, erstellen Sie einen SRV-Eintrag für jede SIP-Domäne. 3 <br/> ||
|A/AAAA  <br/> |Externe Front-End-Pool FQDN der Webdienste  <br/>  _Web-ext.contoso.com_ <br/> |Reverseproxys Proxy öffentliche IP-Adresse, an die externe Web Services VIP-Adresse für den Front-End-Pool 1 <br/> 131.107.155.1 Proxy für 192.168.21.120  <br/> |Front-End-Pool externe Schnittstelle wird von Skype für Web-Geschäfts-App  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _"contoso.com"_ <br/> |Reverse Proxy öffentliche IP-Adresse aufgelöst wird, an die externe Web Services VIP-Adresse für den Director-Pool, falls vorhanden, oder für den Front-End-Pool, wenn ein Director 2 nicht vorhanden ist <br/> 131.107.155.1 Proxy für 192.168.21.120  <br/> | Externer Eintrag für Client aufgelöst AutoErmittlung, auch vom Mobilität, Skype für Business Web App- und Scheduler Web app verwendet den Reverseproxyserver <br/> Um Push Notification Service und Apple-pushbenachrichtigungsdienst unterstützen, erstellen Sie einen SRV-Eintrag für jede SIP-Domäne, Microsoft Lync Mobile-Clients aufweist. 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |meet. _\<sipdomain\>_ <br/> meet. _"contoso.com"_ <br/> |Reverse Proxy öffentliche IP-Adresse, löst die Web-Schnittstelle für den Front-End-pool  <br/> 131.107.155.1 Proxy für 192.168.21.120  <br/> |Skype für Business Web Service-Proxy  <br/> Hier finden Sie [einfache URLs](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |Einwahl- _ \<Sipdomain\>_ <br/> Zugriffsnummer für Einwahl _"contoso.com"_ <br/> |Reverseproxys Proxy öffentliche IP-Adresse, die Web-Schnittstelle für den Front-End-pool  <br/> 131.107.155.1 Proxy für 192.168.21.120  <br/> |Skype für Business Web Service-Proxy  <br/> Hier finden Sie [einfache URLs](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |Office Web Apps Server Pool-FQDN  <br/> OWA.contoso.com  <br/> | Reverseproxys Proxy öffentliche IP-Adresse, die Web-Schnittstelle für die Office Web Apps Server <br/> 131.107.155.1 als Proxy für 192.168.1.5  <br/> | Office Web Apps Server-Pool VIP-Adresse <br/> 192.168.1.5  <br/> |Definiert den Office Web Apps Server-Pool-FQDN  <br/> |
   
 Bereitstellung von Verbund, andernfalls optional **1** erforderlich sind.
  
 **2** wird von einem Client zum Ermitteln der Front-End-Server oder Front-End-Pool und authentifiziert und werden als Benutzer angemeldet verwendet.
  
 **3** Dies gilt nur für Clients auf Apple oder Microsoft-basierte mobile Geräten. Android- und Nokia Symbian-Geräte verwenden die Pushbenachrichtigung nicht.
  
 Weitere Informationen über die Edge-Servern und Umkreisnetzwerken finden Sie unter der Edge-Server [DNS-Planung](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) Inhalte.
  
> [!IMPORTANT]
> Skype für Business Server unterstützt die Verwendung von IPv6-Adressen. Einzelheiten finden Sie unter [Planen für IPv6 in Skype für Unternehmen](ipv6.md) .
  
> [!IMPORTANT]
> Weitere Informationen über FQDNs finden Sie unter [DNS-Grundlagen](basics.md). 
  
 **Split-Brain DNS** 
 <a name="BK_split"> </a>
 
Split-Brain DNS ein DNS-Konfiguration wird, müssen Sie zwei DNS-Zonen mit der gleiche Namespace. Wie aus den Tabellen hervorgeht, verarbeitet die erste DNS-Zone interne Anforderungen, während die zweite DNS-Zone für externe Anforderungen zuständig ist. Weitere Informationen hierzu finden Sie unter [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS). 
  
## <a name="hybrid-considerations"></a>Überlegungen zu Hybridbereitstellungen
<a name="BK_Hybrid"> </a>

Wenn Sie einen Teil der Benutzer online und einen anderen Teil lokal verwalten möchten, lesen Sie den Abschnitt zu den [DNS-Einstellungen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS) für Hybridbereitstellungen. Sie müssen zum Konfigurieren von DNS wie gewohnt für Skype für Business Server 2015 und auch zusätzliche DNS-Datensätze hinzufügen. 
  
Sie sollten auch auf "-Office 365-URLs und IP-Adressbereichen" finden Sie unter [http://aka.ms/o365ips](http://aka.ms/o365ips) zu bestätigen, dass Ihre Benutzer Zugriff auf den online-Ressourcen verfügen sie benötigen.
  
## <a name="simple-urls"></a>Einfache URLs 
<a name="BK_Simple"> </a>

Bei einer URL (Uniform Resource Locator) handelt es sich um einen Verweis auf eine Webressource, der den Speicherort der Ressource in einem Computernetzwerk und das zum Abrufen verwendete Protokoll angibt. 
  
Skype für Business Server unterstützt die Verwendung von drei "einfache" URLs auf Dienste zuzugreifen:
  
- 
                Die **Besprechungs**-URL („meet“) dient als Basis-URL für alle Konferenzen, die am Standort abgehalten werden. Ein Beispiel für eine einfache Meet-URL ist https://meet.contoso.com. Eine URL für eine bestimmte Besprechung möglicherweise https://meet.contoso.com/ _Username_/7322994. 
    
    Mit der einfachen Besprechungs-URL sind Links für die Teilnahme an Besprechungen einfach zu verstehen und leicht zu kommunizieren.
    
- 
                Die **Einwahl**-URL („dialin“) ermöglicht den Zugriff auf die Webseite mit den Einstellungen für Einwahlkonferenzen. Auf dieser Seite werden die Konferenzeinwahlnummern mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und die in einer Konferenz verfügbaren MFV-Steuerelemente angezeigt. Darüber hinaus können auf dieser Seite PINs sowie zugewiesene Konferenzinformationen verwaltet werden. Die einfache Einwahl-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die Einwahl einfache URL ist https://dialin.contoso.com.
    
- **Admin** ermöglicht schnellen Zugriff auf die Skype Business Server-Systemsteuerung. Von einem beliebigen Computer innerhalb der Firewall Ihres Unternehmens kann ein Administrator die Skype Business Server-Systemsteuerung öffnen, indem Sie die einfache Admin-URL in einem Browser eingeben. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation. Ein Beispiel für die einfache Admin-URL ist https://admin.contoso.com.
    
Einfache URLs sind unter [DNS-Anforderungen für einfache URLs in Skype für Business Server 2015](simple-urls.md)ausführlich erläutert.
  
## <a name="dns-by-server-role"></a>DNS nach Serverrollen
<a name="BK_Servers"> </a>

Sie können die Namen dieser Pools und Server beliebig festlegen. Die Namen sollten aber einprägsam sein und Aufschluss über ihre Funktion im System geben.
  
### <a name="dns-records-for-individual-servers-or-pools"></a>DNS-Einträge für einzelne Server oder Pools

Diese generische Datensatz Anforderungen gelten für alle Serverrollen von Skype für Unternehmen verwendet. Bei einem Pool handelt es sich um eine Gruppe von Servern, die die gleichen Dienste ausführen und gemeinsam Clientanforderungen verarbeiten, die über einen Lastenausgleich an sie geleitet werden. Einzelheiten finden Sie unter [Lastenausgleich Anforderungen für Skype für Unternehmen](load-balancing.md)
  
**Der DNS-Eintrag Anforderungen für Server-Pool Rollen (DNS-Lastenausgleich wird vorausgesetzt)**

|**Bereitstellungsszenario**|**DNS-Anforderung**|
|:-----|:-----|
|Ein Server:  <br/> Beständiger Chat, Director, Vermittlungsserver, Front-End-Server  <br/> |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|Pool:  <br/> Beständiger Chat, Director, Edgeserver, Vermittlungsserver, Front-End-Server  <br/> |Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) jedes Serverknotens im Pool in die zugehörige IP-Adresse aufgelöst wird  <br/> **Beispiel** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> Mehrere interne A-Einträge, mit denen der vollqualifizierte Domänenname (FQDN) des Pools in die IP-Adressen der Serverknoten im Pool aufgelöst wird  <br/> **Beispiel** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>Edgeserverspezifische DNS-Themen

 Informationen zum Planen von Edge-Server-Bereitstellung zu überprüfen, [Planen von Edge-Server-Bereitstellungen in Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)und [Erweiterte Edge Server DNS planen Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , die in den folgenden Abschnitten hat
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

