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
ms.openlocfilehash: 91392470d47cc4d59130e7c304656f9eee48ae5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531372"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Bereitstellen des SEFAUtil-Tools in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Zum Bereitstellen und Verwalten der gruppenanrufannahme müssen Sie das SEFAUtil Resource Kit-Tool verwenden. Das Tool ist Teil der lync Server 2013 Resource Kit-Tools. Bevor Sie SEFAUtil installieren können, müssen Sie über einen vertrauenswürdigen Anwendungspool in Ihrer Topologie verfügen, SEFAUtil als vertrauenswürdige Anwendung angeben und die Topologie aktivieren.

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK müssen auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.



</div>

Sie können das SEFAUtil in jeder beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen.

<div>


> [!NOTE]  
> Weitere Informationen zur Ausführung von SEFAUtil finden Sie im TechNet-Blog Artikel "How to Get SEFAUtil Running?". an <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .



</div>

<div>

## <a name="to-deploy-sefautil"></a>So stellen Sie SEFAUtil bereit

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für die Front-End-Pool, in der Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Definieren Sie das SEFAUtil-Tool als vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Sie können bei Bedarf einen anderen Port verwenden.

    
    </div>

5.  Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Enable-CsTopology

6.  Installieren Sie die lync Server 2013 Resource Kit-Tools auf einem Front-End-Server im vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.

7.  Stellen Sie sicher, dass das SEFAUtil-Tool wie folgt ordnungsgemäß ausgeführt wird:
    
    1.  Führen Sie das Tool über die Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
        
        <div>
        

        > [!NOTE]  
        > Das Tool befindet sich im Verzeichnis \Programme\Microsoft lync Server 2013 \ reskit.

        
        </div>
    
    2.  Zeigt die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung Folgendes aus:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

