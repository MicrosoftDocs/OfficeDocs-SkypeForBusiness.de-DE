---
title: Löschen einer Archivierungskonfiguration in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Zusammenfassung: Erfahren Sie, wie eine Archivierungskonfiguration in Skype für Business Server 2015 zu löschen.'
ms.openlocfilehash: 810c195f34a729218118744d4b6943e8dd60eb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server-2015"></a>Löschen einer Archivierungskonfiguration in Skype for Business Server 2015

**Zusammenfassung:** Erfahren Sie, wie eine Archivierungskonfiguration in Skype für Business Server 2015 zu löschen.
  
Eine Standort- oder Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann jedoch nicht gelöscht werden. Wenn Sie die globale Konfiguration löschen, werden die Standardwerte automatisch wieder hergestellt.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Löschen einer Archivierungskonfiguration mithilfe der Systemsteuerung

So löschen Sie eine Archivierungskonfiguration mit der Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.
    
    > [!NOTE]
    > Sie können auch auf die globale Konfiguration klicken. Wählen Sie diese Option jedoch nur, wenn Sie die globale Konfiguration auf die Standardwerte zurücksetzen möchten. 
  
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Löschen einer Archivierungskonfiguration mit Windows PowerShell

Sie können auch eine Archivierungskonfiguration löschen, mit dem Cmdlet **Remove-CsArchivingConfiguration** .
  
Zum Beispiel werden mit dem folgenden Befehl die Einstellungen der Archivierungskonfiguration gelöscht, die auf den Standort „Redmond“ angewendet werden. Wenn eine auf Standortebene konfigurierte Richtlinie gelöscht wird, wird für Benutzer, für die zuvor die Standortrichtlinie galt, stattdessen automatisch die globale Archivierungsrichtlinie angewendet.
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Mit dem folgenden Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, die auf Standortebene angewendet werden:
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Mit dem nächsten Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, für die die Exchange-Archivierung deaktiviert wurde:
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Das Cmdlet **Remove-CsArchivingConfiguration** können auch die globalen Einstellungen auf die Standardwerte zurückgesetzt. Nehmen wir beispielsweise an, dass Sie die Archivierung auf globaler Ebene Sofortnachrichtensitzung aktiviert haben; Der folgende Befehl wird den Wert auf None, wird der Standardwert zurückgesetzt, der Archivierung auf globaler Ebene deaktiviert wird:
  
```
Remove-CsArchivingConfiguration -Identity global
```

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) -Cmdlet.