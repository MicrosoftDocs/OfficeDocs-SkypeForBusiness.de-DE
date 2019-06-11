---
title: 'Lync Server 2013: Konfigurieren eines vorhandenen zentralen Verwaltungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a>Konfigurieren eines vorhandenen zentralen Verwaltungsservers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Wenn Sie einen zentralen Verwaltungs Server aus einer vorhandenen lync Server 2013-Bereitstellung wieder verwenden, müssen Sie das unten beschriebene Verfahren ausführen, um sicherzustellen, dass die lync Server-Systemsteuerung und Windows PowerShell ordnungsgemäß funktionieren.

<div>

## <a name="to-configure-an-existing-central-management-server"></a>So konfigurieren Sie einen vorhandenen zentralen Verwaltungs Server

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Verwenden Sie das Cmdlet **Update-CsAdminRole** , um die rollenbasierten zugriffssteuerungsrollen zu aktualisieren, die auf dem zentralen Verwaltungs Server gespeichert sind.
    
    <div>
    

    > [!NOTE]  
    > Es wird keine Ausgabe erwartet, es sei denn, es liegt ein Fehler vor.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

