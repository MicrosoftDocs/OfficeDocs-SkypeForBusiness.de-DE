---
title: Verwalten von Webdienstkonfigurationseinstellungen in Skype for Business Server
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Zusammenfassung: Verwalten von Webdienstkonfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: 6d79e0567790f10dd86c68f64d7bde54d3540b44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099171"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Verwalten von Webdienstkonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von Webdienstkonfigurationseinstellungen in Skype for Business Server.
  
Auf der Seite **Webdienst** können Sie die Authentifizierungsmethoden für den Zugriff auf skype for Business Server-bezogene Webserver und Webdienste konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.
  
### <a name="to-create-new-web-service-configuration-settings"></a>So erstellen Sie neue Webdienstkonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle CsServerAdministrator oder CsAdministrator zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Klicken Sie **auf der** Seite Webdienst auf **Neu,** und gehen Sie dann wie folgt vor:
    
   - Klicken Sie zum Konfigurieren des Webdiensts für eine Website auf **Websitekonfiguration**. Klicken **Sie unter Website auswählen** auf die Website, auf die die Webdienstrichtlinie angewendet wird, und klicken Sie auf **OK**.
    
   - Klicken Sie zum Konfigurieren des Webdiensts für einen Pool auf **Poolkonfiguration**. Klicken **Sie unter Dienst auswählen** auf den Dienst, auf den die Webdienstrichtlinie angewendet wird, und klicken Sie auf **OK**. 
    
5. Wählen **Sie unter Neue Webdiensteinstellung** unter Integrierte **Windows-Authentifizierung** **die Option Aushandeln,** integrierte **Windows-Authentifizierung** oder **Keine aus.**
    
6. Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
   - **PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.
    
   - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
   - **Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Ändern vorhandener Webdienstkonfigurationseinstellungen

Auf der Seite **Webdienst** können Sie die Authentifizierungsmethoden für den Zugriff auf skype for Business Server-bezogene Webserver und Webdienste konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine vorhandene Webdienstrichtlinie zu ändern.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>So ändern Sie vorhandene Webdienstkonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle CsServerAdministrator oder CsAdministrator zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Klicken Sie auf der Seite **Webdienst** auf eine Konfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.
    
5. Wählen Sie im Abschnitt **Webdiensteinstellung bearbeiten** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine**.
    
6. Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
   - **PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.
    
   - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
   - **Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Löschen vorhandener Webdienstkonfigurationseinstellungen

Führen Sie die folgenden Schritte aus, um Webdienstkonfigurationseinstellungen zu löschen.
  
### <a name="to-delete-web-service-configuration-settings"></a>So löschen Sie Webdienstkonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle CsServerAdministrator oder CsAdministrator zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Geben Sie auf der Seite **Webdienst** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie auf **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Löschen von Webdienstkonfigurationseinstellungen mithilfe Windows PowerShell Cmdlets

Sie können Webdienstkonfigurationseinstellungen mit Windows PowerShell **und dem Cmdlet Remove-CsWebServiceConfiguration** löschen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste

- Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort "Redmond" entfernt:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>So löschen Sie alle auf den Websitebereich angewendeten Webdienstkonfigurationseinstellungen

Mit dem folgenden Befehl werden alle auf Dienstebene angewendeten Webdienstsicherheitseinstellungen entfernt:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>So löschen Sie alle Webdienstkonfigurationseinstellungen, die die Zertifikatauthentifizierung zulassen

Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung erlauben:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Weitere Informationen finden Sie unter [Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
