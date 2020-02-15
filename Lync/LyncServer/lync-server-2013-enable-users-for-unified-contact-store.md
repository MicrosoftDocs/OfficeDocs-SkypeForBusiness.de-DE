---
title: 'Lync Server 2013: Aktivieren von Benutzern für den einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99fd96b16d19305ea5bb63ea9f84096ef6117c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-07_

Wenn Sie lync Server 2013 bereitstellen und die Topologie veröffentlichen, ist der einheitliche Kontaktspeicher standardmäßig für alle Benutzer aktiviert. Sie müssen keine zusätzlichen Aktionen ausführen, um den einheitlichen Kontaktspeicher zu aktivieren, nachdem Sie lync Server 2013 bereitgestellt haben. Sie können jedoch das Cmdlet " **csuserservicespolicy"** "verwenden, um die Verfügbarkeit von Benutzern mit einheitlichem Kontaktspeicher anzupassen. Sie können diese Funktion Global, nach Standort, vom Mandanten oder von Einzelpersonen oder Personengruppen aktivieren.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher Global für alle lync Server Benutzer zu aktivieren:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Wenn Sie den einheitlichen Kontaktspeicher für die Benutzer an einem bestimmten Standort aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Beispiel:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Wenn Sie den einheitlichen Kontaktspeicher nach Mandant aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Beispiel:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Wenn Sie den einheitlichen Kontaktspeicher für bestimmte Benutzer aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden.

        
        </div>
        
        Beispiel:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen <EM>UCS Enabled Users</EM> erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist. Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d. h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

