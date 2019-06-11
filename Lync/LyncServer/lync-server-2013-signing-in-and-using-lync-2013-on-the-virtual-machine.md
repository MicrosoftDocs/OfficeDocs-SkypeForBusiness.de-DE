---
title: 'Lync Server 2013: Anmelden bei und Verwenden von Lync 2013 auf dem virtuellen Computer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Anmelden bei und Verwenden von Lync 2013 auf dem virtuellen Computer

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Nachdem das VDI-Plug-in aktiviert wurde, treten die folgenden Schritte auf, wenn sich der Benutzer bei lync 2013 anmeldet.

1.  Der Benutzer gibt seine Anmeldeinformationen in den lync 2013-Client ein, der auf dem virtuellen Computer ausgeführt wird.

2.  Nachdem lync die Verfügbarkeit des VDI-Plug-ins erkannt hat, fordert lync den Benutzer auf, seine Anmeldeinformationen erneut einzugeben. In diesem Dialogfeld sollten die Benutzer das Kontrollkästchen **Kennwort speichern** aktivieren, damit sie die Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben müssen.

3.  Lync beginnt die Kopplung mit dem VDI-Plug-in. Bevor die Kopplung abgeschlossen ist, zeigt der Client zwei Symbole in der lync-Statusleiste an. Das Symbol in der unteren linken Ecke zeigt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol in der unteren rechten Ecke zeigt an, dass die VDI-Kopplung in Bearbeitung ist (siehe Abbildung).
    
    ![Lync-VDI-Symbol mit erfolgreicher Kopplung] (images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")  

4.  Nach einer erfolgreichen VDI-Kopplung ändern sich die Symbole und zeigen nun das für Anrufe verwendete Audiogerät bzw. den Erfolg der VDI-Kopplung an:
    
    ![Lync-VDI-Kopplungs Symbol mit Erfolg] (images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync-VDI-Kopplungs Symbol mit Erfolg")  

5.  Nach lync-Paaren mit dem VDI-Plug-in kann der Benutzer seine Anwesenheit auf lync-kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind. Der Benutzer kann nun wie gewohnt Anrufe tätigen und annehmen.

</div>

<span> </span>

</div>

</div>

</div>

