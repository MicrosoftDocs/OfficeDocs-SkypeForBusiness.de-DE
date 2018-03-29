---
title: Konfigurieren von Archivierungsoptionen zum Beheben von Fehlern in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Zusammenfassung: Erfahren Sie, wie im- und konferenzsitzungen im Fall einer Skype für Business Server 2015 Fehler zu blockieren, die Archivierung verhindern würden.'
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a>Konfigurieren von Archivierungsoptionen zum Beheben von Fehlern in Skype for Business Server 2015

**Zusammenfassung:** Erfahren Sie, wie im- und konferenzsitzungen im Fall einer Skype für Business Server 2015 Fehler zu blockieren, die Archivierung verhindern würden.
  
Wenn die Archivierung für Ihre Organisation erforderlich ist, können Sie im- und konferenzsitzungen im Fall einer Skype für Business Serverausfall blockieren, die Archivierung verhindern würden. Dies wird manchmal auch als kritischer Modus bezeichnet. Wenn beispielsweise ein Problem mit einem Speicherdienst auftritt, würde Chat für Nutzer blockiert, die für die Archivierung aktiviert sind. Nach der Fehlerkorrektur werden Chat und Konferenzen automatisch wiederhergestellt. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Konfigurieren des kritischen Modus mit der Systemsteuerung

So legen Sie fest, ob Kommunikationssitzungen bei einem Ausfall, der die Archivierung verhindern würde, erlaubt sein sollen:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
5. Aktivieren oder deaktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Konfigurieren des kritischen Modus mit Windows PowerShell

Sie können auch angeben, ob kommunikationssitzungen bei einem Ausfall zugelassen werden soll, die mit dem **Set-CsArchivingConfiguration** -Cmdlet mit dem Parameter BlockOnArchiveFailure Archivierung verhindern würden.
  
Beispielsweise wird mit der folgende Befehl Communications im Fall eines Fehlers Archivierung deaktiviert:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Mit dem nächsten Befehl kann die Kommunikation bei einem Archivierungsfehler aktiviert werden:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Weitere Informationen finden Sie im Hilfethema zum [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) -Cmdlet.
  

