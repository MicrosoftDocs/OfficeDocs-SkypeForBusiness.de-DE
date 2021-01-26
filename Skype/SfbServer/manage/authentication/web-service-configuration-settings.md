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
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806495"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Verwalten von Webdienstkonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von Webdienstkonfigurationseinstellungen in Skype for Business Server.
  
Auf der Seite **"Webdienst"** können Sie die Authentifizierungsmethoden für den Zugriff auf Skype for Business Server-bezogene Webserver und Webdienste konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.
  
### <a name="to-create-new-web-service-configuration-settings"></a>So erstellen Sie neue Webdienstkonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Klicken Sie **auf der Seite Webdienst** auf **"Neu",** und gehen Sie dann wie folgt vor:
    
   - Klicken Sie auf "Websitekonfiguration", um den Webdienst für eine **Website zu konfigurieren.** Klicken **Sie in "Standort auswählen"** auf den Standort, auf den die Webdienstrichtlinie angewendet wird, und klicken Sie dann auf **"OK".**
    
   - Klicken Sie auf "Poolkonfiguration", um den Webdienst für einen **Pool zu konfigurieren.** Klicken **Sie in "Dienst auswählen"** auf den Dienst, auf den die Webdienstrichtlinie angewendet wird, und klicken Sie dann auf **"OK".** 
    
5. Wählen **Sie in "Neue Webdiensteinstellung"** in der integrierten Windows-Authentifizierung **"Aushandeln",** **"Integrierte Windows-Authentifizierung"** oder **"Keine" aus.** 
    
6. Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
   - **PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.
    
   - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
   - **Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Ändern vorhandener Webdienstkonfigurationseinstellungen

Auf der Seite **"Webdienst"** können Sie die Authentifizierungsmethoden für den Zugriff auf Skype for Business Server-bezogene Webserver und Webdienste konfigurieren.
  
Führen Sie die folgenden Schritte aus, um eine vorhandene Webdienstrichtlinie zu ändern.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>So ändern Sie vorhandene Webdienstkonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
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

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.
    
4. Geben Sie auf der Seite **Webdienst** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.
    
5. Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie auf **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Löschen von Webdienstkonfigurationseinstellungen mithilfe Windows PowerShell Cmdlets

Sie können Webdienstkonfigurationseinstellungen mithilfe Windows PowerShell **remove-CsWebServiceConfiguration-Cmdlets** löschen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste

- Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort "Redmond" entfernt:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>So löschen Sie alle Auf Standortbereich angewendeten Webdienstkonfigurationseinstellungen

Mit dem folgenden Befehl werden alle auf Dienstebene angewendeten Webdienstsicherheitseinstellungen entfernt:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>So löschen Sie alle Webdienstkonfigurationseinstellungen, die die Zertifikatauthentifizierung zulassen

Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung erlauben:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Weitere Informationen finden Sie unter [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

