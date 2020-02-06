---
title: Umgebungsanforderungen des Edge-Servers in Skype for Business Server
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
description: 'Zusammenfassung: erfahren Sie mehr über die Umweltanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: 15cc6c54d420cd95962afb1faa219a3a370056a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803375"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Umgebungsanforderungen des Edge-Servers in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Umweltanforderungen für Edgeserver in Skype for Business Server.
  
Viel Planung und Vorbereitung muss außerhalb der Skype for Business Server-Edgeserver-Umgebung selbst erfolgen. In diesem Artikel sehen wir uns an, welche Vorbereitungen laut unserer Liste unten in der Organisationsumgebung getroffen werden müssen:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Topologieplanung
<a name="TopoPlan"> </a>

Skype for Business Server-Edgeserver-Topologien können Folgendes verwenden:
  
- Routingfähige öffentliche IP-Adressen.
    
- Nicht-routingfähige private IP-Adressen, wenn die **symmetrische** Netzwerkadressenübersetzung (Network Address Translation, NAT) verwendet wird
    
> [!TIP]
> Ihr Edgeserver kann für die Verwendung einer einzelnen IP-Adresse mit unterschiedlichen Ports für jeden Dienst konfiguriert werden, oder er kann für jeden Dienst unterschiedliche IP-Adressen verwenden, aber denselben Standardport verwenden (standardmäßig TCP 443). Weitere Informationen finden Sie im Abschnitt „IP-Adressanforderungen“ unten. 
  
Bedenken Sie folgende Punkte, wenn Sie sich für die Verwendung von nicht-routingfähigen privaten IP-Adressen mit NAT entscheiden:
  
- Sie müssen routingfähige private IP-Adressen für **alle drei** externen Schnittstellen verwenden.
    
- Sie müssen ein **symmetrisches** NAT-Gerät für eingehenden und ausgehenden Datenverkehr konfigurieren. Symmetrische NAT ist die einzige unterstützte NAT, die Sie mit Skype for Business Server Edge Server verwenden können.
    
- Konfigurieren Sie Ihr NAT so, dass eingehende Quell-Adressen nicht geändert werden. Der A/V-Edgedienst muss die eingehende Quelladresse empfangen können, um den optimalen Medienpfad zu finden.
    
- Ihre Edgeserver müssen in der Lage sein, miteinander von ihren öffentlichen A/V-Edge-IP-Adressen zu kommunizieren. Ihre Firewall muss diesen Datenverkehr zulassen.
    
- NAT kann **nur** für skalierte konsolidierte Edgeserver verwendet werden, wenn Sie den DNS-Lastenausgleich verwenden. Wenn Sie ein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie eine öffentlich routingfähige IP-Adresse **ohne** NAT verwenden.
    
Sie haben keine Probleme mit ihren Zugriffs-, Webkonferenz-und A/V-Edge-Schnittstellen hinter einem Router oder einer Firewall, die symmetrische NAT für einzelne und skalierte konsolidierte Edgeserver-Topologien ausführen (sofern Sie keinen Hardwarelastenausgleich verwenden).
  
### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Optionen für die Edgeserver-Topologie

Für die Bereitstellung von Skype for Business Server Edge Server stehen verschiedene Topologie-Optionen zur Verfügung:
  
- Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich
    
Die folgende Tabelle hilft Ihnen bei der Auswahl, indem Sie eine Zusammenfassung der Optionen jeder Topologie gibt:
  
|**Topologie**|**Hohe Verfügbarkeit**|**Zusätzliche DNS-Einträge für den externen Edgeserver im Edge-Pool erforderlich?**|**Edge-Failover für Skype for Business Server-Sitzungen**|**Edge-Failover für Skype for Business Server-Verbund Sitzungen**|
|:-----|:-----|:-----|:-----|:-----|
|Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja&sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich  <br/> |Ja  <br/> |Nein (ein DNS A-Eintrag pro VIP)  <br/> |Ja  <br/> |Ja  <br/> |
   
&sup1; Exchange Unified Messaging (um) Remotebenutzer Failover mithilfe des DNS-Lastenausgleichs erfordert Exchange 2013 oder neuer.
  
### <a name="ip-address-requirements"></a>IP-Adressanforderungen

Auf grundlegender Ebene benötigen drei Dienste IP-Adressen; Access Edge Service, Web Conferencing Edge Service und A/V Edge Service. Sie können entweder drei IP-Adressen verwenden, eine für jeden der Dienste, oder Sie können eine IP-Adresse verwenden und festlegen, dass jeder Dienst auf einem anderen Port liegt (weitere Informationen zu diesem Thema siehe Abschnitt [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)). Das sind im Prinzip alle relevanten Informationen über einzelne konsolidierte Edge-Umgebungen.
  
> [!NOTE]
> Wie oben erwähnt, können Sie sich dafür entscheiden, eine IP-Adresse für alle drei Dienste zu verwenden und diese auf verschiedenen Ports ausführen. Wir empfehlen dies allerdings nicht. Wenn Ihre Kunden auf die alternativen Ports, die Sie in diesem Szenario verwenden würden, nicht zugreifen können, haben sie auch keinen Zugriff auf die volle Funktionalität Ihrer Edge-Umgebung. 
  
Skalierte und konsolidierte Topologien können etwas komplizierter sein, sehen wir uns also ein paar Tabellen an, die die IP-Adressanforderungen zeigen. Dabei dürfen wir nicht vergessen, dass die wichtigsten Aspekte bei der Topologiewahl hohe Verfügbarkeit und Lastenausgleich sind. Anforderungen an hohe Verfügbarkeit können einen Einfluss auf die Wahl Ihres Lastenausgleichs haben (darüber mehr nach den Tabellen).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (IP-Adresse pro Rolle)

|**Anzahl der Edgeserver pro Pool**|**Anzahl erforderlicher IP-Adressen für DNS-Lastenausgleich**|**Anzahl erforderlicher IP-Adressen für Hardwaregerät zum Lastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 pro VIP) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 pro VIP) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 pro VIP) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 pro VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (eine IP-Adresse für alle Rollen)

|**Anzahl der Edgeserver pro Pool**|**Anzahl erforderlicher IP-Adressen für DNS-Lastenausgleich**|**Anzahl erforderlicher IP-Adressen für Hardwaregerät zum Lastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 pro VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 pro VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 pro VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 pro VIP) + 5  <br/> |
   
Sehen wir uns noch einige zusätzliche Punkte an, die wir bei der Planung berücksichtigen müssen.
  
- **Höhere Verfügbarkeit**: Wenn Sie in Ihrer Bereitstellung eine höhere Verfügbarkeit benötigen, sollten Sie mindestens zwei Edgeserver in einem Pool bereitstellen. Beachten Sie, dass ein einzelner Edge-Pool bis zu 12 Edge-Server unterstützt (obwohl Sie mit dem Topologie-Generator bis zu 20 hinzufügen können, die nicht getestet oder unterstützt werden, daher raten wir Ihnen, dies nicht zu tun). Wenn Sie mehr als 12 Edge-Server benötigen, sollten Sie zusätzliche Edge-Pools für Sie erstellen.
    
- **Hardware Lastenausgleich**: für die meisten Szenarien empfehlen wir den DNS-Lastenausgleich. Der Hardware Lastenausgleich wird natürlich ebenfalls unterstützt, aber vor allem ist er für ein einzelnes Szenario über den DNS-Lastenausgleich erforderlich:
    
  - Externer Zugriff auf Exchange 2007 oder Exchange 2010 (ohne SP) Unified Messaging (um).
    
- **DNS-Lastenausgleich**: Exchange 2010 SP1 und neuere Versionen können vom DNS-Lastenausgleich unterstützt werden. Beachten Sie, dass es funktioniert, wenn Sie mit dem DNS-Lastenausgleich für eine frühere Version von Exchange arbeiten müssen, aber der gesamte Datenverkehr für diesen Vorgang geht an den ersten Server im Pool, und wenn er nicht verfügbar ist, wird der Datenverkehr später fehlschlagen.
    
    Der DNS-Lastenausgleich wird auch empfohlen, wenn Sie mit Unternehmen eine Föderation verwenden:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>DNS-Planung
<a name="DNSPlan"> </a>

Wenn es um die Bereitstellung von Skype for Business Server Edge Server geht, ist es wichtig, dass Sie sich auf DNS richtig vorbereiten. Mit den richtigen Einträgen ist die Bereitstellung viel einfacher. Sie haben hoffentlich im Abschnitt oben eine Topologie ausgewählt, da wir eine Übersicht machen werden, um dann einige Tabellen aufzuführen, die die DNS-Einträge für diese Szenarien erläutern. Darüber hinaus verfügen wir über eine [Erweiterte DNS-Planung für Edge-Server für Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) für eine ausführlichere Lektüre, wenn Sie Sie benötigen.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-Einträge für einzelne konsolidierte Edgeserver-Szenarien

Hierbei handelt es sich um die DNS-Einträge, die Sie für einen Singing Edge-Server benötigen, wobei entweder Public IPS oder private IPS mit NAT verwendet werden. Da es sich um Beispieldaten handelt, überlassen wir Ihnen Beispiel-IPs, so dass Sie Ihre eigenen Einträge einfacher herausfinden können:
  
- Interner Netzwerkadapter: 172.25.33.10 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit Skype for Business Server-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Öffentliche IPs:
    
  - Access Edge: 131.107.155.10 (Dies ist die primäre, mit dem Standardgateway auf Ihren öffentlichen Router eingestellt, ex: 131.107.155.1)
    
  - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
  - A/V-Edge: 131.107.155.30 (sekundär)
    
  Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internet Protocol, Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Eigenschaften für den lokalen Verbindungsbereich in Windows Server.
    
  - Private IPs:
    
  - Access Edge: 10.45.16.10 (Dies ist die primäre, mit dem Standardgateway auf Ihren Router eingestellt, ex: 10.45.16.1)
    
  - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
  - A/V-Edge: 10.45.16.30 (sekundär)
    
Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internet Protocol, Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Eigenschaften für den lokalen Verbindungsbereich in Windows Server.
  
> [!TIP]
>Es gibt weitere möglich Konfigurationen:
  
- Sie können eine IP-Adresse auf dem externen Netzwerkadapter verwenden. Wir empfehlen dies nicht, da Sie dann zwischen den Thee-Diensten unterschieden werden müssen, die verschiedene Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen hierzu finden Sie im Abschnitt [Port-und Firewall-Planung](edge-environmental-requirements.md#PortFirewallPlan) .
    
- Sie können mit drei externen Netzwerkadaptern statt einem arbeiten und jedem davon eine Dienst-IPs zuweisen. Warum sollten Sie das tun? Dadurch werden die Dienste getrennt und wenn etwas schief läuft, ist die Problembehandlung einfacher. Außerdem können Ihre anderen Dienste möglicherweise weiterarbeiten, während Sie das Problem beheben.
    
|**Standort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 <br/> **Privat:** 10.45.16.10 <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 <br/> **Privat:** 10.45.16.20 <br/> |Eine externe Schnittstelle für Ihren Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 <br/> **Privat:** 10.45.16.30 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für Skype for Business Server, lync Server 2013 und lync Server 2010-Clients erforderlich, um extern zu arbeiten. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Suche von Verbundpartnern notwendig, die „Zugelassene SIP-Domänen“ genannt werden. Sie benötigen eine für jede Domäne mit Skype for Business-Benutzern.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Eintrag  <br/> |NV  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Die interne Schnittstelle für Ihren konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS-Einträge für skalierte DNS-und Hardware-Edgeserver-Szenarien

Hierbei handelt es sich um die DNS-Einträge, die Sie für einen Singing Edge-Server benötigen, wobei entweder Public IPS oder private IPS mit NAT verwendet werden. Da es sich um Beispieldaten handelt, überlassen wir Ihnen Beispiel-IPs, so dass Sie Ihre eigenen Einträge einfacher herausfinden können:
  
- Interner Netzwerkadapter:
    
  - Knoten 1: 172.25.33.10 (keine Standardgateways zugewiesen)
    
  - Knoten 2: 172.25.33.11 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit Skype for Business Server-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0). 
  
- Externer Netzwerkadapter:
    
  - Knoten 1
    
     - Öffentliche IPs:
    
        - Access Edge: 131.107.155.10 (Dies ist die primäre, mit dem Standardgateway auf Ihren öffentlichen Router eingestellt, ex: 131.107.155.1)
    
        - Webkonferenz-Edge: 131.107.155.20 (sekundär)
    
        - A/V-Edge: 131.107.155.30 (sekundär)
    
          Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internet Protocol, Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Eigenschaften für den lokalen Verbindungsbereich in Windows Server.
    
    - Private IPs:
    
         - Access Edge: 10.45.16.10 (Dies ist die primäre, mit dem Standardgateway auf Ihren Router eingestellt, ex: 10.45.16.1)
    
         - Webkonferenz-Edge: 10.45.16.20 (sekundär)
    
         - A/V-Edge: 10.45.16.30 (sekundär)
    
      Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internet Protocol, Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Eigenschaften für den lokalen Verbindungsbereich in Windows Server.
    
  - Knoten 2
    
    - Öffentliche IPs:
    
      - Access Edge: 131.107.155.11 (Dies ist die primäre, mit dem Standardgateway auf Ihren öffentlichen Router eingestellt, ex: 131.107.155.1)
    
      - Webkonferenz-Edge: 131.107.155.21 (sekundär)
    
      - A/V-Edge: 131.107.155.31 (sekundär)
    
      Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internet Protocol, Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Eigenschaften für den lokalen Verbindungsbereich in Windows Server.
    
  - Private IPs:
    
    - Access Edge: 10.45.16.11 (Dies ist die primäre, mit dem Standardgateway auf Ihren Router eingestellt, ex: 10.45.16.1)
    
    - Webkonferenz-Edge: 10.45.16.21 (sekundär)
    
    - A/V-Edge: 10.45.16.31 (sekundär)
    
      Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften von Internet Protocol, Version 4 (TCP/IPv4) und Internet Protocol Version 6 (TCP/IPv6) der Eigenschaften für den lokalen Verbindungsbereich in Windows Server.
    
Es gibt weitere möglich Konfigurationen:
  
- Sie können eine IP-Adresse auf dem externen Netzwerkadapter verwenden. Wir empfehlen dies nicht, da Sie dann zwischen den Thee-Diensten unterschieden werden müssen, die verschiedene Ports verwenden (was Sie in Skype for Business Server tun können), aber es gibt einige Firewalls, die die alternativen Ports blockieren können. Weitere Informationen hierzu finden Sie im Abschnitt [Port-und Firewall-Planung](edge-environmental-requirements.md#PortFirewallPlan) .
    
- Sie können mit drei externen Netzwerkadaptern statt einem arbeiten und jedem davon eine Dienst-IPs zuweisen. Warum sollten Sie das tun? Dadurch werden die Dienste getrennt und wenn etwas schief läuft, ist die Problembehandlung einfacher. Außerdem können Ihre anderen Dienste möglicherweise weiterarbeiten, während Sie das Problem beheben.
    
|**Standort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder FQDN**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |sip.contoso.com  <br/> |**öffentlich:** 131.107.155.10 und 131.107.155.11 <br/> **Privat:** 10.45.16.10 und 10.45.16.11 <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Sie benötigen eine für jede SIP-Domäne mit Skype for Business-Benutzern.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |webcon.contoso.com  <br/> |**öffentlich:** 131.107.155.20 und 131.107.155.21 <br/> **Privat:** 10.45.16.20 und 10.45.16.21 <br/> |Eine externe Schnittstelle für Ihren Webkonferenz-Edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |av.contoso.com  <br/> |**öffentlich:** 131.107.155.30 und 131.107.155.31 <br/> **Privat:** 10.45.16.30 und 10.45.16.31 <br/> |Eine externe Schnittstelle für Ihren A/V-Edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für Skype for Business Server, lync Server 2013 und lync Server 2010-Clients erforderlich, um extern zu arbeiten. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Eine externe Schnittstelle für Ihren Access Edge-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Suche von Verbundpartnern notwendig, die „Zugelassene SIP-Domänen“ genannt werden. Sie benötigen eine für jede Domäne mit Skype for Business.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Eintrag  <br/> |NV  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 und 172.25.33.11  <br/> |Die interne Schnittstelle für Ihren konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-Eintrag für Partnerverbund (alle Szenarien)

|**Standort**|**Typ**|**Port**|**FQDN**|**FQDN-Hosteintrag**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Die externe SIP-Zugriffs Kante-Schnittstelle für die automatische DNS-Erkennung. Von anderen potenziellen Verbundpartnern verwendet. Sie wird auch als "SIP-Domänen zulassen" bezeichnet. Sie benötigen eine dieser beiden SIP-Domänen für Skype for Business-Benutzer.  <br/><br/> **Hinweis:** Sie benötigen diesen SRV-Eintrag für Mobilität und das Clearinghaus für die Push-Benachrichtigung. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-Einträge für XMPP (Extensible Messaging and Presence Protocol)

|**Standort**|**Typ**|**Port**|**FQDN**|**IP-Adresse oder FQDN-Hosteintrag**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |Die XMPP-Proxyschnittstelle in Ihrem Access Edge-Dienst oder Edge-Pool. Sie müssen diese nach Bedarf für alle internen SIP-Domänen mit Skype for Business Server-aktivierten Benutzern wiederholen, wobei der Kontakt mit XMPP-Kontakten über folgende Funktionen zulässig ist:  <br/> • eine globale Richtlinie  <br/> • eine Website Richtlinie, in der der Benutzer aktiviert ist  <br/> • eine Benutzerrichtlinie, die auf den Skype for Business Server-aktivierten Benutzer angewendet wurde  <br/> Eine zulässige XMPP-Richtlinie muss auch in der XMPP-Partnerbenutzerrichtlinie konfiguriert werden.  <br/> |
|Externes DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |IP-Adresse des Access-Edgedienst auf dem Edgeserver oder Edge-Pool, auf dem Ihr XMPP-Proxy Dienst gehostet wird  <br/> |Dies verweist auf den Access-Edgedienst auf dem Edgeserver oder Edge-Pool, der den XMPP-Proxy Dienst hostet. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (A oder AAAA).  <br/> |
   
> [!NOTE]
> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Zertifikatsplanung
<a name="CertPlan"> </a>

Skype for Business Server verwendet Zertifikate für sichere, verschlüsselte Kommunikation zwischen Servern und vom Server zum Client. Wie Sie sich sicher schon gedacht haben, müssen DNS-Einträge Ihrer Zertifikate mit Antragstellername (SN) und alternativem Antragstellernamen (SAN) auf Ihren Zertifikaten zusammenpassen. Das macht jetzt in der Planungsphase Arbeit, um sicherzustellen, dass die richtigen FQDNs im DNS für die SN- und SAN-Einträger Ihrer Zertifikate registriert sind.
  
Wir besprechen externe und interne Zertifikate getrennt und sehen uns dann auch eine Tabelle mit den Anforderungen für beide an.
  
### <a name="external-certificates"></a>Externe Zertifikate

Das Zertifikat, das Ihren externen Edge-Server-Schnittstellen zugewiesen ist, muss mindestens von einer öffentlichen Zertifizierungsstelle bereitgestellt werden. Wir können Ihnen keine bestimmte Zertifizierungsstelle empfehlen, aber wir haben eine Liste mit CAS, [Unified Communications-Zertifikat Partnern](/SkypeForBusiness/certification/services-ssl) , die Sie sich ansehen können, um festzustellen, ob Ihre bevorzugte Zertifizierungsstelle aufgeführt ist.
  
Wann müssen Sie eine Anforderung an eine CA für dieses öffentliche Zertifikat stellen und wie machen Sie das? Es gibt verschiedene Arten:
  
- Sie können die Installation von Skype for Business Server und dann die Edge-Server-Bereitstellung durchlaufen. Der Skype for Business Server-Bereitstellungs-Assistent hat einen Schritt zum Generieren einer Zertifikatanforderung, die Sie dann an die ausgewählte Zertifizierungsstelle senden können.
    
- Sie können auch Windows PowerShell-Befehle zum Generieren dieser Anforderung verwenden, wenn dies mehr Inline mit Ihren Geschäftsanforderungen oder ihrer Bereitstellungsstrategie ist.
    
- Schließlich kann Ihre Zertifizierungsstelle über einen eigenen Übermittlungsprozess verfügen, der möglicherweise auch Windows PowerShell oder eine andere Methode umfasst. In diesem Fall müssen Sie sich zusätzlich zu den hier zur Verfügung gestellten Informationen auf deren Dokumentation verlassen.
    
Nachdem Sie das Zertifikat erhalten haben, müssen Sie es in Skype for Business Server diesen Diensten zuweisen:
  
- Access Edge Service-Schnittstelle
    
- Web Conferencing Edge Service-Schnittstelle
    
- Audio/Video-Authentifizierungsdienst (Dies ist nicht mit dem a/V-Edgedienst zu verwechseln, da dadurch kein Zertifikat zum Verschlüsseln von Audio-und Videostreams verwendet wird)
    
> [!IMPORTANT]
> Alle Edgeserver (wenn Sie zum gleichen Pool von Edge-Servern gehören) müssen genau dasselbe Zertifikat mit dem gleichen privaten Schlüssel für den Media Relay-Authentifizierungsdienst aufweisen. 
  
### <a name="internal-certificates"></a>Interne Zertifikate

Für die interne Edge-Server Schnittstelle können Sie ein öffentliches Zertifikat von einer öffentlichen Zertifizierungsstelle oder ein Zertifikat verwenden, das von der internen Zertifizierungsstelle Ihrer Organisation ausgestellt wurde. Denken Sie daran, dass interne Zertifikate einen SN-Eintrag verwenden und keine SAN-Einträge, über SAN müssen Sie sich bei internen Zertifikaten also keine Gedanken machen.
  
### <a name="required-certificates-table"></a>Tabelle erforderlicher Zertifikate

Diese Tabelle hilft Ihnen bei Ihren Anforderungen. Die FQDN-Einträge sind lediglich Beispiel-Domänen. Ihre Anforderungen müssen sich nach Ihren privaten und öffentlichen Domänen richten; im Folgenden finden Sie eine Richtlinie zu dem, was wir verwendet haben:
  
- Contoso<span></span>. com: öffentlicher FQDN
    
- Fabrikam<span></span>. com: zweiter öffentlicher FQDN (als Demo der anzufordernden Elemente hinzugefügt, wenn Sie über mehrere SIP-Domänen verfügen)
    
- Contoso<span></span>.net: interne Domäne
    
#### <a name="edge-certificate-table"></a>Edgezertifikattabelle

Unabhängig davon, ob Sie einen einzelnen Edge-Server oder einen Edge-Pool ausführen, benötigen Sie für Ihr Zertifikat Folgendes:
  
|**Komponente**|**Antragstellername**|**Alternative Antragstellernamen (SAN)/Reihenfolge**|**Hinweise**|
|:-----|:-----|:-----|:-----|
|Externer Edgeserver  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Sie benötigen dieses Zertifikat, um eine Anfrage an eine öffentliche CA zu stellen. Es muss den externen Edgeschnittstellen für Folgendes zugewiesen werden:<br/> • Access Edge  <br/> • Webkonferenz-Edge  <br/> • Audio/Video-Authentifizierung  <br/> <br/>Die gute Nachricht ist, dass Sans automatisch zu ihrer Zertifikatanforderung und damit zu Ihrem Zertifikat hinzugefügt werden, nachdem Sie die Anforderung gesendet haben, basierend auf dem, was Sie für diese Bereitstellung im Topologie-Generator definiert haben. Sie müssen nur SAN-Einträge für zusätzliche SIP-Domänen oder andere Einträge hinzufügen, die unterstützt werden sollen. Warum wird sip.contoso.com in dieser Instanz repliziert? Dies geschieht auch automatisch und ist notwendig, damit alles reibungslos läuft.  <br/><br/> **Hinweis:** Dieses Zertifikat kann auch für die öffentliche Instant Messaging-Konnektivität verwendet werden. Die Vorgehensweise ist die gleiche; in früheren Versionen dieser Dokumentation wurde das jedoch als getrennte Tabelle aufgeführt, was jetzt nicht mehr der Fall ist. <br/> |
|Interner Edgeserver  <br/> |sfbedge.contoso.com  <br/> |NV  <br/> |Sie können dieses Zertifikat von einer öffentlichen CA oder einer internen CA bekommen. Es muss die Server-EKU (erweiterte Schlüsselverwendung für Server) beinhalten. Sie weisen es der internen Edgeschnittstelle zu.  <br/> |
   
Wenn Sie ein Zertifikat für XMPP (Extensible Messaging and Presence Protocol) benötigen, sieht dieses genau wie in den Tabelleneinträgen für Externer Edgeserver oben aus, hat allerdings die folgenden beiden zusätzlichen SAN-Einträge:
  
- XMPP. <span> </span>Contoso<span></span>. com
    
- \*. contoso<span></span>. com
    
Beachten Sie bitte, dass XMPP derzeit nur in Skype for Business Server für Google Talk unterstützt wird, wenn Sie es für irgendetwas anderes verwenden möchten oder benötigen, müssen Sie diese Funktionalität mit dem Drittanbieter bestätigen.
  
## <a name="port-and-firewall-planning"></a>Port- und Firewallplanung
<a name="PortFirewallPlan"> </a>

Wenn Sie Ihre Planungs Rechte für Ports und Firewalls für die Bereitstellung von Skype for Business Server Edge Server erhalten, können Sie Tage oder Wochen für Problembehandlung und Stress sparen. Daher führen wir einige Tabellen auf, die unsere Protokollverwendung zeigen, und welche Eingangs- und Ausgangsports offen sein müssen, sowohl für NAT als auch für öffentliche IP-Szenarien. Es wird außerdem separate Tabellen für Szenarien mit Hardwaregerät zum Lastenausgleich sowie weiterer Hilfestellung dazu geben. Für weitere Informationen von dort aus haben wir auch einige [Edge-Server-Szenarien in Skype for Business Server](scenarios.md) , die Sie für Ihre speziellen Bereitstellungsprobleme ausprobieren können.
  
### <a name="general-protocol-usage"></a>Allgemeine Protokollverwendung

Betrachten wir die folgenden Tabelle, bevor wir uns die Zusammenfassungstabelle für externe und interne Firewalls ansehen:
  
|**Audio/Videotransport**|**Verwendung**|
|:-----|:-----|
|UDP  <br/> |Das bevorzugte Transportschichtprotokoll für Audio und Video.  <br/> |
|TCP  <br/> |Das Ausweich-Transportschichtprotokoll für Audio und Video.  <br/> Das erforderliche Transportschichtprotokoll für die Anwendungsfreigabe für Skype for Business Server, lync Server 2013 und lync Server 2010.  <br/> Das erforderliche Transportschichtprotokoll für die Dateiübertragung in Skype for Business Server, lync Server 2013 und lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Port-Firewall

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden sowie für alle, die öffentliche IP-Adressen verwenden. Dies beziehe sich auf alle Permutationen in unseren [Edge-Server-Szenarien im Abschnitt Skype for Business Server](scenarios.md) .
  
|**Rollen oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> In Skype for Business Server 2019 nicht unterstützt |TCP  <br/> |5269  <br/> |Beliebig  <br/> |XMPP-Proxy Dienst (Freigabe einer IP-Adresse mit dem Access Edge Service  <br/> |Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen.  <br/> |
|Zugriff/HTTP  <br/> |TCP  <br/> |80  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Beliebig  <br/> |Zertifikatsperre und Zertifikatssperrlistenprüfung und -abruf  <br/> |
|Zugriff/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Beliebig  <br/> |DNS-Abfrage über TCP.  <br/> |
|Zugriff/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Beliebig  <br/> |DNS-Abfrage über UDP.  <br/> |
|Zugriff/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebig  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Beliebig  <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Webkonferenzen/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Webkonferenz-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Webkonferenz-Edgedienst, öffentliche IP-Adresse <br/> |Web-Konferenzmedien.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000–59999  <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |Beliebig  <br/> |3478 ausgehend wird:  <br/> • Wird von Skype for Business Server verwendet, um die Version von Edge Server zu ermitteln, mit der Sie kommuniziert.  <br/> • Wird für den Mediendatenverkehr zwischen Edge-Servern verwendet.  <br/> • Erforderlich für den Verbund mit lync Server 2010.  <br/> • Erforderlich, wenn in Ihrer Organisation mehrere Edge-Pools bereitgestellt werden.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |Beliebig  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Port-Firewall

|**Protokoll**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Jede der folgenden, die den XMPP-Gatewaydienst ausführt:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewayserver, der auf Ihrem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/> **Hinweis:** XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Jede:  <br/> • Regisseur  <br/> • Director-Pool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Ausgehendes SIP-Datenverkehr von Ihrem Director, Director-Pool, Front-End-Server oder Front-End-Pool zur internen Edge-Server-Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Jede:  <br/> • Regisseur  <br/> • Director-Pool  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> |Eingehendes SIP-Aufkommen an Ihren Director, Director-Pool, Front-End-Server oder Front-End-Pool über die interne Schnittstelle des Edge-Servers.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server  <br/>  im Front-End-Pool <br/> |Interne Edge-Server-Schnittstelle  <br/> |Webkonferenz Datenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zur internen Edge-Server-Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Front-End-Pool  <br/> • Alle Überlebenden Branch-Appliances, die diesen Edge-Server verwenden  <br/> • Überlebensfähiger Branch Server mit diesem Edgeserver  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder ihrer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mithilfe Ihres Edge-Servers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern und ihrer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |Interne Edge-Server-Schnittstelle  <br/> |Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern und ihrer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für die Dateiübertragung und die Desktopfreigabe verwendet  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Jede:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher enthält  <br/> • Front-End-Pool, in dem der zentrale Verwaltungsspeicher gespeichert ist  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Replikation von Änderungen aus dem zentralen Verwaltungsspeicher auf Ihren Edgeserver  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Zentralisierter Protokollierungsdienst Controller mit der Skype for Business Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Zentralisierter Protokollierungsdienst Controller mit der Skype for Business Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Zentralisierter Protokollierungsdienst Controller mit der Skype for Business Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Hardwaregeräte zum Lastenausgleich für Edge-Porttabellen

Hardwaregeräte zum Lastenausgleich und Edge-Ports bekommen Ihren eigenen Abschnitt, da die Vorgehensweise aufgrund der zusätzlichen Hardware etwas komplizierter ist. Hilfestellung zu diesem speziellen Szenario finden Sie in den Tabellen unten:
  
#### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Port-Firewall

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden sowie für alle, die öffentliche IP-Adressen verwenden. Dies beziehe sich auf alle Permutationen in unseren [Edge-Server-Szenarien im Abschnitt Skype for Business Server](scenarios.md) .
  
|**Rollen oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Zugriff/HTTP  <br/> |TCP  <br/> |80  <br/> |Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts  <br/> |Beliebig  <br/> |Zertifikatsperre und Zertifikatssperrlistenprüfung und -abruf  <br/> |
|Zugriff/DNS  <br/> |TCP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts  <br/> |Beliebig  <br/> |DNS-Abfrage über TCP.  <br/> |
|Zugriff/DNS  <br/> |UDP  <br/> |53  <br/> |Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts  <br/> |Beliebig  <br/> |DNS-Abfrage über UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000–59999  <br/> |Edge-Server-A/V-Edgedienst-IP-Adresse  <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse  <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse  <br/> |Beliebig  <br/> |3478 ausgehend wird:  <br/> • Wird von Skype for Business Server verwendet, um die Version von Edge Server zu ermitteln, mit der Sie kommuniziert.  <br/> • Wird für den Mediendatenverkehr zwischen Edge-Servern verwendet.  <br/> • Für Föderation erforderlich.  <br/> • Erforderlich, wenn in Ihrer Organisation mehrere Edge-Pools bereitgestellt werden.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse  <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse  <br/> |Beliebig  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Port-Firewall

|**Protokoll**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Jede der folgenden, die den XMPP-Gatewaydienst ausführt:  <br/> • Front-End-Server  <br/> • VIP-Adresse des Front-End-Pools mit dem XMPP-Gatewaydienst  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gatewayserver, der auf Ihrem Front-End-Server oder Front-End-Pool ausgeführt wird.  <br/><br/> **Hinweis:** XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Jede:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher enthält  <br/> • Front-End-Pool, in dem der zentrale Verwaltungsspeicher gespeichert ist  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Replikation von Änderungen aus dem zentralen Verwaltungsspeicher auf Ihren Edgeserver  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server im Front-End-Pool  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Webkonferenz Datenverkehr von Ihrem Front-End-Server oder jedem Front-End-Server (wenn Sie über einen Front-End-Pool verfügen) zur internen Edge-Server-Schnittstelle.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server im Front-End-Pool  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern und ihrer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jeder Front-End-Server in Ihrem Pool  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern und ihrer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für die Dateiübertragung und die Desktopfreigabe verwendet  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Zentralisierter Protokollierungsdienst Controller mit der Skype for Business Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Zentralisierter Protokollierungsdienst Controller mit der Skype for Business Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Zentralisierter Protokollierungsdienst Controller mit der Skype for Business Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Virtuelle IPs externe Schnittstelle

|**Rollen oder Protokoll**|**TCP oder UDP**|**Zielport oder Portbereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Beliebig  <br/> |XMPP-Proxy Dienst (Freigabe einer IP-Adresse mit dem Access Edge-Dienst)  <br/> |Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen.  <br/> |
|XMPP  <br/>Nicht unterstützt in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |XMPP-Proxy Dienst (Freigabe einer IP-Adresse mit dem Access Edge-Dienst)  <br/> |Beliebig  <br/> |Der XMPP-Proxy Dienst sendet Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen.  <br/> |
|Zugriff/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebig  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Zugriffs-Edgedienst <br/> **Öffentliche IP-Adresse:** Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts <br/> |Beliebig  <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Webkonferenzen/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |**Private IP-Adresse mit NAT:** Edge-Server-Webkonferenz-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Webkonferenz-Edgedienst, öffentliche IP-Adresse <br/> |Web-Konferenzmedien.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |**Private IP-Adresse mit NAT:** Edge-Server A/V-Edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Virtuelle IPs interne Schnittstelle

Unsere Hilfestellung ist hier etwas anders. Tatsächlich empfehlen wir in einer HLB-Situation, das Weiterleiten über eine interne VIP nur unter den folgenden Umständen:
  
- Wenn Sie Exchange 2007 oder Exchange 2010 Unified Messaging (um) verwenden.
    
- Wenn Sie Vorversions-Clients haben, die Edge verwenden.
    
Die folgende Tabelle enthält Anleitungen für diese Szenarien, aber ansonsten sollten Sie in der Lage sein, vom zentralen Verwaltungsspeicher (CMS) abhängig zu sein, um den Datenverkehr an den einzelnen Edgeserver weiterzuleiten, der ihm bekannt ist (Dies erfordert, dass CMS auf dem Edgeserver auf dem neuesten Stand gehalten wird. Informationen, natürlich).
  
|**Protokoll**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Jede:  <br/> • Regisseur  <br/> • VIP-Adresse des Director-Pools  <br/> • Front-End-Server  <br/> • VIP-Adresse des Front-End-Pools  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Ausgehende SIP-Datenverkehr von Ihrem Director, Director Pool VIP Address, Front-End-Server oder VIP-Adresse des Front-End-Pools zu ihrer internen Edge-Server-Schnittstelle.  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Edge-Server-interne VIP-Oberfläche  <br/> |Jede:  <br/> • Regisseur  <br/> • VIP-Adresse des Director-Pools  <br/> • Front-End-Server  <br/> • VIP-Adresse des Front-End-Pools  <br/> |Eingehender SIP-Datenverkehr an Ihren Director, den Director-Pool, die VIP-Adresse, den Front-End-Server oder die VIP-Adresse des Front-End-Pools über die interne Schnittstelle  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Jede:  <br/> • IP-Adresse des Front-End-Servers  <br/> • IP-Adresse des Front-End-Pools  <br/> • Alle Überlebenden Branch-Appliances, die diesen Edge-Server verwenden  <br/> • Überlebensfähiger Branch Server mit diesem Edgeserver  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Authentifizierung von A/V-Benutzern von Ihrem Front-End-Server oder Front-End-Pool oder ihrer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mithilfe Ihres Edge-Servers.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Interne Edge-Server-Schnittstelle  <br/> |Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen Ihren internen Benutzern und externen Benutzern.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig   <br/> |Edge-Server-interne VIP-Oberfläche  <br/> |Fallback-Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für die Dateiübertragung und Desktopfreigabe verwendet.  <br/> |
