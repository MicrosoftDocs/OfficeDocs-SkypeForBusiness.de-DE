---
title: Bereitstellen des lync Server 2013-pilotpools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e9068ca3ff5a2827991869598a2066473cc5af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Bereitstellen des lync Server 2013-pilotpools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-22_

Einer der ersten Schritte, die für die Migration zu lync Server 2013 erforderlich sind, ist die Bereitstellungeines pilotpools. Im Pilot Pool wird die Koexistenz von lync Server 2013 mit Ihrer Office Communications Server 2007 R2-Bereitstellung getestet. Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in lync Server 2013 verschoben haben.

Wenn Sie einen Pilot Pool bereitstellen, verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten dieselben Features und Arbeitsauslastungen in Ihrem lync Server 2013-Pilot Pool bereitstellen, die Sie in Ihrem Office Communications Server 2007 R2-Pool haben. Wenn Sie den Archivierungsserver, den Monitoring Server oder den System Center Operations Manager zum Archivieren oder Überwachen Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie Stellen Sie diese Features auch in ihrer Pilotumgebung bereit. Mit der Version, die Sie zum Archivieren oder Überwachen Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben, werden keine Daten in ihrer lync Server 2013-Umgebung erfasst.

<div>


> [!NOTE]  
> Im folgenden Verfahren werden die Features und Einstellungen erörtert, die Sie im Rahmen des gesamten Bereitstellungsprozesses für pilotpools berücksichtigen sollten. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten. Detaillierte Anweisungen finden Sie im Bereitstellungshandbuch für die <A href="lync-server-2013-deploying-lync-server.md">Bereitstellung von lync Server 2013</A> .



</div>

**Bereitstellen eines lync Server 2013-pilotpools**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Öffnen Sie den Topologie-Generator, und wählen Sie aus, um eine neue Topologie zu erstellen.

3.  Geben Sie die primäre SIP-Domäne ein.
    
    ![Erstellen einer neuen Topologie, Seite "primäre Domäne definieren"] (images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Erstellen einer neuen Topologie, Seite \"primäre Domäne definieren\"")

4.  Fahren Sie mit dem Abschließen des Assistenten fort, bis Sie den Assistenten zum **Definieren des neuen Front-End-Pools** erreichen. Klicken Sie auf Weiter.

5.  Geben Sie den Pool-FQDN ein. Wenn Sie Ihren Pilot Pool definieren, können Sie auswählen, ob Sie einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server bereitstellen möchten. Für lync Server 2013 ist es nicht erforderlich, dass die Features Ihres pilotpools mit dem übereinstimmen, was in Ihrem Legacy Pool bereitgestellt wurde.
    
    <div>
    

    > [!WARNING]  
    > Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools oder Servers, den Sie für den Pilot Pool definieren, muss eindeutig sein. Sie kann nicht mit dem Namen des aktuell bereitgestellten Office Communications Server 2007 R2-Pools oder aller anderen Server übereinstimmen, die derzeit bereitgestellt werden.

    
    </div>
    
    ![Definieren der FQDN-Seite des Front-End-Pools] (images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definieren der FQDN-Seite des Front-End-Pools")

6.  Definieren Sie den Computer, der dem Pool hinzugefügt werden soll.
    
    ![Dialogfeld "neuen Front-End-Pool definieren"] (images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Dialogfeld \"neuen Front-End-Pool definieren\"")

7.  Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen. Wenn Sie beispielsweise nur Chat-und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehrteilige Chats zu ermöglichen, aber nicht die Kontrollkästchen Einwahl (PSTN) Conferencing, Enterprise Voice oder Anrufsteuerung aktivieren, Da es sich um sprach-, Video-und kollaborative Konferenzfeatures handelt. Weitere Informationen zum Auswählen von Features finden Sie unter [definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.
    
    ![Front-End-Pool auswählen der Seite "Features] " (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool auswählen der Seite \"Features") "

8.  Auf der Seite **"ausgewählte Serverrollen auswählen** " empfehlen wir, den Vermittlungsserver in lync Server 2013 collocate. Wenn Sie eine Legacy Topologie mit lync Server 2013 zusammenführen, müssen Sie zuerst den Office Communications Server 2007 R2-Vermittlungsserver collocate. Nachdem Sie die Topologien zusammengeführt und den lync Server 2013-Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie den beiliegenden Vermittlungsserver beibehalten oder auf einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später in der Bereitstellung nach lync Server 2013 verschieben. Prozess.
    
    ![Front-End-Pool wählen Sie die Seite mit den Serverrollen] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool wählen Sie die Seite mit den Serverrollen")

9.  Wählen Sie auf der Seite **Associate Server Roles with this Front End Pool** während der Bereitstellung des pilotpools nicht die Option **einen Edge-Pool aktivieren, der von der medienkomponente dieser Front-End-Pool Option verwendet werden soll** . Dies ist ein Feature, das Sie in einer späteren Migrationsphase aktivieren und online schalten können. Lassen Sie diese Einstellung für jetzt deaktiviert.
    
    ![Verknüpfen von Serverrollen mit der Seite "Front-End-Pool"] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Verknüpfen von Serverrollen mit der Seite \"Front-End-Pool\"")

10. Klicken Sie auf der Seite **Office Web Apps-Server auswählen** auf **neu**, und geben Sie den FQDN des Anwendungsservers an.
    
    ![Definieren von neuen Office Web Apps Server-FQDN-Eigenschaften] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren von neuen Office Web Apps Server-FQDN-Eigenschaften")

11. Wählen Sie auf der Seite **Archivierungs-SQL Server-Speicher definieren** die SQL Server-Instanz aus, die zuvor für lync Server 2013 erstellt wurde.
    
    ![Seite "Archivierungs-SQL Server-Store definieren"] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Seite \"Archivierungs-SQL Server-Store definieren\"")

12. Wählen Sie auf der Seite **SQL Server-Überwachungsspeicher definieren** die SQL Server-Instanz aus, die zuvor für lync Server 2013 erstellt wurde. Klicken Sie auf **Fertig stellen**.

13. Klicken Sie im obersten Knoten des Topologie-Generators mit der rechten Maustaste auf **lync Server** , und klicken Sie auf **Eigenschaften bearbeiten.** Klicken Sie auf **einfache URLs**.

14. Aktualisieren Sie die **Administratorzugriffs-URL**.
    
    ![Bearbeiten von Eigenschaften, Seite "einfache URLs"] (images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Bearbeiten von Eigenschaften, Seite \"einfache URLs\"")
    
    Weitere Informationen zu einfachen URLs finden Sie im Thema [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.

15. Klicken Sie in den **Eigenschaften bearbeiten**auf **zentraler Verwaltungs Server**.

16. Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.
    
    ![Eigenschaften bearbeiten, Seite "zentraler Verwaltungs Server"] (images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Eigenschaften bearbeiten, Seite \"zentraler Verwaltungs Server\"")

17. Klicken Sie auf OK, um **die Seite Eigenschaften bearbeiten** zu schließen.

18. Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus.

19. Wenn der Veröffentlichungsprozess abgeschlossen ist, klicken Sie auf **Fertig stellen**.

20. Wenn Sie zum lync Server 2013-Bereitstellungs-Assistenten zurückkehren, klicken Sie auf **lync Server System installieren oder aktualisieren**.
    
    ![Bereitstellungs-Assistent für lync Server 2013] (images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Bereitstellungs-Assistent für lync Server 2013")

Wenn Sie eine lokale Kopie des Konfigurationsspeichers installieren und die erforderlichen Dienste starten möchten, lesen Sie [Einrichten der Front-End-Server und der Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.


</div>

<span> </span>

</div>

</div>

</div>

