---
title: 'Skype for Business Server: Löschen einer vorhandenen Auflistung von SIP-Trunkkonfigurationseinstellungen'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Sammlung von Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server Systemsteuerung löschen.'
---

# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server: Löschen einer vorhandenen Auflistung von SIP-Trunkkonfigurationseinstellungen 
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine Auflistung von Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server Systemsteuerung löschen.
  
Sip trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX) or a Session Border Controller (SBC) at the service provider. Mit diesen Einstellungen kann Folgendes angegeben werden:
  
- Gibt an, ob die Medienumgehung für die Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RTCP-Pakete (Realtime Transport Control Protocol) gesendet werden
    
- Gibt an, ob die SRTP-Verschlüsselung (Secure Realtime Transport Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch die Skype for Business Server Systemsteuerung oder das Cmdlet ["Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration)" verwenden, um die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Enable3pccRefer-Eigenschaft auf "True" festgelegt haben, wird beim Zurücksetzen der globalen Auflistung die Enable3pccRefer-Eigenschaft auf den Standardwert "False" zurückgesetzt.
  
Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen auf Standort- oder Dienstebene (für ein einzelnes PSTN-Gateway) erstellen. diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:
  
- Wenn Sie Einstellungen auf Dienstebene entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
- Wenn Sie Standorteinstellungen entfernen, werden alle sip-Trunks, die von diesen Einstellungen verwaltet werden, jetzt von der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie Trunkkonfigurationseinstellungen mit Skype for Business Server Systemsteuerung

1. Klicken Sie in Skype for Business Server Systemsteuerung auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
    
2. Wählen Sie auf der Registerkarte " **Trunkkonfiguration** " die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **"Bearbeiten"** und dann auf " **Löschen"**. Um mehrere Auflistungen in demselben Vorgang zu löschen, klicken Sie auf die erste zu löschende Auflistung, halten Sie dann die STRG-TASTE gedrückt, und klicken Sie auf alle anderen Auflistungen, die Sie entfernen möchten.
    
3. Die Eigenschaft **State** für die Auflistung wird in **Commit nicht ausgeführt** aktualisiert. Um für die Änderungen ein Commit auszuführen und die Auflistung zu löschen, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Commit für alle Elemente ausführen**.
    
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
    
5. Klicken Sie im Dialogfeld **Skype for Business Server Systemsteuerung** auf **OK**.
    
6. Wenn Sie Ihre Meinung ändern und die Auflistung nicht löschen möchten, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Alle noch nicht übernommenen Änderungen verwerfen**. Wenn das Dialogfeld **Skype for Business Server Systemsteuerung** angezeigt wird, klicken Sie auf **"OK**".
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Entfernen von Trunkkonfigurations-Einstellungen mithilfe Skype for Business Server-Verwaltungsshell-Cmdlets

Sie können Trunkkonfigurationseinstellungen mithilfe Skype for Business Server Verwaltungsshell und des **Cmdlets "Remove-CsTrunkConfiguration**" löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Skype for Business Server Verwaltungsshell ausführen.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>So entfernen Sie eine angegebene Auflistung von Einstellungen

- Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort "Redmond" angewendet wurden:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>So entfernen Sie alle Auflistungen, die auf den Websitebereich angewendet wurden

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf Dienstebene angewendet wurden:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>So entfernen Sie alle Auflistungen, in denen die Medienumgehung aktiviert ist

- Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) ".
