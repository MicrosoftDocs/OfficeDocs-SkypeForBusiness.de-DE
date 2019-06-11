---
title: 'Lync Server 2013: Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc4eefe4c1ef804b1deb06d056bfbd61ade35eb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.

Sie müssen für jede Website mit Front-End-Servern, Standard Edition-Servern und Directors ein Kennwort für das Kerberos-Konto einrichten. Sie können das Kennwort einrichten, indem Sie das Windows PowerShell-Cmdlet " **CsKerberosAccountPassword** " auf einem Server auf der Website ausführen (beispielsweise ein Front-End-Server). Für jede Website müssen Sie das Cmdlet " **Satz-CsKerberosAccountPassword** " ausführen. Das Cmdlet konfiguriert Internet Informationsdienste (IIS) für den Webdienst Dienst und legt dann das Kennwort für das Computerkonto in den Active Directory-Domänendiensten fest. Eine alternative Methode, basierend auf dem mit dem Cmdlet verwendeten Parameter, konfiguriert IIS auf einem Server, während ein anderer Server verwendet wird, der als Quelle des Kerberos-Kontokennworts konfiguriert wurde.

Wenn Sie das Cmdlet **Set-CsKerberosAccountPassword** verwenden, um ein Kennwort festzulegen, wird das Kennwort von Kerberos auf eine zufällig generierte Zeichenfolge festgelegt. Dieses Cmdlet kontaktiert alle IIS-Instanzen in allen lync Server 2013 Central-Websites, denen dieses Konto zugewiesen ist.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>So legen Sie ein Kennwort für ein Kerberos-Authentifizierungs Konto ab

1.  Melden Sie sich bei einem beliebigen Domänencomputer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile die beiden folgenden Befehle aus:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Beispiel:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Sie müssen den Benutzerkonto-Parameter unter Verwendung des Formats Domäne \ Benutzer angeben. Das Format User @ Domain. Extension wird für den Verweis auf die für die Kerberos-Authentifizierung erstellten Computerobjekte nicht unterstützt.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Nachdem Sie die Kerberos-Authentifizierung geändert haben, beispielsweise ein Konto hinzugefügt oder ein Konto entfernt haben, müssen Sie <STRONG>enable-CsTopology</STRONG> über die Eingabeaufforderung der lync Server-Verwaltungsshell ausführen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

