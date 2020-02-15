---
title: 'Lync Server 2013: (optional) Überprüfen der Bereitstellung des Anruf Parks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b18de4af492fb45ef37e64cca45cc2d3d2b965
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Nachdem Sie das Parken von Anrufen installiert und konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Abrufen von anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:

  - Rufen Sie einen Benutzer an, der den Anruf Park aktiviert hat, und lassen Sie den Anruf vom Benutzer Parken.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie den Anruf Park in der VoIP-Richtlinie unmittelbar vor der Durchführung dieses Tests aktiviert haben, muss der Benutzer, der den Anruf abstellt, sich bei lync Server abmelden und dann wieder anmelden, um die Option "Parken" in der Anrufliste für die Anrufweiterleitung anzeigen zu können.

    
    </div>

  - Wählen Sie die Umlaufbahn Nummer, um den Anruf abzurufen.

  - Parken Sie einen weiteren Anruf, lassen Sie die geparkte Anruf-Zeit aus, und nehmen Sie nicht den Rückruf an. Stellen Sie sicher, dass der Timeout-Aufruf ordnungsgemäß an das Fallback-Ziel weitergeleitet wird, das für **OnTimeoutURI**angegeben ist.

</div>

<span> </span>

</div>

</div>

</div>

