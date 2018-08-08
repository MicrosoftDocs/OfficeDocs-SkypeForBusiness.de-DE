---
title: Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Auflistung von trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung zu löschen.'
ms.openlocfilehash: 94f6e24c645a85bf2ed9ba5ded2f8eb4f207209f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968831"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Auflistung von trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung zu löschen.
  
SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:
  
- Ob Medienumgehung für die Trunks aktiviert werden soll
    
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
    
- Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Die Skype für Business Server-Systemsteuerung oder [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) -Cmdlet können Sie jedoch "die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückgesetzt". Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.
  
Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:
  
- Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
- Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie Trunk-Konfigurationseinstellungen mit Skype Business Server-Systemsteuerung

1. Klicken Sie in Skype Business Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf **Trunkkonfiguration**.
    
2. Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **Bearbeiten** und dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
    
3. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
    
5. Klicken Sie im Dialogfeld **Skype Business Server-Systemsteuerung** auf **OK**.
    
6. Wenn Sie sich umentscheiden und die Auflistung nicht löschen möchten, klicken Sie auf **Commit ausführen** und anschließend auf **Alle noch nicht übernommenen Änderungen verwerfen**. Wenn das Dialogfeld **Skype Business Server-Systemsteuerung** angezeigt wird, klicken Sie auf **OK**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Entfernen der Trunkkonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell-Cmdlets

Sie können mithilfe von Skype für Business Server-Verwaltungsshell und das Cmdlet **Remove-CsTrunkConfiguration** trunkkonfigurationseinstellungen löschen. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Skype für Business Server-Verwaltungsshell ausführen.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>So entfernen Sie eine angegebene Auflistung von Einstellungen

- Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) -Cmdlet.
  

