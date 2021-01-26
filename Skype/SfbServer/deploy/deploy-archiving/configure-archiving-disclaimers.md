---
title: Konfigurieren von Archivierungsausschlüssen für externe Benutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie einen Archivierungsausschluss für Skype for Business Server konfigurieren.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820665"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Konfigurieren von Archivierungsausschlüssen für externe Benutzer in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie einen Archivierungsausschluss für Skype for Business Server konfigurieren.
  
Wenn Ihre Organisation mit externen Partnern kommuniziert, müssen Sie ihnen mitgeteilt haben, dass Sie die Kommunikation mit ihnen archivieren. Wenn Sie einen Edgeserver bereitstellen und den Partnerverbund für Ihre Organisation aktivieren, werden Sie gefragt, ob Sie automatisch einen Archivierungsausschluss an externe Partner senden möchten. 
  
Wenn Sie diese Konfiguration ändern müssen, können Sie die Skype for Business Server-Systemsteuerung oder das cmdlet Windows PowerShell **Set-CsAccessEdgeConfiguration** verwenden. Cmdlets können entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell.
  
Damit externe Benutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Externen Benutzerzugriff zu unterstützen. Weitere Informationen finden Sie unter "Verwalten von XMPP-Verbundpartnern für Ihre Organisation". Weitere Informationen zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter "Steuern des Zugriffs durch einzelne Verbunddomänen".
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Aktivieren oder Deaktivieren des Archivierungsausschlusses mithilfe der Systemsteuerung

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **"Verbund" und**"Externer Zugriff" und dann auf **"Zugriffs-Edgekonfiguration".**
    
4. Klicken Sie **auf der Registerkarte "Konfiguration von Zugriffs-Edge"** **auf "Global",** dann auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
5. Aktivieren oder deaktivieren Sie in "Edgekonfiguration bearbeiten" unter  "Partnerverbund und Verbindung mit öffentlichen Benachrichtigungen aktivieren" das Kontrollkästchen "Archivierungsausschluss an Verbundpartner senden", um das automatische Senden des Archivierungsausschlusses zu aktivieren oder zu deaktivieren.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Aktivieren oder Deaktivieren des Archivierungsausschlusses mithilfe Windows PowerShell

Um den Archivierungsausschluss zu aktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer"** auf "True" ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Um den Archivierungsausschluss zu deaktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer"** auf "False" ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


