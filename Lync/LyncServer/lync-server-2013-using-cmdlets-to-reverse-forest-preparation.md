---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung'
description: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580391"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-06-19_

Verwenden Sie das Cmdlet **Disable-CsAdForest** , um den Gesamtstrukturvorbereitungsschritt umzukehren.

<div>


> [!WARNING]  
> Wenn Sie das Cmdlet <STRONG>Disable-CsAdForest</STRONG> in einer Umgebung ausführen, in der Sie auch eine frühere Version von lync Server bereitgestellt haben, werden die globalen Einstellungen für die vorherige Version ebenfalls gelöscht.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>So verwenden Sie Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung

1.  Melden Sie sich bei einem Domänencomputer als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Beispiel:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Der Parameter Force gibt an, ob die Ausführung der Aufgabe erzwungen werden soll. Wenn dieser Parameter nicht vorhanden ist, wird der Befehl nicht ausgeführt, wenn auch eine Domäne in der Gesamtstruktur noch für lync Server 2013 vorbereitet ist. Wenn der Parameter Force angegeben wird, wird die Aktion unabhängig vom Status anderer Domänen in der Gesamtstruktur fortgesetzt.
    
    Wenn Sie den Parameter "GroupDomain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Laufende Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Vorbereiten der Gesamtstruktur auf lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

