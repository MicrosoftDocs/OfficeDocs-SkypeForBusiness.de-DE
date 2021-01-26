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
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Archivierung in Skype for Business Server aktivieren oder deaktivieren.'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817595"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren der Archivierung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Archivierung in Skype for Business Server aktivieren oder deaktivieren.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Aktivieren oder Deaktivieren der Archivierung mithilfe der Systemsteuerung

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Wählen Sie in der Liste der Archivierungskonfigurationen die entsprechende globale Konfiguration, Standortkonfiguration oder Poolkonfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen**, und führen Sie dann die folgenden Aktionen aus:
    
   - Klicken Sie auf **IM-Sitzungen archivieren**, um die Archivierung ausschließlich für IM-Sitzungen (Instant Messaging, Sofortnachrichten) zu aktivieren.
    
   - Klicken Sie auf **IM- und Konferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.
    
   - Klicken Sie auf "Archivierung deaktivieren", um die Archivierung für die Konfiguration **zu deaktivieren.**
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Aktivieren oder Deaktivieren der Archivierung mithilfe Windows PowerShell

Sie können die Archivierung auch mit dem Cmdlet **"Set-CsArchivingConfiguration"** aktivieren oder deaktivieren. Mit dem folgenden Befehl werden beispielsweise alle Archivierungskonfigurationseinstellungen so geändert, dass nur Sitzungssitzungen archiviert werden. Der Befehl ruft das **Cmdlet "Get-CsArchivingConfiguration"** ohne Parameter auf, um alle derzeit in der Organisation verwendeten Archivierungskonfigurationseinstellungen zurückzukehren. Diese Auflistung wird dann an das Cmdlet **"Where-Object"** weiterviert, das nur die Einstellungen auswählt, bei denen die Eigenschaft "EnableArchiving" den Wert "ImAndWebConf" hat (-eq). Die gefilterte Auflistung wird dann an das Cmdlet **"Set-CsArchivingConfiguration"** weiterverteilt, das jedes Element in der Auflistung übernimmt und den Wert von "EnableArchiving" in "ImOnly" ändert:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
