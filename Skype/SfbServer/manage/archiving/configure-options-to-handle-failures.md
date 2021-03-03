---
title: Konfigurieren von Archivierungsoptionen zum Behandeln von Fehlern in Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Zusammenfassung: Informationen zum Blockieren von Chat- und Konferenzsitzungen im Falle eines Skype for Business Server-Ausfalls, der die Archivierung verhindern würde.'
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817675"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen zum Behandeln von Fehlern in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Chat- und Konferenzsitzungen im Falle eines Skype for Business Server-Ausfalls blockieren, der die Archivierung verhindern würde.
  
Wenn die Archivierung für Ihre Organisation erforderlich ist, können Sie Chat- und Konferenzsitzungen im Falle eines Skype for Business Server-Ausfalls blockieren, der die Archivierung verhindern würde. Dies wird manchmal als kritischer Modus bezeichnet. Wenn z. B. ein Problem mit einem Speicherdienst vor liegt, werden Dies für Benutzer blockiert, deren Kommunikation für die Archivierung aktiviert ist. Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Konfigurieren des kritischen Modus mithilfe der Systemsteuerung

So geben Sie an, ob Kommunikationssitzungen im Falle eines Fehlers zulässig sein sollen, der die Archivierung verhindern würde:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration, klicken Sie auf "Bearbeiten" **und** dann auf **"Details anzeigen".**
    
5. Wenn Sie festlegen möchten, wie sich die Archivierung bei einem Fehler verhält, aktivieren oder löschen Sie das Kontrollkästchen Chat- oder Webkonferenzsitzungen blockieren, wenn die Archivierung **fehlschlägt.**
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Konfigurieren des kritischen Modus mithilfe Windows PowerShell

Mit dem Cmdlet **"Set-CsArchivingConfiguration"** und dem Parameter "BlockOnArchiveFailure" können Sie auch angeben, ob Kommunikationssitzungen im Falle eines Fehlers zulässig sein sollen, der die Archivierung verhindern würde.
  
Der folgende Befehl deaktiviert z. B. die Kommunikation im Falle eines Archivierungsfehlers:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Mit dem nächsten Befehl wird die Kommunikation im Falle eines Archivierungsfehlers aktiviert:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsArchivingConfiguration".](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
  

