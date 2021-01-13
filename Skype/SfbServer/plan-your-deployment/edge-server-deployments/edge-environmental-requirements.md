---
title: Umgebungsanforderungen für Edgeserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Zusammenfassung: Erfahren Sie mehr über die Umgebungsanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: 3757a67d36260cce7d14ddf451a3a436429f24fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813835"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Umgebungsanforderungen für Edgeserver in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Umgebungsanforderungen für Edgeserver in Skype for Business Server.
  
Außerhalb der Skype for Business Server Edge Server-Umgebung selbst müssen viele Planungs- und Vorbereitungsarbeiten ausgeführt werden. In diesem Artikel überprüfen wir, welche Vorbereitungen in der Organisationsumgebung gemäß der folgenden Liste vorgenommen werden müssen:
  
- [Topologieplanung](edge-environmental-requirements.md#TopoPlan)
    
- [DNS-Planung](edge-environmental-requirements.md#DNSPlan)
    
- [Zertifikatplanung](edge-environmental-requirements.md#CertPlan)
    
- [Port- und Firewallplanung](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Topologieplanung
<a name="TopoPlan"> </a>

Skype for Business Server Edge Server-Topologien können:
  
- Routingfähige öffentliche IP-Adressen.
    
- Nicht routingfähige private IP-Adressen, wenn **symmetrische Netzwerkadressenübersetzung** (Network Address Translation, NAT) verwendet wird.
    
> [!TIP]
> Der Edgeserver kann für die Verwendung einer einzelnen IP-Adresse mit unterschiedlichen Ports für jeden Dienst konfiguriert werden, oder er kann für jeden Dienst unterschiedliche IP-Adressen verwenden, aber denselben Standardport verwenden (standardmäßig TCP 443). Weitere Informationen finden Sie weiter unten im Abschnitt "IP-Adressanforderungen". 
  
Wenn Sie nicht routingfähige private IP-Adressen mit NAT auswählen, beachten Sie die folgenden Punkte:
  
- Sie müssen routingfähige private IP-Adressen für **alle drei externen Schnittstellen** verwenden.
    
- Sie müssen symmetrische **NAT für** eingehenden und ausgehenden Datenverkehr konfigurieren. Symmetrische NAT ist die einzige unterstützte NAT, die Sie mit dem Skype for Business Server Edge Server verwenden können.
    
- Konfigurieren Sie die NAT so, dass eingehende Quelladressen nicht geändert werden. Der A/V-Edgedienst muss die eingehende Quelladresse empfangen können, um den optimalen Medienpfad zu finden.
    
- Ihre Edgeserver müssen über ihre öffentlichen A/V-Edge-IP-Adressen miteinander kommunizieren können. Ihre Firewall muss diesen Datenverkehr zulassen.
    
- NAT kann **nur** für skalierte konsolidierte Edgeserver verwendet werden, wenn Sie den DNS-Lastenausgleich verwenden. Wenn Sie Hardwarelastenausgleich (Hardware Load Balancing, HLB)  verwenden, müssen Sie öffentlich routingfähige #A0 ohne NAT verwenden.
    
Sie haben keine Probleme damit, dass Ihre Access-, Webkonferenz- und A/V-Edgeschnittstellen hinter einem Router oder einer Firewall symmetrische NAT für einzelne und skalierte konsolidierte Edgeservertopologien ausführen (solange Sie keinen Hardwarelastenausgleich verwenden).
  
### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Edgeservertopologieoptionen

Für Skype for Business Server Edge Server-Bereitstellungen stehen mehrere Topologieoptionen zur Verfügung:
  
- Einzelner konsolidierter Edge mit privaten IP-Adressen und NAT
    
- Einzelner konsolidierter Edge mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edge edge mit privaten IP-Adressen und NAT
    
- Skalierter konsolidierter Edge edge mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edge edge mit Hardwarelastenausgleich
    
Um Ihnen bei der Auswahl zu helfen, finden Sie in der folgenden Tabelle eine Zusammenfassung der Optionen, die Für jede Topologie zur Verfügung stehen:
  
|**Topologie**|**Hohe Verfügbarkeit**|**Zusätzliche DNS-Einträge, die für externe Edgeserver im Edgepool erforderlich sind?**|**Edgefailover für Skype for Business Server-Sitzungen**|**Edgefailover für Skype for Business Server-Verbundsitzungen**|
|:-----|:-----|:-----|:-----|:-----|
|Einzelner konsolidierter Edge mit privaten IP-Adressen und NAT  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Einzelner konsolidierter Edge mit öffentlichen IP-Adressen  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Skalierter konsolidierter Edge edge mit privaten IP-Adressen und NAT (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edge edge mit öffentlichen IP-Adressen (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edge edge mit Hardwarelastenausgleich  <br/> |Ja  <br/> |Nein (ein DNS A-Eintrag pro VIP)  <br/> |Ja  <br/> |Ja  <br/> |
   
&sup1; Das Failover von Exchange Unified Messaging (UM)-Remotebenutzern mithilfe des DNS-Lastenausgleichs erfordert Exchange 2013 oder eine neuere Version.
  
### <a name="ip-address-requirements"></a>Anforderungen an die IP-Adresse

Grundsätzlich benötigen drei Dienste #A0 Zugriff auf Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst. Sie haben die Möglichkeit, entweder drei IP-Adressen zu verwenden, eine für jeden der Dienste, oder Sie können [](edge-environmental-requirements.md#PortFirewallPlan) eine verwenden und sich dafür entscheiden, jeden Dienst an einem anderen Port zu verwenden (weitere Informationen hierzu finden Sie im Abschnitt zur Port- und Firewallplanung). Bei einer einzelnen konsolidierten Edgeumgebung ist dies ziemlich genau das.
  
> [!NOTE]
> Wie oben erwähnt, können Sie eine einzige IP-Adresse für alle drei Dienste verwenden und diese an unterschiedlichen Ports ausführen. Dies wird jedoch nicht empfohlen. Wenn Ihre Kunden nicht auf die alternativen Ports zugreifen können, die Sie in diesem Szenario verwenden würden, können sie auch nicht auf die gesamte Funktionalität Ihrer Edgeumgebung zugreifen. 
  
Da es bei skalierten konsolidierten Topologien etwas komplizierter sein kann, sehen wir uns einige Tabellen an, in der die Anforderungen an die IP-Adresse dargestellt sind, und beachten Sie dabei, dass die wichtigsten Entscheidungspunkte für die Topologieauswahl hohe Verfügbarkeit und Lastenausgleich sind. Anforderungen an die hohe Verfügbarkeit können Sich auf Ihre Entscheidung für den Lastenausgleich (wir werden nach den Tabellen noch mehr darüber sprechen) beeinflussen.
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Anforderungen an die IP-Adresse für skalierte konsolidierte Edgeadressen (IP-Adresse pro Rolle)

|**Anzahl von Edgeservern pro Pool**|**Anzahl der erforderlichen IP-Adressen für den DNS-Lastenausgleich**|**Anzahl der erforderlichen IP-Adressen für den Hardwarelastenausgleich**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 pro VIP) + 6  <br/> |
|3   <br/> |9   <br/> |3 (1 pro VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 pro VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 pro VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Anforderungen an die IP-Adresse für einen skalierten konsolidierten Edge (einzelne IP-Adresse für alle Rollen)

|**Anzahl von Edgeservern pro Pool**|**Anzahl der erforderlichen IP-Adressen für den DNS-Lastenausgleich**|**Anzahl der erforderlichen IP-Adressen für den Hardwarelastenausgleich**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 pro VIP) + 2  <br/> |
|3   <br/> |3   <br/> |1 (1 pro VIP) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 pro VIP) + 4  <br/> |
|5   <br/> |5  <br/> |1 (1 pro VIP) + 5  <br/> |
   
Sehen wir uns einige zusätzliche Dinge an, die bei der Planung zu überlegen sind.
  
- **Hohe Verfügbarkeit:** Wenn Sie hohe Verfügbarkeit in Ihrer Bereitstellung benötigen, sollten Sie mindestens zwei Edgeserver in einem Pool bereitstellen. Es ist erwähnenswert, dass ein einzelner Edgepool bis zu 12 Edgeserver unterstützt (obwohl der Topologie-Generator ihnen die Möglichkeit bietet, bis zu 20 hinzuzufügen, was nicht getestet oder unterstützt wird, daher raten wir davon ab). Wenn Sie mehr als 12 Edgeserver benötigen, sollten Sie zusätzliche Edgepools für diese erstellen.
    
- **Hardwarelastenausgleich:** Wir empfehlen für die meisten Szenarien den DNS-Lastenausgleich. Der Hardwarelastenausgleich wird natürlich auch unterstützt, ist aber vor allem für ein einzelnes Szenario über den DNS-Lastenausgleich erforderlich:
    
  - Externer Zugriff auf Exchange 2007 oder Exchange 2010 (ohne SP) Unified Messaging (UM).
    
- **DNS-Lastenausgleich:** Für UM können Exchange 2010 SP1 und neuere Vom DNS-Lastenausgleich unterstützt werden. Beachten Sie: Wenn Sie den DNS-Lastenausgleich für eine frühere Version von Exchange verwenden müssen, funktioniert dies, aber der datenverkehr wird zum ersten Server im Pool gesendet, und wenn er nicht verfügbar ist, wird der Datenverkehr anschließend fehlschlagen.
    
    Der DNS-Lastenausgleich wird auch empfohlen, wenn Sie einen Verbund mit Unternehmen unter Verwendung von:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 oder Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 oder Office 365
    
## <a name="dns-planning"></a>DNS-Planung
<a name="DNSPlan"> </a>

Wenn es um die Bereitstellung von Skype for Business Server Edge Server geht, ist es wichtig, dass Sie sich ordnungsgemäß auf DNS vorbereiten. Wenn die richtigen Datensätze zur Hand sind, ist die Bereitstellung viel einfacher. Hoffentlich haben Sie im obigen Abschnitt eine Topologie ausgewählt, da wir eine Übersicht erstellen und dann einige Tabellen mit den DNS-Einträgen für diese Szenarien auflisten werden. Wir haben auch einige [erweiterte Edgeserver-DNS-Planungen](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) für Skype for Business Server, die Sie bei Bedarf genauer lesen können.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-Einträge für Szenarien mit einem einzelnen konsolidierten Edgeserver

Dies sind die DNS-Einträge, die Sie für einen eigenen Edgeserver mit öffentlichen IPs oder privaten IPs mit NAT benötigen. Da es sich um Beispieldaten handelt, geben wir Ihnen Beispiel-IPs, damit Sie Ihre eigenen Einträge einfacher ausarbeiten können:
  
- Interner Netzwerkadapter: 172.25.33.10 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu allen Netzwerken vorhanden ist, die Server mit Skype for Business Server- oder Lync Server 2013-Clients enthalten (z. B. von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Öffentliche IPs:
    
  - Zugriffs-Edge: 131.107.155.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren öffentlichen Router festgelegt ist, z. B.: 131.107.155.1)
    
  - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
  - A/V-Edge: 131.107.155.30 (sekundär)
    
  Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokoll, Version 4 (TCP/IPv4) und Internetprotokoll, Version 6 (TCP/IPv6), der Eigenschaften der lokalen Verbindung in Windows Server.
    
  - Private IPs:
    
  - Zugriffs-Edge: 10.45.16.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren Router festgelegt ist, z. B.: 10.45.16.1)
    
  - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
  - A/V-Edge: 10.45.16.30 (sekundär)
    
Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokoll, Version 4 (TCP/IPv4) und Internetprotokoll, Version 6 (TCP/IPv6), der Eigenschaften der lokalen Verbindung in Windows Server.
  
> [!TIP]
>Es gibt hier weitere mögliche Konfigurationen:
  
- Sie können eine einzige IP-Adresse auf dem externen Netzwerkadapter verwenden. Dies wird nicht empfohlen, da Sie dann zwischen den Diensten unterscheiden müssen, die unterschiedliche Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen finden Sie im Abschnitt zur [Port-](edge-environmental-requirements.md#PortFirewallPlan) und Firewallplanung.
    
- Sie können anstelle eines externen Netzwerkadapters drei externe Netzwerkadapter verwenden und jedem einen der Dienst-IPs zuweisen. Warum sollte dies der Grund sein? Es würde die Dienste trennen, und wenn ein Fehler vorgeht, wäre die Problembehandlung einfacher, und ihre anderen Dienste könnten möglicherweise weiter funktionieren, während Sie ein Problem beheben.
    
|**Ort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |Eine externe Schnittstelle für Ihren Zugriffs-Edgedienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |Eine externe Schnittstelle für den Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **privat:** 10.45.16.30 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Zugriffs-Edgedienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Clients extern arbeiten können. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Zugriffs-Edgedienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern erforderlich, die als "Zugelassene SIP-Domänen" bezeichnet werden. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Datensatz  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Die interne Schnittstelle für Den konsolidierten Edge.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS-Einträge für Skalierte DNS- und Hardware-Edgeserver-Szenarien

Dies sind die DNS-Einträge, die Sie für einen eigenen Edgeserver mit öffentlichen IPs oder privaten IPs mit NAT benötigen. Da es sich um Beispieldaten handelt, geben wir Ihnen Beispiel-IPs, damit Sie Ihre eigenen Einträge einfacher ausarbeiten können:
  
- Interner Netzwerkadapter:
    
  - Knoten 1: 172.25.33.10 (kein Standardgateway zugewiesen)
    
  - Knoten 2: 172.25.33.11 (kein Standardgateway zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu allen Netzwerken vorhanden ist, die Server mit Skype for Business Server- oder Lync Server 2013-Clients enthalten (z. B. von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Knoten 1
    
     - Öffentliche IPs:
    
        - Zugriffs-Edge: 131.107.155.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren öffentlichen Router festgelegt ist, z. B.: 131.107.155.1)
    
        - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
        - A/V-Edge: 131.107.155.30 (sekundär)
    
          Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokoll, Version 4 (TCP/IPv4) und Internetprotokoll, Version 6 (TCP/IPv6), der Eigenschaften der lokalen Verbindung in Windows Server.
    
    - Private IPs:
    
         - Zugriffs-Edge: 10.45.16.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren Router festgelegt ist, z. B.: 10.45.16.1)
    
         - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
         - A/V-Edge: 10.45.16.30 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokoll, Version 4 (TCP/IPv4) und Internetprotokoll, Version 6 (TCP/IPv6), der Eigenschaften der lokalen Verbindung in Windows Server.
    
  - Knoten 2
    
    - Öffentliche IPs:
    
      - Zugriffs-Edge: 131.107.155.11 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren öffentlichen Router festgelegt ist, z. B.: 131.107.155.1)
    
      - Webkonferenz-Edge: 131.107.155.21 (sekundär)
    
      - A/V-Edge: 131.107.155.31 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokoll, Version 4 (TCP/IPv4) und Internetprotokoll, Version 6 (TCP/IPv6), der Eigenschaften der lokalen Verbindung in Windows Server.
    
  - Private IPs:
    
    - Zugriffs-Edge: 10.45.16.11 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren Router festgelegt ist, z. B.: 10.45.16.1)
    
    - Webkonferenz-Edge: 10.45.16.21 (sekundär)
    
    - A/V-Edge: 10.45.16.31 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt "Erweitert" der Eigenschaften von Internetprotokoll, Version 4 (TCP/IPv4) und Internetprotokoll, Version 6 (TCP/IPv6), der Eigenschaften der lokalen Verbindung in Windows Server.
    
Es gibt hier weitere mögliche Konfigurationen:
  
- Sie können eine einzige IP-Adresse für den externen Netzwerkadapter verwenden. Dies wird nicht empfohlen, da Sie dann zwischen den Diensten unterscheiden müssen, die unterschiedliche Ports verwenden (dies ist in Skype for Business Server der Fall), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen finden Sie im Abschnitt zur [Port-](edge-environmental-requirements.md#PortFirewallPlan) und Firewallplanung.
    
- Sie können anstelle eines externen Netzwerkadapters drei externe Netzwerkadapter verwenden und jeder einen der Dienst-IPs zuweisen. Warum sollte dies der Grund sein? Es würde die Dienste trennen, und wenn ein Fehler vorgeht, würde dies die Problembehandlung vereinfachen und möglicherweise dazu sorgen, dass Ihre anderen Dienste weiterhin funktionieren, während Sie ein Problem beheben.
    
|**Ort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 und 131.107.155.11 <br/> **privat:** 10.45.16.10 und 10.45.16.11 <br/> |Eine externe Schnittstelle für Ihren Zugriffs-Edgedienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 und 131.107.155.21 <br/> **privat:** 10.45.16.20 und 10.45.16.21 <br/> |Eine externe Schnittstelle für den Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 und 131.107.155.31 <br/> **privat:** 10.45.16.30 und 10.45.16.31 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Zugriffs-Edgedienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Clients extern arbeiten können. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Zugriffs-Edgedienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern erforderlich, die als "Zugelassene SIP-Domänen" bezeichnet werden. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Datensatz  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 und 172.25.33.11  <br/> |Die interne Schnittstelle für Den konsolidierten Edge.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-Eintrag für Den Verbund (alle Szenarien)

|**Ort**|**Typ**|**Port**|**FQDN**|**FQDN-Hostdatensatz**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Die externe Schnittstelle des SIP-Zugriffs-Edge, die für die automatische DNS-Ermittlung erforderlich ist. Wird von Ihren anderen potenziellen Verbundpartnern verwendet. Sie wird auch als "SIP-Domänen zulassen" bezeichnet. Sie benötigen eine dieser Domänen für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/><br/> **Hinweis:** Sie benötigen diesen SRV-Eintrag für Mobilität und das Clearing house für Pushbenachrichtigungen. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-Einträge für das erweiterbare Messaging- und Anwesenheitsprotokoll

|**Ort**|**Typ**|**Port**|**FQDN**|**IP-Adresse oder FQDN-Hostdatensatz**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |Die XMPP-Proxyschnittstelle in Ihrem Zugriffs-Edgedienst oder Edgepool. Sie müssen dies bei Bedarf für alle internen SIP-Domänen mit skype for Business Server-aktivierten Benutzern wiederholen, über die Der Kontakt mit den XMPP-Kontakten zulässig ist:  <br/> • eine globale Richtlinie  <br/> • eine Standortrichtlinie, bei der der Benutzer aktiviert ist  <br/> • Eine Benutzerrichtlinie, die auf den für Skype for Business Server aktivierten Benutzer angewendet wird  <br/> Eine zulässige XMPP-Richtlinie muss auch in der Richtlinie für XMPP-Verbundbenutzer konfiguriert werden.  <br/> |
|Externes DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Die IP-Adresse des Zugriffs-Edgediensts auf dem Edgeserver oder Edgepool, der ihren XMPP-Proxydienst hosten soll  <br/> |Dies verweist auf den Zugriffs-Edgedienst auf dem Edgeserver oder Edgepool, der den XMPP-Proxydienst hostet. In der Regel wird der von Ihnen erstellten SRV-Eintrag auf diesen Hostdatensatz (A oder AAAA) verweisen.  <br/> |
   
> [!NOTE]
> XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

## <a name="certificate-planning"></a>Zertifikatsplanung
<a name="CertPlan"> </a>

Skype for Business Server verwendet Zertifikate für sichere, verschlüsselte Kommunikation zwischen Servern und von Server zu Client. Wie Sie erwarten, müssen Ihre Zertifikate über DNS-Einträge für Ihre Server verfügen, die mit einem beliebigen Subject Name (SN) und alternativen Subject Name (SAN) in Ihren Zertifikaten übereinstimmen. Dies dauert jetzt in der Planungsphase, um sicherzustellen, dass sie über die richtigen FQDNs verfügen, die in DNS für die Einträge "SN" und "SAN" für Ihre Zertifikate registriert sind.
  
Wir werden externe und interne Zertifikatanforderungen separat besprechen und uns dann eine Tabelle mit den Anforderungen für beides anschauen.
  
### <a name="external-certificates"></a>Externe Zertifikate

Das Ihren externen Edgeserverschnittstellen zugewiesene Zertifikat muss mindestens von einer öffentlichen Zertifizierungsstelle bereitgestellt werden. Wir können Ihnen keine bestimmte Zertifizierungsstelle empfehlen, aber wir haben eine Liste der Zertifizierungsstellen, Unified Communications-Zertifikatpartner, die Sie sich anschauen können, um zu sehen, ob Ihre bevorzugte Zertifizierungsstelle aufgeführt ist. [](/SkypeForBusiness/certification/services-ssl)
  
Wann müssen Sie eine Anforderung für dieses öffentliche Zertifikat an eine Zertifizierungsstelle senden, und wie gehen Sie dazu vor? Es gibt verschiedene Möglichkeiten, dies zu erreichen:
  
- Sie können die Installation von Skype for Business Server und dann die Edgeserverbereitstellung durchgehen. Der Skype for Business Server-Bereitstellungs-Assistent hat einen Schritt zum Generieren einer Zertifikatanforderung, die Sie dann an die ausgewählte Zertifizierungsstelle senden können.
    
- Sie können auch Windows PowerShell verwenden, um diese Anforderung zu generieren, wenn dies besser mit Ihren Geschäftsanforderungen oder ihrer Bereitstellungsstrategie inLine ist.
    
- Schließlich verfügt Ihre Zertifizierungsstelle möglicherweise über einen eigenen Übermittlungsprozess, der auch eine Windows PowerShell oder eine andere Methode beinhalten kann. In diesem Fall müssen Sie sich auf ihre Dokumentation verlassen, zusätzlich zu den hier bereitgestellten Informationen für Ihre Referenz.
    
Nachdem Sie das Zertifikat erhalten haben, müssen Sie es diesen Diensten in Skype for Business Server zuweisen:
  
- Schnittstelle des Zugriffs-Edgediensts
    
- Schnittstelle des Webkonferenz-Edgediensts
    
- Audio-/Videoauthentifizierungsdienst (verwechseln Sie dies nicht mit dem A/V-Edgedienst, da er kein Zertifikat zum Verschlüsseln von Audio- und Videostreams verwendet)
    
> [!IMPORTANT]
> Alle Edgeserver (wenn sie zum gleichen Pool von Edgeservern gehören) benötigen genau dasselbe Zertifikat mit demselben privaten Schlüssel für den Media Relay-Authentifizierungsdienst. 
  
### <a name="internal-certificates"></a>Interne Zertifikate

Für die interne Edgeserverschnittstelle können Sie ein öffentliches Zertifikat von einer öffentlichen Zertifizierungsstelle oder ein Zertifikat verwenden, das von der internen Zertifizierungsstelle Ihrer Organisation ausgestellt wurde. Beachten Sie beim internen Zertifikat, dass es einen #A0 und keine #A1 verwendet, sodass Sie sich keine Gedanken über SAN im internen Zertifikat machen müssen.
  
### <a name="required-certificates-table"></a>Tabelle "Erforderliche Zertifikate"

Wir haben eine Tabelle hier, die Ihnen bei Ihren Anforderungen hilft. Die hier angezeigten FQDN-Einträge sind nur für Beispieldomänen verfügbar. Sie müssen Anforderungen basierend auf Ihren eigenen privaten und öffentlichen Domänen stellen, aber hier ist ein Leitfaden zu den verwendeten Bereichen:
  
- contoso <span></span> .com: Öffentlicher FQDN
    
- fabrikam .com: Zweiter öffentlicher FQDN (als Demo hinzugefügt, was sie anfordern müssen, wenn Sie <span></span> mehrere SIP-Domänen haben)
    
- Contoso <span></span> .net: Interne Domäne
    
#### <a name="edge-certificate-table"></a>Edgezertifikattabelle

Unabhängig davon, ob Sie einen einzelnen Edgeserver oder Edgepool verwenden, benötigen Sie für Ihr Zertifikat dies:
  
|**Komponente**|**Antragstellername (SN)**|**Alternative Subject Names (SAN)/Order**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Externer Edge  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Dies ist das Zertifikat, das Sie von einer öffentlichen Zertifizierungsstelle anfordern müssen. Es muss den externen Edgeschnittstellen für Folgendes zugewiesen werden:  <br/> • Zugriffskante  <br/> • Webkonferenz-Edge  <br/> • Audio-/Videoauthentifizierung  <br/> <br/>Die gute Nachricht ist, dass SANs automatisch zu Ihrer Zertifikatanforderung und damit zu Ihrem Zertifikat hinzugefügt werden, nachdem Sie die Anforderung übermittelt haben, basierend auf dem, was Sie für diese Bereitstellung im Topologie-Generator definiert haben. Sie müssen nur einträge für den san für alle zusätzlichen SIP-Domänen oder andere Einträge hinzufügen, die Sie unterstützen müssen. Warum wird sip.contoso.com in dieser Instanz repliziert? Dies geschieht auch automatisch, und es ist erforderlich, damit alles ordnungsgemäß funktioniert.  <br/><br/> **Hinweis:** Dieses Zertifikat kann auch für Verbindungen mit öffentlichen Chats verwendet werden. Sie müssen damit nichts anderes tun, aber in früheren Versionen dieser Dokumentation wurde sie als separate Tabelle aufgeführt, und jetzt ist dies nicht der Weise. <br/> |
|Interner Edge  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Sie können dieses Zertifikat von einer öffentlichen oder einer internen Zertifizierungsstelle erhalten. Sie muss die Server-EKU (Erweiterte Schlüsselverwendung) enthalten, und Sie weisen sie der internen Edgeschnittstelle zu.  <br/> |
   
If you need a certificate for Extensible Messaging and Presence Protocol (XMPP), it will look identical to the External Edge table entries above, but will have the following two additional SAN entries:
  
- xmpp. <span></span> contoso <span></span> .com
    
- \*.contoso <span></span> .com
    
Bitte beachten Sie, dass XMPP derzeit nur in Skype for Business Server für Google Talk unterstützt wird. Wenn Sie es für etwas anderes verwenden möchten oder müssen, müssen Sie diese Funktionalität mit dem beteiligten Drittanbieter bestätigen.
  
## <a name="port-and-firewall-planning"></a>Port- und Firewallplanung
<a name="PortFirewallPlan"> </a>

Wenn Sie ihre Planung für Ports und Firewalls für Skype for Business Server Edge Server-Bereitstellungen richtig planen, können Sie tage- oder wochenlang Problembehandlung und Stress sparen. Daher werden wir eine Reihe von Tabellen auflisten, in denen die Protokollverwendung und die Ports aufgeführt werden, die sowohl für NAT- als auch für öffentliche IP-Szenarien geöffnet, ein- und ausgehend sein müssen. Wir haben auch separate Tabellen für Szenarien mit Hardwarelastenausgleich (Hardware Load Balanced Scenarios, HLB) und einige weitere Anleitungen dazu. Weitere Informationen finden Sie auch in einigen [Edgeserverszenarien in Skype for Business Server,](scenarios.md) die Sie für Ihre speziellen Bereitstellungsbedenken auschecken können.
  
### <a name="general-protocol-usage"></a>Allgemeine Protokollverwendung

Bevor wir uns die Zusammenfassungstabellen für externe und interne Firewalls betrachten, sehen wir uns auch die folgende Tabelle an:
  
|**Audio-/Videotransport**|**Verwendung**|
|:-----|:-----|
|UDP  <br/> |Das bevorzugte Transportschichtprotokoll für Audio und Video.  <br/> |
|TCP  <br/> |Das Fallback-Transport-Layer-Protokoll für Audio und Video.  <br/> Das erforderliche Transportschichtprotokoll für die Anwendungsfreigabe an Skype for Business Server, Lync Server 2013 und Lync Server 2010.  <br/> Das erforderliche Transportschichtprotokoll für die Dateiübertragung an Skype for Business Server, Lync Server 2013 und Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle der Firewall für externe Ports

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie für Personen, die öffentliche IP-Adressen verwenden. Dies wird alle Permutationen in unseren [Edgeserverszenarien im Abschnitt "Skype for Business Server"](scenarios.md) abdecken.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Nicht unterstützt in Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Beliebig  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst  <br/> |Der XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbunds.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Beliebig  <br/> |Zertifikatsperrung und CrL-Überprüfung und -Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Beliebig  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Beliebig  <br/> |DNS-Abfrage über UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Für Verbindungen mit Partner- und öffentlichen Verbindungen mit öffentlichen Verbindungen mithilfe von SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Beliebig  <br/> |Für Verbindungen mit Partner- und öffentlichen Verbindungen mit öffentlichen Verbindungen mithilfe von SIP.  <br/> |
|Webkonferenzen/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver-Webkonferenz-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Webkonferenz-Edgediensts <br/> |Webkonferenzmedien.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Beliebig  <br/> |3478 ausgehende Nachrichten:  <br/> • Wird von Skype for Business Server verwendet, um die Version des Edgeservers zu ermitteln, mit dem er kommuniziert.  <br/> • Wird für Mediendatenverkehr zwischen Edgeservern verwendet.  <br/> • Erforderlich für den Verbund mit Lync Server 2010.  <br/> • Erforderlich, wenn mehrere Edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Beliebig  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle der internen Portfirewall

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Einer der folgenden Schritte, auf dem der XMPP-Gatewaydienst ausgeführt wird:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Dem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/> **Hinweis:** XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../SfBServer2019/migration/migrating-xmpp-federation.md)|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Beliebige:  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, Director-Pool, Front-End-Server oder Front-End-Pool zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interne Edgeserverschnittstelle  <br/> |Beliebige:  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Eingehender SIP-Datenverkehr an Den Director, Directorpool, Front-End-Server oder Front-End-Pool von Der internen Edgeserverschnittstelle.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Beliebige:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server  <br/>  in Ihrem Front-End-Pool <br/> |Interne Edgeserverschnittstelle  <br/> |Webkonferenzdatenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Beliebige:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> • Jede Survivable Branch Appliance, die diesen Edgeserver verwendet  <br/> • Jeder Survivable Branch Server, der diesen Edgeserver verwendet  <br/> |Interne Edgeserverschnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrer Survivable Branch Appliance oder Ihrem Survivable Branch Server mithilfe des Edgeservers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die Übertragung von A/V-Medien zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Ihrem Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Ihrem Survivable Branch Server, wenn die Kommunikation mit der UdP nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Beliebige:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher enthält  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher enthält  <br/> |Interne Edgeserverschnittstelle  <br/> |Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeilenbefehle (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeilenbefehle (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeilenbefehle (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Hardwaregeräte zum Lastenausgleich für Edgeporttabellen

Wir geben Hardwaregeräte zum Lastenausgleich (HLBs) und Edgeports einen eigenen Abschnitt, da die Zusätzliche Hardware etwas komplizierter ist. Eine Anleitung zu diesem bestimmten Szenario finden Sie in den folgenden Tabellen:
  
#### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle der Firewall für externe Ports

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie für Personen, die öffentliche IP-Adressen verwenden. Dies wird alle Permutationen in unseren [Edgeserverszenarien im Abschnitt "Skype for Business Server"](scenarios.md) abdecken.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts  <br/> |Beliebig  <br/> |Zertifikatsperrung und CrL-Überprüfung und -Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts  <br/> |Beliebig  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts  <br/> |Beliebig  <br/> |DNS-Abfrage über UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edgeserver-A/V-Edgedienst-IP-Adresse  <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Beliebig  <br/> |3478 ausgehende Nachrichten:  <br/> • Wird von Skype for Business Server verwendet, um die Version des Edgeservers zu ermitteln, mit dem er kommuniziert.  <br/> • Wird für Mediendatenverkehr zwischen Edgeservern verwendet.  <br/> • Erforderlich für den Verbund.  <br/> • Erforderlich, wenn mehrere Edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Beliebig  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle der internen Portfirewall

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Einer der folgenden Schritte, auf dem der XMPP-Gatewaydienst ausgeführt wird:  <br/> • Front-End-Server  <br/> • Vip-Adresse des Front-End-Pools, unter der der XMPP-Gatewaydienst ausgeführt wird  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Dem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/><br/> **Hinweis:** XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../SfBServer2019/migration/migrating-xmpp-federation.md) |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Beliebige:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher enthält  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher enthält  <br/> |Interne Edgeserverschnittstelle  <br/> |Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Beliebige:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Webkonferenzdatenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebige:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die Übertragung von A/V-Medien zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Ihrem Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebige:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Ihrem Survivable Branch Server, wenn die Kommunikation mit der UdP nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeilenbefehle (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeilenbefehle (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeilenbefehle (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Virtuelle IPs der externen Schnittstelle

|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Beliebig  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst)  <br/> |Der XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbunds.  <br/> |
|XMPP  <br/>Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst)  <br/> |Beliebig  <br/> |Der XMPP-Proxydienst sendet Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbunds.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Für Verbindungen mit Partner- und öffentlichen Verbindungen mit öffentlichen Verbindungen mithilfe von SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mit NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Zugriffs-Edgediensts <br/> |Beliebig  <br/> |Für Verbindungen mit Partner- und öffentlichen Verbindungen mit öffentlichen Verbindungen mithilfe von SIP.  <br/> |
|Webkonferenzen/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver-Webkonferenz-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-Webkonferenz-Edgediensts <br/> |Webkonferenzmedien.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Virtuelle IPs der internen Schnittstelle

Unsere Anleitung hier wird ein wenig anders sein. Tatsächlich empfehlen wir in einer #A0 jetzt, dass Sie das Routing nur über eine interne VIP unter den folgenden Umständen verwenden:
  
- Wenn Sie Exchange 2007 oder Exchange 2010 Unified Messaging (UM) verwenden.
    
- Wenn Sie über Legacyclients verfügen, die Edge verwenden.
    
Die folgende Tabelle enthält Anleitungen für diese Szenarien. Andernfalls sollten Sie jedoch vom zentralen Verwaltungsspeicher (CmS) abhängig sein, um Datenverkehr an den einzelnen Edgeserver weiterleiten zu können, der ihm bekannt ist (dies erfordert natürlich, dass CMS über Edgeserverinformationen auf dem neuesten Stand gehalten wird).
  
|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebige:  <br/> • Director  <br/> • Vip-Adresse des Directorpools  <br/> • Front-End-Server  <br/> • Front-End-Pool-VIP-Adresse  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, der DIRECTOR-Pool-VIP-Adresse, dem Front-End-Server oder der VIP-Adresse des Front-End-Pools zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interne VIP-Schnittstelle des Edgeservers  <br/> |Beliebige:  <br/> • Director  <br/> • Vip-Adresse des Directorpools  <br/> • Front-End-Server  <br/> • Front-End-Pool-VIP-Adresse  <br/> |Eingehender SIP-Datenverkehr an Den Director, die VIP-Adresse des Directorpools, den Front-End-Server oder die Vip-Adresse des Front-End-Pools von Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Beliebige:  <br/> • Front-End-Server-IP-Adresse  <br/> • Front-End-Pool-IP-Adresse  <br/> • Jede Survivable Branch Appliance, die diesen Edgeserver verwendet  <br/> • Jeder Survivable Branch Server, der diesen Edgeserver verwendet  <br/> |Interne Edgeserverschnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrer Survivable Branch Appliance oder Ihrem Survivable Branch Server mithilfe des Edgeservers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die Übertragung von A/V-Medien zwischen Ihren internen und externen Benutzern.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |Interne VIP-Schnittstelle des Edgeservers  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern, wenn die Kommunikation mit udP nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
