---
title: Verwalten von registrierungskonfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Zusammenfassung: Verwalten von registrierungskonfigurationseinstellungen für Skype für Business Server.'
ms.openlocfilehash: a1dda801049313cc2fc4dead94b524c300885924
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877056"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Verwalten von registrierungskonfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Verwalten von registrierungskonfigurationseinstellungen für Skype für Business Server.
  
Mithilfe der Registrierungsstelle können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsaufforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:
  
- **Kerberos** Dies ist die sicherste Authentifizierungsschema für Clients verfügbar, aber es ist normalerweise nur für Enterprise-Clients verfügbar, da es Clientverbindung, um ein Schlüsselverteilungscenter (Domänencontroller Kerberos) erfordert. Diese Einstellung ist geeignet, wenn der Server nur Enterprise Clients authentifiziert.
    
- **NTLM** Dies ist die Authentifizierung von Clients, die auf das Kennwort ein Hashingschema NTLM-verwenden. Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung. Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.
    
- **Zertifikatauthentifizierung** Dies ist die neue Authentifizierungsmethode, wenn der Server benötigt, um Zertifikate von Lync Phone Edition-Clients, Telefone in öffentlichen Bereichen, Skype für Unternehmen und die Lync Windows Store-app beziehen. Klicken Sie auf Lync Phone Edition-Clients, nachdem ein Benutzer anmeldet erfolgreich authentifiziert wurde durch eine persönliche Identifikationsnummer (PIN), den Skype für Business Server bereitstellen und Vorschriften, die den SIP-URI an das Telefon und stellt einen Skype für Business Server signiert Zertifikat oder ein Benutzer, die Joe identifiziert (Ex: SN=joe@contoso.com) auf dem Telefon. Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.
    
> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet. 
  
Wenn Sie Lync Windows Store-app-Clients verwenden möchten, müssen Sie die Zertifikatauthentifizierung aktivieren.
  
### <a name="to-create-new-registrar-configuration-settings"></a>So erstellen Sie neue Konfigurationseinstellungen für eine Registrierungsstelle

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
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

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.
    
4. Klicken Sie auf der Seite **Registrierungsstelle** auf einen Dienst, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.
    
5. Wählen Sie im Abschnitt **Registrierungsstelleneinstellung bearbeiten** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:
    
   - **Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.
    
   - **NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.
    
   - **Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.
    
6. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-delete-registrar-configuration-settings"></a>So löschen Sie Registrierungsstellenkonfigurationseinstellungen

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.
    
4. Geben Sie auf der Seite **Registrierungsstelle** in das Suchfeld den vollständigen oder teilweisen Namen der Registrierungsstelle ein, die Sie löschen möchten.
    
5. Klicken Sie in der Liste auf die gewünschte Registrierungsstelle, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie anschließend auf **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen der Registrierungskonfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die registrierungskonfigurationseinstellungen mithilfe von Windows PowerShell und das Cmdlet " **Remove-CsProxyConfiguration** " löschen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>So entfernen Sie eine bestimmte Gruppe mit Registrierungsstellensicherheitseinstellungen

- Mithilfe des folgenden Befehls werden die auf den Edgeserver „atl-edge-011.litwareinc.com“ angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die auf den Standortbereich angewendet werden

- Mithilfe des folgenden Befehls werden alle auf den Registrierungsstellendienst angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die die NTLM-Authentifizierung zulassen

- Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierungsstelle gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Weitere Informationen hierzu finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

