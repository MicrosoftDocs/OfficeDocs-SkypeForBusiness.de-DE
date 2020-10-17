---
title: 'Lync Server 2013: Erstellen eines Kerberos-Authentifizierungs Kontos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e63b339f9a8d9705af47d9226adde88fe2d053
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507512"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Erstellen eines Kerberos-Authentifizierungs Kontos in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-01-02_

Für die folgenden Schritte sollten Sie auf dem Server oder der Domäne mindestens als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.

Sie können für jeden Standort ein eigenes Kerberos-Authentifizierungskonto oder ein einziges Kerberos-Authentifizierungskonto für alle Standorte erstellen. Verwenden Sie Windows PowerShell-Cmdlets zum Erstellen und Verwalten der Konten, einschließlich der Ermittlung der Konten, die jedem Standort zugewiesen sind. Der Topologie-Generator und die lync Server 2013-Systemsteuerung zeigen keine Kerberos-Authentifizierungs Konten an. Gehen Sie wie folgt vor, um ein oder mehrere Benutzerkonten zur Kerberos-Authentifizierung zu erstellen.

<div>

## <a name="to-create-a-kerberos-account"></a>So erstellen Sie ein Kerberos-Konto

1.  Melden Sie sich als Mitglied der Gruppe "Domänen-Admins" bei einem Computer in der Domäne mit lync Server 2013 oder an einem Computer an, auf dem die Verwaltungstools installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl über die Befehlszeile aus:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Beispiel:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Stellen Sie sicher, dass das Computerobjekt erstellt wurde, indem Sie Active Directory Benutzer und Computer öffnen, den Container **Benutzer** erweitern und dann sicherstellen, dass sich das Computerobjekt für das Benutzerkonto im Container befindet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

