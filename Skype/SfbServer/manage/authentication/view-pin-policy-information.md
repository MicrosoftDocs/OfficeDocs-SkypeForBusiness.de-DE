---
title: Anzeigen von Informationen zu PIN-Richtlinien in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Zusammenfassung: Anzeigen der Informationen zu den PIN-Richtlinien eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806525"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Anzeigen von Informationen zu PIN-Richtlinien in Skype for Business Server
 
**Zusammenfassung:** Zeigen Sie die Informationen zu den PIN-Richtlinien eines Benutzers für Skype for Business Server an.
  
Auf der Registerkarte **"PIN-Richtlinie"** können Sie die Authentifizierung mit persönlichen Identifikationsnummern (PIN) von Benutzern anzeigen, die über IP-Telefone eine Verbindung mit Skype for Business herstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zu einer PIN-Richtlinie in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von PIN-Richtlinien mithilfe Windows PowerShell Cmdlets

Sie können pin-Richtlinien auch anzeigen, indem Sie Windows PowerShell und das Get-CsPinPolicy verwenden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-view-pin-policies"></a>So zeigen Sie die PIN-Richtlinien an

Geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Ihren PIN-Richtlinien ein:
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Get-CsPinPolicy".](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Weitere Informationen

[Erstellen einer neuen PIN-Richtlinie in Skype for Business Server](create-a-new-pin-policy.md)
