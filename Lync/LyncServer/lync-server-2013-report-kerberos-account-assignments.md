---
title: 'Lync Server 2013: Melden von Kerberos-Konto Zuweisungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f44f187b751ec9baa78df8890e64332070d8b33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Melden von Kerberos-Konto Zuweisungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Mit dem Cmdlet **Get-CsKerberosAccountAssignment** können Sie Informationen zu Kontozuweisungen für die Kerberos-Authentifizierung sowie Berichtinformationen zu den aktuellen Zuweisungen in Ihrer Bereitstellung abrufen.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>So rufen Sie Kontozuweisungen für die Kerberos-Authentifizierung für einen Standort ab

1.  Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins bei einem Computer in der Domäne an, auf dem lync Server 2013 oder an einem Computer mit den Verwaltungstools installiert ist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile einen der folgenden Befehle aus:
    
      - Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung in Ihrer Organisation und Zurückgeben von Informationen zu den einzelnen Zuweisungen führen Sie das Cmdlet ohne Parameter aus:
        
            Get-CsKerberosAccountAssignment
    
      - Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung in Ihrer Bereitstellung und Zurückgeben von Standortzuweisungsinformationen zu den einzelnen Zuweisungen führen Sie das Cmdlet mit dem Identitätsparameter aus:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Zum Beispiel:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung an einem einzelnen Standort und Zurückgeben von Informationen zu den einzelnen Zuweisungen führen Sie das Cmdlet mit dem Filterparameter aus:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Beispiel:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Bei Angabe von "*SiteName" als Filterparameter werden Informationen zu sämtlichen Standorten zurückgegeben, deren Standort-ID den angegebenen Standortnamen enthält (z. B. alle Standorte mit der Zeichenfolge "Redmond" in der Standort-ID).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

