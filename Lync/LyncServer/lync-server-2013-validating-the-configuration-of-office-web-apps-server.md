---
title: 'Lync Server 2013: Überprüfen der Konfiguration von Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Überprüfen der Konfiguration von Office Web Apps Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

Nachdem Office Web Apps Server zur Topologie hinzugefügt wurde und die Topologie veröffentlicht wurde, sollten im lync Server-Ereignisprotokoll zwei neue Ereignisprotokoll Ereignisse angezeigt werden. Zunächst sollte ein ls-Daten MCU-Ereignis (Ereignis-ID 41034) hinzugefügt werden. Dieses Ereignis meldet, dass der Office Web Apps-Server erkannt wurde:

**Der Webkonferenzserver Office Web Apps-Server wurde ermittelt, PowerPoint-Inhalte sind aktiviert.**

Außerdem sollte ein weiteres "LS Data MCU"-Ereignis angezeigt werden (Ereignis-ID 41032), das Office Web Apps Server-URLs zurückmeldet. Beispielsweise sollten Meldungen wie etwa folgende angezeigt werden:

**Die Ermittlung des Webkonferenzservers Office Web Apps-Server war erfolgreich.**

**Office Web Apps Server-interne Referenten Seite:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps Server-Seite für interne Teilnehmer:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps Server-externe Referenten Seite:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps Server-Seite für interne Teilnehmer:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Wenn ein ls-Daten MCU-Ereignis mit der Ereignis-ID von 41033 angezeigt wird, bedeutet dies, dass die Server Ermittlung von Office Web Apps fehlgeschlagen ist. In diesem Fall wird Microsoft lync Server 2013 so oft wie erforderlich versuchen, um den neu konfigurierten Office Web Apps-Server zu entdecken. Wenn der Ermittlungsvorgang wiederholt fehlschlägt, sollten Sie Office Web Apps Server aus Ihrem Topologie-Dokument entfernen, die aktualisierte Topologie veröffentlichen und dann versuchen, Office Web Apps Server wieder zur Topologie hinzuzufügen, nachdem die Verbindungsprobleme behoben wurden.

Wenn Office Web Apps Server anscheinend ordnungsgemäß konfiguriert wurde und vom Ermittlungsprozess erkannt wurde, können Sie überprüfen, ob der Office Web Apps-Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen zwei Microsoft lync 2013-Clients freigeben. Wenn Benutzer a die PowerPoint-Präsentation laden und anzeigen kann und wenn Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert der Office Web Apps-Server.

Auch wenn Office Web Apps Server anscheinend richtig konfiguriert ist, können Sie möglicherweise die Fehlermeldung "einige Freigabefeatures sind aufgrund von Server Verbindungsproblemen nicht verfügbar" erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben. Wenn diese Fehlermeldung angezeigt wird, sollten Sie den Front-End-Server (oder die Server) neu starten, die dem neuen Office Web Apps-Server zugeordnet sind.

</div>

<span> </span>

</div>

</div>

</div>

