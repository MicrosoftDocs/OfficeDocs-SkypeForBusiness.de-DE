---
title: 'Lync Server 2013: anmelden und Verwenden von lync 2013 auf dem virtuellen Computer'
description: 'Lync Server 2013: anmelden und Verwenden von lync 2013 auf dem virtuellen Computer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad9a92d450fb9d60aed70617089d95280528892f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555681"
---
# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Anmelden und Verwenden von lync 2013 auf dem virtuellen Computer

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Nachdem das VDI-Plug-in aktiviert wurde, werden die folgenden Schritte ausgeführt, wenn sich der Benutzer bei lync 2013 anmeldet.

1.  Der Benutzer gibt seine Anmeldeinformationen im lync 2013-Client ein, der auf dem virtuellen Computer läuft.

2.  Nachdem lync die Verfügbarkeit des VDI-Plug-ins erkannt hat, fordert lync den Benutzer auf, seine Anmeldeinformationen erneut einzugeben. Es wird empfohlen, in diesem Dialogfeld das Kontrollkästchen **Kennwort speichern** zu aktivieren, damit der Benutzer seine Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben muss.

3.  Lync beginnt mit dem VDI-Plug-in zu koppeln. Bevor die Kopplung abgeschlossen ist, zeigt der Client zwei Symbole in der lync-Statusleiste an. Das Symbol in der linken oberen Ecke gibt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol unten rechts zeigt an, dass die VDI-Kopplung in Bearbeitung ist, wie in der folgenden Abbildung dargestellt:
    
    ![Lync-VDI-Symbol mit erfolgreicher Kopplung](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")  

4.  Nach einer erfolgreichen VDI-Kopplung ändern sich die Symbole und zeigen nun das für Anrufe verwendete Audiogerät bzw. den Erfolg der VDI-Kopplung an:
    
    ![Lync-VDI-Paarungs Symbol mit Erfolg](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync-VDI-Paarungs Symbol mit Erfolg")  

5.  Nachdem lync mit dem VDI-Plug-in paarweise zusammengepaßt hat, kann der Benutzer seine Anwesenheit auf lync-kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind. Nun kann der Benutzer Anrufe wie gewohnt tätigen oder entgegennehmen.

</div>

<span> </span>

</div>

</div>

</div>

