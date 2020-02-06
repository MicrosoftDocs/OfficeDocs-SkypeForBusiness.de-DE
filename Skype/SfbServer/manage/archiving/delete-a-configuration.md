---
title: Löschen einer Archivierungskonfiguration in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.'
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818937"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Löschen einer Archivierungskonfiguration in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.
  
Eine Standort- oder Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann jedoch nicht gelöscht werden. Wenn Sie die globale Konfiguration löschen, werden die Standardwerte automatisch wieder hergestellt.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Löschen einer Archivierungskonfiguration mithilfe der Systemsteuerung

So löschen Sie eine Archivierungskonfiguration mit der Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.
    
    > [!NOTE]
    > Sie können auch auf die globale Konfiguration klicken. Wählen Sie diese Option jedoch nur, wenn Sie die globale Konfiguration auf die Standardwerte zurücksetzen möchten. 
  
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Löschen einer Archivierungskonfiguration mit Windows PowerShell

Sie können eine Archivierungskonfiguration auch mithilfe des Cmdlets **Remove-CsArchivingConfiguration** löschen.
  
Zum Beispiel werden mit dem folgenden Befehl die Einstellungen der Archivierungskonfiguration gelöscht, die auf den Standort „Redmond“ angewendet werden. Wenn eine auf Standortebene konfigurierte Richtlinie gelöscht wird, wird für Benutzer, für die zuvor die Standortrichtlinie galt, stattdessen automatisch die globale Archivierungsrichtlinie angewendet.
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Mit dem folgenden Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, die auf Standortebene angewendet werden:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Mit dem nächsten Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, für die die Exchange-Archivierung deaktiviert wurde:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Sie können auch das Cmdlet **Remove-CsArchivingConfiguration** verwenden, um die globalen Einstellungen auf Standardwerte zurückzusetzen. Angenommen, Sie haben die Chat-Sitzungs Archivierung auf globaler Ebene aktiviert. mit dem folgenden Befehl wird der Wert auf den Standardwert None zurückgesetzt, wodurch die Archivierung auf globaler Ebene deaktiviert wird:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .
