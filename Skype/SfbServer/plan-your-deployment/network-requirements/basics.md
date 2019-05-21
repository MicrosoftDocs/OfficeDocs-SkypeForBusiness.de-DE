---
title: DNS-Grundlagen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 verfügt über integrierte Software, die DNS-Dienste bereitstellen kann, daher möchten Sie möglicherweise die verfügbare Dokumentation überprüfen, beispielsweise den Leitfaden zur DNS-Richtlinien Szenarien. Wenn Sie möchten, können Sie eine Drittanbieterlösung auswählen.
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297274"
---
# <a name="dns-basics"></a>DNS-Grundlagen
 
Windows Server 2016 verfügt über integrierte Software, die DNS-Dienste bereitstellen kann, daher möchten Sie möglicherweise die verfügbare Dokumentation überprüfen, beispielsweise den [Leitfaden zur DNS-Richtlinien Szenarien](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Wenn Sie möchten, können Sie eine Drittanbieterlösung auswählen.
  
Wir empfehlen, dass Sie als bewährte Methode einen bestimmten Server in ihrer Implementierung für die Bereitstellung von DNS reservieren. Sie könnten Sie möglicherweise auf einem der Server einrichten, die für eine der Skype for Business-Serverrollen dediziert sind, aber wenn dieser Server auch Teil eines Pools war und versehentlich außer Betrieb genommen wurde, würde Skype for Business fehlschlagen, bis DNS-Dienste wiederhergestellt wurden.
  
## <a name="dns-records"></a>DNS-Einträge

Jede Zuordnung eines Namens zu einer IP-Adresse (und dies kann eine IPv4-oder IPv6-Adresse sein) wird in einem DNS-Eintrag auf dem DNS-Server gespeichert. Der Name wird im DNS-Bericht speziell als FQDN beschrieben – ein vollständig qualifizierter Domänenname. Obwohl *contoso.com* ein gültiger Domänenname ist, ist es die Kurzform für * \*. contoso.com* , daher ist es mehrdeutig und kann möglicherweise auf einen beliebigen Server in der Domäne verweisen. Ein Beispiel für einen FQDN, der auf einen einzelnen Server in Ihrer Domäne verweisen würde, ist möglicherweise **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Standardmäßig ist der Computername eines Computers, der nicht zu einer Domäne gehört, ein Hostname und kein vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN). Der Topologie-Generator verwendet FQDNs, keine Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. **Nur Standardzeichen verwenden** (einschließlich a-z, a-z, 0-9 und Bindestriche) beim Zuweisen von FQDNs zu Ihren Servern mit Skype for Business Server. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.
  
Zusätzlich zu einer IP-Adresse kann der FQDN einem **VIP** zugeordnet werden – einer virtuellen IP-Adresse. Bei einem VIP handelt es sich um eine IP-Adresse, die keiner tatsächlichen physikalischen Netzwerkschnittstelle entspricht. Ein VIP verweist oft auf einen Serverpool, der eine Serverrolle ausführt, oder auf ein paar von Servern, die für Redundanz und Fehlertoleranz konfiguriert sind.
  
Es gibt verschiedene Arten von DNS-Einträgen, die für diese Diskussion am relevantesten sind: 
  
- **A** – ein Adressdatensatz oder ein Host Eintrag gibt eine 32-Bit-IPv4-Adresse zurück. Wird am häufigsten verwendet, um hostnames einer IP-Adresse des Hosts zuzuordnen.
    
- **AAAA** – ein IPv6-Adressdatensatz. Gibt eine 128-Bit-IPv6-Adresse zurück. Wird am häufigsten verwendet, um hostnames einer IP-Adresse des Hosts zuzuordnen.
    
- **CNAME** – ein kanonischer Namenseintrag. Dadurch wird ein Name in einen anderen aufgelöst: beim DNS-Lookup wird die Suche mit dem neuen Namen erneut versucht.
    
- **SRV** – ein Diensteintrag (SRV-Eintrag) gibt einen Dienst (einen Prozess auf einem Server) an, auf den auf eine bestimmte Port-und IP-Kombination zugegriffen wird. Die Namen der Dienste, die einen Diensteintrag erfordern, sind festgelegt und können nicht mehr angepasst werden, als dass Sie Teil ihrer SIP-Domäne sind. Einige Benutzer Dienste verwenden einfache URLs. Ein SRV-Eintrag muss auf einen Speicherort in der gleichen SIP-Domäne verweisen, daher benötigen Sie mehrere SRV-Einträge für einen bestimmten Dienst, wenn Sie über mehrere Domänen verfügen.
    
## <a name="how-to-choose-a-sip-domain-name"></a>So wählen Sie einen SIP-Domänennamen aus
<a name="BK_NameSIP"> </a>

Der SIP-Domänenname einer Organisation richtet sich in der Regel nach den e-Mail-Adressen, die den Benutzern zugewiesen sind. Wenn ein Benutzer in Ihrer Organisation über eine e-Mail-Adresse wie Brown@contoso.com verfügt \<, ist die\> bevorzugte SIP-Domäne für eine Organisation mit dem contoso.com-Domänennamen einfach contoso.com.
  
### <a name="multiple-sip-domains"></a>Mehrere SIP-Domänen

 In einigen Fällen benötigt Ihre Organisation mehrere SIP-Domänen. Wenn fabrikam.com beispielsweise von contoso.com erworben wurde, müssen Sie möglicherweise eine neue SIP-Domäne erstellen, von der Skype for Business Server erkennt und die Verbindung akzeptiert. Wenn Sie dies tun, müssen Sie eine zusätzliche Gruppe aller DNS-Einträge erstellen, die contoso.com verwenden, mit neuen FQDNs, die anzeigen, wo Anforderungen für Fabrikam gesendet werden.
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

Sie können DNS verwenden, um die Datenverkehrs Auslastung zwischen mehreren Servern freizugeben, die als Serverpool eingerichtet sind. Erstellen Sie dazu mehrere A-Einträge für den FQDN des Pools, die jeweils auf die IP-Adresse eines Knotens im Pool zeigen.
  
Weitere Diskussionen zum Lastenausgleich finden Sie unter [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) .
  

