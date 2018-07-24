---
title: Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Zusammenfassung: Erfahren Sie mehr über die Schritte, die Sie zum Konfigurieren von Skype Besprechung übertragen für Ihre lokale Skype für Business Server hybridbereitstellung ausführen müssen.'
ms.openlocfilehash: 55b7c5c1e97c2e059ead73384ae2914b07d47c4b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21004693"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz
 
**Zusammenfassung:** Informationen Sie zu den Schritten, die Sie zum Konfigurieren von Skype Besprechung übertragen für Ihre lokale Skype für Business Server hybridbereitstellung ausführen müssen.
  
Skype Besprechung übertragen ist ein Onlinedienst, der Teil von Office 365 ist. Wenn Sie Skype für Business Server lokal ausgeführt werden und Skype Besprechung übertragen in Ihrer Umgebung verwenden möchten, müssen Sie die Konfiguration Schritte in diesem Thema. Bevor Sie beginnen, muss Ihre Umgebung für hybride mit Skype für Business Online konfiguriert werden. Weitere Informationen finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online planen](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Konfigurieren der hybridumgebung für Skype Besprechung übertragen

Sie müssen Folgendes tun, um die Vorbereitung Ihrer Umgebung Skype Besprechung übertragen werden:
  
- Konfigurieren des Verbunds mit Skype für Business Onlineressourcen
    
- Konfigurieren von SIP-Partnerverbunddomänen
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Konfigurieren des Verbunds mit Skype für Business Onlineressourcen

Um den Verbund mit Skype für Business Onlineressourcen zu aktivieren, müssen Sie für einen SIP-Partnerverbundanbieter externen Zugriff konfigurieren. Hierzu dies mithilfe der Skype für Business Server-Systemsteuerung gehen Sie folgendermaßen vor:
  
1. Starten Sie die Skype für Business Server-Systemsteuerung, und wählen Sie **Externen Zugriff** auf der linken Seite.
    
2. Wählen Sie **SIP-Partnerverbundanbieter** und klicken Sie auf **Neu**.
    
3. Konfigurieren Sie den neuen Anbieter mit den folgenden Einstellungen:
    
|||
|:-----|:-----|
|**Aktivieren Sie Kommunikation mit diesem Anbieter:** <br/> |Ausgewählt  <br/> |
|**Anbietername:** <br/> |LyncOnlineResources  <br/> |
|**Zugriffs-Edgedienst (FQDN):** <br/> |sipfed.Resources.Lync.com  <br/> |
|**Standardüberprüfungsstufe:** <br/> |Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet  <br/> |
   
Sie können auch mit Skype-Verbund für Business Onlineressourcen aktivieren, indem Sie das folgende Cmdlet in der Skype für Business Server-Verwaltungsshell ausführen:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Konfigurieren von SIP-Partnerverbunddomänen

Im nächsten Schritt müssen Sie SIP Federated Domains die Liste der zulässigen Domänen hinzuzufügen. Wiederholen Sie diese Schritte für alle aufgeführten Domänen und erstellen Sie so vier neue SIP-Partnerverbunddomänen. Diese Domänen enthalten sind für die regionalen Daten verwendeten in Skype für Business Online zentriert.
  
1. Starten Sie die Skype für Business Server-Systemsteuerung, und wählen Sie **Externen Zugriff** auf der linken Seite.
    
2. Wählen Sie **SIP-Partnerverbunddomänen** und klicken Sie auf **Neu**.
    
3. Geben Sie als **Domänenname (oder FQDN):** die Domäne ein und wiederholen Sie diese Vorgehensweise für alle folgenden Domänen:
    
  - noammeetings.Lync.com
    
  - emeameetings.Lync.com
    
  - apacmeetings.Lync.com
    
  - Resources.Lync.com
    
Sie können auch den externen Zugriff für SIP-Verbund Domänen konfigurieren, indem Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell ausführen:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Wenn Sie diese Konfigurationsschritte abgeschlossen haben können Sie beginnen, in Ihrer Bereitstellung mit Skype Besprechung übertragen werden. Weitere Informationen zu Skype Besprechung übertragen werden, finden Sie unter [Was ist eine Skype Besprechung übertragen?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Skype-Besprechung übertragen Administratorhandbuch](https://go.microsoft.com/fwlink/?LinkId=617075).
  

