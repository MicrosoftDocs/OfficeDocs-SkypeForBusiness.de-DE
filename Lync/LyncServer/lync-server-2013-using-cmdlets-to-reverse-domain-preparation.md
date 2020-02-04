---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung'
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
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Verwenden Sie das Cmdlet **Disable-CsAdDomain** , um den Schritt zur Domänenvorbereitung umzukehren.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>So verwenden Sie Cmdlets zum Umkehren der Domänenvorbereitung

1.  Melden Sie sich bei einem beliebigen Server in der Domäne als Mitglied der Gruppe der Domänenadministratoren an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Beispiel:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Wenn der Parameter Force vorhanden ist, wird die Domänenvorbereitung zurückgesetzt, selbst wenn ein oder mehrere Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind. Wenn der Parameter Force nicht vorhanden ist, wird das Rollback zur Domänenvorbereitung beendet, wenn alle Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind.
    
    <div>
    

    > [!NOTE]  
    > Mit dem Parameter GlobalSettingsDomainController können Sie angeben, wo die globalen Einstellungen gespeichert werden. Wenn Ihre Einstellungen im System Container gespeichert sind (typisch für Upgrade-Bereitstellungen, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind und auf einen beliebigen Domänencontroller in&nbsp;AD DS verweisen.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ausführen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

