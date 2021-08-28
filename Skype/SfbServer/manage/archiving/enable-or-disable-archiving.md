---
title: Aktivieren oder Deaktivieren der Archivierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Archivierung in Skype for Business Server aktivieren oder deaktivieren.'
ms.openlocfilehash: 8384c751cbcd7d5d357ca2bdefbb8821b7e282d0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621091"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren der Archivierung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Archivierung in Skype for Business Server aktivieren oder deaktivieren.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Aktivieren oder Deaktivieren der Archivierung mithilfe der Systemsteuerung

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Wählen Sie in der Liste der Archivierungskonfigurationen die entsprechende globale Konfiguration, Standortkonfiguration oder Poolkonfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen**, und führen Sie dann die folgenden Aktionen aus:
    
   - Klicken Sie auf **IM-Sitzungen archivieren**, um die Archivierung ausschließlich für IM-Sitzungen (Instant Messaging, Sofortnachrichten) zu aktivieren.
    
   - Klicken Sie auf **IM- und Konferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.
    
   - Klicken Sie zum Deaktivieren der Archivierung für die Konfiguration auf **"Archivierung deaktivieren".**
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Aktivieren oder Deaktivieren der Archivierung mithilfe von Windows PowerShell

Sie können die Archivierung auch mit dem Cmdlet **"Set-CsArchivingConfiguration"** aktivieren oder deaktivieren. Mit dem folgenden Befehl werden beispielsweise alle Archivierungskonfigurationseinstellungen so geändert, dass nur Chatsitzungen archiviert werden. Der Befehl ruft das Cmdlet **"Get-CsArchivingConfiguration"** ohne Parameter auf, um alle derzeit in der Organisation verwendeten Archivierungskonfigurationseinstellungen zurückzugeben. Diese Auflistung wird dann an das Cmdlet **"Where-Object"** weitergeleitet, das nur die Einstellungen auswählt, bei denen die Eigenschaft "EnableArchiving" gleich (-eq) "ImAndWebConf" ist. Die gefilterte Auflistung wird dann an das Cmdlet **"Set-CsArchivingConfiguration"** weitergeleitet, das jedes Element in der Auflistung übernimmt und den Wert von EnableArchiving in "ImOnly" ändert:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
