---
title: Löschen von vorhandenen Registrierungskonfigurationseinstellungen
TOCTitle: Löschen von vorhandenen Registrierungskonfigurationseinstellungen
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182571(v=OCS.15)
ms:contentKeyID: 49295085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von vorhandenen Registrierungskonfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Registrierung zu löschen.

## So löschen Sie eine Registrierung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.

4.  Geben Sie auf der Seite **Registrierung** im Suchfeld Teile oder den vollständigen Namen der Registrierung ein, die Sie löschen möchten.

5.  Klicken Sie in der Liste auf die gewünschte Registrierung, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

## Entfernen der Registrierungskonfigurationseinstellungen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Mithilfe der Lync Server-Verwaltungsshell und des Cmdlets **Remove-CsProxyConfiguration** können Sie auch Konfigurationseinstellungen für die Registrierung löschen. Sie können dieses Cmdlet über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine bestimmte Gruppe mit Registrierungssicherheitseinstellungen

  - Mithilfe des folgenden Befehls werden die auf den Edgeserver "atl-edge-011.litwareinc.com" angewendeten Sicherheitseinstellungen für die Registrierung entfernt:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

## So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die auf Standortebene angewendet werden

  - Mithilfe des folgenden Befehls werden alle auf den Registrierungsdienst angewendeten Sicherheitseinstellungen für die Registrierung entfernt:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

## So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die die NTLM-Authentifizierung zulassen

  - Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierung gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

Ausführliche Informationen dazu finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsProxyConfiguration).

