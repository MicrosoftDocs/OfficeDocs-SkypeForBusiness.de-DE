---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c9f46944e80c5eb7a2d81de6f164d19aab64d29
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-22_

Lync Server unterstützt drei einfache URLs:

  - **Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.

  - **Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.

  - Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet.

Nach der Migration zu lync Server 2013 müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt. Wenn der Legacy lync Server 2010 Director in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich. Wenn der lync Server 2010 Director nach der Migration aus der Topologie entfernt wird, müssen die DNS-Einträge für einfache URLs so aktualisiert werden, dass Sie auf einen der lync Server 2013-Pools verweist. Bei jeder Namensänderung für eine einfache URL müssen Sie jedoch das Cmdlet "Enable-CsComputer" auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

<div>

## <a name="changing-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

**So aktualisieren Sie die einfache Meet-URL**

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Wählen Sie im linken Bereich **einfache URLs** und dann unter **Besprechungs-URLs:** wählen Sie die URL "Meet" aus, und klicken Sie dann auf **URL bearbeiten**.

3.  Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK**, um die bearbeitete URL zu speichern.

**So aktualisieren Sie die einfache Admin-URL**

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Wählen Sie **einfache URLs** im linken Bereich aus, und geben Sie dann unterhalb des Felds **Administrative Zugriffs-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf lync Server 2013 Systemsteuerung wünschen, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!TIP]  
    > Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden. Die einfachste Option ist <STRONG> https://admin .</STRONG> &lt; Domäne &gt; .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von einfachen URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

