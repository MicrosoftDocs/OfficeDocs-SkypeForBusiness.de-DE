---
title: 'Lync Server 2013: Verwenden von Anrufen bei mit einem lync-fähigen Telefon'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Verwenden von "rufen Sie mich an" mit einem lync-fähigen Telefon und lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-08-09_

Das Feature "mich anrufen" in lync bietet Benutzern eine Möglichkeit, mit einem Mobiltelefon, "Festnetz" oder einem anderen Gerät, das mit dem öffentlichen Telefonnetz (PSTN) verbunden ist, dem Audioteil einer Konferenz beizutreten. Wenn Sie versuchen, mithilfe von lync an einer Besprechung teilzunehmen, wird normalerweise das Dialogfeld **an Besprechungs-Audio teilnehmen** angezeigt:

![Verwenden von lync zum teilnehmen an der Besprechung] des Audiofensters (images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Verwenden von lync zum teilnehmen an der Besprechung") des Audiofensters

Wenn Sie **mich anrufen**, können Sie eine Telefonnummer aus der Dropdown-Liste auswählen. Lync Server 2013 führt einen Telefonanruf an die ausgewählte Nummer, und Sie können dann das Telefon verwenden, um am Audioteil der Konferenz teilzunehmen.

Die Dropdownliste wird mit den Telefonnummern (für Mobiltelefone, privat Telefone oder andere Telefone) gefüllt, die Sie im Dialogfeld **lync – Optionen** auf der Registerkarte **Telefone** eingegeben haben:

![Screenshot der Option "lync-Telefone einrichten] " (images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Screenshot der Option \"lync-Telefone einrichten") "

Wenn Sie keine Telefonnummern auf dem Reiter " **Telefone** " eingegeben haben, stehen Ihnen im Dropdown-Feld keine Nummern zur Verfügung. Sie können jedoch jederzeit auf **neue Rufnummer** klicken und lync Server an eine beliebige Telefonnummer anwählen, die Sie wünschen:

![Screenshot des lync-Dialogfensters "an Besprechung teilnehmen"] (images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Screenshot des lync-Dialogfensters \"an Besprechung teilnehmen\"")

Das Feature "mich anrufen" funktioniert hervorragend, vorausgesetzt, dass Sie es in der beabsichtigten Weise verwenden: Wenn lync Server eine PSTN-Telefonnummer anruft. Sie können jedoch eine weniger optimale Nutzung erreichen, wenn Sie von lync Server aufgefordert werden, Sie an einem lync-fähigen Endpunkt anzurufen (beispielsweise ein Telefon in einem Konferenzraum). Im folgenden finden Sie das Problem, auf das Sie möglicherweise stoßen, und zwei Möglichkeiten, um das Problem zu umgehen.

Um zu beginnen, gehen Sie wie folgt vor, wenn Sie das Feature "anrufen unter" mit der Telefonnummer eines lync-fähigen Telefons angeben. Angenommen, Ken Myers versucht, an einer Besprechung teilzunehmen, indem lync Server ihn bei 1-206-555-1219, einer lync Server-fähigen Telefonnummer, anruft. Ken wird zunächst mit der Besprechung verbunden sein, aber nach ein paar Sekunden zeigt lync an, dass der Nachrichten **Anruf nicht abgeschlossen oder beendet**wurde, und Ken wird anscheinend aus der Besprechung gestrichen:

Screenshot ![des lync-Anruf Konferenz Fensters] Screenshot (images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "des lync-Anruf Konferenz Fensters")

Beachten Sie jedoch, dass es im lync-Unterhaltungsfenster eine Diskrepanz gibt. Ken Myers ist der einzige Name, der unter der Überschrift " **Teilnehmer** " aufgeführt ist. Wenn Sie jedoch in der Titelleiste des Fensters Suchen, sehen Sie, dass die Konferenz insgesamt 4 Teilnehmer enthält.

Auch wenn Sie im Unterhaltungsfenster eines anderen Konferenzteilnehmers suchen, wird Ken Myers nirgendwo aufgeführt:

![Screenshot des Fensters "lync-Teilnehmerliste"] (images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Screenshot des Fensters \"lync-Teilnehmerliste\"")

Gleichzeitig kann Ken Myers aber auch über sein lync-fähiges Telefon am Audioteil des Anrufs teilnehmen. Das Feature "mich anrufen" hat tatsächlich funktioniert, aber die Benutzeroberfläche ist weniger als optimal.

Es gibt mindestens zwei Möglichkeiten, dieses Problem zu umgehen. Wenn Sie bereits an einer Konferenz teilgenommen haben (wie Ken Myers), können Sie das Problem in der Regel beheben, indem Sie sich an einer anderen Modalität beteiligen. Wenn Sie beispielsweise eine Chatnachricht senden, werden im Unterhaltungsfenster nun alle Konferenzteilnehmer angezeigt, einschließlich ihrer selbst:

![Screenshot der lync-Unterhaltung und Teilnehmerliste] (images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Screenshot der lync-Unterhaltung und Teilnehmerliste")

An diesem Punkt sollten Sie in der Lage sein, an der Besprechung in der erwarteten Weise teilzunehmen.

Sie können dieses Problem aber auch ganz vermeiden, indem Sie die Art und Weise ändern, wie Sie an der Besprechung teilnehmen. Wenn lync Server ein lync Server-fähiges Telefon anrufen soll, sollten Sie mit der Teilnahme an der Besprechung ohne eine Audioverbindung beginnen. Wählen Sie dazu im Dialogfeld "an Besprechung teilnehmen" die Option "nicht an Audio teilnehmen" aus:

![Screenshot von lync an der Besprechung des Audiofensters nicht teilnehmen] (images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Screenshot von lync an der Besprechung des Audiofensters nicht teilnehmen")

Nachdem Sie erfolgreich eine Verbindung mit der Besprechung hergestellt haben, können Sie nun das lync Server-fähige Telefon "einladen", auch an der Besprechung teilzunehmen. Setzen Sie dazu den Mauszeiger auf das Symbol Personen, und klicken Sie dann auf **weitere Personen einladen**:

![Screenshot des Fensters "Weitere Teilnehmer einladen"] (images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Screenshot des Fensters \"Weitere Teilnehmer einladen\"")

Dadurch wird das Dialogfeld **Chat senden** eingeblendet. Ignorieren Sie den Titel des Dialogfelds (Sie senden keine Sofortnachricht), und geben Sie die Telefonnummer des lync-fähigen Telefons ein:

![Screenshot des Dialogfelds "Chatnachricht senden] " (images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Screenshot des Dialogfelds \"Chatnachricht senden") "

Nachdem Sie auf **OK**geklickt haben, ruft lync Server die im Dialogfeld eingegebene Nummer ab. Wenn die Verbindung hergestellt wurde, verfügen Sie über das lync-fähige Telefon über vollständige Audiofunktionen, und Sie können die vollständige Konferenzliste anzeigen und mit ihnen interagieren.

</div>

<span> </span>

</div>

</div>

</div>

