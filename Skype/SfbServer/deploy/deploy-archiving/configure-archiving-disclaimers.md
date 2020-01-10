---
title: Konfigurieren von Archivierungs Ausschlüssen für externe Benutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie eine Archivierungs Verzichterklärung für Skype for Business Server konfigurieren.'
ms.openlocfilehash: d6c08b6fe2eaa6c74231b96346661488c3f8e2b0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001055"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Konfigurieren von Archivierungs Ausschlüssen für externe Benutzer in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie einen Haftungsausschluss für die Archivierung von Skype for Business Server konfigurieren.
  
Wenn Ihre Organisation mit externen Partnern kommuniziert, müssen Sie die Partner darüber informieren, dass diese Kommunikationen archiviert werden. Wenn Sie einen Edgeserver bereitstellen und den Verbund für Ihre Organisation aktivieren, werden Sie gefragt, ob Sie einen Archivierungs Ausschluss automatisch an externe Partner senden möchten. 
  
Wenn Sie diese Konfiguration ändern müssen, können Sie die Skype for Business Server-Systemsteuerung oder das Windows PowerShell-Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " verwenden. Cmdlets können entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.
  
Damit externe Benutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch externe Benutzer zu unterstützen. Ausführliche Informationen finden Sie unter Verwalten von XMPP-Verbundpartnern für Ihre Organisation. Ausführliche Informationen zur Steuerung des Zugriffs für bestimmte Partnerdomänen finden Sie unter „Control Access by Individual Federated Domains“.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.
    
4. Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Aktivieren oder deaktivieren Sie im Abschnitt **Zugriffs-Edgekonfiguration bearbeiten** unter **Partnerverbund und Verbindung mit öffentlichen Chatdiensten aktivieren** das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden**, um das automatische Versenden eines Archivierungshaftungsausschlusses zu aktivieren bzw. zu deaktivieren.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe von Windows PowerShell

Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


