---
title: Bereitstellen lync Server 2013 Pilot-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c97ea5304309aaf635ac284e792a73634c5ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Bereitstellen lync Server 2013 Pilot-Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-22_

Einer der ersten Schritte, die für die Migration zu lync Server 2013 erforderlich sind, ist die Bereitstellungeines pilotpools. Der Pilot Pool testet die Koexistenz von lync Server 2013 mit Ihrer Office Communications Server 2007 R2-Bereitstellung. Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in lync Server 2013 verschoben haben.

Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten dieselben Funktionen und Arbeitslasten in Ihrem lync Server 2013 Pilot-Pool bereitstellen, die Sie in Ihrem Office Communications Server 2007 R2-Pool haben. Wenn Sie Archivierungsserver, Monitoring Server oder System Center Operations Manager zur Archivierung oder Überwachung Ihrer Office Communications Server 2007 R2 Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie Stellen Sie diese Features auch in ihrer Pilotumgebung bereit. Die Version, die Sie zum Archivieren oder Überwachen Ihrer Office Communications Server 2007 R2 Umgebung bereitgestellt haben, erfasst keine Daten in ihrer lync Server 2013 Umgebung.

<div>


> [!NOTE]  
> In den nachfolgenden Verfahren werden Features und Einstellungen behandelt, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für Pilotpools berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Anweisungen finden Sie im Bereitstellungshandbuch zur <A href="lync-server-2013-deploying-lync-server.md">Bereitstellung lync Server 2013</A> .



</div>

**So stellen Sie einen lync Server 2013-Pilot Pool bereit**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Öffnen Sie den Topologie-Generator, und wählen Sie die Option zur Erstellung einer neuen Topologie aus.

3.  Geben Sie die primäre SIP-Domäne ein.
    
    ![Neue Topologie erstellen, primäre Domänen Seite definieren](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Neue Topologie erstellen, primäre Domänen Seite definieren")

4.  Fahren Sie mit der Fertigstellung des Assistenten fort, bis Sie zum Assistenten zum **Definieren eines neuen Front-End-Pools** gelangen. Klicken Sie auf "Weiter".

5.  Geben Sie den Pool-FQDN ein. Wenn Sie Ihren Pilot Pool definieren, können Sie eine Enterprise Edition-Front-End-Pool oder ein Standard Edition-Server bereitstellen. Lync Server 2013 erfordert nicht, dass Ihre Pilot-Pool-Features mit dem übereinstimmen, was in Ihrem Legacy-Pool bereitgestellt wurde.
    
    <div>
    

    > [!WARNING]  
    > Der vollqualifizierte Domänenname (FQDN) des Pools oder Servers, den Sie für den Pilotpool festlegen, muss eindeutig sein. Er kann nicht mit dem Namen des derzeit bereitgestellten Office Communications Server 2007 R2 Pools oder anderen derzeit bereitgestellten Servern übereinstimmen.

    
    </div>
    
    ![Definieren der Seite "Front-End-Pool FQDN"](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definieren der Seite "Front-End-Pool FQDN"")

6.  Legen Sie den Computer fest, der dem Pool hinzugefügt wird.
    
    ![Dialogfeld "neuen Front-End-Pool definieren"](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Dialogfeld "neuen Front-End-Pool definieren"")

7.  Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool werden sollen. Wenn Sie beispielsweise nur Chatnachrichten und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehr Parteien-Chat zu ermöglichen, aber nicht die Kontrollkästchen Einwahl (PSTN) Conferencing, Enterprise-VoIP oder Anrufsteuerung aktivieren, Da Sie sprach-, Video-und kollaborative Konferenzfunktionen darstellen. Weitere Informationen zum Auswählen von Features finden Sie unter [define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.
    
    ![Front-End-Pool Features auswählen (Seite)](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool Features auswählen (Seite)")

8.  Auf der Seite **"verbundene Serverrollen auswählen** " wird empfohlen, die Vermittlungsserver in lync Server 2013 collocate. Wenn Sie eine Legacy Topologie mit lync Server 2013 zusammenführen, müssen Sie zuerst die Office Communications Server 2007 R2 Vermittlungsserver collocate. Nachdem Sie die Topologien zusammengeführt und die lync Server 2013 Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie die verbundenen Vermittlungsserver beibehalten oder Sie in einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später in der Bereitstellung zu lync Server 2013 wechseln. Prozess.
    
    ![Front-End-Pool auswählen der Seite "verbundene Serverrollen"](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool auswählen der Seite "verbundene Serverrollen"")

9.  Wählen Sie auf der Seite **Serverrollen diesem Front-End-Pool zuordnen** während einer Pilotpoolbereitstellung nicht die Option **Edgepool zur Verwendung durch die Medienkomponente dieses Front-End-Pools auswählen** aus. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert.
    
    ![Zuordnen von Serverrollen zu Front-End-Pool Seite](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Zuordnen von Serverrollen zu Front-End-Pool Seite")

10. Klicken Sie auf der Seite **Einen Office Web Apps-Server auswählen** auf **Neu**, und geben Sie den FQDN des Anwendungsservers an.
    
    ![Definieren neuer Eigenschaften des Office-webapps-Server-FQDN](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren neuer Eigenschaften des Office-webapps-Server-FQDN")

11. Wählen Sie auf der Seite **Archivierungs SQL Server Speicher definieren** die SQL Server Instanz aus, die zuvor für lync Server 2013 erstellt wurde.
    
    ![Seite "Archivierung SQL Server Speicher definieren"](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Seite "Archivierung SQL Server Speicher definieren"")

12. Wählen Sie auf der Seite **Überwachung SQL Server Speicher definieren** die SQL Server Instanz aus, die zuvor für lync Server 2013 erstellt wurde. Klicken Sie auf **Fertig stellen**.

13. Klicken Sie im obersten Knoten des Topologie-Generators mit der rechten Maustaste auf **Lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten.** Klicken Sie auf **Einfache URLs**.

14. Aktualisieren Sie die **URL für administrativen Zugriff**.
    
    ![Bearbeiten von Eigenschaften, einfache URLs (Seite)](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Bearbeiten von Eigenschaften, einfache URLs (Seite)")
    
    Weitere Informationen zu einfachen URLs finden Sie im Thema [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.

15. Klicken Sie unter **Eigenschaften bearbeiten** auf **Zentraler Verwaltungsserver**.

16. Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.
    
    ![Bearbeiten von Eigenschaften, Seite des zentralen Verwaltungsservers](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Bearbeiten von Eigenschaften, Seite des zentralen Verwaltungsservers")

17. Klicken Sie auf "OK" um die Seite **Eigenschaften bearbeiten** zu schließen.

18. Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus.

19. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

20. Wenn Sie zum lync Server 2013-Bereitstellungs-Assistenten zurückkehren, klicken Sie auf **lync Server System installieren oder aktualisieren**.
    
    ![Lync Server 2013-Bereitstellungs-Assistent](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013-Bereitstellungs-Assistent")

Informationen zum Installieren einer lokalen Kopie des Konfigurationsspeichers und zum Starten der erforderlichen Dienste finden Sie unter [Einrichten von Front-End-Servern und Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.


</div>

<span> </span>

</div>

</div>

</div>

