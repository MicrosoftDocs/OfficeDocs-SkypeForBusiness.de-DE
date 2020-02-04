---
title: 'Lync Server 2013: Erstellen eines Kerberos-Authentifizierungskontos'
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
ms.openlocfilehash: 797e9216aed5d523e39dc4827d630e0cb1b857fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-01-02_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.

Sie können für jede Website Kerberos-Authentifizierungs Konten erstellen, oder Sie können ein einzelnes Kerberos-Authentifizierungs Konto erstellen und für alle Websites verwenden. Sie verwenden Windows PowerShell-Cmdlets zum Erstellen und Verwalten der Konten, einschließlich der Ermittlung der Konten, die den einzelnen Websites zugewiesen sind. Der Topologie-Generator und die lync Server 2013-Systemsteuerung zeigen keine Kerberos-Authentifizierungs Konten an. Gehen Sie wie folgt vor, um ein oder mehrere Benutzerkonten zu erstellen, die für die Kerberos-Authentifizierung verwendet werden sollen.

<div>

## <a name="to-create-a-kerberos-account"></a>So erstellen Sie ein Kerberos-Konto

1.  Melden Sie sich als Mitglied der Gruppe Domänenadministratoren bei einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile den folgenden Befehl aus:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Beispiel:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Vergewissern Sie sich, dass das Computerobjekt erstellt wurde, indem Sie Active Directory-Benutzer und-Computer öffnen, den Container **Benutzer** erweitern und dann bestätigen, dass sich das Computerobjekt für das Benutzerkonto im Container befindet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

