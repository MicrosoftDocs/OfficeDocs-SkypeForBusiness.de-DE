---
title: 'Lync Server 2013: Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server'
description: 'Lync Server 2013: Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 723392e670ca0b4bc9796cd62dab3b1a61f99dd1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574841"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Für das Kerberos-Konto muss für jeden Standort, der über Front-End-Server, Standard Edition-Server und Director-Server verfügt, ein Kennwort eingerichtet werden. Sie können das Kennwort einrichten, indem Sie das Cmdlet " **CsKerberosAccountPassword**   Windows PowerShell" auf einem Server am Standort ausführen (beispielsweise ein Front-End-Server). Für jeden Standort müssen Sie das Cmdlet " **CsKerberosAccountPassword**" Ausführen   . Das Cmdlet konfiguriert Internet Information Services (IIS) für den Webdienste Dienst und legt dann das Kennwort für das Computerkonto in Active Directory-Domänendienste fest. Bei einer alternativen Methode wird IIS abhängig davon, welcher Parameter mit dem Cmdlet verwendet wird, auf einem Server konfiguriert, während ein anderer Server verwendet wird, der als Quelle des Kerberos-Kontokennworts konfiguriert wurde.

Bei Verwendung des Cmdlets **Set-CsKerberosAccountPassword** zum Festlegen des Kennworts legt Kerberos das Kennwort auf eine nach dem Zufallsprinzip generierte Zeichenfolge fest. Dieses Cmdlet kontaktiert alle IIS-Instanzen an allen lync Server 2013 zentralen Standorten, denen dieses Konto zugewiesen ist.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>So legen Sie ein Kennwort für ein Kerberos-Authentifizierungskonto fest

1.  Melden Sie sich an einem beliebigen Domänencomputer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Beispiel:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Sie müssen den Parameter "UserAccount" im Format "Domäne\Benutzer" angeben. Das Format "Benutzer@Domäne.Erweiterung" wird zur Referenzierung der für die Kerberos-Authentifizierung erstellten Computerobjekte nicht unterstützt.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Nachdem Sie Änderungen an der Kerberos-Authentifizierung vorgenommen haben, wie beispielsweise das Hinzufügen eines Kontos oder das Entfernen eines Kontos, müssen Sie <STRONG>enable-CsTopology</STRONG> über die lync Server-Verwaltungsshell Eingabeaufforderung ausführen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

