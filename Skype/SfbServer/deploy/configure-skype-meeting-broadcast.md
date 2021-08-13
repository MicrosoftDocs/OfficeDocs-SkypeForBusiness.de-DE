---
title: Konfigurieren Der lokalen Bereitstellung für Skype-Besprechung Broadcast
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Zusammenfassung: Erfahren Sie mehr über die Schritte, die Sie ausführen müssen, um Skype-Besprechung Broadcast für Ihre lokale Skype for Business Server Hybridbereitstellung zu konfigurieren.'
ms.openlocfilehash: 6cab2ed4fbb5cb2992b970d5a960bbc0ad2e10af2184588aa6c938e9811d2a50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304487"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Konfigurieren Der lokalen Bereitstellung für Skype-Besprechung Broadcast
 
**Zusammenfassung:** Erfahren Sie mehr über die Schritte, die Sie ausführen müssen, um Skype-Besprechung Broadcast für Ihre lokale Skype for Business Server Hybridbereitstellung zu konfigurieren.
  
Skype-Besprechung Broadcast ist ein Onlinedienst, der Teil Office 365 ist. Wenn Sie Skype for Business Server lokal ausführen und Skype-Besprechung Broadcast in Ihrer Umgebung verwenden möchten, müssen Sie die Konfigurationsschritte in diesem Thema ausführen. Bevor Sie beginnen, muss Ihre Umgebung für die Hybridbereitstellung mit Skype for Business Online konfiguriert werden. Weitere Informationen finden Sie unter Planen der [Hybridkonnektivität zwischen Skype for Business Server und Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) und Bereitstellen der [Hybridkonnektivität zwischen Skype for Business Server und Skype for Business Online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Konfigurieren Ihrer Hybridumgebung für Skype-Besprechung Broadcast

Sie müssen die folgenden Schritte ausführen, um Ihre Umgebung auf Skype-Besprechung Broadcast vorzubereiten:
  
- Konfigurieren des Partnerverbunds mit Skype for Business Onlineressourcen
    
- Konfigurieren von SIP-Verbunddomänen
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Konfigurieren des Partnerverbunds mit Skype for Business Onlineressourcen

Um den Partnerverbund mit Skype for Business Onlineressourcen zu aktivieren, müssen Sie den externen Zugriff für einen SIP-Partnerverbundanbieter konfigurieren. Führen Sie dazu mithilfe der Skype for Business Server Systemsteuerung die folgenden Schritte aus:
  
1. Starten Sie die Skype for Business Server Systemsteuerung, und wählen Sie auf der linken Seite **"Externer Zugriff"** aus.
    
2. Wählen Sie **SIP-Partnerverbundanbieter aus,** und klicken Sie auf **"Neu".**
    
3. Konfigurieren Sie den neuen Anbieter mit den folgenden Einstellungen:
    
|||
|:-----|:-----|
|**Aktivieren Sie die Kommunikation mit diesem Anbieter:** <br/> |Ausgewählt  <br/> |
|**Anbietername:** <br/> |LyncOnlineResources  <br/> |
|**Zugriffs-Edgedienst (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Standardüberprüfungsstufe:** <br/> |Zulassen, dass Benutzer mit allen Benutzern kommunizieren, die diesen Anbieter verwenden.  <br/> |
   
Sie können den Partnerverbund auch mit Skype for Business Onlineressourcen aktivieren, indem Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Konfigurieren von SIP-Verbunddomänen

Als Nächstes müssen Sie der Liste der zulässigen Domänen SIP-Partnerdomänen hinzufügen. Wiederholen Sie diese Schritte für jede der aufgeführten Domänen, und erstellen Sie 4 neue SIP-Verbunddomänen. Diese Domänen gelten für die regionalen Rechenzentren, die in Skype for Business Online verwendet werden.
  
1. Starten Sie die Skype for Business Server Systemsteuerung, und wählen Sie auf der linken Seite **"Externer Zugriff"** aus.
    
2. Wählen Sie **SIP-Partnerverbunddomänen aus,** und klicken Sie auf **"Neu".**
    
3. Geben Sie für den **Domänennamen (oder FQDN)** die Domäne ein, und wiederholen Sie dieses Verfahren für jede der folgenden Domänen:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Sie können den externen Zugriff für SIP-Verbunddomänen auch konfigurieren, indem Sie die folgenden Cmdlets in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Nachdem Sie diese Konfigurationsschritte abgeschlossen haben, können Sie mit der Verwendung von Skype-Besprechung Broadcast in Ihrer Bereitstellung beginnen. Weitere Informationen zu Skype-Besprechung Broadcast finden Sie unter [What is a Skype-Besprechung Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and Skype-Besprechung Broadcast Admin [Guide](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).
