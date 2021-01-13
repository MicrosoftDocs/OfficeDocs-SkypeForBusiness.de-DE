---
title: Konfigurieren Ihrer lokalen Bereitstellung für Skype Meeting Broadcast
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Schritte, die Sie zum Konfigurieren von Skype Meeting Broadcast für Ihre lokale Skype for Business Server-Hybridbereitstellung ausführen müssen.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820705"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Konfigurieren Ihrer lokalen Bereitstellung für Skype Meeting Broadcast
 
**Zusammenfassung:** Erfahren Sie mehr über die Schritte, die Sie zum Konfigurieren von Skype Meeting Broadcast für Ihre lokale Skype for Business Server-Hybridbereitstellung ausführen müssen.
  
Skype Meeting Broadcast ist ein Onlinedienst, der Teil von Office 365 ist. Wenn Sie Skype for Business Server lokal ausführen und Skype Meeting Broadcast in Ihrer Umgebung verwenden möchten, müssen Sie die Konfigurationsschritte in diesem Thema ausführen. Bevor Sie beginnen, muss Ihre Umgebung für die Hybridbereitstellung mit Skype for Business Online konfiguriert werden. Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Konfigurieren Ihrer Hybridumgebung für Skype Meeting Broadcast

Gehen Sie wie folgt vor, um Ihre Umgebung für die Übertragung von Skype-Besprechungen vorzubereiten:
  
- Konfigurieren des Verbunds mit Skype for Business Online-Ressourcen
    
- Konfigurieren von SIP-Verbunddomänen
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Konfigurieren des Verbunds mit Skype for Business Online-Ressourcen

Zum Aktivieren des Partnerverbunds mit Skype for Business Online-Ressourcen müssen Sie den externen Zugriff für einen SIP-Verbundanbieter konfigurieren. Führen Sie hierzu die folgenden Schritte mithilfe der Skype for Business Server-Systemsteuerung aus:
  
1. Starten Sie die Skype for Business Server-Systemsteuerung, und wählen **Sie auf** der linken Seite den externen Zugriff aus.
    
2. Wählen Sie **die Option "SIP-Verbundanbieter" aus,** und klicken Sie auf **"Neu".**
    
3. Konfigurieren Sie den neuen Anbieter mit den folgenden Einstellungen:
    
|||
|:-----|:-----|
|**Aktivieren Sie die Kommunikation mit diesem Anbieter:** <br/> |Ausgewählt  <br/> |
|**Anbietername:** <br/> |LyncOnlineResources  <br/> |
|**Zugriffs-Edgedienst (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Standardüberprüfungsstufe:** <br/> |Ermöglichen Sie Benutzern die Kommunikation mit allen Benutzern, die diesen Anbieter verwenden.  <br/> |
   
Sie können den Verbund mit Skype for Business Online-Ressourcen auch aktivieren, indem Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Konfigurieren von SIP-Verbunddomänen

Als Nächstes müssen Sie der Liste der zulässigen Domänen SIP-Verbunddomänen hinzufügen. Wiederholen Sie diese Schritte für jede der aufgeführten Domänen, und erstellen Sie vier neue SIP-Verbunddomänen. Diese Domänen sind für die regionalen Rechenzentren, die in Skype for Business Online verwendet werden.
  
1. Starten Sie die Skype for Business Server-Systemsteuerung, und wählen **Sie auf** der linken Seite den externen Zugriff aus.
    
2. Wählen Sie **"SIP-Verbunddomänen"** aus, und klicken Sie auf **"Neu".**
    
3. Geben Sie **für den Domänennamen (oder FQDN)** die Domäne ein, und wiederholen Sie dieses Verfahren für jede der folgenden Domänen:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Sie können auch den externen Zugriff für SIP-Verbunddomänen konfigurieren, indem Sie die folgenden Cmdlets in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Nachdem Sie diese Konfigurationsschritte abgeschlossen haben, können Sie mit der Verwendung von Skype Meeting Broadcast in Ihrer Bereitstellung beginnen. Weitere Informationen zu Skype Meeting Broadcast finden Sie im Administratorhandbuch zu Skype [Meeting Broadcast.](https://go.microsoft.com/fwlink/?LinkId=617075) [](https://go.microsoft.com/fwlink/?LinkId=617071)
  

