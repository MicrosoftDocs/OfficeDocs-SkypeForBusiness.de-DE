---
title: 'Lync Server 2013: Verwalten von Benutzern in einer Hybridbereitstellung'
TOCTitle: Verwalten von Benutzern in einer Hybridbereitstellung
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204967(v=OCS.15)
ms:contentKeyID: 49294282
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Benutzern in einer Lync Server 2013-Hybridbereitstellung

 

_**Letztes Änderungsdatum des Themas:** 2014-05-29_

Sie können Benutzereinstellungen und -richtlinien für Benutzer, die zu Lync Online migriert wurden, mithilfe der im Microsoft Office 365 -Onlineportal verfügbaren Features verwalten. Zum Ausführen von Verwaltungsaufgaben müssen Sie sich mit Ihrem Mandantenadministratorkonto anmelden.

## Zurückverschieben von Benutzern in die lokale Bereitstellung


> [!IMPORTANT]
> Dieser Abschnitt gilt nur für Benutzer, die für eine lokale Lync-Bereitstellung erstellt und aktiviert und dann von einer lokalen Bereitstellung zu Lync Online verschoben wurden. Wenn Sie Benutzer verschieben möchten, die in Lync Online erstellt wurden (und nie für Lync in einer lokalen Bereitstellung aktiviert wurden), finden Sie weitere Informationen unter <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Verschieben von Lync Online-Benutzern zur lokalen Lync-Bereitstellung in Lync Server 2013</A>.



  - Führen Sie die folgenden Cmdlets aus, um einen Benutzer von Lync Online zurück zu einer lokalen Lync-Bereitstellung zu verschieben:
    
        $cred=Get-Credential

       &nbsp;
    
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>

Das Format der für den Parameter **HostedMigrationOverrideUrl** angegebenen URL muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, und muss folgendes Format haben:

*Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc* . Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.

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

