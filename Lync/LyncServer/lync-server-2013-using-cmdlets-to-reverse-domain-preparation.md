---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung'
description: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d26cc97ee934ee959838f38f4e2f52f9bf89566
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580411"
---
# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Verwenden Sie das Cmdlet **Disable-CsAdDomain**, um die Domänenvorbereitung rückgängig zu machen.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>So machen Sie mithilfe von Cmdlets die Domänenvorbereitung rückgängig

1.  Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Beispiel:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Wenn der Parameter Force vorhanden ist, wird die Domänenvorbereitung zurückgesetzt, auch wenn ein oder mehrere Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind. Wenn der Parameter Force nicht vorhanden ist, wird das Rollback der Domänenvorbereitung beendet, wenn alle Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind.
    
    <div>
    

    > [!NOTE]  
    > Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, in denen die globalen Einstellungen nicht zum Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in AD &nbsp; DS.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ausführung der Domänenvorbereitung für lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

