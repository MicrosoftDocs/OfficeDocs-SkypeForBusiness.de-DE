---
title: Löschen einer PIN-Richtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Zusammenfassung: Löschen Sie die Einwahlkonferenz-PIN eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: 5cc487f5d8f9e66193446922d51c4c62d94143a9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762523"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Löschen einer PIN-Richtlinie in Skype for Business Server
 
**Zusammenfassung:** Löschen Sie die Einwahlkonferenz-PIN eines Benutzers für Skype for Business Server.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie (persönliche Identifikationsnummer) zu löschen.
  
> [!NOTE]
> Die globale PIN-Richtlinie kann nicht gelöscht werden. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>So löschen Sie eine PIN-Richtlinie in Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Geben Sie auf der Seite **PIN-Richtlinie** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie auf **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von PIN-Richtlinien mithilfe Windows PowerShell Cmdlets

Sie können PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet Remove-CsPinPolicy löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specific-pin-policy"></a>So entfernen Sie eine bestimmte PIN-Richtlinie

- Mit diesem Befehl wird die PIN-Richtlinie mit dem Identitätswert „RedmondUsersPinPolicy“ entfernt.
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>So entfernen Sie alle AUF Standortebene angewendeten PIN-Richtlinien

- Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die auf Standortebene konfiguriert sind:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>So entfernen Sie alle PIN-Richtlinien, die die Verwendung gängiger Muster zulassen

- Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die die Verwendung gängiger Muster zulassen: G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsPinPolicy".](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
