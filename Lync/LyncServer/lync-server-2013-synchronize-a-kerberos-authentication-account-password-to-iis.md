---
title: Synchronisieren eines Kennworts für das Kerberos-Authentifizierungs Konto mit IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac886bf4eba4261a733241aa8d1d5396c4acc86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523852"
---
# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Synchronisieren eines Kennworts für das Kerberos-Authentifizierungs Konto mit IIS in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2010-11-08_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Auf einem Standort können Front-End-Server, Standard Edition-Server und Directors ein Kerberos-Authentifizierungs Konto verwenden, um Anforderungen an den Webdienste Dienst zu authentifizieren. Dieses Verfahren sucht jeden Server, auf dem Webdienste ausgeführt wird, auf einem Standort, dem ein Kerberos-Konto zugewiesen wurde, und aktualisiert die Internet Information Services (IIS) Konfigurationseinstellungen für die Verwendung des Kerberos-Kontos. Ausführliche Informationen finden Sie unter [Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>So legen Sie ein Kennwort für das Kerberos-Authentifizierungskonto fest

1.  Melden Sie sich bei einem Quellcomputer (z. B. "fe01.contoso.com") als Mitglied der Gruppe "RTCUniversalServerAdmins" an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der lync Server-Verwaltungsshell Befehlszeile die folgenden zwei Befehle aus:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Beispiel:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > Bei den Namen für den Quell- und den Zielcomputer muss es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers handeln. Sie können den Pool-FQDN nur dann verwenden, wenn der Poolname mit dem Namen des Computers übereinstimmt, den Sie als Quell- oder Zielcomputer verwenden.

    
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

