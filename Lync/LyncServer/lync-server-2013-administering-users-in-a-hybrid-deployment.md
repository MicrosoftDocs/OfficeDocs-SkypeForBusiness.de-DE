---
title: 'Lync Server 2013: Verwalten von Benutzern in einer hybridbereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-29_

Sie können Benutzereinstellungen und Richtlinien für Benutzer verwalten, die nach lync Online migriert wurden, indem Sie die Benutzer Verwaltungsfeatures verwenden, die im Microsoft Office 365 Online-Portal zur Verfügung stehen. Zum Ausführen von Verwaltungsaufgaben müssen Sie sich mit Ihrem Mandantenadministratorkonto anmelden.

<div>

## <a name="moving-users-back-to-on-premises"></a>Verschieben von Benutzern zurück in den lokalen Standort

<div class="">


> [!IMPORTANT]  
> Dieser Abschnitt gilt nur für Benutzer, die für lync lokal erstellt und aktiviert wurden und dann von einer lokalen Bereitstellung zu lync Online verschoben wurden. Wenn Sie Benutzer verschieben möchten, die in lync online erstellt wurden (und in einer lokalen Bereitstellung nicht immer für lync aktiviert wurden), lesen Sie verschieben <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">von Benutzern aus lync Online in lync lokal in lync Server 2013</A>.



</div>

  - Führen Sie die folgenden Cmdlets aus, um einen Benutzer aus lync Online zurück in lync lokal zu verschieben:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

Das Format der für den Parameter **HostedMigrationOverrideUrl** angegebenen URL muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, und muss folgendes Format haben:

Https://\<-Pool\>-FQDN-/HostedMigration/hostedmigrationService.svc. Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.

**So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten**

1.  Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.

2.  Öffnen Sie das **lync Admin Center**.

3.  Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis zu **lync.com**aus, und kopieren Sie Sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:
    
    `https://admin0a.online.lync.com`

5.  Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

