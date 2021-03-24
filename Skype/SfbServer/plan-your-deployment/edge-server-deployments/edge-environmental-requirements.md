---
title: Edgeserver-Umgebungsanforderungen in Skype for Business Server
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
ms.openlocfilehash: 8370fb2c8fa8a9b1d083ba336decd85715e31d25
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095019"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Edgeserver-Umgebungsanforderungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Umgebungsanforderungen für Edgeserver in Skype for Business Server.
  
Außerhalb der Skype for Business Server Edge Server-Umgebung selbst müssen viele Planungs- und Vorbereitungsarbeiten ausgeführt werden. In diesem Artikel werden wir überprüfen, welche Vorbereitungen in der Organisationsumgebung gemäß der folgenden Liste vorgenommen werden müssen:
  
- [Topologieplanung](edge-environmental-requirements.md#TopoPlan)
    
- [DNS-Planung](edge-environmental-requirements.md#DNSPlan)
    
- [Zertifikatplanung](edge-environmental-requirements.md#CertPlan)
    
- [Port- und Firewallplanung](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Topologieplanung
<a name="TopoPlan"> </a>

Skype for Business Server Edge Server-Topologien können:
  
- Routingfähige öffentliche IP-Adressen.
    
- Nicht routingfähige private IP-Adressen, wenn die symmetrische Netzwerkadressenübersetzung **(Symmetric** Network Address Translation, NAT) verwendet wird.
    
> [!TIP]
> Der Edgeserver kann so konfiguriert werden, dass er eine einzelne IP-Adresse mit unterschiedlichen Ports für jeden Dienst verwendet, oder er kann für jeden Dienst unterschiedliche IP-Adressen verwenden, aber denselben Standardport verwenden (der standardmäßig TCP 443 ist). Weitere Informationen finden Sie weiter unten im Abschnitt IP-Adressanforderungen. 
  
Wenn Sie nicht routingfähige private IP-Adressen mit NAT auswählen, beachten Sie die folgenden Punkte:
  
- Sie müssen routingfähige private IP-Adressen für **alle drei externen** Schnittstellen verwenden.
    
- Sie müssen symmetrische NAT **für** eingehenden und ausgehenden Datenverkehr konfigurieren. Symmetrische NAT ist die einzige unterstützte NAT, die Sie mit Skype for Business Server Edge Server verwenden können.
    
- Konfigurieren Sie ihre NAT so, dass eingehende Quelladressen nicht geändert werden. Der A/V-Edgedienst muss die eingehende Quelladresse empfangen können, um den optimalen Medienpfad zu finden.
    
- Ihre Edgeserver müssen über ihre öffentlichen A/V-Edge-IP-Adressen miteinander kommunizieren können. Ihre Firewall muss diesen Datenverkehr zulassen.
    
- NAT kann **nur** für skalierte konsolidierte Edgeserver verwendet werden, wenn Sie den DNS-Lastenausgleich verwenden. Wenn Sie den Hardwarelastenausgleich (Hardware Load Balancing, HLB) verwenden, müssen Sie öffentlich routingfähige #A0 **ohne** NAT verwenden.
    
Sie haben keine Probleme damit, dass Ihre Access-, Webkonferenz- und A/V-Edgeschnittstellen hinter einem Router oder einer Firewall symmetrische NAT für einzelne und skalierte konsolidierte Edgeservertopologien ausführen (solange Sie keinen Hardwarelastenausgleich verwenden).
  
### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Edgeservertopologieoptionen

Für Skype for Business Server Edge Server-Bereitstellungen stehen mehrere Topologieoptionen zur Verfügung:
  
- Einzelner konsolidierter Edge mit privaten IP-Adressen und NAT
    
- Einzelner konsolidierter Edge mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edge mit privaten IP-Adressen und NAT
    
- Skalierter konsolidierter Edge mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edge mit Hardwaregerät zum Lastenausgleich
    
Um Ihnen bei der Auswahl einer dieser Optionen zu helfen, finden Sie die folgende Tabelle, die eine Zusammenfassung der Optionen enthält, die Sie für jede Topologie haben:
  
|**Topologie**|**Hohe Verfügbarkeit**|**Zusätzliche DNS-Einträge für externen Edgeserver im Edgepool erforderlich?**|**Edgefailover für Skype for Business Server-Sitzungen**|**Edgefailover für Skype for Business Server-Verbundsitzungen**|
|:-----|:-----|:-----|:-----|:-----|
|Einzelner konsolidierter Edge mit privaten IP-Adressen und NAT  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Einzelner konsolidierter Edge mit öffentlichen IP-Adressen  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Skalierter konsolidierter Edge mit privaten IP-Adressen und NAT (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edge mit öffentlichen IP-Adressen (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edge mit Hardwaregerät zum Lastenausgleich  <br/> |Ja  <br/> |Nein (ein DNS A-Eintrag pro VIP)  <br/> |Ja  <br/> |Ja  <br/> |
   
&sup1; Exchange Unified Messaging (UM)-Remotebenutzerfailover mithilfe des DNS-Lastenausgleichs erfordert Exchange 2013 oder neuer.
  
### <a name="ip-address-requirements"></a>Anforderungen an IP-Adressen

Auf einer grundlegenden Ebene benötigen drei Dienste #A0 ; Access-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst. Sie haben die Möglichkeit, entweder drei IP-Adressen zu verwenden, eine für jeden Dienst, oder Sie können eine verwenden und entscheiden, jeden Dienst an einem anderen Port zu verwenden (Weitere Informationen dazu finden Sie im Abschnitt [Port-](edge-environmental-requirements.md#PortFirewallPlan) und Firewallplanung). Bei einer einzelnen konsolidierten Edgeumgebung ist dies ziemlich so.
  
> [!NOTE]
> Wie oben erwähnt, können Sie eine IP-Adresse für alle drei Dienste verwenden und diese an verschiedenen Ports ausführen. Dies wird jedoch nicht empfohlen, um es deutlich zu machen. Wenn Ihre Kunden nicht auf die alternativen Ports zugreifen können, die Sie in diesem Szenario verwenden würden, können sie auch nicht auf die volle Funktionalität Ihrer Edgeumgebung zugreifen. 
  
Es kann mit skalierten konsolidierten Topologien etwas komplizierter sein. Sehen wir uns also einige Tabellen an, in der die ANFORDERUNGEN für die IP-Adresse dargestellt sind, und berücksichtigen Wir dabei, dass die wichtigsten Entscheidungspunkte für die Topologieauswahl hohe Verfügbarkeit und Lastenausgleich sind. Anforderungen an hohe Verfügbarkeit können Sich auf Die Auswahl des Lastenausgleichs (wir werden nach den Tabellen mehr darüber sprechen) beeinflussen.
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressanforderungen für skalierten konsolidierten Edge (IP-Adresse pro Rolle)

|**Anzahl von Edgeservern pro Pool**|**Anzahl der erforderlichen IP-Adressen für den DNS-Lastenausgleich**|**Anzahl der erforderlichen IP-Adressen für den Hardwarelastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |6   <br/> |3 (1 pro VIP) + 6  <br/> |
|3  <br/> |9   <br/> |3 (1 pro VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 pro VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 pro VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Anforderungen an die IP-Adresse für den konsolidierten Edgeskalen (Einzelne IP-Adresse für alle Rollen)

|**Anzahl von Edgeservern pro Pool**|**Anzahl der erforderlichen IP-Adressen für den DNS-Lastenausgleich**|**Anzahl der erforderlichen IP-Adressen für den Hardwarelastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 pro VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 pro VIP) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 pro VIP) + 4  <br/> |
|5   <br/> |5  <br/> |1 (1 pro VIP) + 5  <br/> |
   
Sehen wir uns einige zusätzliche Dinge an, über die Sie bei der Planung nachdenken sollten.
  
- **Hohe Verfügbarkeit:** Wenn Sie hohe Verfügbarkeit in Ihrer Bereitstellung benötigen, sollten Sie mindestens zwei Edgeserver in einem Pool bereitstellen. Es ist erwähnenswert, dass ein einzelner Edgepool bis zu 12 Edgeserver unterstützt (obwohl der Topologie-Generator ihnen erlaubt, bis zu 20 hinzuzufügen, das ist nicht getestet oder unterstützt, daher raten wir Ihnen, dies nicht zu tun). Wenn Sie mehr als 12 Edgeserver benötigen, sollten Sie zusätzliche Edgepools für diese erstellen.
    
- **Hardwarelastenausgleich:** Für die meisten Szenarien wird der DNS-Lastenausgleich empfohlen. Der Hardwarelastenausgleich wird natürlich ebenfalls unterstützt, aber insbesondere ist er für ein einzelnes Szenario über den DNS-Lastenausgleich erforderlich:
    
  - Externer Zugriff auf Exchange 2007 oder Exchange 2010 (ohne SP) Unified Messaging (UM).
    
- **DNS-Lastenausgleich:** Für UM können Exchange 2010 SP1 und neuere vom DNS-Lastenausgleich unterstützt werden. Wenn Sie den DNS-Lastenausgleich für eine frühere Version von Exchange verwenden müssen, funktioniert dies, aber der ganze Datenverkehr dafür wird an den ersten Server im Pool gesendet, und wenn er nicht verfügbar ist, wird der Datenverkehr anschließend fehlschlagen.
    
    Der DNS-Lastenausgleich wird auch empfohlen, wenn Sie einen Verbund mit Unternehmen mit den:
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

Wenn es um die Bereitstellung von Skype for Business Server Edge Server geht, ist es wichtig, dass Sie sich ordnungsgemäß auf DNS vorbereiten. Wenn die richtigen Datensätze verwendet werden, ist die Bereitstellung wesentlich einfacher. Hoffentlich haben Sie im obigen Abschnitt eine Topologie ausgewählt, da wir eine Übersicht erstellen und dann einige Tabellen mit den DNS-Einträgen für diese Szenarien auflisten. Wir haben auch eine [erweiterte Edgeserver-DNS-Planung](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) für Skype for Business Server, um das Lesen zu vertiefen, falls Sie dies benötigen.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-Einträge für Einzelne konsolidierte Edgeserverszenarien

Dies sind die DNS-Einträge, die Sie für einen besingten Edgeserver benötigen, der entweder öffentliche IPs oder private IPs mit NAT verwendet. Da es sich um Beispieldaten handelt, geben wir Beispiel-IPs, damit Sie Ihre eigenen Einträge einfacher ausarbeiten können:
  
- Interner Netzwerkadapter: 172.25.33.10 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu allen Netzwerken vorhanden ist, die Server mit Skype for Business Server- oder Lync Server 2013-Clients enthalten (z. B. von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Öffentliche IPs:
    
  - Access Edge: 131.107.155.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren öffentlichen Router festgelegt ist, z. B.: 131.107.155.1)
    
  - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
  - A/V-Edge: 131.107.155.30 (sekundär)
    
  Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt Erweitert der Eigenschaften von Internet protocol Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Lokalen Verbindungseigenschaften in Windows Server.
    
  - Private IPs:
    
  - Access Edge: 10.45.16.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren Router festgelegt ist, z. B.: 10.45.16.1)
    
  - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
  - A/V-Edge: 10.45.16.30 (sekundär)
    
Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt Erweitert der Eigenschaften von Internet protocol Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Lokalen Verbindungseigenschaften in Windows Server.
  
> [!TIP]
>Es gibt hier weitere mögliche Konfigurationen:
  
- Sie können eine IP-Adresse auf dem externen Netzwerkadapter verwenden. Wir empfehlen dies nicht, da Sie dann zwischen den Diensten unterscheiden müssen, die unterschiedliche Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen dazu finden Sie im Abschnitt [Port-](edge-environmental-requirements.md#PortFirewallPlan) und Firewallplanung.
    
- Sie können anstelle eines externen Netzwerkadapters drei externe Netzwerkadapter verwenden und jedem Einzelnen einen der Dienst-IPs zuweisen. Warum sollte dies der Grund sein? Es würde die Dienste trennen, und wenn ein Fehler vorgeht, würde dies die Problembehandlung vereinfachen und ihre anderen Dienste möglicherweise weiter arbeiten lassen, während Sie ein Problem beheben.
    
|**Ort**|**Type**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 <br/> **privat:** 10.45.16.10 <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 <br/> **privat:** 10.45.16.20 <br/> |Eine externe Schnittstelle für Ihren Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 <br/> **privat:** 10.45.16.30 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Clients extern arbeiten können. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern erforderlich, die als zulässige SIP-Domänen bezeichnet werden. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Datensatz  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Die interne Schnittstelle für Den konsolidierten Edge.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS-Einträge für skalierte DNS- und Hardware-Edgeserverszenarien

Dies sind die DNS-Einträge, die Sie für einen besingten Edgeserver benötigen, der entweder öffentliche IPs oder private IPs mit NAT verwendet. Da es sich um Beispieldaten handelt, geben wir Beispiel-IPs, damit Sie Ihre eigenen Einträge einfacher ausarbeiten können:
  
- Interner Netzwerkadapter:
    
  - Knoten 1: 172.25.33.10 (kein Standardgateway zugewiesen)
    
  - Knoten 2: 172.25.33.11 (kein Standardgateway zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edgeschnittstelle zu allen Netzwerken vorhanden ist, die Server mit Skype for Business Server- oder Lync Server 2013-Clients enthalten (z. B. von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Knoten 1
    
     - Öffentliche IPs:
    
        - Access Edge: 131.107.155.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren öffentlichen Router festgelegt ist, z. B.: 131.107.155.1)
    
        - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
        - A/V-Edge: 131.107.155.30 (sekundär)
    
          Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt Erweitert der Eigenschaften von Internet protocol Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Lokalen Verbindungseigenschaften in Windows Server.
    
    - Private IPs:
    
         - Access Edge: 10.45.16.10 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren Router festgelegt ist, z. B.: 10.45.16.1)
    
         - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
         - A/V-Edge: 10.45.16.30 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt Erweitert der Eigenschaften von Internet protocol Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Lokalen Verbindungseigenschaften in Windows Server.
    
  - Knoten 2
    
    - Öffentliche IPs:
    
      - Access Edge: 131.107.155.11 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren öffentlichen Router festgelegt ist, z. B.: 131.107.155.1)
    
      - Webkonferenz-Edge: 131.107.155.21 (sekundär)
    
      - A/V-Edge: 131.107.155.31 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt Erweitert der Eigenschaften von Internet protocol Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Lokalen Verbindungseigenschaften in Windows Server.
    
  - Private IPs:
    
    - Access Edge: 10.45.16.11 (dies ist das primäre Gateway, bei dem das Standardgateway auf Ihren Router festgelegt ist, z. B.: 10.45.16.1)
    
    - Webkonferenz-Edge: 10.45.16.21 (sekundär)
    
    - A/V-Edge: 10.45.16.31 (sekundär)
    
      Webkonferenzen und öffentliche A/V-Edge-IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt Erweitert der Eigenschaften von Internet protocol Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Lokalen Verbindungseigenschaften in Windows Server.
    
Es gibt hier weitere mögliche Konfigurationen:
  
- Sie können eine IP-Adresse auf dem externen Netzwerkadapter verwenden. Wir empfehlen dies nicht, da Sie dann zwischen den Diensten unterscheiden müssen, die unterschiedliche Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen dazu finden Sie im Abschnitt [Port-](edge-environmental-requirements.md#PortFirewallPlan) und Firewallplanung.
    
- Sie können anstelle eines externen Netzwerkadapters drei externe Netzwerkadapter verwenden und jedem Einzelnen einen der Dienst-IPs zuweisen. Warum sollte dies der Grund sein? Es würde die Dienste trennen, und wenn ein Fehler vorgeht, würde dies die Problembehandlung vereinfachen und ihre anderen Dienste möglicherweise weiter arbeiten lassen, während Sie ein Problem beheben.
    
|**Ort**|**Type**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 und 131.107.155.11 <br/> **privat:** 10.45.16.10 und 10.45.16.11 <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 und 131.107.155.21 <br/> **privat:** 10.45.16.20 und 10.45.16.21 <br/> |Eine externe Schnittstelle für Ihren Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Datensatz  <br/> |NA  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 und 131.107.155.31 <br/> **privat:** 10.45.16.30 und 10.45.16.31 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Clients extern arbeiten können. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern erforderlich, die als zulässige SIP-Domänen bezeichnet werden. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Datensatz  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 und 172.25.33.11  <br/> |Die interne Schnittstelle für Den konsolidierten Edge.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-Eintrag für den Verbund (alle Szenarien)

|**Ort**|**Type**|**Port**|**FQDN**|**FQDN-Hostdatensatz**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Die externe SIP-Zugriffs-Edgeschnittstelle, die für die automatische DNS-Ermittlung erforderlich ist. Wird von Ihren anderen potenziellen Verbundpartnern verwendet. Es wird auch als "Zulassen von SIP-Domänen" bezeichnet. Sie benötigen eine davon für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/><br/> **Hinweis:** Sie benötigen diesen SRV-Eintrag für die Mobilität und die Pushbenachrichtigungs-Clearingstelle. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-Einträge für erweiterbares Messaging- und Anwesenheitsprotokoll

|**Ort**|**Type**|**Port**|**FQDN**|**IP-Adresse oder FQDN-Hostdatensatz**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |Die XMPP-Proxyschnittstelle in Ihrem Access Edge-Dienst oder Edgepool. Sie müssen dies bei Bedarf für alle internen SIP-Domänen mit aktivierten Skype for Business Server-Benutzern wiederholen, in denen Der Kontakt mit XMPP-Kontakten zulässig ist:  <br/> • eine globale Richtlinie  <br/> • eine Websiterichtlinie, bei der der Benutzer aktiviert ist  <br/> • eine Benutzerrichtlinie, die auf den aktivierten Skype for Business Server-Benutzer angewendet wird  <br/> Eine zulässige XMPP-Richtlinie muss auch in der XMPP-Verbundbenutzerrichtlinie konfiguriert werden.  <br/> |
|Externes DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |IP-Adresse des Zugriffs-Edgediensts auf dem Edgeserver oder Edgepool, der Ihren XMPP-Proxydienst hosten soll  <br/> |Dies verweist auf den Access-Edgedienst auf dem Edgeserver oder Edgepool, der den XMPP-Proxydienst hostet. In der Regel wird der von Ihnen erstellte SRV-Eintrag auf diesen Hostdatensatz (A oder AAAA) verweisen.  <br/> |
   
> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter Migrieren des [XMPP-Verbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

## <a name="certificate-planning"></a>Zertifikatsplanung
<a name="CertPlan"> </a>

Skype for Business Server verwendet Zertifikate für die sichere, verschlüsselte Kommunikation zwischen Servern und von Server zu Client. Wie Sie erwarten, müssen Ihre Zertifikate über DNS-Einträge für Ihre Server verfügen, die mit jedem Betreffnamen (Subject Name, SN) und dem alternativen Betreffnamen (Subject Alternate Name, SAN) in Ihren Zertifikaten übereinstimmen. Dies dauert jetzt in der Planungsphase, um sicherzustellen, dass die richtigen FQDNs für die SN- und SAN-Einträge für Ihre Zertifikate in DNS registriert sind.
  
Wir werden externe und interne Zertifikatanforderungen separat besprechen und uns dann eine Tabelle mit den Anforderungen für beides anschauen.
  
### <a name="external-certificates"></a>Externe Zertifikate

Das Den externen Edgeserverschnittstellen zugewiesene Zertifikat muss mindestens von einer öffentlichen Zertifizierungsstelle bereitgestellt werden. Wir können Ihnen keine bestimmte Zertifizierungsstelle empfehlen, aber wir verfügen über eine Liste der Zertifizierungsstellen, Unified Communications-Zertifikatpartner, die Sie sich anschauen können, um zu sehen, ob Ihre bevorzugte Zertifizierungsstelle aufgeführt ist. [](../../../SfbPartnerCertification/certification/services-ssl.md)
  
Wann müssen Sie eine Anforderung an eine Zertifizierungsstelle für dieses öffentliche Zertifikat senden, und wie wird dies gemacht? Es gibt mehrere Möglichkeiten, dies zu erreichen:
  
- Sie können die Installation von Skype for Business Server und dann die Edgeserverbereitstellung durchgehen. Der Skype for Business Server-Bereitstellungs-Assistent hat einen Schritt zum Generieren einer Zertifikatanforderung, die Sie dann an die ausgewählte Zertifizierungsstelle senden können.
    
- Sie können auch Windows PowerShell Befehlen verwenden, um diese Anforderung zu generieren, wenn dies ihren Geschäftlichen Anforderungen oder Ihrer Bereitstellungsstrategie besser entspricht.
    
- Schließlich verfügt Ihre Zertifizierungsstelle möglicherweise über einen eigenen Übermittlungsprozess, der auch eine Windows PowerShell oder eine andere Methode umfassen kann. In diesem Fall müssen Sie sich zusätzlich zu den hier angegebenen Informationen auf ihre Dokumentation verlassen.
    
Nachdem Sie das Zertifikat erhalten haben, müssen Sie es den folgenden Diensten in Skype for Business Server zuweisen:
  
- Access Edge-Dienstschnittstelle
    
- Webkonferenz-Edge-Dienstschnittstelle
    
- Audio-/Videoauthentifizierungsdienst (Verwechseln Sie dies nicht mit dem A/V-Edgedienst, da dieser kein Zertifikat zum Verschlüsseln von Audio- und Videodatenströmen verwendet)
    
> [!IMPORTANT]
> Alle Edgeserver (wenn sie zum gleichen Pool von Edgeservern gehören) benötigen dasselbe Zertifikat mit demselben privaten Schlüssel für den Medienrelaisauthentifizierungsdienst. 
  
### <a name="internal-certificates"></a>Interne Zertifikate

Für die interne Edgeserverschnittstelle können Sie ein öffentliches Zertifikat von einer öffentlichen Zertifizierungsstelle oder ein Von der internen Zertifizierungsstelle Ihrer Organisation ausgestelltes Zertifikat verwenden. Beachten Sie beim internen Zertifikat, dass es einen SN-Eintrag und keine #A0 verwendet, sodass Sie sich keine Gedanken über SAN auf dem internen Zertifikat machen müssen.
  
### <a name="required-certificates-table"></a>Tabelle "Erforderliche Zertifikate"

Wir haben hier eine Tabelle, die Ihnen bei Ihren Anforderungen hilft. Die FQDN-Einträge hier sind nur für Beispieldomänen. Sie müssen Anforderungen basierend auf Ihren eigenen privaten und öffentlichen Domänen stellen, aber hier finden Sie eine Anleitung zu den von uns verwendeten Informationen:
  
- contoso <span></span> .com: Öffentlicher FQDN
    
- fabrikam .com: Zweiter öffentlicher FQDN (als Demo hinzugefügt, was sie anfordern <span></span> müssen, wenn Sie über mehrere SIP-Domänen verfügen)
    
- Contoso <span></span> .net: Interne Domäne
    
#### <a name="edge-certificate-table"></a>Edgezertifikattabelle

Unabhängig davon, ob Sie einen einzelnen Edgeserver oder einen Edgepool verwenden, benötigen Sie dies für Ihr Zertifikat:
  
|**Komponente**|**Antragstellername (SN)**|**Alternative Betreffnamen (SAN)/Reihenfolge**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Externer Edge  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Dies ist das Zertifikat, das Sie von einer öffentlichen Zertifizierungsstelle anfordern müssen. Sie muss den externen Edgeschnittstellen für Folgendes zugewiesen werden:  <br/> • Access Edge  <br/> • Edge für Webkonferenzen  <br/> • Audio-/Videoauthentifizierung  <br/> <br/>Die gute Nachricht ist, dass SANs automatisch ihrer Zertifikatanforderung und damit Ihrem Zertifikat hinzugefügt werden, nachdem Sie die Anforderung übermittelt haben, basierend auf dem, was Sie für diese Bereitstellung im Topologie-Generator definiert haben. Sie müssen nur SAN-Einträge für zusätzliche SIP-Domänen oder andere Einträge hinzufügen, die Sie unterstützen müssen. Warum wird sip.contoso.com in dieser Instanz repliziert? Dies geschieht auch automatisch, und es ist erforderlich, damit die Dinge ordnungsgemäß funktionieren.  <br/><br/> **Hinweis:** Dieses Zertifikat kann auch für die Verbindung mit öffentlichen Instant Messaging verwendet werden. Sie müssen damit nichts anderes tun, aber in früheren Versionen dieser Dokumentation wurde sie als separate Tabelle aufgeführt, und jetzt nicht. <br/> |
|Interner Edge  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Sie können dieses Zertifikat von einer öffentlichen oder einer internen Zertifizierungsstelle erhalten. Sie muss die Server-EKU (Erweiterte Schlüsselverwendung) enthalten, und Sie weisen sie der internen Edgeschnittstelle zu.  <br/> |
   
Wenn Sie ein Zertifikat für das Extensible Messaging and Presence Protocol (XMPP) benötigen, sieht es identisch mit den obigen Einträgen der Externen Edgetabelle aus, hat jedoch die folgenden zwei zusätzlichen SAN-Einträge:
  
- xmpp. <span></span> contoso <span></span> .com
    
- \*.contoso <span></span> .com
    
Denken Sie daran, dass XMPP derzeit nur in Skype for Business Server für Google Talk unterstützt wird. Wenn Sie es für etwas anderes verwenden möchten oder müssen, müssen Sie diese Funktionalität mit dem beteiligten Drittanbieter bestätigen.
  
## <a name="port-and-firewall-planning"></a>Port- und Firewallplanung
<a name="PortFirewallPlan"> </a>

Wenn Sie Ihre Planung für Ports und Firewalls für Skype for Business Server Edge Server-Bereitstellungen richtig planen, können Sie Tage oder Wochen der Problembehandlung und des Stress sparen. Daher werden wir einige Tabellen auflisten, die unsere Protokollverwendung angeben und welche Ports für NAT- und öffentliche IP-Szenarien geöffnet, ein- und ausgehend sein müssen. Wir verfügen außerdem über separate Tabellen für Szenarien für den Hardwarelastenausgleich (Hardware Load Balanced, HLB) und einige weitere Anleitungen dazu. Weitere Informationen finden Sie auch in [einigen Edgeserverszenarien in Skype for Business Server,](scenarios.md) die Sie für Ihre speziellen Bereitstellungsbedenken prüfen können.
  
### <a name="general-protocol-usage"></a>Allgemeine Protokollverwendung

Bevor wir uns die Zusammenfassungstabellen für externe und interne Firewalls anschauen, sollten wir auch die folgende Tabelle berücksichtigen:
  
|**Audio-/Videotransport**|**Nutzung**|
|:-----|:-----|
|UDP  <br/> |Das bevorzugte Transportschichtprotokoll für Audio und Video.  <br/> |
|TCP  <br/> |Das Fallback-Transport-Layer-Protokoll für Audio und Video.  <br/> Das erforderliche Transportschichtprotokoll für die Anwendungsfreigabe an Skype for Business Server, Lync Server 2013 und Lync Server 2010.  <br/> Das erforderliche Transportschichtprotokoll für die Dateiübertragung an Skype for Business Server, Lync Server 2013 und Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Übersichtstabelle der Firewall für externe Ports

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie Personen, die öffentliche IP-Adressen verwenden. Dies wird alle Permutationen in unseren [Edgeserverszenarien in Skype for Business Server](scenarios.md) abdecken.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> In Skype for Business Server 2019 nicht unterstützt |TCP  <br/> |5269  <br/> |Any  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Access Edge-Dienst  <br/> |Der XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbundverbunden.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Any  <br/> |Zertifikatssperrung und CRL-Überprüfung und -Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Any  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Any  <br/> |DNS-Abfrage über UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Client-zu-Server-SIP-Datenverkehr für externen Benutzerzugriff.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Für Verbund- und Public -Im-Im-In-Verbindungen mithilfe von SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Any  <br/> |Für Verbund- und Public -Im-Im-In-Verbindungen mithilfe von SIP.  <br/> |
|Webkonferenzen/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver-Webkonferenz-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverwebkonferenz-Edgediensts <br/> |Webkonferenzmedien.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |Dies wird zum Relayn von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |Dies wird zum Relayn von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |3478 ausgehend ist:  <br/> • Wird von Skype for Business Server verwendet, um die Version des Edgeservers zu bestimmen, mit dem er kommuniziert.  <br/> • Wird für Mediendatenverkehr zwischen Edgeservern verwendet.  <br/> • Erforderlich für den Verbund mit Lync Server 2010.  <br/> • Erforderlich, wenn mehrere Edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |Any  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Übersichtstabelle der internen Portfirewall

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Einer der folgenden Ausgeführten des XMPP-Gatewaydiensts:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Ihrem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/> **Hinweis:** XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter Migrieren des [XMPP-Verbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Any:  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, Directorpool, Front-End-Server oder Front-End-Pool zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interne Edgeserverschnittstelle  <br/> |Any:  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Eingehender SIP-Datenverkehr zu Ihrem Director, Directorpool, Front-End-Server oder Front-End-Pool von Ihrer internen Edgeserverschnittstelle.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Any:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server  <br/>  im Front-End-Pool <br/> |Interne Edgeserverschnittstelle  <br/> |Webkonferenzdatenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Any:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> • Jede Survivable Branch Appliance, die diesen Edgeserver verwendet  <br/> • Jeder Survivable Branch Server, der diesen Edgeserver verwendet  <br/> |Interne Edgeserverschnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrer Survivable Branch Appliance oder Survivable Branch Server mithilfe Ihres Edgeservers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Survivable Branch Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Any:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher enthält  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher enthält  <br/> |Interne Edgeserverschnittstelle  <br/> |Replikation von Änderungen aus dem zentralen Verwaltungsspeicher auf den Edgeserver.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Hardwaregerät zum Lastenausgleich für Edgeporttabellen

Wir geben hardware load balancers (HLBs) und Edgeports einen eigenen Abschnitt, da die Dinge mit der zusätzlichen Hardware etwas komplizierter sind. Anleitungen zu diesem bestimmten Szenario finden Sie in den folgenden Tabellen:
  
#### <a name="external-port-firewall-summary-table"></a>Übersichtstabelle der Firewall für externe Ports

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie Personen, die öffentliche IP-Adressen verwenden. Dies wird alle Permutationen in unseren [Edgeserverszenarien in Skype for Business Server](scenarios.md) abdecken.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts  <br/> |Any  <br/> |Zertifikatssperrung und CRL-Überprüfung und -Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts  <br/> |Any  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts  <br/> |Any  <br/> |DNS-Abfrage über UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edgeserver-A/V-Edgedienst-IP-Adresse  <br/> |Any  <br/> |Dies wird zum Relayn von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |Dies wird zum Relayn von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |3478 ausgehend ist:  <br/> • Wird von Skype for Business Server verwendet, um die Version des Edgeservers zu bestimmen, mit dem er kommuniziert.  <br/> • Wird für Mediendatenverkehr zwischen Edgeservern verwendet.  <br/> • Erforderlich für den Verbund.  <br/> • Erforderlich, wenn mehrere Edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts  <br/> |Any  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Übersichtstabelle der internen Portfirewall

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Einer der folgenden Ausgeführten des XMPP-Gatewaydiensts:  <br/> • Front-End-Server  <br/> • Front-End-Pool-VIP-Adresse, unter der der XMPP-Gatewaydienst ausgeführt wird  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Ihrem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/><br/> **Hinweis:** XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter Migrieren des [XMPP-Verbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md) |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Any:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher enthält  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher enthält  <br/> |Interne Edgeserverschnittstelle  <br/> |Replikation von Änderungen aus dem zentralen Verwaltungsspeicher auf den Edgeserver.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Any:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Webkonferenzdatenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Front-End-Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Pool  <br/> |Interne Edgeserverschnittstelle  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern und Ihrer Survivable Branch Appliance oder Survivable Branch Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Zentraler Protokollierungsdienstcontroller mit Skype for Business Server Management Shell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollsammlung.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Externe Schnittstelle Virtuelle IPs

|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> In Skype for Businesss Server 2019 nicht unterstützt |TCP  <br/> |5269  <br/> |Any  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Access Edge-Dienst)  <br/> |Der XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbundverbunden.  <br/> |
|XMPP  <br/>In Skype for Businesss Server 2019 nicht unterstützt |TCP  <br/> |5269  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit dem Access Edge-Dienst)  <br/> |Any  <br/> |Der XMPP-Proxydienst sendet Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbundverbunden.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Client-zu-Server-SIP-Datenverkehr für externen Benutzerzugriff.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Für Verbund- und Public -Im-Im-In-Verbindungen mithilfe von SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mithilfe von NAT:** Edgeserverzugriffs-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverzugriffs-Edgediensts <br/> |Any  <br/> |Für Verbund- und Public -Im-Im-In-Verbindungen mithilfe von SIP.  <br/> |
|Webkonferenzen/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver-Webkonferenz-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserverwebkonferenz-Edgediensts <br/> |Webkonferenzmedien.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP an Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver-A/V-Edgedienst <br/> **Öffentliche IP:** Öffentliche IP-Adresse des Edgeserver-A/V-Edgediensts <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP an Port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Interne Schnittstelle Virtuelle IPs

Unsere Anleitung hier wird etwas anders sein. In einer #A0 wird nun empfohlen, nur unter folgenden Umständen über eine interne VIP zu routingn:
  
- Wenn Sie Exchange 2007 oder Exchange 2010 Unified Messaging (UM) verwenden.
    
- Wenn Sie über Legacyclients verfügen, die edge verwenden.
    
Die folgende Tabelle enthält Anleitungen für diese Szenarien. Andernfalls sollten Sie jedoch vom zentralen Verwaltungsspeicher (Central Management Store, CMS) abhängig sein, um Datenverkehr an den einzelnen Edgeserver weiter zu routen, der ihm bekannt ist (dies erfordert natürlich, dass CMS in Edgeserverinformationen auf dem neuesten Stand gehalten wird).
  
|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any:  <br/> • Director  <br/> • VIP-Adresse des Directorpools  <br/> • Front-End-Server  <br/> • Front-End-Pool-VIP-Adresse  <br/> |Interne Edgeserverschnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrer Director-, Directorpool-VIP-Adresse, Front-End-Server- oder Front-End-Pool-VIP-Adresse zu Ihrer internen Edgeserverschnittstelle.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interne VIP-Schnittstelle des Edgeservers  <br/> |Any:  <br/> • Director  <br/> • VIP-Adresse des Directorpools  <br/> • Front-End-Server  <br/> • Front-End-Pool-VIP-Adresse  <br/> |Eingehender SIP-Datenverkehr an Ihren Director, Die VIP-Adresse des Directorpools, den Front-End-Server oder die FRONT-End-Pool-VIP-Adresse von Ihrer internen Edgeserverschnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Any:  <br/> • Front-End-Server-IP-Adresse  <br/> • Front-End-Pool-IP-Adresse  <br/> • Jede Survivable Branch Appliance, die diesen Edgeserver verwendet  <br/> • Jeder Survivable Branch Server, der diesen Edgeserver verwendet  <br/> |Interne Edgeserverschnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrer Survivable Branch Appliance oder Survivable Branch Server mithilfe Ihres Edgeservers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Interne Edgeserverschnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen ihren internen und externen Benutzern.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Interne VIP-Schnittstelle des Edgeservers  <br/> |Fallbackpfad für die A/V-Medienübertragung zwischen ihren internen und externen Benutzern, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |