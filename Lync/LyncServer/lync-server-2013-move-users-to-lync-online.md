---
title: 'Lync Server 2013: Migrieren von Benutzern zu lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5106d4e27921d9407b2663410cc0872892479ebb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Migrieren von Benutzern zu lync Online in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-29_

Bevor Sie mit der Migration von Benutzern zu lync Online beginnen, sollten Sie die Benutzerdaten sichern, die den zu verschiebenden Konten zugeordnet sind. Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben. Weitere Informationen finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migrieren von Benutzereinstellungen zu lync Online

Benutzereinstellungen werden mit dem Benutzerkonto verschoben. Einige lokale Einstellungen werden nicht mit dem Benutzerkonto verschoben.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Verschieben von Pilot Benutzern nach lync Online

Bevor Sie mit dem Migrieren von Benutzern zu lync Online beginnen, sollten Sie einige Pilotbenutzer zur Bestätigung der ordnungsgemäßen Konfiguration Ihrer Umgebung migrieren. Sie können dann überprüfen, ob lync-Features und-Dienste wie erwartet funktionieren, bevor Sie versuchen, zusätzliche Benutzer zu migrieren.

Wenn Sie einen lokalen Benutzer zu Ihrem lync Online Mandanten migrieren möchten, führen Sie die folgenden Cmdlets im lync Server-Verwaltungsshell aus, wobei Sie die Administratoranmeldeinformationen für Ihre Microsoft Office 365-Organisation verwenden. Ersetzen Sie "username@contoso.com" durch die Informationen für den Benutzer, den Sie wechseln möchten.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird,\<im folgenden\>Format: https://Pool FQDN/HostedMigration/hostedmigrationService.svc.

Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Office 365 organisationskonto anzeigen.

**So bestimmen Sie die URL des gehosteten Migrations Diensts für Ihre Office 365 Organisation**

1.  Melden Sie sich als Administrator bei Ihrer Office 365 Organisation an.

2.  Öffnen Sie das **lync Admin Center**.

3.  Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie. Eine Beispiel-URL sieht wie folgt aus:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:
    
    `https://admin0a.online.lync.com`

5.  Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Verschieben von Benutzern nach lync Online

Sie können mehrere Benutzer mithilfe des Cmdlets [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) mit dem Parameter – Filter migrieren, um die Benutzer auszuwählen, denen eine bestimmte Eigenschaft für die Benutzerkonten zugewiesen ist, beispielsweise RegistrarPool. Sie können dann die zurückgegebenen Benutzer an das Cmdlet " [CsUser" weiter](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) leiten, wie im folgenden Beispiel gezeigt.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Sie können auch den Parameter "– OU" verwenden, um alle Benutzer in der angegebenen Organisationseinheit abzurufen, wie im folgenden Beispiel dargestellt.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Überprüfen lync Online Benutzereinstellungen und-Features

Sie können sicherstellen, dass der Benutzer auf folgende Weise erfolgreich verschoben wurde:

  - Zeigen Sie den Status des Benutzers in der lync Online-Systemsteuerung an. Der visuelle Indikator für lokale Benutzer und Online Benutzer ist unterschiedlich.

  - Führen Sie das folgende Cmdlet aus:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

