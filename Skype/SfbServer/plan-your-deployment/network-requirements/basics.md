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
description: Windows Server 2016 über integrierte Software verfügt, die DNS-Dienste bereitstellen kann. Daher sollten Sie sich die verfügbare Dokumentation wie z. B. den LEITFADEN für DNS-Richtlinienszenarien ansehen. Sie können eine Drittanbieterlösung auswählen, wenn Sie möchten.
ms.openlocfilehash: e9187b5a619a55b4525d32eb20272e32cae514c2533d9c78f32d7ffed77d30ad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283087"
---
# <a name="dns-basics"></a>Grundlagen von DNS
 
Windows Server 2016 über integrierte Software verfügt, die DNS-Dienste bereitstellen kann. Daher sollten Sie sich die verfügbare Dokumentation wie z. B. den Leitfaden für [DNS-Richtlinienszenarien](/windows-server/networking/dns/deploy/dns-policy-scenario-guide)ansehen. Sie können eine Drittanbieterlösung auswählen, wenn Sie möchten.
  
Es wird empfohlen, dass Sie als bewährte Methode einen bestimmten Server in Ihrer Implementierung für die Bereitstellung von DNS verwenden. Sie können es möglicherweise auf einem der Server einrichten, der einer der Skype for Business Serverrollen zugeordnet ist, aber wenn dieser Server auch Teil eines Pools war und versehentlich außer Betrieb gesetzt wurde, würde Skype for Business fehlfunktionieren, bis DNS-Dienste wiederhergestellt wurden.
  
## <a name="dns-records"></a>DNS-Einträge

Jede Zuordnung eines Namens zu einer IP-Adresse (die eine IPv4- oder IPv6-Adresse sein kann) wird in einem DNS-Eintrag auf dem DNS-Server gespeichert. Der Name wird im DNS-Bericht speziell als FQDN – ein vollqualifizierte Domänenname – beschrieben. Obwohl *contoso.com* ein gültiger Domänenname ist, ist er kurz für *\* .contoso.com,* sodass er mehrdeutig ist und möglicherweise auf einen beliebigen Server in der Domäne verweisen kann. Ein Beispiel für einen FQDN, der auf einen einzelnen Server in Ihrer Domäne verweisen würde, kann **meeting01.contoso.com** sein.
  
> [!IMPORTANT]
> Standardmäßig ist der Computername eines Computers, der keiner Domäne beigetreten ist, ein Hostname und kein vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN). Der Topologie-Generator verwendet FQDNs und keine Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. **Verwenden Sie nur Standardzeichen** (einschließlich A-Z, a-z, 0-9 und Bindestriche), wenn Sie Ihren Servern, die Skype for Business Server ausgeführt werden, FQDNs zuweisen. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.
  
Zusätzlich zu einer IP-Adresse könnte der FQDN einer **VIP** zugeordnet werden – einer virtuellen IP-Adresse. Eine VIP ist eine IP-Adresse, die keiner tatsächlichen physischen Netzwerkschnittstelle entspricht. Eine VIP verweist häufig auf einen Pool von Servern, die eine Serverrolle ausführen, oder auf ein Serverpaar, das für Redundanz und Fehlertoleranz konfiguriert ist.
  
Es gibt verschiedene Arten von DNS-Einträgen, die für diese Diskussion am relevantesten sind: 
  
- **A** – Adress- oder Hostdatensatz, Gibt eine 32-Bit-IPv4-Adresse zurück. Wird am häufigsten verwendet, um Hostnamen einer IP-Adresse des Hosts zuzuordnen.
    
- **AAAA** – ein IPv6-Adresseintrag. Gibt eine 128-Bit-IPv6-Adresse zurück. Wird am häufigsten verwendet, um Hostnamen einer IP-Adresse des Hosts zuzuordnen.
    
- **CNAME** – ein kanonischer Namenseintrag. Dadurch wird ein Name in einen anderen aufgelöst: Die DNS-Suche wiederholt die Suche mit dem neuen Namen.
    
- **SRV** – ein Dienstdatensatz (SRV-Eintrag) gibt einen Dienst (einen Prozess auf einem Server) an, auf den über eine bestimmte Port- und IP-Kombination zugegriffen wird. Die Namen von Diensten, die einen Dienstdatensatz erfordern, sind festgelegt und können nicht über ihre SIP-Domäne hinaus angepasst werden. Einige Benutzerdienste verwenden einfache URLs. Ein SRV-Eintrag muss auf einen Speicherort in derselben SIP-Domäne verweisen. Wenn Sie also über mehrere Domänen verfügen, benötigen Sie mehrere SRV-Einträge für einen bestimmten Dienst.
    
## <a name="how-to-choose-a-sip-domain-name"></a>So wählen Sie einen SIP-Domänennamen aus
<a name="BK_NameSIP"> </a>

Der SIP-Domänenname einer Organisation richtet sich in der Regel nach den E-Mail-Adressen, die den Benutzern zugewiesen wurden. Wenn ein Benutzer in Ihrer Organisation über eine E-Mail-Adresse wie Brown@contoso.com verfügt, ist die bevorzugte \<sip-domain\> Adresse für eine Organisation mit dem contoso.com Domänennamen einfach contoso.com.
  
### <a name="multiple-sip-domains"></a>Mehrere SIP-Domänen

 Ihre Organisation benötigt möglicherweise in einigen Fällen mehrere SIP-Domänen. Wenn Fabrikam.com beispielsweise von contoso.com erworben wurde, müssen Sie möglicherweise eine neue SIP-Domäne erstellen, von der Skype for Business Server eine Verbindung erkennt und akzeptiert. In diesem Fall müssten Sie einen zusätzlichen Satz aller DNS-Einträge erstellen, die contoso.com verwenden, mit neuen FQDNs, die anzeigen, wo Anforderungen für Fabrikam gesendet werden sollen.
  
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="BK_NameSIP"> </a>

Sie können DNS verwenden, um die Datenverkehrslast zwischen mehreren Servern zu teilen, die als Serverpool eingerichtet sind. Dazu erstellen Sie mehrere A-Einträge für den FQDN des Pools, die jeweils auf die IP-Adresse eines Knotens im Pool verweist.
  
Weitere Informationen zum Lastenausgleich finden Sie unter [DNS-Lastenausgleich.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
