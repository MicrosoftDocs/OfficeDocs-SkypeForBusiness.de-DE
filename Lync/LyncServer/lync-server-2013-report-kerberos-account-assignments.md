---
title: 'Lync Server 2013: Melden von Kerberos-Kontozuweisungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Melden von Kerberos-Kontozuweisungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.

Mit dem Cmdlet **Get-CsKerberosAccountAssignment** können Sie Informationen zu den Kerberos-Authentifizierungs Konto Zuweisungen Abfragen und Informationen zu den aktuellen Aufgaben in Ihrer Bereitstellung melden.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>So Abfragen Sie Kerberos-Authentifizierungs Konto Zuweisungen für eine Website

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile einen der folgenden Befehle aus:
    
      - Wenn Sie alle Kerberos-Authentifizierungs Konto Zuweisungen in Ihrer Organisation Abfragen und Zuordnungsinformationen zu den einzelnen Aufgaben zurückgeben möchten, führen Sie das Cmdlet ohne Parameter aus:
        
            Get-CsKerberosAccountAssignment
    
      - Führen Sie das Cmdlet mit dem Parameter Identity aus, um alle Kerberos-Authentifizierungs Konto Zuweisungen in Ihrer Bereitstellung abzufragen und Websitezuordnungsinformationen zu diesen zurückzugeben:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Beispiel:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Führen Sie das Cmdlet mit dem Parameter Filter aus, um alle Kerberos-Authentifizierungs Konto Zuweisungen an einer einzigen Website abzufragen und Zuordnungsinformationen zu den einzelnen Websites zurückzugeben:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Beispiel:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Durch die Angabe von * Sitename für den Filter-Parameter werden Informationen zu allen Websites zurückgegeben, die den angegebenen Websitenamen an einer beliebigen Stelle in der Website-ID enthalten (beispielsweise alle Websites, die die Zeichenfolge Redmond in der Website-ID enthalten).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

