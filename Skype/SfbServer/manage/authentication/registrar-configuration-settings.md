---
title: Verwalten von Registrierungs Konfigurationseinstellungen in Skype for Business Server
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Zusammenfassung: Verwalten der Registrierungs Konfigurationseinstellungen für Skype for Business Server.'
ms.openlocfilehash: 0c4529fb7343cf3db1e516858987a3ba60435513
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818757"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Verwalten von Registrierungs Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten der Registrierungs Konfigurationseinstellungen für Skype for Business Server.
  
Mithilfe der Registrierungsstelle können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsaufforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:
  
- **Kerberos** Hierbei handelt es sich um das am stärksten für Clients verfügbare kennwortbasierte Authentifizierungsschema, das jedoch normalerweise nur für Unternehmensclients verfügbar ist, da eine Clientverbindung mit einem Schlüssel Verteilungs Center (Kerberos-Domänencontroller) erforderlich ist. Diese Einstellung ist geeignet, wenn der Server nur Enterprise-Clients authentifiziert.
    
- **NTLM** Hierbei handelt es sich um die kennwortbasierte Authentifizierung, die für Clients verfügbar ist, die ein Abfrage-Hash Schema für das Kennwort verwenden. Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung. Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.
    
- **Zertifikatauthentifizierung** Dies ist die neue Authentifizierungsmethode, wenn der Serverzertifikate von lync Phone Edition-Clients, öffentlichen Telefonen, Skype for Business und der lync Windows Store-App abrufen muss. Wenn sich ein Benutzer bei lync Phone Edition-Clients anmeldet und erfolgreich authentifiziert wird, indem er eine persönliche Identifikationsnummer (PIN) angibt, stellt Skype for Business Server den SIP-URI dem Telefon zur Verfügung und stellt ein signiertes Zertifikat von Skype for Business Server oder ein Benutzerzertifikat bereit, das Joe (ex: SN=Joe@Contoso.com) auf dem Smartphone identifiziert. Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.
    
> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet. 
  
Wenn Sie lync Windows Store-App-Clients verwenden, müssen Sie die Zertifikatauthentifizierung aktivieren.
  
### <a name="to-create-new-registrar-configuration-settings"></a>So erstellen Sie neue Konfigurationseinstellungen für eine Registrierungsstelle

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.
    
4. Klicken Sie auf der Seite **Registrierungsstelle** auf **Neu**.
    
5. Klicken Sie unter **Dienst auswählen** auf den Dienst, auf den die Registrierungsstelle angewendet werden soll, und klicken Sie anschließend auf **OK**.
    
6. Wählen Sie im Abschnitt **Neue Registrierungsstelleneinstellung** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:
    
   - **Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.
    
   - **NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.
    
   - **Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Ändern von vorhandenen Registrierungsstellenkonfigurationseinstellungen

Mithilfe der Registrierungsstelle können Sie Protokolle für die Proxyserverauthentifizierung konfigurieren. 
  
> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet. 
  
Führen Sie die folgenden Schritte aus, um eine vorhandene Registrierungsstelle zu ändern. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>So ändern Sie vorhandene Registrierungsstellenkonfigurationseinstellungen

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.
    
4. Klicken Sie auf der Seite **Registrierungsstelle** auf einen Dienst, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.
    
5. Wählen Sie im Abschnitt **Registrierungsstelleneinstellung bearbeiten** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:
    
   - **Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.
    
   - **NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.
    
   - **Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.
    
6. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-delete-registrar-configuration-settings"></a>So löschen Sie Registrierungsstellenkonfigurationseinstellungen

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.
    
4. Geben Sie auf der Seite **Registrierungsstelle** in das Suchfeld den vollständigen oder teilweisen Namen der Registrierungsstelle ein, die Sie löschen möchten.
    
5. Klicken Sie in der Liste auf die gewünschte Registrierungsstelle, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie anschließend auf **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Registrierungsstellen-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen der Registrierungsstelle mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsProxyConfiguration** löschen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>So entfernen Sie eine bestimmte Gruppe mit Registrierungsstellensicherheitseinstellungen

- Mithilfe des folgenden Befehls werden die auf den Edgeserver „atl-edge-011.litwareinc.com“ angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die auf den Standortbereich angewendet werden

- Mithilfe des folgenden Befehls werden alle auf den Registrierungsstellendienst angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die die NTLM-Authentifizierung zulassen

- Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierungsstelle gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Ausführliche Informationen finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

