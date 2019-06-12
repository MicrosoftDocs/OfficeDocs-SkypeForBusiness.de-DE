---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-06-19_

Verwenden Sie das Cmdlet **Disable-CsAdForest** , um den Vorbereitungsschritt für die Gesamtstruktur umzukehren.

<div>


> [!WARNING]  
> Wenn Sie das Cmdlet <STRONG>Disable-CsAdForest</STRONG> in einer Umgebung ausführen, in der auch eine frühere Version von lync Server bereitgestellt ist, werden die globalen Einstellungen für die vorherige Version ebenfalls gelöscht.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>So verwenden Sie Cmdlets zum Umkehren der Gesamtstrukturvorbereitung

1.  Melden Sie sich bei einem Computer an, der einer Domäne als Mitglied der Gruppe der Domänenadministratoren in der Stammdomäne der Gesamtstruktur beigetreten ist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Beispiel:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Der Parameter Force gibt an, ob die Ausführung der Aufgabe erzwungen werden soll. Wenn dieser Parameter nicht vorhanden ist, wird der Befehl nicht ausgeführt, wenn noch eine Domäne in der Gesamtstruktur für lync Server 2013 vorbereitet ist. Wenn der Parameter Force angegeben wird, wird die Aktion ungeachtet des Zustands anderer Domänen in der Gesamtstruktur fortgesetzt.
    
    Wenn Sie den GroupDomain-Parameter nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

