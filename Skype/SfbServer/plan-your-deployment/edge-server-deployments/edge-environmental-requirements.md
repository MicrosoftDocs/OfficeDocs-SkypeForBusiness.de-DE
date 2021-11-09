---
title: Edgeserver-Umgebungsanforderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Zusammenfassung: Erfahren Sie mehr über die Umgebungsanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: ce545b6d8242db34a716d386fdca9149c0296a8c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830809"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Edgeserver-Umgebungsanforderungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Umgebungsanforderungen für Edgeserver in Skype for Business Server.
  
Außerhalb der Skype for Business Server Edgeserverumgebung selbst muss viel Geplant und vorbereitet werden. In diesem Artikel erfahren Sie, welche Vorbereitungen in der Organisationsumgebung gemäß der nachstehenden Liste getroffen werden müssen:
  
- [Topologieplanung](edge-environmental-requirements.md#TopoPlan)
    
- [DNS-Planung](edge-environmental-requirements.md#DNSPlan)
    
- [Zertifikatplanung](edge-environmental-requirements.md#CertPlan)
    
- [Port- und Firewallplanung](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Topologieplanung
<a name="TopoPlan"> </a>

Skype for Business Server Edgeservertopologien können Folgendes verwenden:
  
- Routingfähige öffentliche IP-Adressen.
    
- Nicht routingfähige private IP-Adressen, wenn die symmetrische Netzwerkadressenübersetzung **(Symmetric** Network Address Translation, NAT) verwendet wird.
    
> [!TIP]
> Ihr Edgeserver kann so konfiguriert werden, dass er eine einzelne IP-Adresse mit unterschiedlichen Ports für jeden Dienst verwendet, oder er kann unterschiedliche IP-Adressen für jeden Dienst verwenden, aber den gleichen Standardport verwenden (standardmäßig TCP 443). Weitere Informationen finden Sie unten im Abschnitt zu den IP-Adressanforderungen. 
  
Wenn Sie nicht routingfähige private IP-Adressen mit NAT auswählen, beachten Sie die folgenden Punkte:
  
- Sie müssen routingfähige private IP-Adressen für **alle drei** externen Schnittstellen verwenden.
    
- Sie müssen **symmetrische** NAT für eingehenden und ausgehenden Datenverkehr konfigurieren. Symmetrische NAT ist die einzige unterstützte NAT, die Sie mit Skype for Business Server Edgeserver verwenden können.
    
- Konfigurieren Sie Ihre NAT so, dass eingehende Quelladressen nicht geändert werden. Der A/V-Edgedienst muss die eingehende Quelladresse empfangen können, um den optimalen Medienpfad zu finden.
    
- Ihre Edgeserver müssen in der Lage sein, über ihre öffentlichen A/V-Edge-IP-Adressen miteinander zu kommunizieren. Ihre Firewall muss diesen Datenverkehr zulassen.
    
- NAT kann **nur** für skalierte konsolidierte Edgeserver verwendet werden, wenn Sie den DNS-Lastenausgleich verwenden. Wenn Sie Hardwarelastenausgleich (Hardware Load Balancing, HLB) verwenden, müssen Sie öffentlich routingfähige IP-Adressen **ohne** NAT verwenden.
    
Sie haben keine Probleme, wenn Ihre Access-, Webkonferenz- und A/V-Edgeschnittstellen hinter einem Router oder einer Firewall symmetrische NAT für einzelne und skalierte konsolidierte Edgeservertopologien ausführen (solange Sie keinen Hardwarelastenausgleich verwenden).
  
### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Edgeservertopologieoptionen

Es stehen mehrere Topologieoptionen für Skype for Business Server Edgeserverbereitstellungen zur Verfügung:
  
- Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit Hardwaregerät zum Lastenausgleich
    
Um Ihnen bei der Auswahl zu helfen, haben wir die folgende Tabelle, die eine Zusammenfassung der Optionen für jede Topologie enthält:
  
|**Topologie**|**Hohe Verfügbarkeit**|**Zusätzliche DNS-Einträge für externen Edgeserver im Edgepool erforderlich?**|**Edgefailover für Skype for Business Server Sitzungen**|**Edgefailover für Skype for Business Server Verbundsitzungen**|
|:-----|:-----|:-----|:-----|:-----|
|Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit Hardwaregerät zum Lastenausgleich  <br/> |Ja  <br/> |Nein (ein DNS A-Eintrag pro VIP)  <br/> |Ja  <br/> |Ja  <br/> |
   
&sup1; Exchange Unified Messaging (UM)-Remotebenutzerfailover mit DNS-Lastenausgleich erfordert Exchange 2013 oder höher.
  
### <a name="ip-address-requirements"></a>IP-Adressanforderungen

Grundsätzlich benötigen drei Dienste IP-Adressen; Zugreifen auf Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst. Sie haben die Möglichkeit, entweder drei IP-Adressen zu verwenden, eine für jeden der Dienste, oder Sie können eine verwenden und sich dafür entscheiden, jeden Dienst auf einem anderen Port zu platzieren (weitere Informationen hierzu finden Sie im Abschnitt zur [Port- und Firewallplanung).](edge-environmental-requirements.md#PortFirewallPlan) Bei einer einzelnen konsolidierten Edgeumgebung ist dies ziemlich genau das.
  
> [!NOTE]
> Wie oben erwähnt, können Sie eine IP-Adresse für alle drei Dienste auswählen und diese auf verschiedenen Ports ausführen. Um es klar zu machen, wird dies jedoch nicht empfohlen. Wenn Ihre Kunden nicht auf die alternativen Ports zugreifen können, die Sie in diesem Szenario verwenden würden, können sie auch nicht auf die vollständige Funktionalität Ihrer Edgeumgebung zugreifen. 
  
Bei skalierten konsolidierten Topologien kann es etwas komplizierter sein. Sehen wir uns also einige Tabellen an, in denen die IP-Adressanforderungen festgelegt sind, und beachten Sie, dass die wichtigsten Entscheidungspunkte für die Topologieauswahl hohe Verfügbarkeit und Lastenausgleich sind. Anforderungen an hohe Verfügbarkeit können Sich auf die Auswahl des Lastenausgleichs auswirken (darüber werden wir nach den Tabellen noch ausführlicher sprechen).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressanforderungen für skalierten konsolidierten Edgeserver (IP-Adresse pro Rolle)

|**Anzahl von Edgeservern pro Pool**|**Anzahl der erforderlichen IP-Adressen für den DNS-Lastenausgleich**|**Anzahl der erforderlichen IP-Adressen für den Hardwarelastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |6   <br/> |3 (1 pro VIP) + 6  <br/> |
|3  <br/> |9   <br/> |3 (1 pro VIP) + 9  <br/> |
|4  <br/> |12   <br/> |3 (1 pro VIP) + 12  <br/> |
|5  <br/> |15   <br/> |3 (1 pro VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>IP-Adressanforderungen für einen skalierten konsolidierten Edgeserver (einzelne IP-Adresse für alle Rollen)

|**Anzahl von Edgeservern pro Pool**|**Anzahl der erforderlichen IP-Adressen für den DNS-Lastenausgleich**|**Anzahl der erforderlichen IP-Adressen für den Hardwarelastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 pro VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 pro VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 pro VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 pro VIP) + 5  <br/> |
   
Sehen wir uns einige zusätzliche Dinge an, die Sie bei der Planung berücksichtigen sollten.
  
- **Hohe Verfügbarkeit:** Wenn Sie hohe Verfügbarkeit in Ihrer Bereitstellung benötigen, sollten Sie mindestens zwei Edgeserver in einem Pool bereitstellen. Beachten Sie, dass ein einzelner Edgepool bis zu 12 Edgeserver unterstützt (mit dem Topologie-Generator können Sie jedoch bis zu 20 hinzufügen, die nicht getestet oder unterstützt werden, daher empfehlen wir Ihnen, dies nicht zu tun). Wenn Sie mehr als 12 Edgeserver benötigen, sollten Sie zusätzliche Edgepools für sie erstellen.
    
- **Hardwarelastenausgleich:** Für die meisten Szenarien wird der DNS-Lastenausgleich empfohlen. Der Hardwarelastenausgleich wird natürlich auch unterstützt, ist aber insbesondere für ein einzelnes Szenario über den DNS-Lastenausgleich erforderlich:
    
  - Externer Zugriff auf Exchange 2007 oder Exchange 2010 (ohne SP) Unified Messaging (UM).
    
- **DNS-Lastenausgleich:** Für UM können Exchange 2010 SP1 und neuer vom DNS-Lastenausgleich unterstützt werden. Wenn Sie den DNS-Lastenausgleich für eine frühere Version von Exchange durchführen müssen, funktioniert dies, aber der gesamte Datenverkehr dafür wird zum ersten Server im Pool weitergeleitet, und wenn er nicht verfügbar ist, schlägt dieser Datenverkehr dann fehl.
    
    Der DNS-Lastenausgleich wird auch empfohlen, wenn Sie einen Verbund mit Unternehmen erstellen, die Folgendes verwenden:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 oder Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 oder Office 365
    
## <a name="dns-planning"></a>DNS-Planung
<a name="DNSPlan"> </a>

Wenn es um Skype for Business Server Edgeserverbereitstellung geht, ist es wichtig, sich ordnungsgemäß auf DNS vorzubereiten. Wenn die richtigen Datensätze vorhanden sind, ist die Bereitstellung viel einfacher. Wir hoffen, dass Sie im obigen Abschnitt eine Topologie ausgewählt haben, da wir eine Übersicht erstellen und dann einige Tabellen mit den DNS-Einträgen für diese Szenarien auflisten. Wir werden auch einige [erweiterte Edgeserver-DNS-Planungen für Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) für ausführlichere Lesefunktionen haben, wenn Sie dies benötigen.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-Einträge für Szenarien mit einem einzelnen konsolidierten Edgeserver

Dies sind die DNS-Einträge, die Sie für einen Singe-Edgeserver mit öffentlichen oder privaten IPs mit NAT benötigen. Da es sich hierbei um Beispieldaten handelt, geben wir Beispiel-IPs an, damit Sie Ihre eigenen Einträge einfacher ermitteln können:
  
- Interner Netzwerkadapter: 172.25.33.10 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu allen Netzwerken vorhanden ist, die Server enthalten, auf denen Skype for Business Server- oder Lync Server 2013-Clients ausgeführt werden (z. B. von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Öffentliche IPs:
    
  - Zugriffs-Edge: 131.107.155.10 (dies ist das primäre Gateway mit Standardgateway für Ihren öffentlichen Router, z. B.: 131.107.155.1)
    
  - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
  - A/V Edge: 131.107.155.30 (sekundär)
    
  Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokollversion 4 (TCP/IPv4) und Internetprotokollversion 6 (TCP/IPv6) der Eigenschaften für lokale Verbindungen in Windows Server.
    
  - Private IPs:
    
  - Zugriffs-Edge: 10.45.16.10 (dies ist das primäre Gateway, mit Standardgateway für Ihren Router, z. B.: 10.45.16.1)
    
  - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
  - A/V Edge: 10.45.16.30 (sekundär)
    
Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokollversion 4 (TCP/IPv4) und Internetprotokollversion 6 (TCP/IPv6) der Eigenschaften für lokale Verbindungen in Windows Server.
  
> [!TIP]
>Hier gibt es weitere mögliche Konfigurationen:
  
- Sie können eine IP-Adresse auf dem externen Netzwerkadapter verwenden. Dies wird nicht empfohlen, da Sie dann zwischen den Diensten unterscheiden müssen, die unterschiedliche Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen hierzu finden Sie im Abschnitt zur [Port- und Firewallplanung.](edge-environmental-requirements.md#PortFirewallPlan)
    
- Sie können drei externe Netzwerkadapter anstelle eines haben und jedem einen der Dienst-IPs zuweisen. Warum sollte dies der Fall sein? Es würde die Dienste trennen, und wenn etwas schief geht, würde dies die Problembehandlung vereinfachen und ihre anderen Dienste möglicherweise weiterhin funktionieren lassen, während Sie ein Problem beheben.
    
|**Ort**|**Type**|**Port**|**FQDN- oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Datensatz  <br/> |–  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **privat:** 10.45.16.10 <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |–  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 <br/> **privat:** 10.45.16.20 <br/> |Eine externe Schnittstelle für Ihren Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |–  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **privat:** 10.45.16.30 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Clients extern funktionieren. Sie benötigen eine für jede Domäne mit Skype for Business Benutzern.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern erforderlich, die als zulässige SIP-Domänen bezeichnet werden. Sie benötigen eine für jede Domäne mit Skype for Business Benutzern.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Datensatz  <br/> |–  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Die interne Schnittstelle für Ihren konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS-Einträge für Skalierte DNS- und Hardware-Edgeserverszenarien

Dies sind die DNS-Einträge, die Sie für einen Singe-Edgeserver mit öffentlichen oder privaten IPs mit NAT benötigen. Da es sich hierbei um Beispieldaten handelt, geben wir Beispiel-IPs an, damit Sie Ihre eigenen Einträge einfacher ermitteln können:
  
- Interner Netzwerkadapter:
    
  - Knoten 1: 172.25.33.10 (kein Standardgateway zugewiesen)
    
  - Knoten 2: 172.25.33.11 (kein Standardgateway zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu allen Netzwerken vorhanden ist, die Server enthalten, auf denen Skype for Business Server- oder Lync Server 2013-Clients ausgeführt werden (z. B. von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Knoten 1
    
     - Öffentliche IPs:
    
        - Zugriffs-Edge: 131.107.155.10 (dies ist das primäre Gateway mit Standardgateway für Ihren öffentlichen Router, z. B.: 131.107.155.1)
    
        - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
        - A/V Edge: 131.107.155.30 (sekundär)
    
          Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokollversion 4 (TCP/IPv4) und Internetprotokollversion 6 (TCP/IPv6) der Eigenschaften für lokale Verbindungen in Windows Server.
    
    - Private IPs:
    
         - Zugriffs-Edge: 10.45.16.10 (dies ist das primäre Gateway, mit Standardgateway für Ihren Router, z. B.: 10.45.16.1)
    
         - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
         - A/V Edge: 10.45.16.30 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokollversion 4 (TCP/IPv4) und Internetprotokollversion 6 (TCP/IPv6) der Eigenschaften für lokale Verbindungen in Windows Server.
    
  - Knoten 2
    
    - Öffentliche IPs:
    
      - Zugriffs-Edge: 131.107.155.11 (dies ist das primäre Gateway, mit Standardgateway für Ihren öffentlichen Router, z. B.: 131.107.155.1)
    
      - Webkonferenz-Edge: 131.107.155.21 (sekundär)
    
      - A/V Edge: 131.107.155.31 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokollversion 4 (TCP/IPv4) und Internetprotokollversion 6 (TCP/IPv6) der Eigenschaften für lokale Verbindungen in Windows Server.
    
  - Private IPs:
    
    - Zugriffs-Edge: 10.45.16.11 (dies ist das primäre Gateway mit Standardgateway für Ihren Router, z. B.: 10.45.16.1)
    
    - Webkonferenz-Edge: 10.45.16.21 (sekundär)
    
    - A/V Edge: 10.45.16.31 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokollversion 4 (TCP/IPv4) und Internetprotokollversion 6 (TCP/IPv6) der Eigenschaften für lokale Verbindungen in Windows Server.
    
Hier gibt es weitere mögliche Konfigurationen:
  
- Sie können eine IP-Adresse auf dem externen Netzwerkadapter verwenden. Dies wird nicht empfohlen, da Sie dann zwischen den Diensten unterscheiden müssen, die unterschiedliche Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen hierzu finden Sie im Abschnitt zur [Port- und Firewallplanung.](edge-environmental-requirements.md#PortFirewallPlan)
    
- Sie können drei externe Netzwerkadapter anstelle eines haben und jedem einen der Dienst-IPs zuweisen. Warum sollte dies der Fall sein? Es würde die Dienste trennen, und wenn etwas schief geht, würde dies die Problembehandlung vereinfachen und ihre anderen Dienste möglicherweise weiterhin funktionieren lassen, während Sie ein Problem beheben.
    
|**Ort**|**Type**|**Port**|**FQDN- oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Datensatz  <br/> |–  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 und 131.107.155.11 <br/> **privat:** 10.45.16.10 und 10.45.16.11 <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |–  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 und 131.107.155.21 <br/> **privat:** 10.45.16.20 und 10.45.16.21 <br/> |Eine externe Schnittstelle für Ihren Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |–  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 und 131.107.155.31 <br/> **privat:** 10.45.16.30 und 10.45.16.31 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Clients extern funktionieren. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern erforderlich, die als zulässige SIP-Domänen bezeichnet werden. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Datensatz  <br/> |–  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 und 172.25.33.11  <br/> |Die interne Schnittstelle für Ihren konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-Eintrag für Partnerverbund (alle Szenarien)

|**Ort**|**Type**|**Port**|**FQDN**|**FQDN-Hosteintrag**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Die externe SIP-Zugriffs-Edgeschnittstelle, die für die automatische DNS-Ermittlung erforderlich ist. Wird von Ihren anderen potenziellen Verbundpartnern verwendet. Sie wird auch als "SIP-Domänen zulassen" bezeichnet. Sie benötigen eine davon für jede SIP-Domäne mit Skype for Business Benutzern.  <br/><br/> **Hinweis:** Sie benötigen diesen SRV-Eintrag für Mobilität und das Clearing-House für Pushbenachrichtigungen. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-Einträge für erweiterbares Messaging- und Anwesenheitsprotokoll

|**Ort**|**Type**|**Port**|**FQDN**|**IP-Adresse oder FQDN-Hosteintrag**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |Die XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Sie müssen dies bei Bedarf für alle internen SIP-Domänen mit Skype for Business Server aktivierten Benutzern wiederholen, wobei der Kontakt mit XMPP-Kontakten über Folgendes zulässig ist:  <br/> • eine globale Richtlinie  <br/> • Eine Standortrichtlinie, bei der der Benutzer aktiviert ist  <br/> • eine Benutzerrichtlinie, die auf den Skype for Business Server aktivierten Benutzer angewendet wird  <br/> Eine zulässige XMPP-Richtlinie muss auch in der XMPP-Verbundbenutzerrichtlinie konfiguriert werden.  <br/> |
|Externes DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |IP-Adresse des Zugriffs-Edgediensts auf dem Edgeserver oder Edgepool, der Ihren XMPP-Proxydienst hostet  <br/> |Dies verweist auf den Zugriffs-Edgedienst auf dem Edgeserver oder Edgepool, der den XMPP-Proxydienst hostet. In der Regel verweist der SRV-Eintrag, den Sie erstellen, auf diesen Hosteintrag (A oder AAAA).  <br/> |
   
> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

## <a name="certificate-planning"></a>Zertifikatsplanung
<a name="CertPlan"> </a>

Skype for Business Server verwendet Zertifikate für die sichere und verschlüsselte Kommunikation zwischen Servern und von Server zu Client. Wie Sie erwarten, müssen ihre Zertifikate DNS-Einträge für Ihre Server mit einem beliebigen Antragstellernamen (SN) und alternativen Antragstellernamen (Subject Alternate Name, SAN) auf Ihren Zertifikaten übereinstimmen. Dies nimmt jetzt in der Planungsphase Arbeit in Anspruch, um sicherzustellen, dass Sie die richtigen FQDNs im DNS für die SN- und SAN-Einträge für Ihre Zertifikate registriert haben.
  
Wir werden externe und interne Zertifikatsanforderungen separat besprechen und dann eine Tabelle mit den Anforderungen für beides betrachten.
  
### <a name="external-certificates"></a>Externe Zertifikate

Das Ihren externen Edgeserverschnittstellen zugewiesene Zertifikat muss mindestens von einer öffentlichen Zertifizierungsstelle (Ca) bereitgestellt werden. Wir können Ihnen keine bestimmte Zertifizierungsstelle empfehlen, aber wir verfügen über eine Liste von Zertifizierungsstellen, [Unified Communications-Zertifikatpartnern,](../../../SfbPartnerCertification/certification/services-ssl.md) die Sie sich ansehen können, um festzustellen, ob Ihre bevorzugte Zertifizierungsstelle aufgeführt ist.
  
Wann müssen Sie eine Anforderung für dieses öffentliche Zertifikat an eine Zertifizierungsstelle senden, und wie führen Sie dies aus? Es gibt verschiedene Möglichkeiten, dies zu erreichen:
  
- Sie können die Installation von Skype for Business Server und dann die Edgeserverbereitstellung durchlaufen. Der Skype for Business Server Bereitstellungs-Assistent verfügt über einen Schritt zum Generieren einer Zertifikatanforderung, die Sie dann an die ausgewählte Zertifizierungsstelle senden können.
    
- Sie können auch Windows PowerShell Befehle verwenden, um diese Anforderung zu generieren, wenn dies mit Ihren Geschäftsanforderungen oder Ihrer Bereitstellungsstrategie inLine ist.
    
- Schließlich kann Ihre Zertifizierungsstelle über einen eigenen Übermittlungsprozess verfügen, der auch Windows PowerShell oder eine andere Methode umfassen kann. In diesem Fall müssen Sie sich zusätzlich zu den hier für Ihre Referenz bereitgestellten Informationen auf deren Dokumentation verlassen.
    
Nachdem Sie das Zertifikat abgerufen haben, müssen Sie es diesen Diensten in Skype for Business Server zuweisen:
  
- Zugriffs-Edgedienstschnittstelle
    
- Webkonferenz-Edgedienstschnittstelle
    
- Audio-/Videoauthentifizierungsdienst (verwechseln Sie dies nicht mit dem A/V-Edgedienst, da dieser kein Zertifikat zum Verschlüsseln von Audio- und Videodatenströmen verwendet)
    
> [!IMPORTANT]
> Alle Edgeserver (wenn sie zum selben Pool von Edgeservern gehören) müssen genau dasselbe Zertifikat mit demselben privaten Schlüssel für den Medienrelay-Authentifizierungsdienst besitzen. 
  
### <a name="internal-certificates"></a>Interne Zertifikate

Für die interne Edgeserverschnittstelle können Sie ein öffentliches Zertifikat von einer öffentlichen Zertifizierungsstelle oder ein von der internen Zertifizierungsstelle Ihrer Organisation ausgestelltes Zertifikat verwenden. Denken Sie an das interne Zertifikat daran, dass es einen SN-Eintrag und keine SAN-Einträge verwendet, sodass Sie sich überhaupt keine Gedanken über SAN im internen Zertifikat machen müssen.
  
### <a name="required-certificates-table"></a>Tabelle "Erforderliche Zertifikate"

Wir haben hier eine Tabelle, die Sie bei Ihren Anforderungen unterstützt. Die FQDN-Einträge hier gelten nur für Beispieldomänen. Sie müssen Anforderungen basierend auf Ihren eigenen privaten und öffentlichen Domänen stellen. Hier ist jedoch ein Leitfaden zu dem, was wir verwendet haben:
  
- <span></span>contoso.com: Öffentlicher FQDN
    
- fabrikam <span></span> .com: Zweiter öffentlicher FQDN (hinzugefügt als Demo, was angefordert werden soll, wenn Sie über mehrere SIP-Domänen verfügen)
    
- Contoso <span></span> .net: Interne Domäne
    
#### <a name="edge-certificate-table"></a>Edgezertifikatstabelle

Unabhängig davon, ob Sie einen einzelnen Edgeserver oder einen Edgepool ausführen, benötigen Sie dies für Ihr Zertifikat:
  
|**Komponente**|**Antragstellername (SN)**|**Alternative Antragstellernamen (SAN)/Reihenfolge**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Externer Edgeserver  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Dies ist das Zertifikat, das Sie von einer öffentlichen Zertifizierungsstelle anfordern müssen. Sie muss den externen Edgeschnittstellen für Folgendes zugewiesen werden:  <br/> • Zugriffs-Edge  <br/> • Webkonferenz-Edge  <br/> • Audio-/Videoauthentifizierung  <br/> <br/>Die gute Nachricht ist, dass SANs automatisch zu Ihrer Zertifikatsanforderung und damit ihrem Zertifikat hinzugefügt werden, nachdem Sie die Anforderung übermittelt haben, basierend auf dem, was Sie für diese Bereitstellung im Topologie-Generator definiert haben. Sie müssen nur SAN-Einträge für zusätzliche SIP-Domänen oder andere Einträge hinzufügen, die Sie unterstützen müssen. Warum wird sip.contoso.com in dieser Instanz repliziert? Dies geschieht auch automatisch und wird benötigt, damit alles ordnungsgemäß funktioniert.  <br/><br/> **Hinweis:** Dieses Zertifikat kann auch für die Verbindung mit öffentlichen Chatnachrichten verwendet werden. Sie müssen damit nichts anderes tun, aber in früheren Versionen dieser Dokumentation wurde sie als separate Tabelle aufgeführt, und jetzt ist dies nicht mehr der Fall. <br/> |
|Interner Edge  <br/> |sfbedge.contoso.com  <br/> |–  <br/> |Sie können dieses Zertifikat von einer öffentlichen Zertifizierungsstelle oder einer internen Zertifizierungsstelle abrufen. Sie muss die Server-EKU (Enhanced Key Usage) enthalten, und Sie weisen sie der internen Edgeschnittstelle zu.  <br/> |
   
Wenn Sie ein Zertifikat für XMPP (Extensible Messaging and Presence Protocol) benötigen, sieht es identisch mit den Einträgen in der Tabelle "Externer Edge" oben aus, weist jedoch die folgenden beiden zusätzlichen SAN-Einträge auf:
  
- xmpp. <span></span> contoso <span></span> .com
    
- \*<span></span>CONTOSO.com
    
Bitte beachten Sie, dass XMPP derzeit nur in Skype for Business Server für Google Talk unterstützt wird, wenn Sie es für andere Zwecke verwenden möchten oder müssen, müssen Sie diese Funktionalität bei dem betreffenden Drittanbieter bestätigen.
  
## <a name="port-and-firewall-planning"></a>Port- und Firewallplanung
<a name="PortFirewallPlan"> </a>

Wenn Sie die richtige Planung für Ports und Firewalls für Skype for Business Server Edgeserverbereitstellungen haben, können Sie Tage oder Wochen mit Problembehandlung und Stress sparen. Daher werden wir einige Tabellen auflisten, die unsere Protokollnutzung angeben und angeben, welche Ports sowohl für NAT- als auch für öffentliche IP-Szenarien geöffnet, ein- und ausgehend sein müssen. Wir werden auch separate Tabellen für Szenarien mit Hardwarelastenausgleich (Hardware Load Balanced Scenarios, HLB) und einige weitere Anleitungen dazu haben. Für weitere Informationen von dort haben wir auch einige [Edgeserverszenarien in Skype for Business Server](scenarios.md) Sie sich für Ihre speziellen Bereitstellungsprobleme informieren können.
  
### <a name="general-protocol-usage"></a>Allgemeine Protokollnutzung

Bevor wir uns die Zusammenfassungstabellen für externe und interne Firewalls ansehen, sehen wir uns auch die folgende Tabelle an:
  
|**Audio-/Videotransport**|**Nutzung**|
|:-----|:-----|
|UDP  <br/> |Das bevorzugte Transportschichtprotokoll für Audio und Video.  <br/> |
|TCP  <br/> |Das Fallback-Transportschichtprotokoll für Audio und Video.  <br/> Das erforderliche Transportschichtprotokoll für die Anwendungsfreigabe für Skype for Business Server, Lync Server 2013 und Lync Server 2010.  <br/> Das erforderliche Transportschichtprotokoll für die Dateiübertragung zu Skype for Business Server, Lync Server 2013 und Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Portfirewalls

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie personen, die öffentliche IP-Adressen verwenden. Dies deckt alle Variationen in unseren [Edgeserverszenarien in Skype for Business Server](scenarios.md) Abschnitt ab.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> In Skype for Business Server 2019 nicht unterstützt |TCP  <br/> |5269  <br/> |Any  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst  <br/> |Der XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbunden.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Any  <br/> |Zertifikatsperrung und CRL-Prüfung und -Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Any  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Any  <br/> |DNS-Abfrage über UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Client-zu-Server-SIP-Datenverkehr für externen Benutzerzugriff.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Für Verbund- und Verbindungen mit öffentlichen Chatdiensten mit SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Any  <br/> |Für Verbund- und Verbindungen mit öffentlichen Chatdiensten mit SIP.  <br/> |
|Webkonferenzen/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-Webkonferenz-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgediensts für Edgekonferenzen <br/> |Webkonferenzmedien.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |3478 ausgehend ist:  <br/> • Wird von Skype for Business Server verwendet, um die Version des Edgeservers zu bestimmen, mit dem sie kommuniziert.  <br/> • Wird für Mediendatenverkehr zwischen Edgeservern verwendet.  <br/> • Erforderlich für den Partnerverbund mit Lync Server 2010.  <br/> • Erforderlich, wenn mehrere Edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Portfirewalls

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Eine der folgenden Aktionen, die den XMPP-Gatewaydienst ausführen:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Ihrem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/> **Hinweis:** XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Jegliche:  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, Director-Pool, Front-End-Server oder Front-End-Pool zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interne Edgeserverschnittstelle  <br/> |Jegliche:  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Eingehender SIP-Datenverkehr zu Ihrem Director, Director-Pool, Front-End-Server oder Front-End-Pool von der internen Edgeserverschnittstelle aus.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Jegliche:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server  <br/>  in Ihrem Front-End-Pool <br/> |Interne Edgeserverschnittstelle  <br/> |Webkonferenzdatenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Jegliche:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> • Jede Survivable Branch Appliance, die diesen Edgeserver verwendet  <br/> • Jeder Survivable Branch-Server, der diesen Edgeserver verwendet  <br/> |Interne Edgeserverschnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrer Survivable Branch Appliance oder Dem Survivable Branch Server mithilfe Ihres Edgeservers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Dem Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder dem Survivable Branch Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und die Desktopfreigabe verwendet.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Jegliche:  <br/> • Front-End-Server mit dem zentralen Verwaltungsspeicher  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher enthält  <br/> |Interne Edgeserverschnittstelle  <br/> |Replikation von Änderungen von Ihrem zentralen Verwaltungsspeicher zu Ihrem Edgeserver.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienst-Controller mit Skype for Business Server Verwaltungsshell und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenbefehlen (ClsController.exe) oder Agentbefehlen (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienst-Controller mit Skype for Business Server Verwaltungsshell und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenbefehlen (ClsController.exe) oder Agentbefehlen (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienst-Controller mit Skype for Business Server Verwaltungsshell und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenbefehlen (ClsController.exe) oder Agentbefehlen (ClsAgent.exe) und Protokollsammlung.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Hardwaregeräte zum Lastenausgleich für Edgeporttabellen

Hardwaregeräte zum Lastenausgleich (HLBs) und Edgeports erhalten einen eigenen Abschnitt, da die Dinge mit der zusätzlichen Hardware etwas komplizierter sind. Eine Anleitung für dieses szenario finden Sie in den folgenden Tabellen:
  
#### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Portfirewalls

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie personen, die öffentliche IP-Adressen verwenden. Dies deckt alle Variationen in unseren [Edgeserverszenarien in Skype for Business Server](scenarios.md) Abschnitt ab.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts  <br/> |Any  <br/> |Zertifikatsperrung und CRL-Prüfung und -Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts  <br/> |Any  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts  <br/> |Any  <br/> |DNS-Abfrage über UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Ip-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |3478 ausgehend ist:  <br/> • Wird von Skype for Business Server verwendet, um die Version des Edgeservers zu bestimmen, mit dem sie kommuniziert.  <br/> • Wird für Mediendatenverkehr zwischen Edgeservern verwendet.  <br/> • Erforderlich für partnerverbunden.  <br/> • Erforderlich, wenn mehrere Edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Portfirewalls

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Eine der folgenden Aktionen, die den XMPP-Gatewaydienst ausführen:  <br/> • Front-End-Server  <br/> • VIP-Adresse des Front-End-Pools, auf der der XMPP-Gatewaydienst ausgeführt wird  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Ihrem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/><br/> **Hinweis:** XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md) |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Jegliche:  <br/> • Front-End-Server mit dem zentralen Verwaltungsspeicher  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher enthält  <br/> |Interne Edgeserverschnittstelle  <br/> |Replikation von Änderungen von Ihrem zentralen Verwaltungsspeicher zu Ihrem Edgeserver.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Jegliche:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Webkonferenzdatenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Jegliche:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Dem Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Jegliche:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder dem Survivable Branch Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und die Desktopfreigabe verwendet.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienst-Controller mit Skype for Business Server Verwaltungsshell und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenbefehlen (ClsController.exe) oder Agentbefehlen (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienst-Controller mit Skype for Business Server Verwaltungsshell und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenbefehlen (ClsController.exe) oder Agentbefehlen (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienst-Controller mit Skype for Business Server Verwaltungsshell und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenbefehlen (ClsController.exe) oder Agentbefehlen (ClsAgent.exe) und Protokollsammlung.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Virtuelle IPs für externe Schnittstellen

|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Any  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst)  <br/> |Der XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbunden.  <br/> |
|XMPP  <br/>Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst)  <br/> |Any  <br/> |Der XMPP-Proxydienst sendet Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbunden.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Client-zu-Server-SIP-Datenverkehr für externen Benutzerzugriff.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Für Verbund- und Verbindungen mit öffentlichen Chatdiensten mit SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mit NAT:** Edgeserver-Zugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Any  <br/> |Für Verbund- und Verbindungen mit öffentlichen Chatdiensten mit SIP.  <br/> |
|Webkonferenzen/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-Webkonferenz-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgediensts für Edgekonferenzen <br/> |Webkonferenzmedien.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Virtuelle IPs für interne Schnittstellen

Unsere Anleitung hier wird ein wenig anders sein. Tatsächlich wird in einer HLB-Situation jetzt empfohlen, dass Sie nur unter den folgenden Umständen eine interne VIP durchlaufen:
  
- Wenn Sie Exchange 2007 oder Exchange 2010 Unified Messaging (UM) verwenden.
    
- Wenn Sie Legacyclients verwenden, die Edge verwenden.
    
In der folgenden Tabelle finden Sie Anleitungen für diese Szenarien. Andernfalls sollten Sie sich auf den zentralen Verwaltungsspeicher (CMS) verlassen können, um Den Datenverkehr an den jeweiligen Edgeserver weiterzuleiten, den er kennt (dies erfordert natürlich, dass CMS über Edgeserverinformationen auf dem neuesten Stand ist).
  
|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Jegliche:  <br/> • Director  <br/> • VIP-Adresse des Directorpools  <br/> • Front-End-Server  <br/> • VIP-Adresse des Front-End-Pools  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, ihrer Director-Pool-VIP-Adresse, dem Front-End-Server oder der VIP-Adresse des Front-End-Pools zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interne VIP-Schnittstelle des Edgeservers  <br/> |Jegliche:  <br/> • Director  <br/> • VIP-Adresse des Directorpools  <br/> • Front-End-Server  <br/> • VIP-Adresse des Front-End-Pools  <br/> |Eingehender SIP-Datenverkehr an Ihren Director, die VIP-Adresse des Directorpools, den Front-End-Server oder die VIP-Adresse des Front-End-Pools von Ihrer internen Edgeserverschnittstelle aus.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Jegliche:  <br/> • IP-Adresse des Front-End-Servers  <br/> • IP-Adresse des Front-End-Pools  <br/> • Jede Survivable Branch Appliance, die diesen Edgeserver verwendet  <br/> • Jeder Survivable Branch-Server, der diesen Edgeserver verwendet  <br/> |Interne Edgeserverschnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrer Survivable Branch Appliance oder Dem Survivable Branch Server mithilfe Ihres Edgeservers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Interne VIP-Schnittstelle des Edgeservers  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und die Desktopfreigabe verwendet.  <br/> |