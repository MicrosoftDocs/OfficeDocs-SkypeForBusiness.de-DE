---
title: Verwalten von Konfigurationseinstellungen für den Webdienst in Skype for Business 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Zusammenfassung: Verwalten von Konfigurationseinstellungen für Webdienste in Skype für Business Server 2015.'
ms.openlocfilehash: a0976728ecd09392408fb719861681e0465d7bed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server-2015"></a>Verwalten von Konfigurationseinstellungen für den Webdienst in Skype for Business 2015
 
**Zusammenfassung:** Verwalten von Konfigurationseinstellungen für Webdienste in Skype für Business Server 2015.
  
Die Seite **Webdienst** können Sie die Authentifizierungsmethoden für den Zugriff auf Skype für Business Server 2015 bezogene Webserver und Webdienste konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.
  
### <a name="to-create-new-web-service-configuration-settings"></a>So erstellen Sie neue Webdienst-Konfigurationseinstellungen

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Klicken Sie auf der Seite **Webdienst** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
   - Zum Konfigurieren des Webdiensts für einen Standort klicken Sie auf **Standortkonfiguration**. Klicken Sie in **Standort auswählen** auf den Standort, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.
    
   - Zum Konfigurieren des Webdiensts für einen Pool klicken Sie auf **Poolkonfiguration**. Klicken Sie in **Dienst auswählen** auf den Dienst, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**. 
    
5. Wählen Sie im Abschnitt **Neue Webdiensteinstellung** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine** aus.
    
6. Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:
    
   - **PIN-Authentifizierung aktivieren**: Clients werden über eine PIN authentifiziert.
    
   - **Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.
    
   - **Download einer Zertifikatkette aktivieren**: Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Ändern von vorhandenen Webdienst-Konfigurationseinstellungen

Die Seite **Webdienst** können Sie die Authentifizierungsmethoden für den Zugriff auf Skype für Business Server 2015 bezogene Webserver und Webdienste konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine vorhandene Webdienstrichtlinie zu ändern.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>So ändern Sie vorhandene Webdienst-Konfigurationseinstellungen

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Klicken Sie auf der Seite **Webdienst** auf eine Konfiguration, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Wählen Sie im Abschnitt **Webdiensteinstellung bearbeiten** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine** aus.
    
6. Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:
    
   - **PIN-Authentifizierung aktivieren**: Clients werden über eine PIN authentifiziert.
    
   - **Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.
    
   - **Download einer Zertifikatkette aktivieren**: Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Löschen von vorhandenen Webdienst-Konfigurationseinstellungen

Führen Sie die folgenden Schritte aus, um Webdienst-Konfigurationseinstellungen zu löschen.
  
### <a name="to-delete-web-service-configuration-settings"></a>So löschen Sie vorhandene Webdienst-Konfigurationseinstellungen

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Geben Sie auf der Seite **Webdienst** in das Suchfeld den vollständigen oder teilweisen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, dann auf **Bearbeiten** und anschließend auf **Löschen**.
    
6. Klicken Sie anschließend auf **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Löschen von Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell und das Cmdlet **"Remove-cswebserviceconfiguration"** löschen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste

- Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort „Redmond“ entfernt:
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>So löschen Sie alle auf den Standortbereich angewendeten Konfigurationseinstellungen für Webdienste

Mit dem folgenden Befehl werden alle auf den Dienstbereich angewendeten Webdienstsicherheitseinstellungen entfernt:
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>So löschen Sie alle Konfigurationseinstellungen für Webdienste, die eine Zertifikatauthentifizierung zulassen

Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung zulassen:
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Weitere Informationen hierzu finden Sie unter [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

