---
title: Verwalten von Registrierungskonfigurationseinstellungen in Skype for Business Server
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Zusammenfassung: Verwalten von Registrierungskonfigurationseinstellungen für Skype for Business Server.'
ms.openlocfilehash: 9a56e803470054ab8c2ba3cf9e2c758d4e71e17a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828325"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Verwalten von Registrierungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von Registrierungsstellenkonfigurationseinstellungen für Skype for Business Server.
  
Mithilfe der Registrierung können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsanforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:
  
- **Kerberos** Dies ist das stärkste kennwortbasierte Authentifizierungsschema, das clients zur Verfügung steht. Es ist jedoch normalerweise nur für Unternehmensclients verfügbar, da es eine Clientverbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller) erfordert. Diese Einstellung ist geeignet, wenn der Server nur Unternehmensclients authentifiziert.
    
- **NTLM** Dies ist die kennwortbasierte Authentifizierung, die Clients zur Verfügung stellt, die für das Kennwort ein Hashingschema mit #A0 verwenden. Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung. Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.
    
- **Zertifikatauthentifizierung** Dies ist die neue Authentifizierungsmethode, wenn der Server Zertifikate von Lync Phone Edition-Clients, Telefonen in common area, Skype for Business und der Lync Windows Store-App abrufen muss. Auf Lync Phone Edition-Clients stellt Skype for Business Server, nachdem sich ein Benutzer angemeldet hat und erfolgreich authentifiziert wurde, durch Angabe einer persönlichen Identifikationsnummer (PIN) den SIP-URI für das Telefon zur Verfügung und stellt ein von Skype for Business Server signiertes Zertifikat oder ein Benutzerzertifikat zur Identifizierung von Joe (Z: SN=joe@contoso.com) für das Telefon zur Verfügung. Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.
    
> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet. 
  
Wenn Sie Lync Windows Store-App-Clients verwenden, müssen Sie die Zertifikatauthentifizierung aktivieren.
  
### <a name="to-create-new-registrar-configuration-settings"></a>So erstellen Sie neue Registrierungskonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.
    
4. Klicken Sie auf der Seite **Registrierung** auf **Neu**.
    
5. Klicken Sie in **Dienst auswählen** auf den Dienst, auf den die Registrierung angewendet werden soll, und anschließend auf **OK**.
    
6. Wählen Sie im Abschnitt **Neue Registrierungseinstellung**, je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
   - **Kerberos-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das Kerberos-Protokoll.
    
   - **NTLM-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das NTLM-Protokoll.
    
   - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
7. Klicken Sie auf **Commit**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Ändern vorhandener Registrierungskonfigurationseinstellungen

Sie können die Registrierungsstelle verwenden, um Proxyserverauthentifizierungsprotokolle zu konfigurieren. 
  
> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet. 
  
Führen Sie die folgenden Schritte aus, um eine vorhandene Registrierungsstelle zu ändern. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>So ändern Sie vorhandene Registrierungsstellenkonfigurationseinstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.
    
4. Klicken Sie **auf der** Registrierungsseite auf einen Dienst, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
5. Wählen **Sie in "Registrierungseinstellung** bearbeiten" eine oder mehrere der folgenden Optionen aus, abhängig von den Funktionen der Clients und der Unterstützung in Ihrer Umgebung:
    
   - **Kerberos-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das Kerberos-Protokoll.
    
   - **NTLM-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das NTLM-Protokoll.
    
   - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
6. Klicken Sie auf **Commit**.
    
### <a name="to-delete-registrar-configuration-settings"></a>So löschen Sie Registrierungskonfigurationseinstellungen

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.
    
4. Geben Sie auf der Seite **Registrierung** im Suchfeld Teile oder den vollständigen Namen der Registrierung ein, die Sie löschen möchten.
    
5. Klicken Sie in der Liste auf die gewünschte Registrierung, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
6. Klicken Sie auf **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Registrierungskonfigurationseinstellungen mithilfe Windows PowerShell Cmdlets

Sie können die Registrierungskonfigurationseinstellungen mithilfe Windows PowerShell **remove-CsProxyConfiguration-Cmdlets** löschen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. Details zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>So entfernen Sie eine bestimmte Gruppe mit Registrierungssicherheitseinstellungen

- Mithilfe des folgenden Befehls werden die auf den Edgeserver "atl-edge-011.litwareinc.com" angewendeten Sicherheitseinstellungen für die Registrierung entfernt:
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die auf Standortebene angewendet werden

- Mithilfe des folgenden Befehls werden alle auf den Registrierungsdienst angewendeten Sicherheitseinstellungen für die Registrierung entfernt:
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die die NTLM-Authentifizierung zulassen

- Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierung gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Weitere Informationen finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  

