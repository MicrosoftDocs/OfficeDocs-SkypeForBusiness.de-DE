---
title: Verwalten von Webdienst-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Zusammenfassung: Verwalten von Webdienst-Konfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: 2ab23e499cff7678ddb50c57cdc6f396a3c4203c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818677"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Verwalten von Webdienst-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Web Service-Konfigurationseinstellungen in Skype for Business Server verwalten.
  
Sie können die **Webdienst** Seite verwenden, um die Authentifizierungsmethoden für den Zugriff auf Skype for Business Server-Webserver und-Webdienste zu konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.
  
### <a name="to-create-new-web-service-configuration-settings"></a>So erstellen Sie neue Webdienst-Konfigurationseinstellungen

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
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

Sie können die **Webdienst** Seite verwenden, um die Authentifizierungsmethoden für den Zugriff auf Skype for Business Server-Webserver und-Webdienste zu konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine vorhandene Webdienstrichtlinie zu ändern.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>So ändern Sie vorhandene Webdienst-Konfigurationseinstellungen

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
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

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Geben Sie auf der Seite **Webdienst** in das Suchfeld den vollständigen oder teilweisen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, dann auf **Bearbeiten** und anschließend auf **Löschen**.
    
6. Klicken Sie anschließend auf **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Löschen von Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsWebServiceConfiguration** löschen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste

- Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort „Redmond“ entfernt:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>So löschen Sie alle auf den Standortbereich angewendeten Konfigurationseinstellungen für Webdienste

Mit dem folgenden Befehl werden alle auf den Dienstbereich angewendeten Webdienstsicherheitseinstellungen entfernt:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>So löschen Sie alle Konfigurationseinstellungen für Webdienste, die eine Zertifikatauthentifizierung zulassen

Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung zulassen:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Ausführliche Informationen finden Sie unter [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

