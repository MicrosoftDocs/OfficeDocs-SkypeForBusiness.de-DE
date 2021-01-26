---
title: Grundlagen von DNS
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 verfügt über integrierte Software, die DNS-Dienste bereitstellen kann, daher sollten Sie die verfügbare Dokumentation lesen, z. B. das Dns Policy Scenario Guide. Sie können eine Drittanbieterlösung auswählen, wenn Sie es vorziehen.
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825585"
---
# <a name="dns-basics"></a>Grundlagen von DNS
 
Windows Server 2016 verfügt über integrierte Software, die DNS-Dienste bereitstellen kann, daher sollten Sie die verfügbare Dokumentation lesen, z. B. das [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Sie können eine Drittanbieterlösung auswählen, wenn Sie es vorziehen.
  
Es wird empfohlen, in Ihrer Implementierung einen bestimmten Server für die Bereitstellung von DNS zu verwenden. Sie könnten es möglicherweise auf einem der Server einrichten, die einer der Skype for Business-Serverrollen zugewiesen sind, aber wenn dieser Server auch Teil eines Pools ist und durch einen Zufall außer Betrieb genommen wurde, würde Skype for Business fehlinbetrieb nehmen, bis die DNS-Dienste wieder hergestellt wurden.
  
## <a name="dns-records"></a>DNS-Einträge

Jede Zuordnung eines Namens zu einer IP-Adresse (und dies kann eine IPv4- oder IPv6-Adresse sein) wird in einem DNS-Eintrag auf dem DNS-Server gespeichert. Der Name wird im DNS-Bericht speziell als vollqualifizierter Domänenname (FQDN) beschrieben. Obwohl *contoso.com* ein gültiger Domänenname ist, ist er kurz für *\* .contoso.com,* daher ist er mehrdeutig und kann möglicherweise auf einen beliebigen Server in der Domäne verweisen. Ein Beispiel für einen FQDN, der auf einen einzelnen Server in Ihrer Domäne verweisen würde, kann **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Standardmäßig ist der Computername eines Computers, der nicht mitglied einer Domäne ist, ein Hostname und kein vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN). Der Topologie-Generator verwendet FQDNs, keine Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie nur Standardzeichen **(einschließlich** A-Z, a-z, 0-9 und Bindestriche), wenn Sie Ihren Servern mit Skype for Business Server FQDNs zuweisen. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.
  
Zusätzlich zu einer IP-Adresse könnte der FQDN einer **VIP** zugeordnet werden – einer virtuellen IP-Adresse. Eine VIP ist eine IP-Adresse, die nicht einer tatsächlichen physischen Netzwerkschnittstelle entspricht. Eine VIP verweist häufig auf einen Pool von Servern, die eine Serverrolle ausführen, oder auf ein Serverpaar, das für Redundanz und Fehlertoleranz konfiguriert ist.
  
Es gibt verschiedene Typen von DNS-Einträgen, die für diese Diskussion am wichtigsten sind: 
  
- **A** – ein Adressdatensatz oder Hostdatensatz, gibt eine 32-Bit-IPv4-Adresse zurück. Am häufigsten werden Hostnamen einer IP-Adresse des Hosts zugeordnet.
    
- **AAAA** – ein IPv6-Adressdatensatz. Gibt eine 128-Bit-IPv6-Adresse zurück. Am häufigsten werden Hostnamen einer IP-Adresse des Hosts zugeordnet.
    
- **CNAME** – ein kanonischer Namensdatensatz. Dadurch wird ein Name in einen anderen aufgelöst: Die DNS-Suche wird den Nachschlageversuch mit dem neuen Namen wiederholen.
    
- **SRV** – ein Dienstdatensatz (SRV-Eintrag) gibt einen Dienst (einen Prozess auf einem Server) an, auf den über einen bestimmten Port und eine bestimmte Ip-Kombination zugegriffen wird. Die Namen der Dienste, für die ein Dienstdatensatz erforderlich ist, sind festgelegt und können nicht mehr angepasst werden, als teil Ihrer SIP-Domäne zu werden. Einige Benutzerdienste verwenden einfache URLs. Ein SRV-Eintrag muss auf einen Standort in derselben SIP-Domäne verweisen. Wenn Sie also mehrere Domänen haben, benötigen Sie mehrere SRV-Einträge für einen bestimmten Dienst.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Auswählen eines SIP-Domänennamens
<a name="BK_NameSIP"> </a>

Der Name einer Organisation entspricht in der Regel den E-Mail-Adressen, die den Benutzern zur Verfügung steht. Wenn ein Benutzer in Ihrer Organisation über eine E-Mail-Adresse wie Brown@contoso.com verfügen würde, ist die bevorzugte Für eine Organisation mit dem \<sip-domain\> contoso.com A0 einfach contoso.com.
  
### <a name="multiple-sip-domains"></a>Mehrere SIP-Domänen

 Ihre Organisation benötigt in einigen Fällen möglicherweise mehrere SIP-Domänen. Wenn z. B. Fabrikam.com von contoso.com erworben wurde, müssen Sie möglicherweise eine neue SIP-Domäne erstellen, von der Skype for Business Server die Verbindung erkennt und akzeptiert. Wenn Sie dies tun, müssen Sie einen zusätzlichen Satz aller DNS-Einträge erstellen, die contoso.com verwenden, mit neuen FQDNs, die anzeigen, wo Anforderungen für Fabrikam gesendet werden.
  
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="BK_NameSIP"> </a>

Sie können DNS verwenden, um die Datenverkehrslast auf mehrere Server zu verteilen, die als Serverpool eingerichtet sind. Dazu würden Sie mehrere A-Einträge für den FQDN des Pools erstellen, von denen jeder auf die IP-Adresse eines Knotens im Pool verweist.
  
Weitere [Informationen zum Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) finden Sie unter DNS-Lastenausgleich.
  

