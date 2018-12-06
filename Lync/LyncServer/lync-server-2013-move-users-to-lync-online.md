---
title: 'Lync Server 2013: Verschieben von Benutzern zu Lync Online'
TOCTitle: Verschieben von Benutzern zu Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204969(v=OCS.15)
ms:contentKeyID: 49294294
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Benutzern zu Lync Online in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-05-29_

Bevor Sie mit der Migration von Benutzern zu Lync Online beginnen, sollten Sie eine Sicherung der Benutzerdaten der zu verschiebenden Konten erstellen. Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben. Informationen finden Sie unter [Anforderungen für die Sicherung und Wiederherstellung: Daten](lync-server-2013-backup-and-restoration-requirements-data.md).

## Migration von Benutzereinstellungen zu Lync Online

Benutzereinstellungen werden zusammen mit dem Benutzerkonto verschoben. Einige lokale Einstellungen werden jedoch nicht mit dem Benutzerkonto verschoben.

## Verschieben von Pilotbenutzern nach Lync Online

Bevor Sie mit dem Verschieben von Benutzern nach Lync Online beginne, sollten Sie einige Pilotbenutzer verschieben, um sicherzustellen, dass Ihre Umgebung ordnungsgemäß konfiguriert ist. Anschließend können Sie überprüfen, ob Lync-Features und -Dienste erwartungsgemäß funktionieren, bevor Sie weitere Benutzer verschieben.

Zum Verschieben eines lokalen Benutzers zu Ihrem Skype for Business Online-Mandanten führen Sie in der Lync Server-Verwaltungsshell folgende Cmdlets aus und verwenden dabei die Administratoranmeldeinformationen für Ihren Microsoft Office 365-Mandanten. Ersetzen Sie "benutzername@contoso.com" mit den Informationen des zu verschiebenden Benutzers.

    $creds=Get-Credential

   &nbsp;

    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Das Format der für den Parameter **HostedMigrationOverrideUrl** angegebenen URL muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, und muss folgendes Format haben: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc* .

Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.

**So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten**

1.  Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.

2.  Öffen Sie das **Lync Admin Center** .

3.  Wenn das **Lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:
    
    `https://admin0a.online.lync.com`

5.  Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

## Verschieben von Benutzern nach Lync Online

Sie können mehrere Benutzer verschieben, indem Sie das Cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) mit dem Parameter "\\endash Filter" verwenden, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen, die den Benutzerkonten zugewiesen ist, z. B. RegistrarPool. Anschließend können Sie die zurückgegebenen Benutzer an das Cmdlet [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser) weiterleiten, wie im folgenden Beispiel dargestellt.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Sie können auch den Parameter "-OU" verwenden, um alle Benutzer in der angegebenen Organisationseinheit (Organizational Unit, OU) abzurufen, wie im folgenden Beispiel dargestellt.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

## Überprüfen von Lync Online-Benutzereinstellungen und -Features

Mit folgenden Methoden können Sie überprüfen, ob ein Benutzer erfolgreich verschoben wurde:

  - Zeigen Sie in der Lync Online-Systemsteuerung den Status des Benutzers an. Für lokale Benutzer und Onlinebenutzer werden unterschiedliche visuelle Indikatoren verwendet.

  - Führen Sie das folgende Cmdlet aus:
    
        Get-CsUser -Identity

