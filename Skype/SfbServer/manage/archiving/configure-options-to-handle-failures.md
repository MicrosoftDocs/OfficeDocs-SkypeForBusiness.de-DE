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
description: 'Zusammenfassung: Informationen zum Blockieren von Chat- und Konferenzsitzungen im Falle eines Skype for Business Server-Fehlers, der die Archivierung verhindern würde.'
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095449"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen zum Behandeln von Fehlern in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Chat- und Konferenzsitzungen im Falle eines Skype for Business Server-Ausfalls blockieren, der die Archivierung verhindern würde.
  
Wenn die Archivierung eine Anforderung für Ihre Organisation ist, können Sie Chat- und Konferenzsitzungen blockieren, wenn Skype for Business Server einen Fehler hat, der die Archivierung verhindern würde. Dies wird manchmal als kritischer Modus bezeichnet. Wenn beispielsweise ein Problem mit einem Speicherdienst vor liegt, wird Dies für Benutzer blockiert, deren Kommunikation für die Archivierung aktiviert ist. Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Konfigurieren des kritischen Modus mithilfe der Systemsteuerung

So geben Sie an, ob Kommunikationssitzungen im Falle eines Fehlers zulässig sein sollen, der die Archivierung verhindern würde:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten,** und klicken Sie dann auf **Details anzeigen**.
    
5. Wenn Sie festlegen möchten, wie sich die Archivierung bei einem Fehler verhält, aktivieren oder löschen Sie das Kontrollkästchen Chat- oder Webkonferenzsitzungen blockieren, wenn die Archivierung **fehlschlägt.**
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Konfigurieren des kritischen Modus mithilfe Windows PowerShell

Sie können auch angeben, ob Kommunikationssitzungen im Falle eines Fehlers zulässig sein sollen, der die Archivierung verhindern würde, indem Sie das **Cmdlet Set-CsArchivingConfiguration** mit dem Parameter BlockOnArchiveFailure verwenden.
  
Der folgende Befehl deaktiviert z. B. die Kommunikation im Falle eines Archivierungsfehlers:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Der nächste Befehl ermöglicht die Kommunikation im Falle eines Archivierungsfehlers:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
