---
title: 'Skype for Business Server 2015: Archivierung aktivieren oder deaktivieren'
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Zusammenfassung: Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server 2015.'
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015: Archivierung aktivieren oder deaktivieren

**Zusammenfassung:** Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server 2015.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Aktivieren oder Deaktivieren der Archivierung mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Wählen Sie in der Liste der Archivierungskonfigurationen die entsprechende globale Konfiguration, Standortkonfiguration oder Poolkonfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen** und führen Sie dann die folgenden Aktionen aus:
    
   - Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.
    
   - Klicken Sie auf **IM- und Konferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.
    
   - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Konfiguration zu deaktivieren.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Aktivieren oder Deaktivieren der Archivierung mithilfe von Windows PowerShell

Sie können die Archivierung außerdem mithilfe des **Set-CsArchivingConfiguration**-Cmdlet aktivieren oder deaktivieren. Mithilfe des folgenden Befehls werden beispielsweise alle Archivierungskonfigurationseinstellungen geändert, sodass nur Chatsitzungen archiviert werden. Der Befehl ruft das Cmdlet **Get-CsArchivingConfiguration** ohne Parameter, um alle archivierungskonfigurationseinstellungen, die derzeit in der Organisation verwendet werden. Diese Auflistung wird dann an das Cmdlet **Where-Object** -Cmdlet, die nur diese Einstellungen auswählt, in dem die EnableArchiving-Eigenschaft gleich ist (-Eq) "ImAndWebConf". Gefilterte Auflistung wird dann an das Cmdlet **Set-CsArchivingConfiguration** weitergeleitet das nimmt jedes Element in der Auflistung und den Wert der EnableArchiving in "ImOnly" geändert:
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```