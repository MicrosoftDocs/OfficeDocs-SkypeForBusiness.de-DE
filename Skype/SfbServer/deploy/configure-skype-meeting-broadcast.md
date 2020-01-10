---
title: Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Zusammenfassung: erfahren Sie mehr über die Schritte, die Sie ausführen müssen, um Skype-Live Konferenz für Ihre lokale Skype for Business Server-hybridbereitstellung zu konfigurieren.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002805"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz
 
**Zusammenfassung:** Informieren Sie sich über die Schritte, die Sie ausführen müssen, um Skype-Live Konferenz für Ihre lokale Skype for Business Server-hybridbereitstellung zu konfigurieren.
  
Skype-Live Konferenz ist ein Onlinedienst, der Teil von Office 365 ist. Wenn Sie Skype for Business Server lokal ausführen und die Skype-Live Konferenz in Ihrer Umgebung verwenden möchten, müssen Sie die Konfigurationsschritte in diesem Thema befolgen. Bevor Sie beginnen, muss Ihre Umgebung für hybride mit Skype for Business Online konfiguriert sein. Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) und [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Konfigurieren der Hybridumgebung für Skype-Live Konferenz

Sie müssen die folgenden Schritte ausführen, um Ihre Umgebung für die Skype-Live Konferenz vorzubereiten:
  
- Konfigurieren des Verbunds mit Skype for Business Online-Ressourcen
    
- Konfigurieren von SIP-Partnerverbunddomänen
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Konfigurieren des Verbunds mit Skype for Business Online-Ressourcen

Um die Föderation mit Skype for Business Online-Ressourcen zu aktivieren, müssen Sie den externen Zugriff für einen SIP-Verbund Anbieter konfigurieren. Führen Sie dazu die folgenden Schritte aus, indem Sie das Skype for Business Server Control Panel verwenden:
  
1. Starten Sie die Skype for Business Server-Systemsteuerung, und wählen Sie auf der linken Seite **externen Zugriff** aus.
    
2. Wählen Sie **SIP-Partnerverbundanbieter** und klicken Sie auf **Neu**.
    
3. Konfigurieren Sie den neuen Anbieter mit den folgenden Einstellungen:
    
|||
|:-----|:-----|
|**Aktivieren der Kommunikation mit diesem Anbieter:** <br/> |Ausgewählt  <br/> |
|**Anbietername:** <br/> |LyncOnlineResources  <br/> |
|**Zugriffs-Edgedienst (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Standardüberprüfungsstufe:** <br/> |Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet  <br/> |
   
Sie können auch den Verbund mit Skype for Business Online-Ressourcen aktivieren, indem Sie in der Skype for Business Server-Verwaltungsshell das folgende Cmdlet ausführen:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Konfigurieren von SIP-Partnerverbunddomänen

Als nächstes müssen Sie SIP-Verbunddomänen zur Liste der zulässigen Domänen hinzufügen. Wiederholen Sie diese Schritte für alle aufgeführten Domänen und erstellen Sie so vier neue SIP-Partnerverbunddomänen. Zu diesen Domänen gehören die regionalen Rechenzentren, die in Skype for Business Online verwendet werden.
  
1. Starten Sie die Skype for Business Server-Systemsteuerung, und wählen Sie auf der linken Seite **externen Zugriff** aus.
    
2. Wählen Sie **SIP-Partnerverbunddomänen** und klicken Sie auf **Neu**.
    
3. Geben Sie als **Domänenname (oder FQDN):** die Domäne ein und wiederholen Sie diese Vorgehensweise für alle folgenden Domänen:
    
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

Nachdem Sie diese Konfigurationsschritte abgeschlossen haben, können Sie Skype-Live Konferenz in Ihrer Bereitstellung verwenden. Weitere Informationen zu Skype-Live Konferenz finden Sie unter [Was ist eine Skype-Live Konferenz?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Skype-Live Konferenz-Administratorhandbuch](https://go.microsoft.com/fwlink/?LinkId=617075).
  

