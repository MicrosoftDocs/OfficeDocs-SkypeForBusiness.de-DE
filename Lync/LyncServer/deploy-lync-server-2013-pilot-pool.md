---
title: Bereitstellen lync Server 2013 Pilot-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb620a4846b05c7f81ecea4d5cc525c9c16c0c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Bereitstellen lync Server 2013 Pilot-Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-22_

Einer der ersten Schritte, die für die Migration zu lync Server 2013 erforderlich sind, ist die Bereitstellungeines pilotpools. Der Pilot Pool testet die Koexistenz von lync Server 2013 mit ihrer lync Server 2010-Bereitstellung. Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in lync Server 2013 verschoben haben.

Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten dieselben Funktionen und Arbeitslasten in Ihrem lync Server 2013 Pilot-Pool bereitstellen, die Sie in Ihrem lync Server 2010-Pool haben. Wenn Sie Archivierungsserver, Monitoring Server oder System Center Operations Manager zur Archivierung oder Überwachung ihrer lync Server 2010 Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie diese ebenfalls bereitstellen. Funktionen in ihrer Pilotumgebung. Die Version, die Sie zum Archivieren oder Überwachen Ihrer lync Server 2010 Umgebung bereitgestellt haben, erfasst keine Daten in ihrer lync Server 2013 Umgebung.

<div>


> [!NOTE]  
> In den nachfolgenden Verfahren werden Features und Einstellungen behandelt, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für Pilotpools berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Anweisungen finden Sie im Bereitstellungshandbuch zur <A href="lync-server-2013-deploying-lync-server.md">Bereitstellung lync Server 2013</A> .



</div>

**So stellen Sie einen lync Server 2013-Pilot Pool bereit**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Erweitern Sie die Struktur so lange, bis Sie **lync Server 2013** **Enterprise Edition-Front-End-Pools**erreichen.

3.  Klicken Sie mit der rechten Maustaste auf **Enterprise Edition-Front-End-Pools**, und wählen Sie **Neues Front-End**
    
    ![Untermenü "Topologie-Generator-Server Pool Auswahl"](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Untermenü "Topologie-Generator-Server Pool Auswahl"")

4.  Geben Sie den Pool-FQDN ein. Wenn Sie Ihren Pilot Pool definieren, können Sie eine Enterprise Edition-Front-End-Pool oder ein Standard Edition-Server bereitstellen. Lync Server 2013 erfordert nicht, dass Ihre Pilot-Pool-Features mit dem übereinstimmen, was in Ihrem Legacy-Pool bereitgestellt wurde.
    
    <div>
    

    > [!WARNING]  
    > Der vollqualifizierte Domänenname (FQDN) des Pools oder Servers, den Sie für den Pilotpool festlegen, muss eindeutig sein. Er kann nicht mit dem Namen des derzeit bereitgestellten lync Server 2010 Pools oder anderen derzeit bereitgestellten Servern übereinstimmen.

    
    </div>
    
    ![Seite "FQDN des Front-End-Pools definieren"](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Seite "FQDN des Front-End-Pools definieren"")

5.  Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool werden sollen. Wenn Sie beispielsweise nur Chatnachrichten und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehr Parteien-Chat zu ermöglichen, aber nicht die Kontrollkästchen Einwahl (PSTN) Conferencing, Enterprise-VoIP oder Anrufsteuerung aktivieren, Da Sie sprach-, Video-und kollaborative Konferenzfunktionen darstellen. Weitere Informationen zum Auswählen von Features finden Sie unter [define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.
    
    ![Front-End-Pool Features auswählen (Seite)](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool Features auswählen (Seite)")

6.  Auf der Seite **"verbundene Serverrollen auswählen** " wird empfohlen, die Vermittlungsserver in lync Server 2013 collocate. Wenn Sie eine Legacy Topologie mit lync Server 2013 zusammenführen, müssen Sie zuerst die lync Server 2010 Vermittlungsserver collocate. Nachdem Sie die Topologien zusammengeführt und die lync Server 2013 Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie die verbundenen Vermittlungsserver beibehalten oder Sie in einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später in der Bereitstellung zu lync Server 2013 wechseln. Prozess.
    
    ![Front-End-Pool auswählen der Seite "verbundene Serverrollen"](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool auswählen der Seite "verbundene Serverrollen"")

7.  Wählen Sie auf der Seite **Serverrollen diesem Front-End-Pool zuordnen** während einer Pilotpoolbereitstellung nicht die Option **Edgepool zur Verwendung durch die Medienkomponente dieses Front-End-Pools auswählen** aus. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert.
    
    ![Zuordnen von Serverrollen zu Front-End-Pool Seite](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Zuordnen von Serverrollen zu Front-End-Pool Seite")

8.  Klicken Sie auf der Seite **Einen Office Web Apps-Server auswählen** auf **Neu**, und geben Sie den FQDN des Anwendungsservers an.
    
    ![Definieren neuer Eigenschaften des Office-webapps-Server-FQDN](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren neuer Eigenschaften des Office-webapps-Server-FQDN")

9.  Wählen Sie auf der Seite **Archivierungs SQL Server Speicher definieren** beim Definieren des SQL Server Speichers sowohl für lync Server Archivierung als auch für die Überwachung die zuvor für lync Server 2013 erstellte SQL Server Instanz aus.
    
    ![Seite "Archivierung SQL Server Speicher definieren"](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Seite "Archivierung SQL Server Speicher definieren"")

10. Klicken Sie zum Veröffentlichen der Topologie mit der rechten Maustaste auf den Knoten **lync Server** , und klicken Sie dann auf **Topologie veröffentlichen**.
    
    ![Topologie-Generator, der eine konfigurierte Topologie anzeigt](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topologie-Generator, der eine konfigurierte Topologie anzeigt")

11. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

Informationen zum Installieren einer lokalen Kopie des Konfigurationsspeichers und zum Starten der erforderlichen Dienste finden Sie unter [Einrichten von Front-End-Servern und Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.


</div>

<span> </span>

</div>

</div>

</div>

