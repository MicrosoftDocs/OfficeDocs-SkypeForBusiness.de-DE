---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0203b33d787310544f4f376872ecf9c99fc7254d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Lync Server unterstützt drei einfache URLs:

  - **Meet** wird als Basis-URL für alle Konferenzen auf der Website oder Organisation verwendet. Mit der einfachen URL für Besprechungen sind Links zu Besprechungen einfach zu verstehen und einfach zu kommunizieren und zu verteilen.

  - **Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzeinstellungen. Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können.

  - Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation.

Nach der Migration zu lync Server 2013 müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt. Wenn der Legacy-lync Server 2010-Director in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich. Wenn der lync Server 2010-Director nach der Migration aus der Topologie entfernt wird, müssen die einfachen URL-DNS-Einträge so aktualisiert werden, dass Sie auf einen der lync Server 2013-Pools verweisen. Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie Enable-CsComputer auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

<div>

## <a name="changing-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

**So aktualisieren Sie die einfache URL für Besprechungen**

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Wählen Sie im linken Bereich und dann unter Besprechungs- **URLs** **einfache URLs** aus: Wählen Sie die URL erfüllen aus, und klicken Sie dann auf **URL bearbeiten**.

3.  Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern.

**So aktualisieren Sie die einfache Administrator-URL**

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Wählen Sie im linken Bereich **einfache URLs** aus, und geben Sie dann unter **Administratorzugriff-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf die lync Server 2013-Systemsteuerung benötigen, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!TIP]  
    > Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden. Die einfachste Option ist <STRONG> https://admin.</STRONG> &lt;Domäne&gt;aus.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

