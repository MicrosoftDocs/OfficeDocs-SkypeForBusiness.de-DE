---
title: 'Lync Server 2013: Bereitstellen des SEFAUtil-Tools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Zum Bereitstellen und Verwalten der Gruppenanruf Abholung müssen Sie das SEFAUtil Resource Kit-Tool verwenden. Das Tool ist Teil der lync Server 2013 Resource Kit-Tools. Bevor Sie SEFAUtil installieren können, müssen Sie über einen vertrauenswürdigen Anwendungspool in Ihrer Topologie verfügen, SEFAUtil als vertrauenswürdige Anwendung angeben und die Topologie aktivieren.

<div>


> [!IMPORTANT]  
> Das Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.



</div>

Sie können die SEFAUtil in einem beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen.

<div>


> [!NOTE]  
> Weitere Informationen zum Ausführen von SEFAUtil finden Sie im TechNet-Blog Artikel "wie erhalte ich SEFAUtil?" bei <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.



</div>

<div>

## <a name="to-deploy-sefautil"></a>So stellen Sie das SEFAUtil-Tool bereit

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört. Falls erforderlich, definieren Sie einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Sie können ggf. einen anderen Port verwenden.

    
    </div>

5.  Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Enable-CsTopology

6.  Installieren Sie die lync Server 2013 Resource Kit-Tools auf einem Front-End-Server, der sich in dem vertrauenswürdigen Anwendungspool befindet, den Sie in Schritt 3 erstellt haben.

7.  Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:
    
    1.  Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
        
        <div>
        

        > [!NOTE]  
        > Das Tool befindet sich unter \Programme\Microsoft lync Server 2013 \ reskit.

        
        </div>
    
    2.  Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

