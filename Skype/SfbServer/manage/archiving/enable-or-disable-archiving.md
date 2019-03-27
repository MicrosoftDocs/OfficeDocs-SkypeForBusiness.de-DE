---
title: Aktivieren Sie oder deaktivieren Sie der Archivierung in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Zusammenfassung: Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server.'
ms.openlocfilehash: b7f9ab424a9fc24c733fa61c75c1d4564b636941
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883025"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie der Archivierung in Skype für Business Server

**Zusammenfassung:** Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server.
  
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

Sie können die Archivierung außerdem mithilfe des **Set-CsArchivingConfiguration**-Cmdlet aktivieren oder deaktivieren. Mithilfe des folgenden Befehls werden beispielsweise alle Archivierungskonfigurationseinstellungen geändert, sodass nur Chatsitzungen archiviert werden. Der Befehl ruft das **Get-CsArchivingConfiguration**-Cmdlet ohne Parameter auf, um alle derzeit in der Organisation verwendeten Archivierungskonfigurationseinstellungen zurückzugeben. Diese Auflistung wird dann an das **Where-Object**-Cmdlet weitergeleitet, das nur die Einstellungen auswählt, bei denen die Eigenschaft „EnableArchiving“ den Wert „ImAndWebConf“ aufweist (der Vergleichsoperator „-eq“ steht für „equal to“). Die Auflistung wird dann an das **Set-CsArchivingConfiguration**-Cmdlet weitergeleitet, das für jedes Element in der Auflistung die Eigenschaft „EnableArchiving“ auf „ImOnly“ festlegt:
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
