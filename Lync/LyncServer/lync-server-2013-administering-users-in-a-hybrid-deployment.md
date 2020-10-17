---
title: 'Lync Server 2013: Verwalten von Benutzern in einer hybridbereitstellung'
description: 'Lync Server 2013: Verwalten von Benutzern in einer hybridbereitstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1d7684a9f56eb013574a985ded0313378621c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552991"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-29_

Sie können Benutzereinstellungen und Richtlinien für Benutzer verwalten, die zu lync Online migriert wurden, indem Sie die Benutzerverwaltungsfunktionen verwenden, die im Microsoft 365 Admin Center zur Verfügung stehen. Sie müssen sich mit Ihrem mandantenadministrator Konto anmelden, um Verwaltungsaufgaben auszuführen.

<div>

## <a name="moving-users-back-to-on-premises"></a>Verschieben von Benutzern zurück zu lokal

<div class="">


> [!IMPORTANT]  
> Dieser Abschnitt gilt nur für Benutzer, die lokal erstellt und für lync aktiviert und dann von einer lokalen Bereitstellung in lync Online verschoben wurden. Wenn Sie Benutzer verschieben möchten, die in lync online erstellt wurden (und nicht immer für lync in einer lokalen Bereitstellung aktiviert wurden), sehen Sie, wie Sie <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Benutzer von lync Online in lync lokal in lync Server 2013 verschieben</A>.



</div>

  - Führen Sie die folgenden Cmdlets aus, um einen Benutzer von lync Online zurück zu lokal in lync zu migrieren:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, in folgendem Format:

Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc. Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Microsoft 365-oder Office 365-organisationskonto anzeigen.

**So bestimmen Sie die URL des gehosteten Migrations Diensts für Ihre Microsoft 365-oder Office 365-Organisation**

1.  Melden Sie sich als Administrator bei Ihrer Organisation an.

2.  Öffnen Sie das **lync Admin Center**.

3.  Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie. Eine Beispiel-URL sieht wie folgt aus:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:
    
    `https://admin0a.online.lync.com`

5.  Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

