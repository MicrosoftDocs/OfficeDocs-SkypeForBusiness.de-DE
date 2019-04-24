---
title: Löschen Sie eine PIN-Richtlinie in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Zusammenfassung: Löschen eines Benutzers einwahlkonferenzen PIN für Skype für Business Server.'
ms.openlocfilehash: d8b8a901e15e0b301dcce149b3f55a27f8298af6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211025"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Löschen Sie eine PIN-Richtlinie in Skype für Business Server
 
**Zusammenfassung:** Löschen eines Benutzers einwahlkonferenzen PIN für Skype für Business Server.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie (persönliche Identifikationsnummer) zu löschen.
  
> [!NOTE]
> Die globale PIN-Richtlinie kann nicht gelöscht werden. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>So löschen Sie eine PIN-Richtlinie in Skype Business Server-Systemsteuerung

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Geben Sie auf der Seite **PIN-Richtlinie** im Suchfeld den vollständigen oder teilweisen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie anschließend auf **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen der PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können die PIN-Richtlinien löschen, mithilfe von Windows PowerShell und das Cmdlet Remove-CsPinPolicy. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-remove-a-specific-pin-policy"></a>So entfernen Sie eine bestimmte PIN-Richtlinie

- Mit diesem Befehl wird die PIN-Richtlinie mit dem Identitätswert „RedmondUsersPinPolicy“ entfernt.
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>So entfernen Sie alle PIN-Richtlinien, die auf den Standortbereich angewendet wurden

- Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die für den Standortbereich konfiguriert sind:
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>So entfernen Sie alle PIN-Richtlinien, die die Verwendung gängiger Muster zulassen

- Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die die Verwendung gängiger Muster zulassen: G
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) -Cmdlet.
  

