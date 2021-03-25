---
title: Anzeigen von INFORMATIONEN zu PIN-Richtlinien in Skype for Business Server
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
ms.openlocfilehash: 80383ce7e78ba8806119121f8c27c6e469363003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119534"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Anzeigen von INFORMATIONEN zu PIN-Richtlinien in Skype for Business Server
 
**Zusammenfassung:** Anzeigen der PIN-Richtlinieninformationen eines Benutzers für Skype for Business Server.
  
Auf der Registerkarte **PIN-Richtlinie** können Sie die PIN-Authentifizierung (Personal Identification Number) von Benutzern anzeigen, die eine Verbindung mit Skype for Business mit IP-Telefonen herstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zu einer PIN-Richtlinie in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle CsServerAdministrator oder CsAdministrator zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von PIN-Richtlinien mithilfe Windows PowerShell Cmdlets

Sie können PIN-Richtlinien auch mithilfe von Windows PowerShell und dem cmdlet Get-CsPinPolicy anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-pin-policies"></a>So zeigen Sie PIN-Richtlinien an

Geben Sie zum Anzeigen von Informationen zu allen IHREN PIN-Richtlinien den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
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

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Siehe auch

[Erstellen einer neuen PIN-Richtlinie in Skype for Business Server](create-a-new-pin-policy.md)