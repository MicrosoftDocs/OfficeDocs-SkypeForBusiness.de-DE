---
title: 'Lync Server 2013: Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb755f7e7b814d4ca643bd04ddfc0241b4d96d60
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-04-18_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.

Nachdem Sie das Kerberos-Konto erstellt haben, müssen Sie es einer Website zuweisen. Hierbei handelt es sich um eine lync Server 2013-Website, nicht um einen Active Directory-Standort. Sie können pro Bereitstellung mehrere Kerberos-Authentifizierungs Konten erstellen, aber Sie können einer Website nur ein Konto zuweisen. Gehen Sie wie folgt vor, um einer Website ein zuvor erstelltes Kerberos-Authentifizierungs Konto zuzuweisen. Details zum Erstellen des Kerberos-Kontos finden Sie unter [Erstellen eines Kerberos-Authentifizierungs Kontos in lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>So weisen Sie einer Website ein Kerberos-Authentifizierungs Konto zu

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile die beiden folgenden Befehle aus:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    Beispiel:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Sie müssen den Benutzerkonto-Parameter unter Verwendung des Formats Domäne \ Benutzer angeben. Das User@Domain. Extension-Format wird nicht unterstützt, um auf die für die Kerberos-Authentifizierung erstellten Computerobjekte zu verweisen.

    
    </div>

4.  **Optional**: Sie haben möglicherweise einen überschreiben-FQDN (Fully Qualified Domain Name, vollständig qualifizierter Domänenname) für Ihre Webdienste konfiguriert, wie pro [Änderung der URL für Webdienste in lync Server 2013](lync-server-2013-change-the-web-services-url.md). Wenn dies der Fall ist, müssen Sie auch einen SPN für diesen FQDN hinzufügen. Wenn der FQDN beispielsweise Webservices. contoso. local lautete, würden Sie Folgendes ausführen:
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > Nachdem Sie die Kerberos-Authentifizierung geändert haben, beispielsweise ein Konto hinzugefügt oder ein Konto entfernt haben, müssen Sie <STRONG>enable-CsTopology</STRONG> über die Eingabeaufforderung der lync Server-Verwaltungsshell ausführen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

