---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204c183ad63da3278d10b802d3f2140fa9a86a70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-11_

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als lync Server 2013 Pool festlegen. In einer gemischten Umgebung werden sowohl der Legacy lync Server 2010 Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.

**Auswählen lync Server 2013 als nächster Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers**

1.  Öffnen Sie den Topologie-Generator.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie auf **Neuer Pool für vertrauenswürdige Anwendungen**.

3.  Geben Sie den **Pool-FQDN** des Pools vertrauenswürdiger Anwendungen ein. Geben Sie an, ob der Pool einen einzelnen oder mehrere Server enthalten soll.

4.  Klicken Sie auf **Weiter**.

5.  Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die lync Server 2013 Front-End-Pool aus.

6.  Klicken Sie auf **Fertig stellen**.

7.  Wählen Sie den obersten Knoten **Lync Server** aus, und wählen Sie dann im Menü **Aktionen** die Option **Veröffentlichen** aus.
    
    Überprüfen Sie, dass der **vertrauenswürdige Anwendungspool** erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet worden ist.

</div>

<span> </span>

</div>

</div>

</div>

