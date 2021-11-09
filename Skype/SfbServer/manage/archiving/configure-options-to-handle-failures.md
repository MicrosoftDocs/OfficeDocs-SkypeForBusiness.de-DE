---
title: Konfigurieren von Archivierungsoptionen zur Behandlung von Fehlern in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Zusammenfassung: Erfahren Sie, wie Sie Chat- und Konferenzsitzungen bei einem Skype for Business Server Fehler blockieren, der die Archivierung verhindern würde.'
ms.openlocfilehash: f3f20bf53a784972c720ce5578d78462cbb222c8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836467"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen zur Behandlung von Fehlern in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Chat- und Konferenzsitzungen bei einem Skype for Business Server Fehler blockieren, der die Archivierung verhindern würde.
  
Wenn die Archivierung eine Anforderung für Ihre Organisation ist, können Sie Chat- und Konferenzsitzungen im Falle eines Skype for Business Server Fehlers blockieren, der die Archivierung verhindern würde. Dies wird manchmal als kritischer Modus bezeichnet. Wenn beispielsweise ein Problem mit einem Speicherdienst vorliegt, werden Chatnachrichten für Benutzer blockiert, deren Kommunikation für die Archivierung aktiviert ist. Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Konfigurieren des kritischen Modus mithilfe der Systemsteuerung

So geben Sie an, ob Kommunikationssitzungen im Falle eines Fehlers zulässig sein sollen, der die Archivierung verhindern würde:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
5. Um festzulegen, wie sich die Archivierung verhält, wenn ein Fehler auftritt, aktivieren oder deaktivieren Sie das Kontrollkästchen Chat- **oder Webkonferenzsitzungen blockieren, wenn die Archivierung fehlschlägt.**
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Konfigurieren des kritischen Modus mithilfe von Windows PowerShell

Mit dem Cmdlet **"Set-CsArchivingConfiguration"** mit dem Parameter "BlockOnArchiveFailure" können Sie auch angeben, ob Kommunikationssitzungen bei einem Fehler zugelassen werden sollen, der die Archivierung verhindern würde.
  
Beispielsweise deaktiviert der folgende Befehl die Kommunikation im Falle eines Archivierungsfehlers:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Der nächste Befehl aktiviert die Kommunikation im Falle eines Archivierungsfehlers:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Set-CsArchivingConfiguration".](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
