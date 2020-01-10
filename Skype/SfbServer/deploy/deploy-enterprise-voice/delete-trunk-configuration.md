---
title: Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Sammlung von trunk-Konfigurationseinstellungen mithilfe des Skype for Business Server-Control Panels löschen.'
ms.openlocfilehash: 97a0820258a837968b88e6840232829f3ad11d21
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000995"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Sammlung von trunk-Konfigurationseinstellungen mithilfe des Skype for Business Server-Control Panels löschen.
  
SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:
  
- Ob Medienumgehung für die Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
    
- Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch die Skype for Business Server-Systemsteuerung oder das Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) verwenden, um die Eigenschaften in der globalen Sammlung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.
  
Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:
  
- Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
- Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie die trunk-Konfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **VoIP-Routing** und dann auf **trunk-Konfiguration**.
    
2. Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **Bearbeiten** und dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
    
3. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
    
5. Klicken Sie im Dialogfeld **Skype for Business Server Control Panel** auf **OK**.
    
6. Wenn Sie es sich anders überlegen und die Sammlung nicht löschen möchten, klicken Sie auf **Commit** , und klicken Sie dann auf **alle nicht übernommenen Änderungen abbrechen**. Wenn das Dialogfeld " **Skype for Business Server Control Panel** " angezeigt wird, klicken Sie auf **OK**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Entfernen von trunk-Konfigurationseinstellungen mithilfe von Skype for Business Server-Verwaltungsshell-Cmdlets

Sie können trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell und des Cmdlets **Remove-CsTrunkConfiguration** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung der Skype for Business Server-Verwaltungsshell ausführen.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>So entfernen Sie eine angegebene Auflistung von Einstellungen

- Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .
  

