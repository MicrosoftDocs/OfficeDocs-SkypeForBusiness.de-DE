---
title: Edgeserver Umgebungsanforderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Hier finden Sie Informationen zu den Umgebungsanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: 8e2ec6d2afc53648fe50af4cd5ab02ad21d11643
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219925"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Edgeserver Umgebungsanforderungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Umgebungsanforderungen für Edgeserver in Skype for Business Server.
  
Viel Planung und Vorbereitung müssen außerhalb der Skype for Business Server Edgeserver Umgebung selbst erfolgen. In diesem Artikel erfahren Sie, welche Vorbereitungen in der Organisationsumgebung getroffen werden müssen, wie in der folgenden Liste aufgeführt:
  
- [Planen der Topologie](edge-environmental-requirements.md#TopoPlan)
    
- [DNS-Planung](edge-environmental-requirements.md#DNSPlan)
    
- [Zertifikatplanung](edge-environmental-requirements.md#CertPlan)
    
- [Planung von Ports und Firewalls](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planen der Topologie
<a name="TopoPlan"> </a>

Skype for Business Server Edgeserver Topologien können Folgendes verwenden:
  
- Routingfähige öffentliche IP-Adressen.
    
- Nicht routingfähige private IP-Adressen, wenn die **symmetrische** Netzwerkadressübersetzung (NAT) verwendet wird.
    
> [!TIP]
> Ihr Edgeserver kann so konfiguriert werden, dass für jeden Dienst eine einzelne IP-Adresse mit verschiedenen Ports verwendet wird, oder es kann unterschiedliche IP-Adressen für jeden Dienst verwenden, aber den gleichen Standardport verwenden (standardmäßig TCP 443). Weitere Informationen finden Sie unter IP Address Requirements Section. 
  
Wenn Sie nicht routingfähige private IP-Adressen mit NAT auswählen, denken Sie daran, diese Punkte zu beachten:
  
- Sie müssen routingfähige private IP-Adressen für **alle drei** externen Schnittstellen verwenden.
    
- Sie müssen **symmetrische** NAT für eingehenden und ausgehenden Datenverkehr konfigurieren. Symmetrische NAT ist die einzige unterstützte NAT, die Sie mit Skype for Business Server Edgeserver verwenden können.
    
- Konfigurieren Sie Ihre NAT so, dass eingehende Quelladressen nicht geändert werden. Die A/V-Edgedienst muss in der Lage sein, die eingehende Quelladresse zu erhalten, um den optimalen Medienpfad zu finden.
    
- Ihre Edgeserver müssen in der Lage sein, miteinander aus ihren öffentlichen A/V-Edge-IP-Adressen zu kommunizieren. Die Firewall muss diesen Datenverkehr zulassen.
    
- NAT kann **nur** für skalierte konsolidierte Edgeserver verwendet werden, wenn Sie den DNS-Lastenausgleich verwenden. Wenn Sie den Hardwarelastenausgleich (Hardware Lastenausgleich, HLB) verwenden, müssen Sie öffentlich routingfähige IP-Adressen **ohne** NAT verwenden.
    
Sie haben keine Probleme mit ihren Zugriffs-, Webkonferenz-und A/V-Edge-Schnittstellen hinter einem Router oder einer Firewall, die symmetrische NAT für einzelne und skalierte konsolidierte Edgeserver Topologien ausführt (sofern Sie keinen Hardwarelastenausgleich verwenden).
  
### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Optionen für Edgeserver Topologie

Für Skype for Business Server Edgeserver-Bereitstellungen stehen verschiedene Topologie-Optionen zur Verfügung:
  
- Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit Hardwaregeräten zum Lastenausgleich
    
Um Ihnen bei der Auswahl behilflich zu sein, finden Sie in der folgenden Tabelle eine Übersicht über die Optionen, die Sie für die einzelnen Topologien haben:
  
|**Topologie**|**Hohe Verfügbarkeit**|**Zusätzliche DNS-Einträge für externe Edgeserver im Edgepool erforderlich?**|**Edge-Failover für Skype for Business Server Sitzungen**|**Edge-Failover für Skype for Business Server Verbund Sitzungen**|
|:-----|:-----|:-----|:-----|:-----|
|Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit Hardwaregeräten zum Lastenausgleich  <br/> |Ja  <br/> |Nein (ein DNS A-Eintrag pro VIP)  <br/> |Ja  <br/> |Ja  <br/> |
   
&sup1; Für Exchange Unified Messaging (um) Remotebenutzer Failover mithilfe des DNS-Lastenausgleichs ist Exchange 2013 oder neuer erforderlich.
  
### <a name="ip-address-requirements"></a>IP-Adressanforderungen

Auf einer grundlegenden Ebene benötigen drei Dienste IP-Adressen; Zugriffs-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst. Sie haben die Möglichkeit, entweder drei IP-Adressen zu verwenden, einen für jeden der Dienste, oder Sie können einen verwenden und sich dafür entscheiden, jeden Dienst auf einen anderen Port zu setzen (Sie können auch den Abschnitt [Port and Firewall Planning](edge-environmental-requirements.md#PortFirewallPlan) lesen, um weitere Informationen zu diesem Thema zu erhalten). Für eine einzelne konsolidierte Edge-Umgebung ist das ziemlich viel.
  
> [!NOTE]
> Wie oben erwähnt, können Sie eine IP-Adresse für alle drei Dienste auswählen und diese auf verschiedenen Ports ausführen. Aber um es deutlich zu machen, wird dies nicht empfohlen. Wenn Ihre Kunden nicht auf die alternativen Ports zugreifen können, die Sie in diesem Szenario verwenden würden, können Sie auch nicht auf die vollständige Funktionalität Ihrer Edge-Umgebung zugreifen. 
  
Es kann ein wenig komplizierter mit skalierten konsolidierten Topologien sein, schauen wir uns also einige Tabellen an, in denen die IP-Adressanforderungen festgelegt sind, wobei berücksichtigt wird, dass die primären Entscheidungspunkte für die Topologie-Auswahl hohe Verfügbarkeit und Lastenausgleich sind. Hohe Verfügbarkeit kann Einfluss auf die Auswahl des Lastenausgleichs haben (wir sprechen darüber nach den Tabellen).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressanforderungen für einen skalierten konsolidierten Edgeserver (IP-Adresse pro Rolle)

|**Anzahl von Edgeservern pro Pool**|**Anzahl erforderlicher IP-Adressen für den DNS-Lastenausgleich**|**Anzahl erforderlicher IP-Adressen für den Hardware Lastenausgleich**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 pro VIP) + 6  <br/> |
|3  <br/> |9   <br/> |3 (1 pro VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 pro VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 pro VIP) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>IP-Adressanforderungen für den konsolidierten Skalierungs Edgeserver (einzelne IP-Adresse für alle Rollen)

|**Anzahl von Edgeservern pro Pool**|**Anzahl erforderlicher IP-Adressen für den DNS-Lastenausgleich**|**Anzahl erforderlicher IP-Adressen für den Hardware Lastenausgleich**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 pro VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 pro VIP) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 pro VIP) + 4  <br/> |
|5   <br/> |5  <br/> |1 (1 pro VIP) + 5  <br/> |
   
Im folgenden finden Sie einige zusätzliche Aspekte, die Sie bei der Planung berücksichtigen sollten.
  
- **Hohe Verfügbarkeit**: Wenn Sie hohe Verfügbarkeit in Ihrer Bereitstellung benötigen, sollten Sie mindestens zwei Edgeserver in einem Pool bereitstellen. Es sollte darauf hingewiesen werden, dass ein einzelnes Edgepool bis zu 12 Edgeserver unterstützt (obwohl der Topologie-Generator Ihnen das Hinzufügen von bis zu 20 ermöglichen wird, das nicht getestet oder unterstützt wird, deshalb raten wir Ihnen, dies nicht zu tun). Wenn Sie mehr als 12 Edgeserver benötigen, sollten Sie zusätzliche Edge-Pools für diese Server erstellen.
    
- **Hardware Lastenausgleich**: für die meisten Szenarien wird der DNS-Lastenausgleich empfohlen. Der Hardware Lastenausgleich wird natürlich auch unterstützt, aber er ist für ein einzelnes Szenario über den DNS-Lastenausgleich erforderlich:
    
  - Externer Zugriff auf Exchange 2007 oder Exchange 2010 (ohne SP) Unified Messaging (um).
    
- **DNS-Lastenausgleich**: für um können Exchange 2010 SP1 und neuer von DNS-Lastenausgleich unterstützt werden. Beachten Sie, dass es funktioniert, wenn Sie mit dem DNS-Lastenausgleich für eine frühere Version von Exchange wechseln müssen, aber der gesamte Datenverkehr wird an den ersten Server im Pool übertragen, und wenn er nicht verfügbar ist, wird der Datenverkehr anschließend fehlschlagen.
    
    Der DNS-Lastenausgleich wird auch empfohlen, wenn Sie mit Unternehmen zusammenarbeiten:
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

Wenn es um die Skype for Business Server Edgeserver-Bereitstellung geht, ist es wichtig, die DNS ordnungsgemäß vorzubereiten. Da die richtigen Datensätze vorhanden sind, ist die Bereitstellung wesentlich einfacher. Hoffentlich haben Sie eine Topologie im obigen Abschnitt ausgewählt, da wir eine Übersicht durchführen und dann eine Reihe von Tabellen auflisten, in denen die DNS-Einträge für diese Szenarien skizziert werden. Wir haben auch einige [Erweiterte Edgeserver DNS-Planung für Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) für eine ausführlichere Lektüre, wenn Sie Sie benötigen.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-Einträge für einzelne konsolidierte Edgeserver Szenarien

Dabei handelt es sich um die DNS-Einträge, die Sie für einen singe-Edgeserver benötigen, die entweder öffentliche IPS oder private IPS mit NAT verwenden. Da es sich hierbei um Beispieldaten handelt, geben wir Beispiel-IPS, damit Sie Ihre eigenen Einträge einfacher bearbeiten können:
  
- Interner Netzwerkadapter: 172.25.33.10 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit Skype for Business Server oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist. 
  
- Externer Netzwerkadapter:
    
  - Öffentliche IPS:
    
  - Zugriffs-Edge: 131.107.155.10 (Dies ist die primäre, wobei das Standardgateway auf Ihren öffentlichen Router festgelegt ist, ex: 131.107.155.1)
    
  - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
  - A/V-Edge: 131.107.155.30 (sekundär)
    
  Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internetprotokoll Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) der Eigenschaften für die LAN-Verbindung in Windows Server.
    
  - Private IPS:
    
  - Zugriffs-Edge: 10.45.16.10 (Dies ist die primäre, mit dem Standardgateway auf Ihren Router festgelegt, ex: 10.45.16.1)
    
  - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
  - A/V-Edge: 10.45.16.30 (sekundär)
    
Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internetprotokoll Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) der Eigenschaften für die LAN-Verbindung in Windows Server.
  
> [!TIP]
>Es gibt weitere mögliche Konfigurationen:
  
- Sie können eine IP-Adresse für den externen Netzwerkadapter verwenden. Dies wird nicht empfohlen, da Sie dann zwischen den Thee-Diensten unterschiedlicher Ports unterscheiden müssen (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen hierzu finden Sie im Abschnitt [Port and Firewall Planning](edge-environmental-requirements.md#PortFirewallPlan) .
    
- Sie können über drei externe Netzwerkadapter anstelle von einem verfügen und jedem ein Dienst-IPS zuweisen. Warum? Es würde die Dienste trennen, und wenn etwas schief geht, würde dies die Problembehandlung erleichtern und möglicherweise Ihre anderen Dienste weiter arbeiten lassen, während Sie ein Problem lösen.
    
|**Standort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Einen Datensatz  <br/> |NA  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 <br/> **Privat:** 10.45.16.10 <br/> |Eine externe Schnittstelle für ihre Zugriffs-Edgedienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Einen Datensatz  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 <br/> **Privat:** 10.45.16.20 <br/> |Eine externe Schnittstelle für Ihre Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Einen Datensatz  <br/> |NA  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 <br/> **Privat:** 10.45.16.30 <br/> |Eine externe Schnittstelle für Ihre A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für ihre Zugriffs-Edgedienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server, lync Server 2013 und lync Server 2010 Clients extern arbeiten können. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für ihre Zugriffs-Edgedienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern mit dem Namen zugelassene SIP-Domänen erforderlich. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Interne DNS-Konfiguration  <br/> |Einen Datensatz  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Die interne Schnittstelle für den konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS-Einträge für skalierte DNS-und Hardware Edgeserver Szenarien

Dabei handelt es sich um die DNS-Einträge, die Sie für einen singe-Edgeserver benötigen, die entweder öffentliche IPS oder private IPS mit NAT verwenden. Da es sich hierbei um Beispieldaten handelt, geben wir Beispiel-IPS, damit Sie Ihre eigenen Einträge einfacher bearbeiten können:
  
- Interner Netzwerkadapter:
    
  - Knoten 1:172.25.33.10 (kein Standardgateway zugewiesen)
    
  - Knoten 2:172.25.33.11 (kein Standardgateway zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit Skype for Business Server oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist. 
  
- Externer Netzwerkadapter:
    
  - Knoten 1
    
     - Öffentliche IPS:
    
        - Zugriffs-Edge: 131.107.155.10 (Dies ist die primäre, wobei das Standardgateway auf Ihren öffentlichen Router festgelegt ist, ex: 131.107.155.1)
    
        - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
        - A/V-Edge: 131.107.155.30 (sekundär)
    
          Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internetprotokoll Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) der Eigenschaften für die LAN-Verbindung in Windows Server.
    
    - Private IPS:
    
         - Zugriffs-Edge: 10.45.16.10 (Dies ist die primäre, mit dem Standardgateway auf Ihren Router festgelegt, ex: 10.45.16.1)
    
         - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
         - A/V-Edge: 10.45.16.30 (sekundär)
    
      Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internetprotokoll Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) der Eigenschaften für die LAN-Verbindung in Windows Server.
    
  - Knoten 2
    
    - Öffentliche IPS:
    
      - Zugriffs-Edge: 131.107.155.11 (Dies ist die primäre, wobei das Standardgateway auf Ihren öffentlichen Router festgelegt ist, ex: 131.107.155.1)
    
      - Webkonferenz-Edge: 131.107.155.21 (sekundär)
    
      - A/V-Edge: 131.107.155.31 (sekundär)
    
      Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internetprotokoll Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) der Eigenschaften für die LAN-Verbindung in Windows Server.
    
  - Private IPS:
    
    - Zugriffs-Edge: 10.45.16.11 (Dies ist die primäre, mit dem Standardgateway auf Ihren Router festgelegt, ex: 10.45.16.1)
    
    - Webkonferenz-Edge: 10.45.16.21 (sekundär)
    
    - A/V-Edge: 10.45.16.31 (sekundär)
    
      Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internetprotokoll Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) der Eigenschaften für die LAN-Verbindung in Windows Server.
    
Es gibt weitere mögliche Konfigurationen:
  
- Sie können eine IP-Adresse für den externen Netzwerkadapter verwenden. Dies wird nicht empfohlen, da Sie dann zwischen den Thee-Diensten unterschiedlicher Ports unterscheiden müssen (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen hierzu finden Sie im Abschnitt [Port and Firewall Planning](edge-environmental-requirements.md#PortFirewallPlan) .
    
- Sie können über drei externe Netzwerkadapter anstelle von einem verfügen und jedem ein Dienst-IPS zuweisen. Warum? Es würde die Dienste trennen, und wenn etwas schief geht, würde dies die Problembehandlung erleichtern und möglicherweise Ihre anderen Dienste weiter arbeiten lassen, während Sie ein Problem lösen.
    
|**Standort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Einen Datensatz  <br/> |NA  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 und 131.107.155.11 <br/> **Privat:** 10.45.16.10 und 10.45.16.11 <br/> |Eine externe Schnittstelle für ihre Zugriffs-Edgedienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Einen Datensatz  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 und 131.107.155.21 <br/> **Privat:** 10.45.16.20 und 10.45.16.21 <br/> |Eine externe Schnittstelle für Ihre Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Einen Datensatz  <br/> |NA  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 und 131.107.155.31 <br/> **Privat:** 10.45.16.30 und 10.45.16.31 <br/> |Eine externe Schnittstelle für Ihre A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für ihre Zugriffs-Edgedienst. Dieser SRV-Eintrag ist erforderlich, damit Skype for Business Server, lync Server 2013 und lync Server 2010 Clients extern arbeiten können. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für ihre Zugriffs-Edgedienst. Dieser SRV-Eintrag ist für die automatische DNS-Ermittlung von Verbundpartnern mit dem Namen zugelassene SIP-Domänen erforderlich. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Interne DNS-Konfiguration  <br/> |Einen Datensatz  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 und 172.25.33.11  <br/> |Die interne Schnittstelle für den konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-Eintrag für den Verbund (alle Szenarien)

|**Standort**|**Typ**|**Port**|**FQDN**|**FQDN-Hosteintrag**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Die externe SIP-Zugriffs-Edge-Schnittstelle, die für die automatische DNS-Ermittlung erforderlich ist. Wird von den anderen potenziellen Partnerverbund Partnern verwendet. Er wird auch als "SIP-Domänen zulassen" bezeichnet. Sie benötigen eine dieser für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/><br/> **Hinweis:** Sie benötigen diesen SRV-Eintrag für Mobility und das Push Notification Clearing House. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-Einträge für das Extensible Messaging and Presence Protocol

|**Standort**|**Typ**|**Port**|**FQDN**|**IP-Adresse oder FQDN-Hosteintrag**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-Server. _tcp. contoso. com  <br/> |xmpp.contoso.com  <br/> |Die XMPP-Proxyschnittstelle auf Ihrem Zugriffs-Edgedienst oder Edgepool. Sie müssen dies bei Bedarf für alle internen SIP-Domänen mit Skype for Business Server aktivierten Benutzern wiederholen, wobei der Kontakt mit XMPP-Kontakten über Folgendes zulässig ist:  <br/> • eine globale Richtlinie  <br/> • eine Standortrichtlinie, in der der Benutzer aktiviert ist  <br/> • eine Benutzerrichtlinie, die auf den Skype for Business Server aktivierten Benutzers angewendet wird  <br/> Eine zulässige XMPP-Richtlinie muss auch in der XMPP-Verbundbenutzer Richtlinie konfiguriert werden.  <br/> |
|Externes DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edgepool Hosten Ihres XMPP-Proxy Diensts  <br/> |Dies verweist auf den Zugriffs-Edgedienst auf dem Edgeserver oder Edgepool, der den XMPP-Proxy Dienst hostet. Normalerweise zeigt der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (a oder AAAA).  <br/> |
   
> [!NOTE]
> XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Zertifikatsplanung
<a name="CertPlan"> </a>

Skype for Business Server verwendet Zertifikate für sichere, verschlüsselte Kommunikation zwischen Servern und vom Server zum Client. Wie Sie erwarten, müssen ihre Zertifikate DNS-Einträge für Ihre Server haben, die mit jedem Antragstellernamen (SN) und dem alternativen Antragstellernamen (San) auf ihren Zertifikaten übereinstimmen. Dies wird nun in der Planungsphase funktionieren, um sicherzustellen, dass Sie die richtigen FQDNs in DNS für die Einträge SN und San für Ihre Zertifikate registriert haben.
  
Wir besprechen externe und interne Zertifikatanforderungen separat und sehen uns dann eine Tabelle an, die die Anforderungen für beide bereitstellt.
  
### <a name="external-certificates"></a>Externe Zertifikate

Das Zertifikat, das Ihren externen Edgeserver-Schnittstellen zugewiesen ist, muss mindestens von einer öffentlichen Zertifizierungsstelle (Certification Authority, ca) bereitgestellt werden. Wir können Ihnen keine bestimmte Zertifizierungsstelle empfehlen, aber wir haben eine Liste mit CAS, [Unified Communications Zertifikat Partnern](/SkypeForBusiness/certification/services-ssl) , die Sie sich ansehen können, um zu sehen, ob Ihre bevorzugte Zertifizierungsstelle aufgeführt ist.
  
Wann müssen Sie eine Anforderung an eine Zertifizierungsstelle für dieses öffentliche Zertifikat senden, und wie tun Sie dies? Es gibt mehrere Möglichkeiten, dies zu erreichen:
  
- Sie können die Installation von Skype for Business Server und dann die Edgeserver-Bereitstellung durchlaufen. Der Assistent für die Skype for Business Server-Bereitstellung enthält einen Schritt zum Generieren einer Zertifikatanforderung, die Sie dann an die ausgewählte Zertifizierungsstelle senden können.
    
- Sie können auch Windows PowerShell Befehle verwenden, um diese Anforderung zu generieren, wenn dies mehr Inline mit Ihren geschäftlichen Anforderungen oder der Bereitstellungsstrategie ist.
    
- Schließlich kann Ihre Zertifizierungsstelle über einen eigenen Übermittlungsprozess verfügen, der auch Windows PowerShell oder eine andere Methode beinhalten kann. In diesem Fall müssen Sie sich zusätzlich zu den hier zur Verfügung gestellten Informationen auf Ihre Dokumentation verlassen.
    
Nachdem Sie das Zertifikat erhalten haben, müssen Sie es den folgenden Diensten in Skype for Business Server zuweisen:
  
- Zugriffs-Edgedienst-Schnittstelle
    
- Webkonferenz-Edgedienst-Schnittstelle
    
- Audio/Video-Authentifizierungsdienst (nicht mit dem A/V-Edgedienst verwechseln, da dies kein Zertifikat zum Verschlüsseln von Audio-und Videodatenströmen verwendet)
    
> [!IMPORTANT]
> Alle Edgeserver (wenn Sie zum selben Pool von Edgeserver gehören) benötigen genau dasselbe Zertifikat mit demselben privaten Schlüssel für den Medien Relay-Authentifizierungsdienst. 
  
### <a name="internal-certificates"></a>Interne Zertifikate

Für die interne Edgeserver-Schnittstelle können Sie ein öffentliches Zertifikat von einer öffentlichen Zertifizierungsstelle oder ein Zertifikat verwenden, das von der internen Zertifizierungsstelle Ihrer Organisation ausgestellt wurde. Was Sie über das interne Zertifikat wissen sollten, ist, dass es einen SN-Eintrag und keine San-Einträge verwendet, damit Sie sich keine Sorgen um San im internen CERT machen müssen.
  
### <a name="required-certificates-table"></a>Tabelle "erforderliche Zertifikate"

Wir haben hier eine Tabelle, die Ihnen bei Ihren Anfragen helfen kann. Die hier eingefügten FQDN-Einträge gelten nur für Beispiel Domänen. Sie müssen Anforderungen basierend auf Ihren eigenen privaten und öffentlichen Domänen stellen, aber hier finden Sie eine Anleitung dazu, was wir verwendet haben:
  
- Contoso <span></span> . com: öffentlicher FQDN
    
- Fabrikam <span></span> . com: zweiter öffentlicher FQDN (als Demo hinzugefügt, was angefordert werden soll, wenn Sie über mehrere SIP-Domänen verfügen)
    
- Contoso <span></span> .net: interne Domäne
    
#### <a name="edge-certificate-table"></a>Edge-Zertifikats Tabelle

Unabhängig davon, ob Sie eine einzelne Edgeserver oder eine Edgepool ausführen, benötigen Sie Folgendes für Ihr Zertifikat:
  
|**Komponente**|**Antragstellername (SN)**|**Alternative Antragstellernamen (San)/Order**|**Hinweise**|
|:-----|:-----|:-----|:-----|
|Externer Edge  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Dies ist das Zertifikat, das Sie von einer öffentlichen Zertifizierungsstelle anfordern müssen. Es muss den externen Edge-Schnittstellen für Folgendes zugewiesen werden:  <br/> • Zugriffs Kante  <br/> • Webkonferenz-Edge  <br/> • Audio/Video-Authentifizierung  <br/> <br/>Die gute Nachricht ist, dass Sans automatisch zu ihrer Zertifikatanforderung und damit zu Ihrem Zertifikat hinzugefügt werden, nachdem Sie die Anforderung gesendet haben, basierend auf dem, was Sie für diese Bereitstellung im Topologie-Generator definiert haben. Sie müssen nur San-Einträge für zusätzliche SIP-Domänen oder andere Einträge hinzufügen, die Sie unterstützen müssen. Warum wird SIP.contoso.com in dieser Instanz repliziert? Dies geschieht auch automatisch, und es ist erforderlich, damit die Dinge ordnungsgemäß funktionieren.  <br/><br/> **Hinweis:** Dieses Zertifikat kann auch für die Verbindung mit öffentlichen Instant Messaging-Diensten verwendet werden. Sie müssen damit keine Unterschiede machen, aber in früheren Versionen dieser Dokumentation wurde sie als separate Tabelle aufgeführt und nun nicht. <br/> |
|Interner Edge  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Sie können dieses Zertifikat von einer öffentlichen Zertifizierungsstelle oder einer internen Zertifizierungsstelle erhalten. Er muss die Server-EKU (Enhanced Key Usage) enthalten, und Sie weisen ihn der internen Edge-Schnittstelle zu.  <br/> |
   
Wenn Sie ein Zertifikat für das Extensible Messaging and Presence Protocol (XMPP) benötigen, sieht es identisch mit den oben aufgeführten externen Edge-Tabelleneinträgen aus, weist jedoch die folgenden zwei zusätzlichen San-Einträge auf:
  
- xmpp. <span></span> Contoso <span></span> . com
    
- \*. contoso <span></span> . com
    
Bitte beachten Sie, dass XMPP derzeit nur in Skype for Business Server für Google Talk unterstützt wird, wenn Sie es für irgendetwas anderes verwenden möchten oder benötigen, müssen Sie diese Funktionalität mit dem Drittanbieter bestätigen.
  
## <a name="port-and-firewall-planning"></a>Planung von Ports und Firewalls
<a name="PortFirewallPlan"> </a>

Durch das einholen ihrer Planungs Rechte für Ports und Firewalls für Skype for Business Server Edgeserver-Bereitstellungen können Sie Tage oder Wochen der Problembehandlung und des Stresses sparen. Daher werden wir eine Reihe von Tabellen auflisten, in denen unsere Protokoll Belegung und die Ports angezeigt werden, die Sie für die Verwendung von Open, eingehend und Outbound benötigen, sowohl für NAT-als auch für öffentliche IP-Szenarien. Außerdem verfügen wir über separate Tabellen für Hardware Lastenausgleichsszenarien (HLB) und weitere Anleitungen dazu. Um weitere Informationen zu erhalten, haben wir auch einige [Edgeserver Szenarien in Skype for Business Server](scenarios.md) , die Sie für Ihre speziellen Bereitstellungs Belange Auschecken können.
  
### <a name="general-protocol-usage"></a>Allgemeine Protokollnutzung

Bevor wir uns die Zusammenfassungstabellen für externe und interne Firewalls ansehen, betrachten wir auch die folgende Tabelle:
  
|**Audio/Video-Transport**|**Verwendung**|
|:-----|:-----|
|UDP  <br/> |Das bevorzugte Transportschichtprotokoll für Audio und Video.  <br/> |
|TCP  <br/> |Das Fallback-Transportschichtprotokoll für Audio und Video.  <br/> Das erforderliche Transportschichtprotokoll für die Anwendungsfreigabe für Skype for Business Server, lync Server 2013 und lync Server 2010.  <br/> Das erforderliche Transportschichtprotokoll für die Dateiübertragung an Skype for Business Server, lync Server 2013 und lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Port Firewall

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie Personen, die öffentliche IP-Adressen verwenden. Dadurch werden alle Permutationen in unseren [Edgeserver Szenarien in Skype for Business Server](scenarios.md) Abschnitt behandelt.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Ziel Port oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Nicht unterstützt in Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Any  <br/> |XMPP-Proxy Dienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst  <br/> |Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-verbünden.  <br/> |
|Access/http  <br/> |TCP  <br/> |80  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |Zertifikatsperrung und CRL-Prüfung und-Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |DNS-Abfrage über UDP.  <br/> |
|Access/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Für Verbund-und öffentliche Instant Messaging-Verbindungen mit SIP.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |Für Verbund-und öffentliche Instant Messaging-Verbindungen mit SIP.  <br/> |
|Webkonferenz-PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver Webkonferenz-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Webkonferenz-Edgedienst öffentliche IP-Adresse <br/> |Webkonferenz-Medien.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |Dies wird zum Weiterleiten von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |Dies wird zum Weiterleiten von Mediendatenverkehr verwendet.  <br/> |
|A/V/Stun. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |3478 Outbound ist:  <br/> • Wird von Skype for Business Server verwendet, um die Version von Edgeserver zu bestimmen, mit der kommuniziert wird.  <br/> • Wird für den Mediendatenverkehr zwischen den Edge-Servern verwendet.  <br/> • Für Partnerverbund mit lync Server 2010 erforderlich.  <br/> • Erforderlich, wenn in Ihrer Organisation mehrere Edge-Pools bereitgestellt werden.  <br/> |
|A/V/Stun. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Stun/Turn-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/Stun. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Stun/Turn-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
|A/V/Stun. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |Stun/Turn-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Port Firewall

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Eine der folgenden Aktionen, die den XMPP-Gatewaydienst ausführen:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Edgeserver interne Schnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Ihrem Front-End-Server oder Front-End-Pool läuft.  <br/> **Hinweis:** XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Alle  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Edgeserver interne Schnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, Directorpool, Front-End-Server oder Front-End-Pool zu ihrer Edgeserver internen Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Edgeserver interne Schnittstelle  <br/> |Alle  <br/> • Director  <br/> • Directorpool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Eingehender SIP-Datenverkehr zu Ihrem Director, Directorpool, Front-End-Server oder Front-End-Pool von der internen Edgeserver-Schnittstelle aus.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Alle  <br/> • Front-End-Server  <br/> • Jede Front-End-Server  <br/>  in Ihrer Front-End-Pool <br/> |Edgeserver interne Schnittstelle  <br/> |Webkonferenz Datenverkehr von Ihrem Front-End-Server oder jeder Front-End-Server (wenn Sie über ein Front-End-Pool verfügen) auf die interne Edgeserver-Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Alle  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> • Beliebige Survivable Branch Appliance mit diesem Edgeserver  <br/> • Beliebige Survivable Branch Server mit diesem Edgeserver  <br/> |Edgeserver interne Schnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrem Survivable Branch Appliance oder Survivable Branch Server mit Ihrem Edgeserver.  <br/> |
|Stun/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen ihren internen und externen Benutzern und ihren Survivable Branch Appliance oder Survivable Branch Server.  <br/> |
|Stun/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Fall Back Pfad für A/V-Medienübertragung zwischen ihren internen und externen Benutzern und Ihrem Survivable Branch Appliance oder Survivable Branch Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Alle  <br/> • Front-End-Server, in der der zentrale Verwaltungsspeicher gespeichert ist  <br/> • Front-End-Pool, in der der zentrale Verwaltungsspeicher gespeichert ist  <br/> |Edgeserver interne Schnittstelle  <br/> |Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in ihren Edgeserver.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Dienstcontroller für zentralisierte Protokollierung mit Skype for Business Server-Verwaltungsshell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController Command Zeile (ClsController. exe) oder Agent-Befehle (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Dienstcontroller für zentralisierte Protokollierung mit Skype for Business Server-Verwaltungsshell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController Command Zeile (ClsController. exe) oder Agent-Befehle (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Dienstcontroller für zentralisierte Protokollierung mit Skype for Business Server-Verwaltungsshell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController Command Zeile (ClsController. exe) oder Agent-Befehle (ClsAgent. exe) und Protokollsammlung.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Hardware-Lastenausgleich für Edge-Port-Tabellen

Wir geben Hardware-Lastenausgleichsmodule (HLBs) und Edge-Ports einen eigenen Abschnitt, da die Dinge etwas komplizierter mit der zusätzlichen Hardware sind. In den folgenden Tabellen finden Sie Anleitungen für dieses spezielle Szenario:
  
#### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Port Firewall

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden, sowie Personen, die öffentliche IP-Adressen verwenden. Dadurch werden alle Permutationen in unseren [Edgeserver Szenarien in Skype for Business Server](scenarios.md) Abschnitt behandelt.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Ziel Port oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/http  <br/> |TCP  <br/> |80  <br/> |Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse  <br/> |Any  <br/> |Zertifikatsperrung und CRL-Prüfung und-Abruf.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse  <br/> |Any  <br/> |DNS-Abfrage über TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse  <br/> |Any  <br/> |DNS-Abfrage über UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edgeserver A/V-Edgedienst IP-Adresse  <br/> |Any  <br/> |Dies wird zum Weiterleiten von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edgeserver A/V-Edgedienst öffentliche IP-Adresse  <br/> |Any  <br/> |Dies wird zum Weiterleiten von Mediendatenverkehr verwendet.  <br/> |
|A/V/Stun. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edgeserver A/V-Edgedienst öffentliche IP-Adresse  <br/> |Any  <br/> |3478 Outbound ist:  <br/> • Wird von Skype for Business Server verwendet, um die Version von Edgeserver zu bestimmen, mit der kommuniziert wird.  <br/> • Wird für den Mediendatenverkehr zwischen den Edge-Servern verwendet.  <br/> • Erforderlich für den Partnerverbund.  <br/> • Erforderlich, wenn in Ihrer Organisation mehrere Edge-Pools bereitgestellt werden.  <br/> |
|A/V/Stun. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Edgeserver A/V-Edgedienst öffentliche IP-Adresse  <br/> |Stun/Turn-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/Stun. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Edgeserver A/V-Edgedienst öffentliche IP-Adresse  <br/> |Stun/Turn-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
|A/V/Stun. MSTURN  <br/> |TCP  <br/> |443  <br/> |Edgeserver A/V-Edgedienst öffentliche IP-Adresse  <br/> |Any  <br/> |Stun/Turn-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Port Firewall

|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Eine der folgenden Aktionen, die den XMPP-Gatewaydienst ausführen:  <br/> • Front-End-Server  <br/> • Front-End-Pool VIP-Adresse, die den XMPP-Gatewaydienst ausführt  <br/> |Edgeserver interne Schnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewaydienst, der auf Ihrem Front-End-Server oder Front-End-Pool läuft.  <br/><br/> **Hinweis:** XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Alle  <br/> • Front-End-Server, in der der zentrale Verwaltungsspeicher gespeichert ist  <br/> • Front-End-Pool, in der der zentrale Verwaltungsspeicher gespeichert ist  <br/> |Edgeserver interne Schnittstelle  <br/> |Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in ihren Edgeserver.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Alle  <br/> • Front-End-Server  <br/> • Jede Front-End-Server in Ihrem Front-End-Pool  <br/> |Edgeserver interne Schnittstelle  <br/> |Webkonferenz Datenverkehr von Ihrem Front-End-Server oder jeder Front-End-Server (wenn Sie über ein Front-End-Pool verfügen) auf die interne Edgeserver-Schnittstelle.  <br/> |
|Stun/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Alle  <br/> • Front-End-Server  <br/> • Jede Front-End-Server in Ihrem Front-End-Pool  <br/> |Edgeserver interne Schnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen ihren internen und externen Benutzern und ihren Survivable Branch Appliance oder Survivable Branch Server.  <br/> |
|Stun/MSTURN  <br/> |TCP  <br/> |443  <br/> |Alle  <br/> • Front-End-Server  <br/> • Jede Front-End-Server im Pool  <br/> |Edgeserver interne Schnittstelle  <br/> |Fall Back Pfad für A/V-Medienübertragung zwischen ihren internen und externen Benutzern und Ihrem Survivable Branch Appliance oder Survivable Branch Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Dienstcontroller für zentralisierte Protokollierung mit Skype for Business Server-Verwaltungsshell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController Command Zeile (ClsController. exe) oder Agent-Befehle (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Dienstcontroller für zentralisierte Protokollierung mit Skype for Business Server-Verwaltungsshell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController Command Zeile (ClsController. exe) oder Agent-Befehle (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Dienstcontroller für zentralisierte Protokollierung mit Skype for Business Server-Verwaltungsshell und Cmdlets für den zentralisierten Protokollierungsdienst, ClsController Command Zeile (ClsController. exe) oder Agent-Befehle (ClsAgent. exe) und Protokollsammlung.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Virtuelle IPS für externe Schnittstellen

|**Rolle oder Protokoll**|**TCP oder UDP**|**Ziel Port oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Any  <br/> |XMPP-Proxy Dienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst)  <br/> |Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-verbünden.  <br/> |
|XMPP  <br/>Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |XMPP-Proxy Dienst (teilt eine IP-Adresse mit dem Zugriffs-Edgedienst)  <br/> |Any  <br/> |Der XMPP-Proxy Dienst sendet Datenverkehr von XMPP-Kontakten in definierten XMPP-verbünden.  <br/> |
|Access/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Für Verbund-und öffentliche Instant Messaging-Verbindungen mit SIP.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mithilfe von NAT:** Edgeserver Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse <br/> |Any  <br/> |Für Verbund-und öffentliche Instant Messaging-Verbindungen mit SIP.  <br/> |
|Webkonferenz-PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver Webkonferenz-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver Webkonferenz-Edgedienst öffentliche IP-Adresse <br/> |Webkonferenz-Medien.  <br/> |
|A/V/Stun. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Stun/Turn-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/Stun. MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |**Private IP mithilfe von NAT:** Edgeserver A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver A/V-Edgedienst öffentliche IP-Adresse <br/> |Stun/Turn-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Virtuelle IPS-interne Schnittstelle

Unsere Anleitung hier wird ein wenig anders sein. Tatsächlich wird in einer HLB-Situation empfohlen, dass Sie nur unter den folgenden Umständen über ein internes VIP-Routing verfügen:
  
- Wenn Sie Exchange 2007 oder Exchange 2010 Unified Messaging (um) verwenden.
    
- Wenn Sie über Legacy-Clients verfügen, die den Edge verwenden.
    
In der folgenden Tabelle finden Sie Anleitungen für diese Szenarien, aber ansonsten sollten Sie in der Lage sein, vom zentralen Verwaltungsspeicher (CMS) abhängig zu sein, um den Datenverkehr zu den einzelnen Edgeserver zu leiten, die er kennt (Dies erfordert natürlich, dass CMS auf dem neuesten Stand ist, um Edgeserver Informationen zu erhalten).
  
|**Protocol**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Alle  <br/> • Director  <br/> • Directorpool VIP-Adresse  <br/> • Front-End-Server  <br/> • Front-End-Pool VIP-Adresse  <br/> |Edgeserver interne Schnittstelle  <br/> |Ausgehender SIP-Datenverkehr von Ihrem Director, Directorpool VIP-Adresse, Front-End-Server oder Front-End-Pool VIP-Adresse zu ihrer Edgeserver internen Schnittstelle.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Edgeserver interne VIP-Schnittstelle  <br/> |Alle  <br/> • Director  <br/> • Directorpool VIP-Adresse  <br/> • Front-End-Server  <br/> • Front-End-Pool VIP-Adresse  <br/> |Eingehender SIP-Datenverkehr zu Ihrem Director, Directorpool VIP-Adresse, Front-End-Server oder Front-End-Pool VIP-Adresse von ihrer Edgeserver internen Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Alle  <br/> • Front-End-Server IP-Adresse  <br/> • Front-End-Pool IP-Adresse  <br/> • Beliebige Survivable Branch Appliance mit diesem Edgeserver  <br/> • Beliebige Survivable Branch Server mit diesem Edgeserver  <br/> |Edgeserver interne Schnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder Ihrem Survivable Branch Appliance oder Survivable Branch Server mit Ihrem Edgeserver.  <br/> |
|Stun/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Any  <br/> |Edgeserver interne Schnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen ihren internen und externen Benutzern.  <br/> |
|Stun/MSTURN  <br/> |TCP  <br/> |443  <br/> |Any  <br/> |Edgeserver interne VIP-Schnittstelle  <br/> |Fallback-Pfad für die A/V-Medienübertragung zwischen ihren internen und externen Benutzern, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für Dateiübertragungen und Desktopfreigaben verwendet.  <br/> |
