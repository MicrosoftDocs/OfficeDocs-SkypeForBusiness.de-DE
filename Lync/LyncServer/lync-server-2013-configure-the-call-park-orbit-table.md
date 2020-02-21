---
title: 'Lync Server 2013: Konfigurieren der Orbit-Tabelle für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce2919e783b24148cd6526a1b4ecfbf082c11985
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Konfigurieren der Orbit-Tabelle für das Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-10_

Der Anruf Park verwendet Umlaufbahnen für das Parken von anrufen. Bevor Benutzer Anrufe parken und abrufen können, müssen Sie die Orbit-Tabelle für das Parken von anrufen konfigurieren. Sie müssen die Bereiche der Durchwahlnummern (Umlaufbahnen) angeben, die Ihre Organisation für das Parken von Anrufen reserviert, und das Routing für diese Bereiche definieren, indem Sie angeben, welcher Anruf Park Pool für jeden Bereich zuständig ist. Wenn Sie orbitbereiche definieren, besteht das Ziel darin, genügend Umlaufbahnen zu haben, sodass eine Umlaufbahn nicht zu schnell wieder verwendet wird, aber nicht so viele Umlaufbahnen, dass Sie die Anzahl der für Benutzer oder andere Dienste verfügbaren Erweiterungen begrenzen. Sie können mehrere orbitbereiche für das Parken von Anrufen für jeden lync Server Pool erstellen, in dem die Anwendung zum Parken von Anrufen bereitgestellt wird. Jeder orbitbereich für das Parken von Anrufen muss einen global eindeutigen Namen und eine eindeutige Gruppe von Durchwahlnummern aufweisen.

<div>


> [!IMPORTANT]  
> Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.



</div>

Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).

<div>


> [!NOTE]  
> Das Zuweisen von Durchwahlnummern (DID) als Orbit-Nummern in der Orbit-Tabelle für das Parken von Anrufen wird nicht unterstützt.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Erstellen oder Ändern eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

