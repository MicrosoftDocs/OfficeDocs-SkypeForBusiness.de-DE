---
title: Löschen einer Archivierungskonfiguration in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817625"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Löschen einer Archivierungskonfiguration in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.
  
Sie können eine Standort- oder Poolkonfiguration löschen, die globale Konfiguration jedoch nicht. Wenn Sie die globale Konfiguration löschen, werden automatisch die Standardwerte wieder hergestellt.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Löschen einer Archivierungskonfiguration mithilfe der Systemsteuerung

So löschen Sie eine Archivierungskonfiguration mithilfe der Systemsteuerung
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf die Standort- oder Poolkonfiguration, die Sie löschen möchten, klicken Sie auf "Bearbeiten" **und** dann auf **"Löschen".**
    
    > [!NOTE]
    > Sie können auch auf die globale Konfiguration klicken, diese Option jedoch nur auswählen, wenn Sie die globale Konfiguration auf die Standardwerte zurücksetzen möchten. 
  
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Löschen einer Archivierungskonfiguration mithilfe Windows PowerShell

Sie können eine Archivierungskonfiguration auch mit dem Cmdlet **"Remove-CsArchivingConfiguration"** löschen.
  
Mit dem folgenden Befehl werden beispielsweise die Archivierungskonfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden. Wenn eine auf Standortbereich konfigurierte Richtlinie gelöscht wird, unterliegen Benutzer, die zuvor durch die Standortrichtlinie verwaltet wurden, stattdessen automatisch der globalen Archivierungsrichtlinie:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Mit dem folgenden Befehl werden alle Archivierungskonfigurationseinstellungen entfernt, die auf Dienstbereich angewendet wurden:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Mit dem nächsten Befehl werden alle Archivierungskonfigurationseinstellungen entfernt, bei denen die Archivierung von Exchange deaktiviert wurde:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Sie können auch das **Cmdlet "Remove-CsArchivingConfiguration"** verwenden, um die globalen Einstellungen auf die Standardwerte zurückzusetzen. Angenommen, Sie haben die Archivierung von #A0 auf globaler Ebene aktiviert. Mit dem folgenden Befehl wird der Wert auf den Standardwert "None" zurückgesetzt, wodurch die Archivierung auf globaler Ebene deaktiviert wird:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsArchivingConfiguration".](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)
