---
title: Anzeigen von PIN-Richtlinieninformationen in Skype for Business Server
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
description: 'Zusammenfassung: Anzeigen der PIN-Richtlinieninformationen eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: 385602c4395ec0a189bc25d8a1ab052a8bf1475b440fc34795d54110b4bcffc2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286834"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Anzeigen von PIN-Richtlinieninformationen in Skype for Business Server
 
**Zusammenfassung:** Anzeigen der PIN-Richtlinieninformationen eines Benutzers für Skype for Business Server.
  
Auf der Registerkarte **"PIN-Richtlinie"** können Sie die PIN-Authentifizierung (Persönliche Identifikationsnummer) von Benutzern anzeigen, die eine Verbindung mit Skype for Business mit IP-Telefonen herstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zu einer PIN-Richtlinie in Skype for Business Server Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von PIN-Richtlinien mithilfe Windows PowerShell Cmdlets

Sie können PIN-Richtlinien auch mithilfe von Windows PowerShell und dem Cmdlet Get-CsPinPolicy anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-pin-policies"></a>So zeigen Sie PIN-Richtlinien an

Um Informationen zu allen PIN-Richtlinien anzuzeigen, geben Sie den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
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

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Get-CsPinPolicy".](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Siehe auch

[Erstellen einer neuen PIN-Richtlinie in Skype for Business Server](create-a-new-pin-policy.md)