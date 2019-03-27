---
title: DNS-Grundlagen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 verfügt über integrierte Software, die DNS-Dienste bereitstellen, können Sie die verfügbare Dokumentation wie das DNS-Richtlinie Szenario Handbuch überprüfen möchten. Sie können eine Drittanbieter-Lösung auswählen, falls gewünscht.
ms.openlocfilehash: 2ba20c6aabd296f13ea5e84053d140123097f114
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886613"
---
# <a name="dns-basics"></a>DNS-Grundlagen
 
Windows Server 2016 verfügt über integrierte Software, die DNS-Dienste bereitstellen, können Sie die verfügbare Dokumentation wie [DNS Policy Szenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)überprüfen möchten. Sie können eine Drittanbieter-Lösung auswählen, falls gewünscht.
  
Es wird empfohlen, dass es empfiehlt sich einen bestimmten Server in Ihrer Implementierung anzugebende DNS reservieren. Sie könnten es potenziell einrichten, auf einem von den Servern für eines der Skype für Business-Serverrollen, aber wenn dieser Server auch Teil eines Pools wurde und haben Sie außer Betrieb versehentlich Skype genommen für Business fehlerhaft würde, bis DNS-Dienste neu eingerichtet wurden.
  
## <a name="dns-records"></a>DNS-Einträge

Jede Zuordnung eines Namens in eine IP-Adresse (und das wäre eine IPv4 oder IPv6-Adresse) in einer DNS-Eintrag auf dem DNS-Server gespeichert ist. Der Name wird im speziell als FQDN des DNS-Berichts beschrieben – einen vollständig qualifizierten Domänennamen. Zwar *"contoso.com"* auf einen gültigen Domänennamen ein, es ist die Abkürzung für * \*. contoso.com* , sodass es nicht eindeutig ist und könnte möglicherweise auf einem beliebigen Server in der Domäne verweisen. Ein Beispiel für einen vollqualifizierten Domänennamen, die auf einem einzelnen Server in Ihrer Domäne verweisen würde möglicherweise **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Standardmäßig ist der Computername eines Computers, der keiner Domäne Mitglied einen Hostnamen und nicht über einen vollqualifizierten Domänennamen (FQDN). Topologie-Generator verwendet FQDNs nicht Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. **Nur Standardzeichen verwenden** (einschließlich A – Z, a – Z, 0-9 und Bindestriche) bei der Zuweisung von FQDNs auf Servern mit Skype für Business Server. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.
  
Zusätzlich zu einer IP-Adresse der vollqualifizierten Domänennamen zuordnen eine **VIP-Adresse** konnte – eine virtuelle IP-Adresse. Eine VIP-Adresse ist eine IP-Adresse, die eine tatsächliche physische Netzwerkschnittstelle entsprechen nicht. Eine VIP-Adresse verweist häufig auf einen Pool von Servern durchführen einer Serverrolle oder auf ein Paar von Servern für die Redundanz und Fehlertoleranz konfiguriert sind.
  
Es gibt mehrere Arten von DNS-Eintrag, die die zu dieser Diskussion am relevantesten sind sind: 
  
- **A** – eine Adressdatensatz oder Hosteintrag, gibt eine 32-Bit-IPv4-Adresse. Zuordnen von Hostnamen in eine IP-Adresse des Hosts verwendet am häufigsten.
    
- **DNS-AAAA** -Datensatz eine IPv6-Adresse. Gibt eine 128-Bit-IPv6-Adresse zurück. Zuordnen von Hostnamen in eine IP-Adresse des Hosts verwendet am häufigsten.
    
- **CNAME** – einen CNAME-Datensatz. Dies löst einen Namen in eine andere: der DNS-Lookup wiederholt die Suche mit den neuen Namen.
    
- **SRV** -Diensteintrag (SRV-Eintrag) gibt einen Dienst (einen Prozess auf einem Server), die für eine bestimmte Ports und eine Kombination aus IP-zugegriffen wird. Die Namen von Diensten, erfordern einen-Diensteintrag behoben werden, und nicht mehr als tätigen sie angepasst werden Teil der SIP-Domäne. Einige Benutzerdienste verwenden einfache URLs. Ein SRV-Eintrag muss an einem Speicherort in der gleichen SIP-Domäne zeigen, wenn Sie mehrere Domänen verfügen Sie mehrere SRV-Einträge für einen bestimmten Dienst benötigen.
    
## <a name="how-to-choose-a-sip-domain-name"></a>So wählen einen SIP-Domänennamen
<a name="BK_NameSIP"> </a>

Die e-Mail-Adressen, die Benutzern zugewiesen wird in der Regel einer Organisation SIP-Domänennamens ausgerichtet. Wenn ein Benutzer in Ihrer Organisation eine e-Mail-Adresse wie Brown@contoso.com, die bevorzugte müssten \<Sip-Domäne\> Name ist für eine Organisation mit der Domäne "contoso.com" einfach "contoso.com".
  
### <a name="multiple-sip-domains"></a>Mehrere SIP-Domänen

 Ihre Organisation möglicherweise mehrere SIP-Domänen in einigen Fällen erforderlich. Beispielsweise wenn Fabrikam.com von contoso.com, erworben wurde müssen Sie möglicherweise eine neue SIP-Domäne erstellen, die Skype für Business Server erkennt und akzeptiert die Verbindung aus. Wenn Sie dies tun, müssen Sie eine zusätzliche Menge der alle DNS-Einträge erstellen, die "contoso.com" mit neuen FQDNs verwenden, mit denen umgeleitet werden Anforderungen für Fabrikam angezeigt.
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

DNS können Sie den zu erwartenden Datenverkehr zwischen mehreren Servern freigeben, die als einen Serverpool eingerichtet werden. Zu diesem Zweck würden Sie mehrere A-Einträge für den Pool-FQDN, von denen jedes verweist auf die IP-Adresse eines Knotens im Pool erstellen.
  
Zusätzliche Diskussionen für den Lastenausgleich finden Sie unter [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) .
  

