---
title: Löschen einer PIN-Richtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
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
ms.openlocfilehash: 6585da84c6dfb9f3ae09fbe25a1baafd2e9ae8dd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612364"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Löschen einer PIN-Richtlinie in Skype for Business Server
 
**Zusammenfassung:** Löschen Sie die Einwahlkonferenz-PIN eines Benutzers für Skype for Business Server.
  
Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie (persönliche Identifikationsnummer) zu löschen.
  
> [!NOTE]
> Die globale PIN-Richtlinie kann nicht gelöscht werden. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>So löschen Sie eine PIN-Richtlinie in Skype for Business Server Systemsteuerung

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.
    
4. Geben Sie auf der Seite **PIN-Richtlinie** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie auf **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von PIN-Richtlinien mithilfe Windows PowerShell Cmdlets

Sie können PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet Remove-CsPinPolicy löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Der Vorgang ist in Skype for Business Server identisch.
  
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
