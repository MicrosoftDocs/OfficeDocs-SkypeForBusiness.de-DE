---
title: Anzeigen von Informationen zu PIN-Richtlinien
TOCTitle: Anzeigen von Informationen zu PIN-Richtlinien
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49890649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu PIN-Richtlinien

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Auf der Registerkarte **PIN-Richtlinie** können Sie die PIN-Authentifizierung der Benutzer anzeigen, die mit IP-Telefonen eine Verbindung mit Lync 2013 herstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist. Ausführliche Informationen finden Sie unter [Ändern von vorhandenen Webdienst-Konfigurationseinstellungen](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern.

## So zeigen Sie in Lync Server-Systemsteuerung Informationen zu einer PIN-Richtlinie an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.

4.  Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

## Anzeigen von PIN-Richtlinien mithilfe der Lync Server PowerShell-Cmdlets

Sie können die PIN-Richtlinien auch mithilfe von Windows PowerShell und dem Cmdlet "Get-CsPinPolicy" anzeigen. Dieses Cmdlet kann über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen von PIN-Richtlinien

  - Geben Sie zum Anzeigen von Informationen zu allen PIN-Richtlinien den folgenden Befehl in die Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsPinPolicy
    
    Es werden Informationen der folgenden Art zurückgegeben:
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPinPolicy).

## Siehe auch

#### Aufgaben

[Ändern von vorhandenen Webdienst-Konfigurationseinstellungen](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Erstellen einer neuen PIN-Richtlinie](lync-server-2013-create-a-new-pin-policy.md)

