---
title: Löschen einer Archivierungskonfiguration in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.'
---

# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Löschen einer Archivierungskonfiguration in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.
  
Sie können eine Standort- oder Poolkonfiguration löschen, die globale Konfiguration jedoch nicht. Wenn Sie die globale Konfiguration löschen, werden automatisch die Standardwerte wieder hergestellt.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Löschen einer Archivierungskonfiguration mithilfe der Systemsteuerung

So löschen Sie eine Archivierungskonfiguration mithilfe der Systemsteuerung:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf die Zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten** und dann auf **"Löschen**".
    
    > [!NOTE]
    > Sie können auch auf die globale Konfiguration klicken, diese Option jedoch nur auswählen, wenn Sie die globale Konfiguration auf die Standardwerte zurücksetzen möchten. 
  
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Löschen einer Archivierungskonfiguration mithilfe von Windows PowerShell

Sie können eine Archivierungskonfiguration auch mithilfe des Cmdlets **"Remove-CsArchivingConfiguration** " löschen.
  
Mit dem folgenden Befehl werden beispielsweise die Archivierungskonfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden. Wenn eine auf Standortebene konfigurierte Richtlinie gelöscht wird, werden Benutzer, die zuvor von der Standortrichtlinie verwaltet wurden, stattdessen automatisch von der globalen Archivierungsrichtlinie gesteuert:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Mit dem folgenden Befehl werden alle Archivierungskonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet werden:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Mit dem nächsten Befehl werden alle Archivierungskonfigurationseinstellungen entfernt, in denen Exchange Archivierung deaktiviert wurde:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Sie können auch das Cmdlet **"Remove-CsArchivingConfiguration** " verwenden, um die globalen Einstellungen auf Standardwerte zurückzusetzen. Angenommen, Sie haben die Chatsitzungsarchivierung auf globaler Ebene aktiviert. Mit dem folgenden Befehl wird der Wert auf den Standardwert "None" zurückgesetzt, wodurch die Archivierung auf globaler Ebene deaktiviert wird:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) ".