---
title: 'Lync Server 2013: Konfigurieren eines vorhandenen zentralen Verwaltungsservers'
description: 'Lync Server 2013: Konfigurieren eines vorhandenen zentralen Verwaltungsservers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef93281be2537ca5e4a5892a8617500ce54f3c45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546711"
---
# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a>Konfigurieren eines vorhandenen zentralen Verwaltungsservers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Wenn Sie einen zentralen Verwaltungs Server aus einer vorhandenen lync Server 2013-Bereitstellung wieder verwenden, müssen Sie das unten beschriebene Verfahren ausführen, um sicherzustellen, dass lync Server-Systemsteuerung und Windows PowerShell ordnungsgemäß funktionieren.

<div>

## <a name="to-configure-an-existing-central-management-server"></a>So konfigurieren Sie einen vorhandenen zentralen Verwaltungs Server

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Verwenden Sie das Cmdlet **Update-CsAdminRole** , um die rollenbasierten zugriffssteuerungsrollen (Role-Based Access Control, RBAC) zu aktualisieren, die auf dem zentralen Verwaltungs Server gespeichert sind.
    
    <div>
    

    > [!NOTE]  
    > Es wird keine Ausgabe erwartet, außer es tritt ein Fehler auf.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

