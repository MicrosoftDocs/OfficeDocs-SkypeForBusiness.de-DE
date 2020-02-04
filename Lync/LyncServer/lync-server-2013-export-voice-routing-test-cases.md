---
title: 'Lync Server 2013: Exportieren von Testfällen für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 781c9e312044193cb6195ee849a880bea6e08485
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: Sie definieren solche Dinge wie die Nummer, die gewählt werden soll, und die Richtlinie für Wähleinstellungen und VoIP, die verwendet werden soll, und lync Server kann dann überprüfen, ob die angegebene Nummer unter diesen Bedingungen erfolgreich an das PSTN-Netzwerk weitergeleitet.

Testfälle, die mithilfe der lync Server-Systemsteuerung erstellt werden können, werden in der Regel nur auf dem Server gespeichert, auf dem der Fall ursprünglich erstellt und ausgeführt wurde. Diese Testfälle können jedoch als XML-Dateien (mit der Erweiterung. vtest) exportiert und dann auf anderen Servern importiert werden. Auf diese Weise können Sie dieselben Tests auf verschiedenen Computern ausführen, die sich an unterschiedlichen Stellen in Ihrer Topologie befinden.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>So exportieren Sie einen Test Case für VoIP-Routing

1.  Klicken Sie in der lync Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf **VoIP-Routing testen**.

2.  Wählen Sie auf der Registerkarte **VoIP-Routing testen** den Testfall (oder Testfälle) aus, der exportiert werden soll. Wenn Sie mehrere Testfälle auswählen möchten, klicken Sie auf den ersten zu exportierenden Fall, halten Sie dann die STRG-Taste gedrückt, und wählen Sie die zu exportierenden zusätzlichen Fälle aus.

3.  Klicken Sie auf **Aktion**und dann auf **Test Cases exportieren**.

4.  Wählen Sie im Dialogfeld **Speichern** unter einen Ordner zum Speichern der exportierten Testfälle aus, und geben Sie im Feld **Dateiname** einen Namen für die resultierende XML-Datei ein. Beachten Sie, dass alle diese Testfälle in einer einzelnen XML-Datei gespeichert werden, wenn Sie mehrere Test Cases exportieren.

5.  Klicken Sie auf **Speichern**, um die Test Cases zu speichern.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Importieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

