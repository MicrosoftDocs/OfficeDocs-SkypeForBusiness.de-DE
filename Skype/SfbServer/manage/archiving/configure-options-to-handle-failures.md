---
title: Konfigurieren von Archivierungsoptionen zur Behandlung von Fehlern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Chat-und Konferenzsitzungen blockieren, wenn ein Skype for Business Server-Fehler auftritt, der die Archivierung verhindert.'
ms.openlocfilehash: ed8a59a8c19ace9a83b699e1b69515f52c3af010
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992752"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen zur Behandlung von Fehlern in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie Chat-und Konferenzsitzungen blockieren, wenn ein Skype for Business Server-Fehler auftritt, der die Archivierung verhindert.
  
Wenn die Archivierung eine Voraussetzung für Ihre Organisation ist, können Sie im Fall eines Skype for Business Server-Fehlers Chat-und Konferenzsitzungen blockieren, die die Archivierung verhindern. Dies wird manchmal auch als kritischer Modus bezeichnet. Wenn beispielsweise ein Problem mit einem Speicherdienst auftritt, würde Chat für Nutzer blockiert, die für die Archivierung aktiviert sind. Nach der Fehlerkorrektur werden Chat und Konferenzen automatisch wiederhergestellt. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Konfigurieren des kritischen Modus mit der Systemsteuerung

So legen Sie fest, ob Kommunikationssitzungen bei einem Ausfall, der die Archivierung verhindern würde, erlaubt sein sollen:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
5. Aktivieren oder deaktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Konfigurieren des kritischen Modus mit Windows PowerShell

Sie können auch angeben, ob Kommunikationssitzungen zulässig sein sollen, wenn ein Fehler auftritt, der das Archivieren mithilfe des Cmdlets "CsArchivingConfiguration" mit dem BlockOnArchiveFailure **-** Parameter verhindert.
  
Mit dem folgenden Befehl wird beispielsweise die Kommunikation im Fall eines Archivierungs Fehlers deaktiviert:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Mit dem nächsten Befehl kann die Kommunikation bei einem Archivierungsfehler aktiviert werden:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) ".
  

