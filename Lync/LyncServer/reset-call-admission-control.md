---
title: Zurücksetzen der Anrufsteuerung
description: Zurücksetzen der Anrufsteuerung.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4539cda453de6249be3a9b9b61521ecf478cb70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551241"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-11_

Wenn ein lync Server 2010-Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das CAC-Hosting in einen lync Server 2013 Pool versetzen, bevor Sie die lync Server 2010 Front-End-Pool entfernen können.

<div>

## <a name="to-reset-cac"></a>So setzen Sie die Anrufsteuerung zurück

1.  Öffnen Sie den Topologie-Generator.

2.  Klicken Sie mit der rechten Maustaste auf den Standortknoten, und klicken Sie auf **Eigenschaften bearbeiten**.

3.  Vergewissern Sie sich, dass in der **Einstellung für Anrufsteuerung** die Option **Anrufsteuerung aktivieren** ausgewählt wurde.

4.  Wählen Sie unter **Front-End-Pool zum Ausführen der Anrufsteuerung (Call Admission Control, CAC)** den lync Server 2013 Pool aus, auf dem die Anrufsteuerung gehostet werden soll, und klicken Sie dann auf **OK**.

5.  Veröffentlichen Sie die Topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

