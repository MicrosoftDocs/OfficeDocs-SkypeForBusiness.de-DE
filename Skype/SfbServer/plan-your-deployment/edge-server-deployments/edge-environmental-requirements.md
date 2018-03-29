---
title: Umgebungsanforderungen des Edgeservers in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Zusammenfassung: Erfahren Sie mehr über die umgebungsanforderungen für Edge-Server in Skype für Business Server 2015.'
ms.openlocfilehash: fd3c7d6c5fe138878b0122ea5c1885ad6ef84171
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server-2015"></a>Umgebungsanforderungen des Edgeservers in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den umgebungsanforderungen für Edge-Server in Skype für Business Server 2015.
  
Ein Großteil der Planung und Vorbereitung muss außerhalb der Skype für Business Server 2015 Edge-Server-Umgebung selbst stattfinden. In diesem Artikel sehen wir uns an, welche Vorbereitungen laut unserer Liste unten in der Organisationsumgebung getroffen werden müssen:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Topologieplanung
<a name="TopoPlan"> </a>

Skype für Topologien mit Business Server 2015 Edge-Server verwendet werden können:
  
- Routingfähige öffentliche IP-Adressen.
    
- Nicht-routingfähige private IP-Adressen, wenn die **symmetrische** Netzwerkadressenübersetzung (Network Address Translation, NAT) verwendet wird
    
> [!TIP]
> Den Edge-Server kann eine einzelne IP-Adresse mit unterschiedlichen Ports verwenden Sie für jeden Dienst konfiguriert werden, oder es unterschiedliche IP-Adressen für jeden Dienst verwenden kann, aber verwenden Sie den gleichen Standardport (die standardmäßig TCP 443 werden). Weitere Informationen finden Sie im Abschnitt „IP-Adressanforderungen“ unten. 
  
Bedenken Sie folgende Punkte, wenn Sie sich für die Verwendung von nicht-routingfähigen privaten IP-Adressen mit NAT entscheiden:
  
- Sie müssen routingfähige private IP-Adressen für **alle drei** externen Schnittstellen verwenden.
    
- Sie müssen ein **symmetrisches** NAT-Gerät für eingehenden und ausgehenden Datenverkehr konfigurieren. Symmetrisches NAT-Gerät handelt es sich um die einzige NAT unterstützt mit Skype für Business Server 2015 Edge-Server verwendet werden können.
    
- Konfigurieren Sie Ihr NAT so, dass eingehende Quell-Adressen nicht geändert werden. Der A / V-edgedienst muss die eingehende Quelladresse, um die optimale Medienpfad suchen empfangen können.
    
- Edge-Server von ihren öffentlichen A miteinander kommunizieren können müssen / V-Edgeserver IP-Adressen. Ihre Firewall muss diesen Datenverkehr zulassen.
    
- NAT kann **nur** werden für einen skalierten konsolidierten Edge-Server verwendet, wenn Sie DNS-Lastenausgleich verwenden. Wenn Sie ein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie eine öffentlich routingfähige IP-Adresse **ohne** NAT verwenden.
    
Sie müssen keine Probleme mit Ihrer Access, Webkonferenzen und A / V-edgeschnittstellen hinter einem Router oder einer Firewall symmetrisches NAT-Gerät ausführen, für die einzelnen und skalierte konsolidierte Edge-Server-Topologien (sofern Sie nicht Hardwaregerät zum Lastenausgleich verwenden).
  
### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Topologieoptionen für Edgeserver

Wir haben mehrere verfügbaren Topologieoptionen für Skype für Business Server 2015 Edge-Server-Bereitstellungen:
  
- Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT
    
- Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen
    
- Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich
    
Die folgende Tabelle hilft Ihnen bei der Auswahl, indem Sie eine Zusammenfassung der Optionen jeder Topologie gibt:
  
|**Topologie**|**Hohe Verfügbarkeit**|**Zusätzliche DNS-Einträge für externe Edgeserver im edgepool erforderlich?**|**Edgefailover für Skype für Business Server-Sitzungen**|**Edgefailover für Skype für verbundsitzungen zwischen Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Skalierter konsolidierter Edgeserver mit privaten IP-Adressen und NAT (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja & sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit öffentlichen IP-Adressen (DNS-Lastenausgleich)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja & sup1;  <br/> |
|Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich  <br/> |Ja  <br/> |Nein (ein DNS A-Eintrag pro VIP)  <br/> |Ja  <br/> |Ja  <br/> |
   
& sup1; Exchange Unified Messaging (UM) Remotebenutzer Failover mit DNS-Lastenausgleich erfordert Exchange 2013 oder höher.
  
### <a name="ip-address-requirements"></a>IP-Adressanforderungen

Auf einer grundlegenden Ebene benötigen drei Dienste IP-Adressen. Zugriffs-edgedienst, Webkonferenz-edgedienst und A / V-edgedienst. Sie können entweder drei IP-Adressen verwenden, eine für jeden der Dienste, oder Sie können eine IP-Adresse verwenden und festlegen, dass jeder Dienst auf einem anderen Port liegt (weitere Informationen zu diesem Thema siehe Abschnitt [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)). Das sind im Prinzip alle relevanten Informationen über einzelne konsolidierte Edge-Umgebungen.
  
> [!NOTE]
> Wie oben erwähnt, können Sie sich dafür entscheiden, eine IP-Adresse für alle drei Dienste zu verwenden und diese auf verschiedenen Ports ausführen. Wir empfehlen dies allerdings nicht. Wenn Ihre Kunden auf die alternativen Ports, die Sie in diesem Szenario verwenden würden, nicht zugreifen können, haben sie auch keinen Zugriff auf die volle Funktionalität Ihrer Edge-Umgebung. 
  
Skalierte und konsolidierte Topologien können etwas komplizierter sein, sehen wir uns also ein paar Tabellen an, die die IP-Adressanforderungen zeigen. Dabei dürfen wir nicht vergessen, dass die wichtigsten Aspekte bei der Topologiewahl hohe Verfügbarkeit und Lastenausgleich sind. Anforderungen an hohe Verfügbarkeit können einen Einfluss auf die Wahl Ihres Lastenausgleichs haben (darüber mehr nach den Tabellen).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (IP-Adresse pro Rolle)

|**Anzahl von Edgeservern pro pool**|**Anzahl erforderlicher IP-Adressen für DNS-Lastenausgleich**|**Anzahl erforderlicher IP-Adressen für Hardwaregeräte zum Lastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 pro VIP) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 pro VIP) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 pro VIP) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 pro VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (eine IP-Adresse für alle Rollen)

|**Anzahl von Edgeservern pro pool**|**Anzahl erforderlicher IP-Adressen für DNS-Lastenausgleich**|**Anzahl erforderlicher IP-Adressen für Hardwaregeräte zum Lastenausgleich**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 pro VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 pro VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 pro VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 pro VIP) + 5  <br/> |
   
Sehen wir uns noch einige zusätzliche Punkte an, die wir bei der Planung berücksichtigen müssen.
  
- **Hohe Verfügbarkeit**: Wenn Sie hohen Verfügbarkeit in Ihrer Bereitstellung benötigen, sollten Sie mindestens zwei Edge-Server in einem Pool bereitstellen. Dabei ist zu beachten, dass ein einziger edgepool (obwohl Topologie-Generator ermöglicht Ihnen das Hinzufügen von bis zu 20; die nicht getestet unterstützt oder hat, und wir empfehlen, dass Sie dies nicht zu tun) bis zu 12 Edge-Server unterstützt. Wenn Sie mehr als 12 Edge-Server benötigen, sollten Sie zusätzliche Edge-Pools für sie erstellen.
    
- **Hardwaregeräte zum Lastenausgleich**: Es wird empfohlen, DNS-Lastenausgleich für die meisten Szenarien. Hardwaregerät zum Lastenausgleich wird ebenfalls unterstützt, natürlich, aber insbesondere es ist erforderlich, für ein einzelnes Szenario über DNS-Lastenausgleich:
    
  - Externen Zugriff auf Exchange 2007 oder Exchange 2010 (mit keine SP) Unified Messaging (UM).
    
- **DNS-Lastenausgleich**: für UM Exchange 2010 SP1 und neuere sind von DNS-Lastenausgleich unterstützt werden können. Beachten Sie, dass, wenn Sie mit DNS-Lastenausgleich für eine frühere Version von Exchange wechseln müssen, es arbeiten, jedoch der gesamten Datenverkehr für diese an den ersten Server im Pool gehen, und wenn es nicht verfügbar ist, wird dieser Datenverkehr anschließend fehl.
    
    DNS-Lastenausgleich wird zudem empfohlen, wenn Sie mit Unternehmen mithilfe von Lync Server 2010, Lync Server 2013 und Microsoft Office 365 zusammenfassen sind.
    
## <a name="dns-planning"></a>DNS-Planung
<a name="DNSPlan"> </a>

Wenn es sich um Skype für Business Server 2015 Edge-Server-Bereitstellung geht, ist es wichtig, zur Vorbereitung der DNS ordnungsgemäß. Mit den richtigen Einträgen ist die Bereitstellung viel einfacher. Sie haben hoffentlich im Abschnitt oben eine Topologie ausgewählt, da wir eine Übersicht machen werden, um dann einige Tabellen aufzuführen, die die DNS-Einträge für diese Szenarien erläutern. Wir müssen auch den einige [Erweiterte Edge Server DNS planen Skype für Business Server 2015](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) für weitere ausführliche lesen, wenn er benötigt.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-Einträge für einzelne konsolidierte Edge-Server-Szenarien

Die DNS-Einträge werden, Sie möchten eines einzigen Edge-Server entweder öffentlich mit IP-Adressen oder private IP-Adressen mit NAT erforderlich Da es sich um Beispieldaten handelt, überlassen wir Ihnen Beispiel-IPs, so dass Sie Ihre eigenen Einträge einfacher herausfinden können:
  
- Interner Netzwerkadapter: 172.25.33.10 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass das Netzwerk mit der internen Schnittstelle des Edgeservers mit Netzwerken verbunden, die Servern mit Skype für Business Server 2015 oder Lync Server 2013-Clients (z. B. von 172.25.33.0 zu 192.168.10.0) enthalten eine Route vorhanden ist. 
  
- Externer Netzwerkadapter:
    
  - Öffentliche IPs:
    
  - Zugriffs-Edgeservers: 131.107.155.10 (Dies ist die primäre, mit Standardgateway auf den öffentlichen Router ex festgelegt: 131.107.155.1)
    
  - Webkonferenz-Edgeserver: 131.107.155.20 (sekundär)
    
  - A / V-Edgeserver: 131.107.155.30 (sekundär)
    
  Webkonferenzen und A / V-Edgeserver, öffentliche IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften des Internet Protocol Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) von der LAN-Verbindungseigenschaften in WindowsServer.
    
  - Private IPs:
    
  - Zugriffs-Edgeservers: 10.45.16.10 (Dies ist die primäre, mit Standardgateway auf dem Router ex festgelegt: 10.45.16.1)
    
  - Webkonferenz-Edgeserver: 10.45.16.20 (sekundär)
    
  - A / V-Edgeserver: 10.45.16.30 (sekundär)
    
Webkonferenzen und A / V-Edgeserver, öffentliche IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften des Internet Protocol Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) von der LAN-Verbindungseigenschaften in WindowsServer.
  
> [!TIP]
>Es gibt weitere möglich Konfigurationen:
  
- Sie können auf dem externen Netzwerkadapter eine IP-Adresse verwenden. Nicht empfohlen, da, und klicken Sie dann Sie nun die drei Unterscheidung von Diensten mithilfe der verschiedenen Ports (was in Skype für Business Server möglich) müssen, aber es gibt einige Firewalls, die die alternative Ports blockieren können. Finden Sie im Abschnitt [Port und Planung Firewall](edge-environmental-requirements.md#PortFirewallPlan) für Weitere Informationen zu diesem ein.
    
- Sie können mit drei externen Netzwerkadaptern statt einem arbeiten und jedem davon eine Dienst-IPs zuweisen. Warum sollten Sie das tun? Dadurch werden die Dienste getrennt und wenn etwas schief läuft, ist die Problembehandlung einfacher. Außerdem können Ihre anderen Dienste möglicherweise weiterarbeiten, während Sie das Problem beheben.
    
|**Standort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder den FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |SIP.contoso.com  <br/> |**Öffentliche:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |Eine externe Schnittstelle für den Zugriffs-Edgeservers-Dienst. Sie benötigen einen für jede SIP-Domäne mit Skype für Geschäftsbenutzer.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |"webcon.contoso.com"  <br/> |**Öffentliche:** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |Eine externe Schnittstelle für Ihre Webkonferenz-edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |AV.contoso.com  <br/> |**Öffentliche:** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |Eine externe Schnittstelle des a / V-edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Eine externe Schnittstelle für den Zugriffs-Edgeservers-Dienst. Dieser SRV-Eintrag ist für Skype für Business Server 2015, Lync Server 2013 und Lync Server 2010-Clients verwenden, extern funktionieren erforderlich. Sie benötigen einen für jede Domäne mit Skype für Geschäftsbenutzer.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Eine externe Schnittstelle für den Zugriffs-Edgeservers-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Suche von Verbundpartnern notwendig, die „Zugelassene SIP-Domänen“ genannt werden. Sie benötigen einen für jede Domäne mit Skype für Geschäftsbenutzer.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Eintrag  <br/> |NV  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10  <br/> |Die interne Schnittstelle für Ihren konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS-Einträge für eine skalierte DNS- und Hardware-Edge-Server-Szenarien

Die DNS-Einträge werden, Sie möchten eines einzigen Edge-Server entweder öffentlich mit IP-Adressen oder private IP-Adressen mit NAT erforderlich Da es sich um Beispieldaten handelt, überlassen wir Ihnen Beispiel-IPs, so dass Sie Ihre eigenen Einträge einfacher herausfinden können:
  
- Interner Netzwerkadapter:
    
  - Knoten 1: 172.25.33.10 (keine Standardgateways zugewiesen)
    
  - Knoten 2: 172.25.33.11 (keine Standardgateways zugewiesen)
    
    > [!NOTE]
    > Stellen Sie sicher, dass das Netzwerk mit der internen Schnittstelle des Edgeservers mit Netzwerken verbunden, die Servern mit Skype für Business Server 2015 oder Lync Server 2013-Clients (z. B. von 172.25.33.0 zu 192.168.10.0) enthalten eine Route vorhanden ist. 
  
- Externer Netzwerkadapter:
    
  - Knoten 1
    
     - Öffentliche IPs:
    
        - Zugriffs-Edgeservers: 131.107.155.10 (Dies ist die primäre, mit Standardgateway auf den öffentlichen Router ex festgelegt: 131.107.155.1)
    
        - Webkonferenz-Edgeserver: 131.107.155.20 (sekundär)
    
        - A / V-Edgeserver: 131.107.155.30 (sekundär)
    
          Webkonferenzen und A / V-Edgeserver, öffentliche IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften des Internet Protocol Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) von der LAN-Verbindungseigenschaften in WindowsServer.
    
    - Private IPs:
    
         - Zugriffs-Edgeservers: 10.45.16.10 (Dies ist die primäre, mit Standardgateway auf dem Router ex festgelegt: 10.45.16.1)
    
         - Webkonferenz-Edgeserver: 10.45.16.20 (sekundär)
    
         - A / V-Edgeserver: 10.45.16.30 (sekundär)
    
      Webkonferenzen und A / V-Edgeserver, öffentliche IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften des Internet Protocol Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) von der LAN-Verbindungseigenschaften in WindowsServer.
    
  - Knoten 2
    
     - Öffentliche IPs:
    
       - Zugriffs-Edgeservers: 131.107.155.11 (Dies ist die primäre, mit Standardgateway auf den öffentlichen Router ex festgelegt: 131.107.155.1)
    
       - Webkonferenz-Edgeserver: 131.107.155.21 (sekundär)
    
       - A / V-Edgeserver: 131.107.155.31 (sekundär)
    
      Webkonferenzen und A / V-Edgeserver, öffentliche IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften des Internet Protocol Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) von der LAN-Verbindungseigenschaften in WindowsServer.
    
  - Private IPs:
    
      - Zugriffs-Edgeservers: 10.45.16.11 (Dies ist die primäre, mit Standardgateway auf dem Router ex festgelegt: 10.45.16.1)
    
      - Webkonferenz-Edgeserver: 10.45.16.21 (sekundär)
    
      - A / V-Edgeserver: 10.45.16.31 (sekundär)
    
      Webkonferenzen und A / V-Edgeserver, öffentliche IP-Adressen sind zusätzliche (sekundäre) IP-Adressen im Abschnitt erweitert der Eigenschaften des Internet Protocol Version 4 (TCP/IPv4) und Internetprotokoll Version 6 (TCP/IPv6) von der LAN-Verbindungseigenschaften in WindowsServer.
    
Es gibt weitere möglich Konfigurationen:
  
- Sie können auf dem externen Netzwerkadapter eine IP-Adresse verwenden. Nicht empfohlen, da, und klicken Sie dann Sie nun die drei Unterscheidung von Diensten mithilfe der verschiedenen Ports (was in Skype für Business Server möglich) müssen, aber es gibt einige Firewalls, die die alternative Ports blockieren können. Finden Sie im Abschnitt [Port und Planung Firewall](edge-environmental-requirements.md#PortFirewallPlan) für Weitere Informationen zu diesem ein.
    
- Sie können mit drei externen Netzwerkadaptern statt einem arbeiten und jedem davon eine Dienst-IPs zuweisen. Warum sollten Sie das tun? Dadurch werden die Dienste getrennt und wenn etwas schief läuft, ist die Problembehandlung einfacher. Außerdem können Ihre anderen Dienste möglicherweise weiterarbeiten, während Sie das Problem beheben.
    
|**Standort**|**Typ**|**Port**|**FQDN oder DNS-Eintrag**|**IP-Adresse oder den FQDN**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |SIP.contoso.com  <br/> |**Öffentliche:** 131.107.155.10 und 131.107.155.11 <br/> **Privat:** 10.45.16.10 und 10.45.16.11 <br/> |Eine externe Schnittstelle für den Zugriffs-Edgeservers-Dienst. Sie benötigen einen für jede SIP-Domäne mit Skype für Geschäftsbenutzer.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |"webcon.contoso.com"  <br/> |**Öffentliche:** 131.107.155.20 und 131.107.155.21 <br/> **Privat:** 10.45.16.20 und 10.45.16.21 <br/> |Eine externe Schnittstelle für Ihre Webkonferenz-edgedienst.  <br/> |
|Externes DNS  <br/> |Ein Eintrag  <br/> |NV  <br/> |AV.contoso.com  <br/> |**Öffentliche:** 131.107.155.30 und 131.107.155.31 <br/> **Privat:** 10.45.16.30 und 10.45.16.31 <br/> |Eine externe Schnittstelle des a / V-edgedienst.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Eine externe Schnittstelle für den Zugriffs-Edgeservers-Dienst. Dieser SRV-Eintrag ist für Skype für Business Server 2015, Lync Server 2013 und Lync Server 2010-Clients verwenden, extern funktionieren erforderlich. Sie benötigen einen für jede Domäne mit Skype für Unternehmen.  <br/> |
|Externes DNS  <br/> |SRV-Eintrag  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Eine externe Schnittstelle für den Zugriffs-Edgeservers-Dienst. Dieser SRV-Eintrag ist für die automatische DNS-Suche von Verbundpartnern notwendig, die „Zugelassene SIP-Domänen“ genannt werden. Sie benötigen einen für jede Domäne mit Skype für Unternehmen.  <br/> |
|Interne DNS-Konfiguration  <br/> |Ein Eintrag  <br/> |NV  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10 und 172.25.33.11  <br/> |Die interne Schnittstelle für Ihren konsolidierten Edgeserver.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-Eintrag für Partnerverbund (alle Szenarien)

|**Standort**|**Typ**|**Port**|**FQDN**|**FQDN-Hosteintrag**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Die SIP-Zugriffs-Edgeservers externe Schnittstelle für die automatische DNS-Ermittlung erforderlich. Wird von der potenziellen Verbundpartnern verwendet. Es ist auch bekannt als "SIP-Domänen zulassen". Sie benötigen eine der folgenden für jede SIP-Domäne mit Skype für Geschäftsbenutzer.  <br/><br/> **Hinweis:** Sie benötigen diesen SRV-Eintrag für die Mobilität und das Push Notification clearing House verwenden. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-Einträge für XMPP (Extensible Messaging and Presence Protocol)

|**Standort**|**Typ**|**Port**|**FQDN**|**IP-Adresse oder den FQDN-Hosteintrag**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Externes DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp server._tcp.contoso.com  <br/> |"XMPP.contoso.com"  <br/> |Die XMPP-Proxy-Schnittstelle auf dem Zugriffs-edgedienst oder Edge-Pool. Sie müssen dies wiederholen nach Bedarf für alle internen SIP-Domänen mit Skype für aktiviert Unternehmensbenutzer, Kontakt mit XMPP-Kontakten durch zulässig ist:  <br/> • eine globale Richtlinie  <br/> • ein, in dem der Benutzer aktiviert die, Standortrichtlinie  <br/> • eine Benutzerrichtlinie angewendet, der Skype für Unternehmen aktivierten Benutzer  <br/> Eine zulässige XMPP-Richtlinie muss auch in der XMPP-Partnerbenutzerrichtlinie konfiguriert werden.  <br/> |
|Externes DNS  <br/> |SRV  <br/> |A  <br/> |"XMPP.contoso.com"  <br/> |IP-Adresse des Zugriffs-edgediensts auf dem Edgeserver oder edgepool XMPP-Proxydienst hosting  <br/> |Dies verweist auf Zugriffs-edgediensts auf dem Edge-Server oder Edge-Pool, der als Host den XMPP-Proxydienst. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (A oder AAAA).  <br/> |
   
## <a name="certificate-planning"></a>Zertifikatsplanung
<a name="CertPlan"> </a>

Skype für Business Server 2015 verwendet Zertifikate für die sichere, verschlüsselte Kommunikation zwischen Servern sowohl vom Server an den Client. Wie Sie sich sicher schon gedacht haben, müssen DNS-Einträge Ihrer Zertifikate mit Antragstellername (SN) und alternativem Antragstellernamen (SAN) auf Ihren Zertifikaten zusammenpassen. Das macht jetzt in der Planungsphase Arbeit, um sicherzustellen, dass die richtigen FQDNs im DNS für die SN- und SAN-Einträger Ihrer Zertifikate registriert sind.
  
Wir besprechen externe und interne Zertifikate getrennt und sehen uns dann auch eine Tabelle mit den Anforderungen für beide an.
  
### <a name="external-certificates"></a>Externe Zertifikate

Das Zertifikat zugewiesen Ihrer externen Edge-Server-Schnittstellen müssen mindestens von einer öffentlichen Zertifizierungsstelle (CA) bereitgestellt werden. Es kann keine bestimmte Zertifizierungsstelle wird empfohlen, Ihnen, aber haben wir eine Liste von Zertifizierungsstellen, die [Unified Communications-Zertifikats Partner](https://support.microsoft.com/en-us/kb/929395) , die Sie eine Aufstellung der ergreifen können, um festzustellen, ob Ihre bevorzugten Zertifizierungsstellen aufgeführt ist.
  
Wann müssen Sie eine Anforderung an eine CA für dieses öffentliche Zertifikat stellen und wie machen Sie das? Es gibt verschiedene Arten:
  
- Navigieren Sie durch die Installation von Skype für Business Server, und klicken Sie dann die Edge-Server-Bereitstellung. Die Skype für Business Server-Bereitstellungsassistenten müssen einen Schritt, eine zertifikatanforderung zu generieren, die Sie dann auf die gewählte Zertifizierungsstelle senden können.
    
- Sie können auch Windows PowerShell-Befehle verwenden zum Generieren dieser Anforderung, die mit Ihrer geschäftlichen Anforderungen oder Bereitstellungsstrategie Weitere Inline ist.
    
- Schließlich möglicherweise die Zertifizierungsstelle ihre eigenen Prozess der Übermittlung, auch Windows PowerShell oder eine andere Methode beteiligt ist. In diesem Fall müssen Sie sich zusätzlich zu den hier zur Verfügung gestellten Informationen auf deren Dokumentation verlassen.
    
Nachdem Sie das Zertifikat gelangt sind, benötigen Sie fahren fort, und weisen sie diese Dienste in Skype für Business Server:
  
- Zugriff auf Edge-Service-Schnittstelle
    
- Webdienstschnittstelle für den Webkonferenz-Edgeserver
    
- Audio/Video-Authentifizierungsdienst (nicht Verwechseln Sie dies mit dem A / V-Edgeserver als, die nicht verwenden Sie ein Zertifikat zum Verschlüsseln von Audio- und Videostreams)
    
> [!IMPORTANT]
> Alle Edgeserver müssen über genau das gleiche Zertifikat mit dem gleichen privaten Schlüssel für den Mediarelay-Authentifizierungsdienst verfügen. 
  
### <a name="internal-certificates"></a>Interne Zertifikate

Für die interne Edge-Server-Schnittstelle können Sie ein öffentliches Zertifikat von einer öffentlichen Zertifizierungsstelle oder ein von Ihrer Organisation internen Zertifizierungsstelle ausgestelltes Zertifikat verwenden. Denken Sie daran, dass interne Zertifikate einen SN-Eintrag verwenden und keine SAN-Einträge, über SAN müssen Sie sich bei internen Zertifikaten also keine Gedanken machen.
  
### <a name="required-certificates-table"></a>Tabelle erforderlicher Zertifikate

Diese Tabelle hilft Ihnen bei Ihren Anforderungen. Die FQDN-Einträge sind lediglich Beispiel-Domänen. Ihre Anforderungen müssen sich nach Ihren privaten und öffentlichen Domänen richten; im Folgenden finden Sie eine Richtlinie zu dem, was wir verwendet haben:
  
- contoso.com: Öffentlicher FQDN
    
- fabrikam.com: Zweiter öffentlicher FQDN (als Demo dessen hinzufügt, was angefordert werden muss, wenn Sie mehrere SIP-Domänen haben)
    
- Contoso.net: Interne Domäne
    
#### <a name="edge-certificate-table"></a>Edgezertifikattabelle

Unabhängig davon, ob Sie einen einzelnen Edgeserver oder einem edgepool durchführen ist dies für das Zertifikat benötigen:
  
|**Komponente**|**Name des Antragstellers (SN)**|**Alternative Antragstellernamen (SAN) / Reihenfolge**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Externer Edgeserver  <br/> |SIP.contoso.com  <br/> |SIP.contoso.com  <br/> "webcon.contoso.com"  <br/> "SIP.Fabrikam.com"  <br/> |Sie benötigen dieses Zertifikat, um eine Anfrage an eine öffentliche CA zu stellen. Es muss den externen Edgeschnittstellen für Folgendes zugewiesen werden:<br/> • Zugriffs-Edgeservers  <br/> • Webkonferenz-Edgeserver  <br/> • Audio/Video-Authentifizierung  <br/> <br/>Die gute Nachricht ist, dass SANs werden automatisch auf Ihre zertifikatanforderung hinzugefügt, und daher senden Sie Ihr Zertifikat nach der die Anforderung, basierend auf was Sie für diese Bereitstellung im Topologie-Generator definiert haben. Sie müssen nur SAN-Einträge für zusätzliche SIP-Domänen oder andere Einträge hinzufügen, die unterstützt werden sollen. Warum wird sip.contoso.com in dieser Instanz repliziert? Dies geschieht auch automatisch und ist notwendig, damit alles reibungslos läuft.  <br/><br/> **Hinweis:** Dieses Zertifikat kann auch für Öffentliche Instant Messaging-Diensten verwendet werden. Die Vorgehensweise ist die gleiche; in früheren Versionen dieser Dokumentation wurde das jedoch als getrennte Tabelle aufgeführt, was jetzt nicht mehr der Fall ist. <br/> |
|Interner Edgeserver  <br/> |sfbedge.contoso.com  <br/> |NV  <br/> |Sie können dieses Zertifikat von einer öffentlichen CA oder einer internen CA bekommen. Es muss die Server-EKU (erweiterte Schlüsselverwendung für Server) beinhalten. Sie weisen es der internen Edgeschnittstelle zu.  <br/> |
   
Wenn Sie ein Zertifikat für XMPP (Extensible Messaging and Presence Protocol) benötigen, sieht dieses genau wie in den Tabelleneinträgen für Externer Edgeserver oben aus, hat allerdings die folgenden beiden zusätzlichen SAN-Einträge:
  
- "XMPP.contoso.com"
    
- \*. contoso.com
    
Denken Sie daran, dass XMPP derzeit nur für Google Talk unterstützt wird. Wenn Sie es für etwas anderes verwenden wollen oder müssen, müssen Sie die Funktion mit dem entsprechenden Drittanbieter klären.
  
## <a name="port-and-firewall-planning"></a>Port- und Firewallplanung
<a name="PortFirewallPlan"> </a>

Abrufen der Planung der richtige für Ports und Firewalls Skype für Business Server-Edgeserver können Bereitstellungen Tage oder Wochen der Problembehandlung zu speichern und belasten. Daher führen wir einige Tabellen auf, die unsere Protokollverwendung zeigen, und welche Eingangs- und Ausgangsports offen sein müssen, sowohl für NAT als auch für öffentliche IP-Szenarien. Es wird außerdem separate Tabellen für Szenarien mit Hardwaregerät zum Lastenausgleich sowie weiterer Hilfestellung dazu geben. Für weitere dort lesen haben wir auch [technische Diagramme für Skype für Business Server 2015](../../technical-diagrams.md)sowie einige [Szenarien in Skype für Business Server 2015 Edge-Server](scenarios.md) für Ihre bestimmter Bereitstellungsprobleme Auschecken kann.
  
### <a name="general-protocol-usage"></a>Allgemeine Protokollverwendung

Betrachten wir die folgenden Tabelle, bevor wir uns die Zusammenfassungstabelle für externe und interne Firewalls ansehen:
  
|**A/v-transport**|**Verwendung**|
|:-----|:-----|
|UDP  <br/> |Das bevorzugte Transportschichtprotokoll für Audio und Video.  <br/> |
|TCP  <br/> |Das Ausweich-Transportschichtprotokoll für Audio und Video.  <br/> Erforderliche Ebene Transportprotokoll für die Anwendungsfreigabe zu Skype für Business Server 2015, Lync Server 2013 und Lync Server 2010.  <br/> Das erforderliche Ebene Transportprotokoll für die Dateiübertragung zu Skype für Business Server 2015, Lync Server 2013 und Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Port-Firewall

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden sowie für alle, die öffentliche IP-Adressen verwenden. Dadurch werden alle Variationen in unseren [Edge-Server-Szenarien in Skype für Business Server 2015](scenarios.md) Abschnitt behandelt.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Port-Bereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Beliebig  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit Zugriffs-edgediensts  <br/> |XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbünden.  <br/> |
|Zugriff/HTTP  <br/> |TCP  <br/> |80  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Beliebig  <br/> |Zertifikatsperre und Zertifikatssperrlistenprüfung und -abruf  <br/> |
|Zugriff/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Beliebig  <br/> |DNS-Abfrage über TCP.  <br/> |
|Zugriff/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Beliebig  <br/> |DNS-Abfrage über UDP.  <br/> |
|Zugriff/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Beliebig  <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Webkonferenzen/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edge-Server Webkonferenz-edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server Webkonferenz-Edgeserver Service öffentliche IP-Adresse <br/> |Web-Konferenzmedien.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |Beliebig  <br/> |3478 ausgehend wird:  <br/> • Von Skype für Business Server verwendet, um den Edge-Server-Version zu bestimmen, mit dem Sie kommunizieren wird.  <br/> • Für Mediendatenverkehr zwischen dem Edge-Servern verwendet.  <br/> • Für den Verbund mit Lync Server 2010 erforderlich.  <br/> • Erforderlich, wenn mehrere edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |Beliebig  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Port-Firewall

|**Protokoll**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Jede der folgenden, die den XMPP-Gatewaydienst ausführt:  <br/> • Front-End-Server  <br/> • Front-End-pool  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gateway-Dienst auf dem Front-End-Server oder Front-End-Pool ausgeführt.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Jede:  <br/> • Director  <br/> • Director-pool  <br/> • Front-End-Server  <br/> • Front-End-pool  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Ausgehender SIP-Datenverkehr aus dem Director, Director-Pool, Front-End-Server oder Front-End-Pool zu Ihrer internen Edge-Server-Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Jede:  <br/> • Director  <br/> • Director-pool  <br/> • Front-End-Server  <br/> • Front-End-pool  <br/> |Eingehender SIP-Datenverkehr auf den Director, Director-Pool, Front-End-Server oder Front-End-Pool aus der internen Edge-Server-Schnittstelle.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jedem Front-End-Server  <br/>  im Front-End-pool <br/> |Interne Schnittstelle des Edgeservers  <br/> |Webkonferenzdatenverkehr von der Front-End-Server oder einzelnen Front-End-Server (Wenn Sie einen Front-End-Pool verwenden) auf die interne Schnittstelle des Edge-Server.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Front-End-pool  <br/> • Alle Survivable Branch Appliance mit diesem Edgeserver  <br/> • Alle Survivable Branch Server mit diesem Edgeserver  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Authentifizierung von A / V-Benutzern von den Front-End-Server oder Front-End-Pool, oder Ihrer Survivable Branch Appliance oder einen Survivable Branch Server, den Edge-Server verwenden.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Bevorzugter Pfad für A / V-Mediendaten zwischen Ihrem internen und externen Benutzern und Ihrer Survivable Branch Appliance oder einen Survivable Branch Server übertragen.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Ausweichpfad für A / V-Mediendaten zwischen Ihrem internen und externen Benutzern und Ihrer Survivable Branch Appliance oder einen Survivable Branch Server übertragen, wenn keine UDP-Kommunikation nicht funktioniert. TCP wird dann für die Dateiübertragung und die Desktopfreigabe verwendet  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Jede:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher beinhaltet  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher beinhaltet  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Replikation von Änderungen aus Ihrer zentralen Verwaltungsspeicher an den Edge-Server zu speichern.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Zentralisierte Protokollierungsdienst Controller Skype für Cmdlets für Business Server-Verwaltungsshell und Centralized Logging Service, ClsController-Befehlszeile (ClsController.exe) oder Agent (ClsAgent.exe) Befehle und Protokoll-Auflistung verwenden.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Zentralisierte Protokollierungsdienst Controller Skype für Cmdlets für Business Server-Verwaltungsshell und Centralized Logging Service, ClsController-Befehlszeile (ClsController.exe) oder Agent (ClsAgent.exe) Befehle und Protokoll-Auflistung verwenden.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Zentralisierte Protokollierungsdienst Controller Skype für Cmdlets für Business Server-Verwaltungsshell und Centralized Logging Service, ClsController-Befehlszeile (ClsController.exe) oder Agent (ClsAgent.exe) Befehle und Protokoll-Auflistung verwenden.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Hardwaregeräte zum Lastenausgleich für Edge-Porttabellen

Hardwaregeräte zum Lastenausgleich und Edge-Ports bekommen Ihren eigenen Abschnitt, da die Vorgehensweise aufgrund der zusätzlichen Hardware etwas komplizierter ist. Hilfestellung zu diesem speziellen Szenario finden Sie in den Tabellen unten:
  
#### <a name="external-port-firewall-summary-table"></a>Zusammenfassungstabelle für externe Port-Firewall

Die Quell-IP-Adresse und die Ziel-IP-Adresse enthalten Informationen für Benutzer, die private IP-Adressen mit NAT verwenden sowie für alle, die öffentliche IP-Adressen verwenden. Dadurch werden alle Variationen in unseren [Edge-Server-Szenarien in Skype für Business Server 2015](scenarios.md) Abschnitt behandelt.
  
|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Port-Bereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Zugriff/HTTP  <br/> |TCP  <br/> |80  <br/> |Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse  <br/> |Beliebig  <br/> |Zertifikatsperre und Zertifikatssperrlistenprüfung und -abruf  <br/> |
|Zugriff/DNS  <br/> |TCP  <br/> |53  <br/> |Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse  <br/> |Beliebig  <br/> |DNS-Abfrage über TCP.  <br/> |
|Zugriff/DNS  <br/> |UDP  <br/> |53  <br/> |Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse  <br/> |Beliebig  <br/> |DNS-Abfrage über UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edgeserver, A / V-Edgedienst-IP-Adresse  <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edgeserver, A / V-edgedienst öffentliche IP-Adresse  <br/> |Beliebig  <br/> |Dies wird für die Weiterleitung von Mediendatenverkehr verwendet.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edgeserver, A / V-edgedienst öffentliche IP-Adresse  <br/> |Beliebig  <br/> |3478 ausgehend wird:  <br/> • Von Skype für Business Server verwendet, um den Edge-Server-Version zu bestimmen, mit dem Sie kommunizieren wird.  <br/> • Für Mediendatenverkehr zwischen dem Edge-Servern verwendet.  <br/> • Für den Verbund erforderlich.  <br/> • Erforderlich, wenn mehrere edgepools in Ihrer Organisation bereitgestellt werden.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Edgeserver, A / V-edgedienst öffentliche IP-Adresse  <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |Edgeserver, A / V-edgedienst öffentliche IP-Adresse  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Edgeserver, A / V-edgedienst öffentliche IP-Adresse  <br/> |Beliebig  <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Zusammenfassungstabelle für interne Port-Firewall

|**Protokoll**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Jede der folgenden, die den XMPP-Gatewaydienst ausführt:  <br/> • Front-End-Server  <br/> • Front-End-Pool VIP-Adresse den XMPP-Gatewaydienst ausführt  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Ausgehender XMPP-Datenverkehr von Ihrem XMPP-Gateway-Dienst auf dem Front-End-Server oder Front-End-Pool ausgeführt.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Jede:  <br/> • Front-End-Server, der den zentralen Verwaltungsspeicher beinhaltet  <br/> • Front-End-Pool, der den zentralen Verwaltungsspeicher beinhaltet  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Replikation von Änderungen aus Ihrer zentralen Verwaltungsspeicher an den Edge-Server.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jedem Front-End-Server im Front-End-Pool  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Webkonferenzdatenverkehr von der Front-End-Server oder einzelnen Front-End-Server (Wenn Sie einen Front-End-Pool verwenden) auf die interne Schnittstelle des Edge-Server.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jedem Front-End-Server im Front-End-Pool  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Bevorzugter Pfad für A / V-Mediendaten zwischen Ihrem internen und externen Benutzern und Ihrer Survivable Branch Appliance oder einen Survivable Branch Server übertragen.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Jede:  <br/> • Front-End-Server  <br/> • Jedem Front-End-Server im Pool  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Ausweichpfad für A / V-Mediendaten zwischen Ihrem internen und externen Benutzern und Ihrer Survivable Branch Appliance oder einen Survivable Branch Server übertragen, wenn keine UDP-Kommunikation nicht funktioniert. TCP wird dann für die Dateiübertragung und die Desktopfreigabe verwendet  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Zentralisierte Protokollierungsdienst Controller Skype für Cmdlets für Business Server-Verwaltungsshell und Centralized Logging Service, ClsController-Befehlszeile (ClsController.exe) oder Agent (ClsAgent.exe) Befehle und Protokoll-Auflistung verwenden.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Zentralisierte Protokollierungsdienst Controller Skype für Cmdlets für Business Server-Verwaltungsshell und Centralized Logging Service, ClsController-Befehlszeile (ClsController.exe) oder Agent (ClsAgent.exe) Befehle und Protokoll-Auflistung verwenden.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Zentralisierte Protokollierungsdienst Controller Skype für Cmdlets für Business Server-Verwaltungsshell und Centralized Logging Service, ClsController-Befehlszeile (ClsController.exe) oder Agent (ClsAgent.exe) Befehle und Protokoll-Auflistung verwenden.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Virtuelle IPs externe Schnittstelle

|**Rolle oder Protokoll**|**TCP oder UDP**|**Zielport oder Port-Bereich**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Beliebig  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit Zugriffs-edgedienst)  <br/> |XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbünden.  <br/> |
|XMPP  <br/> |TCP  <br/> |5269  <br/> |XMPP-Proxydienst (teilt eine IP-Adresse mit Zugriffs-edgedienst)  <br/> |Beliebig  <br/> |XMPP-Proxydienst sendet Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbünden.  <br/> |
|Zugriff/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP mit NAT:** Edge-Server-Zugriffsedge-Dienst <br/> **Öffentliche IP-Adresse:** Edge-Server-Zugriffs-Edgeservers öffentliche IP-Adresse <br/> |Beliebig  <br/> |Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP.  <br/> |
|Webkonferenzen/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edge-Server Webkonferenz-edgedienst <br/> **Öffentliche IP-Adresse:** Edge-Server Webkonferenz-Edgeserver öffentliche IP-Adresse <br/> |Web-Konferenzmedien.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über UDP auf Port 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |**Private IP mit NAT:** Edgeserver, A / V-edgedienst <br/> **Öffentliche IP-Adresse:** Edgeserver, A / V-edgedienst öffentliche IP-Adresse <br/> |STUN/TURN-Aushandlung von Kandidaten über TCP auf Port 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Virtuelle IPs interne Schnittstelle

Unsere Hilfestellung ist hier etwas anders. Tatsächlich empfehlen wir in einer HLB-Situation, das Weiterleiten über eine interne VIP nur unter den folgenden Umständen:
  
- Wenn Sie Exchange 2007 oder Exchange 2010 Unified Messaging (UM) verwenden.
    
- Wenn Sie Vorversions-Clients haben, die Edge verwenden.
    
Die folgende Tabelle liefert Anweisungen für diese Szenarien, jedoch können von zentralen Verwaltungsspeicher (CMS) für die Weiterleitung von Verkehr an den einzelnen Edgeserver abhängig bekannt, dass ist Sie andernfalls sollte (Dies erfordert, dass CMS auf Edge-Server auf dem aktuellen Stand ist Informationen, natürlich).
  
|**Protokoll**|**TCP oder UDP**|**Port**|**Quell-IP-Adresse**|**Ziel-IP-Adresse**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Jede:  <br/> • Director  <br/> • Director-Pool-VIP-Adresse  <br/> • Front-End-Server  <br/> • IP-Adresse des Front-End-pool  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Ausgehender SIP-Datenverkehr aus dem Director, Director-Pool-VIP-Adresse, Front-End-Server oder Front-End-Pool-VIP-Adresse in Ihrer internen Edge-Server-Schnittstelle.  <br/> |
|Zugriff/ SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Edge-Server interne VIP-Schnittstelle  <br/> |Jede:  <br/> • Director  <br/> • Director-Pool-VIP-Adresse  <br/> • Front-End-Server  <br/> • IP-Adresse des Front-End-pool  <br/> |Eingehender SIP-Datenverkehr auf dem Director Director-Pool-VIP-Adresse, Front-End-Server oder Front-End-Pool-VIP-Adresse von der internen Edge-Server-Schnittstelle.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Jede:  <br/> • Front-End-Server-IP-Adresse  <br/> • Front-End-Pool-IP-Adresse  <br/> • Alle Survivable Branch Appliance mit diesem Edgeserver  <br/> • Alle Survivable Branch Server mit diesem Edgeserver  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Authentifizierung von A / V-Benutzern von den Front-End-Server oder Front-End-Pool, oder Ihrer Survivable Branch Appliance oder einen Survivable Branch Server, den Edge-Server verwenden.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Beliebig  <br/> |Interne Schnittstelle des Edgeservers  <br/> |Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen Ihren internen Benutzern und externen Benutzern.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Beliebig  <br/> |Edge-Server interne VIP-Schnittstelle  <br/> |Fallback-Pfad für die A/V-Medienübertragung zwischen Ihren internen und externen Benutzern, wenn die UDP-Kommunikation nicht funktioniert. TCP wird dann für die Dateiübertragung und Desktopfreigabe verwendet.  <br/> |