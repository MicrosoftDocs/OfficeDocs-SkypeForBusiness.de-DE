---
title: 'Lync Server 2013: Überprüfen der Konfiguration von Office-webapps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c3fcfd33668918eb330b64d816ceca818de27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Überprüfen der Konfiguration von Office-webapps Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-22_

Nachdem Office webapps Server zur Topologie hinzugefügt wurde und diese Topologie veröffentlicht wurde, sollten im lync Server Ereignisprotokoll zwei neue Ereignisprotokoll Ereignisse angezeigt werden. Zunächst sollte ein ls Data MCU-Ereignis (Ereigniskennung 41034) hinzugefügt werden; Dieses Ereignis meldet, dass der Office-webapps-Server erkannt wurde:

**Webkonferenzserver Office-webapps-Server wird ermittelt, PowerPoint-Inhalte sind aktiviert.**

Darüber hinaus sollte ein weiteres ls Data MCU-Ereignis (Ereigniskennung 41032) angezeigt werden, das Office-webapps-Server-URLs zurückgibt. Beispielsweise sollten Sie etwas Ähnliches sehen:

**Die Office-webapps-Server Ermittlung für den Webkonferenzserver ist erfolgreich.**

**Interne Office-webapps-Server-Referenten Seite:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office-webapps-Server-interne Teilnehmerseite:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Externe Referenten Seite von Office-webapps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office-webapps-Server-interne Teilnehmerseite:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Wenn ein ls Data MCU-Ereignis mit der Ereignis-ID 41033 angezeigt wird, bedeutet dies, dass die Ermittlung von Office-webapps-Servern fehlgeschlagen ist. In diesem Fall versucht Microsoft lync Server 2013 so oft wie erforderlich, den neu konfigurierten Office-webapps-Server zu ermitteln. Wenn der Ermittlungsprozess wiederholt fehlschlägt, sollten Sie Office-webappsserver aus Ihrem Topologie-Dokument entfernen, die aktualisierte Topologie veröffentlichen und dann Office-webapps-Server wieder der Topologie hinzufügen, nachdem die Verbindungsprobleme behoben wurden.

Wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist und durch den Ermittlungsprozess erkannt wurde, können Sie sicherstellen, dass Office-webapps Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem Paar Microsoft lync 2013 Clients freigeben. Wenn Benutzer a die PowerPoint-Präsentation laden und anzeigen kann und wenn Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert Office-webapps-Server.

Selbst wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist, könnten Sie möglicherweise die Fehlermeldung "einige Freigabefunktionen sind aufgrund von Server Verbindungsproblemen nicht verfügbar" erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben. Wenn Sie diese Fehlermeldung erhalten, sollten Sie den Front-End-Server (oder Server) neu starten, der dem neuen Office-webapps-Server zugeordnet ist.

</div>

<span> </span>

</div>

</div>

</div>

