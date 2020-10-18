---
title: 'Lync Server 2013: Verwenden von "anrufen unter" mit einem lync-fähigen Telefon'
description: 'Lync Server 2013: Verwenden von "anrufen unter" mit einem lync-fähigen Telefon.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd7855e45132b133c78230e7f8769bdab897140
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580421"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Verwenden von "anrufen unter" mit einem lync-fähigen Telefon und lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-08-09_

Das Feature "rufen Sie mich unter" in lync bietet Benutzern die Möglichkeit, dem Audioteil einer Konferenz mithilfe eines Mobiltelefons, einer "Festnetz-Verbindung" oder eines anderen Geräts, das mit dem öffentlichen Telefon Festnetz (PSTN) verbunden ist, beizutreten. Wenn Sie versuchen, mit lync an einer Besprechung teilzunehmen, wird Ihnen normalerweise das Dialogfeld **Besprechungs-Audio beitreten** angezeigt:

![Screenshot des Besprechungs-Audiofensters mithilfe von lync](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Screenshot des Besprechungs-Audiofensters mithilfe von lync")

Wenn Sie **anrufen unter**wählen, können Sie eine Telefonnummer aus der Dropdownliste auswählen. Lync Server 2013 einen Anruf an die ausgewählte Rufnummer weiter, und Sie können dann das Telefon verwenden, um am Audioteil der Konferenz teilzunehmen.

Die Dropdownliste wird von den Telefonnummern (für Mobiltelefone, privat Telefone oder andere Telefone) aufgefüllt, die Sie auf der Registerkarte **Telefone** im Dialogfeld **lync – Optionen** eingegeben haben:

![Screenshot von lync Phones-Setupoptionen](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Screenshot von lync Phones-Setupoptionen")

Wenn Sie auf der Registerkarte **Telefone** keine Telefonnummern eingegeben haben, stehen Ihnen im Dropdownfeld keine Nummern zur Verfügung. Sie können jedoch jederzeit auf **neue Nummer** klicken und lync Server eine beliebige Telefonnummer wählen, die Sie wünschen:

![Windows-Screenshot für lync Join Meeting-Audioanrufe](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Windows-Screenshot für lync Join Meeting-Audioanrufe")

Das Feature "rufen Sie mich an" funktioniert äußerst gut, vorausgesetzt, Sie verwenden es so, wie es beabsichtigt war: indem Sie lync Server eine PSTN-Telefonnummer anrufen. Sie können jedoch eine weniger als optimale Umgebung ausführen, wenn Sie lync Server bitten, an einem lync-fähigen Endpunkt anzurufen (beispielsweise ein Telefon in einem Konferenzraum). Im folgenden finden Sie das Problem, das Sie möglicherweise ausführen können, sowie zwei Möglichkeiten, um das Problem zu umgehen.

Um zu beginnen, gehen Sie wie folgt vor, wenn Sie das Feature "anrufen unter" mit der Telefonnummer eines lync-fähigen Telefons bereitstellen. Angenommen, Ken Myers versucht, an einer Besprechung teilzunehmen, indem er lync Server ihn unter 1-206-555-1219 anrufen kann, eine lync Server fähige Telefonnummer. Ken wird anfänglich mit der Besprechung verbunden sein, aber nach ein paar Sekunden zeigt lync an, dass der Nachrichten **Aufruf nicht abgeschlossen oder beendet**wurde, und Ken wird anscheinend aus der Besprechung gelöscht.

![Screenshot des lync-Anruf Konferenz Fensters](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screenshot des lync-Anruf Konferenz Fensters")

Beachten Sie jedoch, dass im lync-Unterhaltungsfenster eine Diskrepanz vorliegt. Ken Myers ist der einzige Name, der unter der Überschrift **Teilnehmer** aufgeführt ist. Wenn Sie jedoch in der Titelleiste des Fensters Suchen, sehen Sie, dass die Konferenz insgesamt vier Teilnehmer enthält.

Wenn Sie im Unterhaltungsfenster eines anderen Konferenzteilnehmers suchen, wird Ken Myers auch nicht an beliebiger Stelle angezeigt:

![Screenshot des lync-Teilnehmerlisten Fensters](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Screenshot des lync-Teilnehmerlisten Fensters")

Dennoch kann Ken Myers gleichzeitig mit seinem lync-fähigen Telefon am Audioteil des Anrufs teilnehmen. Das Feature "Anruf bei Funktion" wurde tatsächlich verwendet, aber die Benutzeroberfläche ist weniger als optimal.

Es gibt mindestens zwei Möglichkeiten, um dieses Problem zu umgehen. Wenn Sie bereits einer Konferenz auf diese Weise beigetreten sind (wie Ken Myers), können Sie das Problem in der Regel beheben, indem Sie sich an einer anderen Modalität beteiligen. Wenn Sie beispielsweise eine Sofortnachricht senden, werden im Unterhaltungsfenster nun alle Konferenzteilnehmer einschließlich ihrer selbst angezeigt:

![Screenshot von lync-Unterhaltung und Teilnehmerliste](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Screenshot von lync-Unterhaltung und Teilnehmerliste")

An diesem Punkt sollten Sie in der Lage sein, an der Besprechung in der erwarteten Weise teilzunehmen.

Alternativ können Sie dieses Problem ganz vermeiden, indem Sie die Art und Weise ändern, wie Sie an der Besprechung teilnehmen. Wenn lync Server ein lync Server fähiges Telefon anrufen müssen, sollten Sie zunächst ohne Audioverbindung an der Besprechung teilnehmen. Wählen Sie dazu im Dialogfeld Besprechungs-Audio beitreten die Option Audiodaten nicht beitreten aus:

![Screenshot für lync nicht an Besprechungs-Audiofenster teilnehmen](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Screenshot für lync nicht an Besprechungs-Audiofenster teilnehmen")

Nachdem Sie erfolgreich eine Verbindung mit der Besprechung hergestellt haben, können Sie das lync Server fähige Telefon nun auch für die Teilnahme an der Besprechung einladen. Platzieren Sie dazu die Maus über dem Symbol Personen, und klicken Sie dann auf **weitere Personen einladen**:

![Screenshot von lync invite more participants Window](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Screenshot von lync invite more participants Window")

Dadurch wird das Dialogfeld **Sofortnachrichten senden** angezeigt. Ignorieren Sie den Titel des Dialogfelds (Sie senden keine Sofortnachricht tatsächlich), und geben Sie die Telefonnummer des lync-fähigen Telefons ein:

![Screenshot des Dialogfelds "Chat" senden](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Screenshot des Dialogfelds "Chat" senden")

Nachdem Sie auf **OK**geklickt haben, wird lync Server die im Dialogfeld eingegebene Nummer aufrufen. Wenn die Verbindung hergestellt wurde, haben Sie über das lync-fähige Telefon vollständige Audiofunktionen, und Sie können die vollständige Konferenzliste anzeigen und mit ihnen interagieren.

</div>

<span> </span>

</div>

</div>

</div>

