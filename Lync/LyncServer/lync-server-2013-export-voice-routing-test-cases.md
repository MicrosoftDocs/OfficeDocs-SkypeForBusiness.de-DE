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
ms.openlocfilehash: f4f366c286c332625779a7ebf45fecfa918ea16b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528352"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportieren von Testfällen für das VoIP-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: Sie definieren beispielsweise die Nummer, die gewählt werden soll, und die Wähleinstellungen und die VoIP-Richtlinie, die verwendet werden sollen, und lync Server können dann anhand dieser Bedingungen sicherstellen, dass die angegebene Nummer erfolgreich an das PSTN-Netzwerk weitergeleitet werden kann.

Testfälle, die mithilfe von lync Server-Systemsteuerung erstellt werden können, werden normalerweise nur auf dem Server gespeichert, auf dem der Fall ursprünglich erstellt und ausgeführt wurde. Sie können jedoch in Form von XML-Dateien (mit der Erweiterung VTEST) exportiert und dann auf anderen Servern importiert werden. Auf diese Weise können Sie die gleichen Tests auf verschiedenen Computern an unterschiedlichen Standorten in Ihrer Topologie durchführen.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>So exportieren Sie einen Testfall für das VoIP-Routing

1.  Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf VoIP- **Routing testen**.

2.  Wählen Sie auf der Registerkarte **VoIP-Routing testen** den Testfall (oder die Testfälle) aus, die exportiert werden sollen. Sie können mehrere Fälle auswählen, indem Sie auf den ersten Fall klicken, der exportiert werden soll, und beim Klicken auf weitere Fälle die STRG-Taste gedrückt halten.

3.  Klicken Sie auf **Aktion** und dann auf **Testfälle exportieren**.

4.  Wählen Sie im Dialogfeld **Speichern unter** einen Ordner aus, in dem die exportierten Testfälle gespeichert werden sollen, und geben Sie einen Namen für die resultierende XML-Datei im Feld **Dateiname** ein. Wenn Sie mehrere Testfälle exportieren, werden alle Testfälle in einer einzelnen XML-Datei gespeichert.

5.  Klicken Sie auf **Speichern**, um die Testfälle zu speichern.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Importieren von Testfällen für das VoIP-Routing in lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

