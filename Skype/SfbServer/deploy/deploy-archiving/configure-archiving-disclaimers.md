---
title: Konfigurieren von Archivierungshaftungsausschlüssen für externe Benutzer in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie einen Archivierungshaftungsausschluss für Skype for Business Server konfigurieren.'
---

# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Konfigurieren von Archivierungshaftungsausschlüssen für externe Benutzer in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie einen Archivierungshaftungsausschluss für Skype for Business Server konfigurieren.
  
Wenn Ihre Organisation mit externen Partnern kommuniziert, müssen Sie sie darüber informieren, dass Sie die Kommunikation mit ihnen archivieren. Wenn Sie einen Edgeserver bereitstellen und den Partnerverbund für Ihre Organisation aktivieren, werden Sie gefragt, ob Sie automatisch einen Archivierungshaftungsausschluss an externe Partner senden möchten. 
  
Wenn Sie diese Konfiguration ändern müssen, können Sie die Skype for Business Server Systemsteuerung oder das Cmdlet Windows PowerShell **Set-CsAccessEdgeConfiguration** verwenden. Cmdlets können entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.
  
Damit externe Benutzer in Ihrer Skype for Business Server Bereitstellung mit Benutzern zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff externer Benutzer zu unterstützen. Ausführliche Informationen finden Sie unter Verwalten von XMPP-Verbundpartnern für Ihre Organisation. Ausführliche Informationen zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter Steuern des Zugriffs durch einzelne Verbunddomänen.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe der Systemsteuerung

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **"Partnerverbund" und "Externer Zugriff**", und klicken Sie dann auf **"Zugriffs-Edgekonfiguration"**.
    
4. Klicken Sie auf der Registerkarte **"Zugriffs-Edgekonfiguration** " auf **"Global**", klicken Sie auf **"Bearbeiten**" und dann auf " **Details anzeigen"**.
    
5. Aktivieren oder deaktivieren Sie unter "**Partnerverbund und Verbindung mit öffentlichen Chatdiensten aktivieren**" in der **Edgekonfiguration für den Bearbeitungszugriff** das Kontrollkästchen **"Archivierungshaftungsausschluss an Verbundpartner** senden", um das automatische Senden des Archivierungshaftungsausschlusses zu aktivieren oder zu deaktivieren.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mit Windows PowerShell

Um den Archivierungshaftungsausschluss zu aktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer** " auf "True" ($True) fest:
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Um den Archivierungshaftungsausschluss zu deaktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer** " auf "False" ($False) fest:
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


