---
title: Löschen einer vorhandenen Auflistung von Sip-Trunk-Konfigurationseinstellungen in Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Zusammenfassung: Informationen zum Löschen einer Auflistung von Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836975"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Auflistung von Sip-Trunk-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine Auflistung von Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung löschen.
  
Sip-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway, einer IP-Public Branch eXchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Mit diesen Einstellungen kann Folgendes angegeben werden:
  
- Ob die Medienumgebung für Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RtCP (Realtime Transport Control Protocol)-Pakete gesendet werden.
    
- Gibt an, ob für jeden Trunk eine Secure Realtime Transport Protocol (SRTP)-Verschlüsselung erforderlich ist.
    
Bei der Installation von Skype for Business Server wird eine globale Auflistung von Sip-Trunk-Konfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch die Skype for Business Server-Systemsteuerung oder das [Cmdlet "Remove-CsTrunkConfiguration"](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) verwenden, um die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Eigenschaft "Enable3pccRefer" auf "True" festgelegt haben, wird beim Zurücksetzen der globalen Auflistung die Eigenschaft "Enable3pccRefer" auf den Standardwert "False" zurückgesetzt.
  
Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen auf Standort- oder Dienstebene (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:
  
- Wenn Sie Einstellungen auf Dienstebene entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
- Wenn Sie Einstellungen auf Standortebene entfernen, werden alle mit diesen Einstellungen verwaltete SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie Trunkkonfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Systemsteuerung von Skype for Business Server auf **"Sprachrouting"** und dann auf **"Trunkkonfiguration".**
    
2. Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt, und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
    
3. Die Eigenschaft **State** für die Auflistung wird in **Commit nicht ausgeführt** aktualisiert. Um für die Änderungen ein Commit auszuführen und die Auflistung zu löschen, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Commit für alle Elemente ausführen**.
    
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
    
5. Klicken Sie **im Dialogfeld "Skype for Business Server-Systemsteuerung"** auf **"OK".**
    
6. Wenn Sie Ihre Meinung ändern und die Auflistung nicht löschen möchten, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Alle noch nicht übernommenen Änderungen verwerfen**. Klicken Sie auf OK, wenn das Dialogfeld **"Skype for Business Server-Systemsteuerung"** **angezeigt wird.**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Entfernen von Trunkkonfigurationseinstellungen mithilfe von Skype for Business Server-Verwaltungsshell-Cmdlets

Sie können Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets "Remove-CsTrunkConfiguration"** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung der Skype for Business Server-Verwaltungsshell ausführen.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>So entfernen Sie eine angegebene Auflistung von Einstellungen

- Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort "Redmond" angewendet wurden:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>So entfernen Sie alle Auflistungen, die auf Websitebereich angewendet wurden

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf Dienstebene angewendet wurden:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>So entfernen Sie alle Auflistungen, in denen die Medienumgehung aktiviert ist

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsTrunkConfiguration".](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)
  

