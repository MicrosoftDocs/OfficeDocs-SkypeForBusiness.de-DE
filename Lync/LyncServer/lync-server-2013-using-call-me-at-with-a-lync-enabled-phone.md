---
title: Verwenden von "Rückruf unter" mit einem für Lync aktivierten Telefon und Lync Server 2013
TOCTitle: Verwenden von "Rückruf unter" mit einem für Lync aktivierten Telefon und Lync Server 2013
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56558906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von \"Rückruf unter\" mit einem für Lync aktivierten Telefon und Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-08-09_

Das Feature **Rückruf unter** von Lync bietet den Benutzern eine Möglichkeit, mit einem Mobiltelefon, einem Festnetztelefon oder einem anderen Gerät, das mit der PSTN (öffentlichen Telefonnetz) verbunden ist, am Audioteil einer Konferenz teilzunehmen. Wenn Sie versuchen, mit Lync an eine Besprechung teilzunehmen, wird normalerweise das Dialogfeld **An Besprechungsaudio teilnehmen** angezeigt:

![Verwenden des Lync-Fensters zum Teilnehmen an Besprechungsaudio (Screenshot)](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Verwenden des Lync-Fensters zum Teilnehmen an Besprechungsaudio (Screenshot)")

Wenn Sie **Rückruf unter** auswählen, können Sie in der Dropdownliste eine Telefonnummer auswählen. Lync Server 2013 ruft dann die von Ihnen angegebene Nummer an, und Sie können dann mit diesem Telefon am Audioteil der Konferenz teilnehmen.

In der Dropdownliste befinden sich die Telefonnummern (Mobiltelefon, privat oder eine andere Telefonnummer), die Sie auf der Registerkarte **Telefone** im Lync-Dialogfeld **Optionen** eingegeben haben:

![Lync-Optionen zum Einrichten von Telefonen (Screenshot)](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync-Optionen zum Einrichten von Telefonen (Screenshot)")

Wenn Sie auf der Registerkarte **Telefone** keine Telefonnummern eingegeben haben, stehen auch in der Dropdownliste keine Telefonnummern zur Verfügung. Sie können jedoch immer auf **Neue Nummer** klicken, damit Lync Server die von Ihnen gewünschte Rufnummer anwählt:

![Lync-Fenster für Teilnahme an Besprechungsaudio mit Rückruf (Screenshot)](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync-Fenster für Teilnahme an Besprechungsaudio mit Rückruf (Screenshot)")

Die Funktion **Rückruf unter** funktioniert außerordentlich gut, vorausgesetzt, Sie verwenden sie in der vorgesehenen Weise, d. h., sie veranlassen Lync Server, eine Nummer im öffentlichen Telefonnetz anzurufen. Die Erfahrung ist nicht ganz so optimal, wenn Sie Lync Server veranlassen, Sie auf einem für Lync aktivierten Endpunkt (z. B. ein Telefon in einem Konferenzraum) anzurufen. Im Folgenden wird das möglicherweise auftretende Problem beschrieben, und es werden zwei Wege genannt, wie Sie das Problem umgehen können.

Zunächst einmal das Szenario, das sich ergibt, wenn die Funktion **Rückruf unter** in Verbindung mit einem für Lync aktivierten Telefon verwendet wird: Einmal angenommen, Ken Myer versucht, an einer Besprechung teilzunehmen, indem er Lync Server veranlasst, ihn unter der Nummer 1-206-555-1219 zurückzurufen, die zu einem für Lync Server aktivierten Telefon gehört. Anfangs wird Ken mit der Besprechung verbunden, nach einige Sekunden zeigt Lync jedoch die Meldung **Der Anruf kann nicht durchgeführt werden oder wurde beendet** an, und für Ken sieht es so aus, als sei er aus der Besprechung entfernt worden:

![Screenshot von Lync-Anrufkonferenzfenster](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screenshot von Lync-Anrufkonferenzfenster")

Beachten Sie jedoch, dass es im Lync-Unterhaltungsfenster eine Unstimmigkeit gibt. "Ken Myer" ist der einzige Name, der unter der Überschrift **Teilnehmer** aufgeführt wird, wenn Sie sich jedoch die Titelleiste des Fensters anschauen, sehen Sie, dass an der Konferenz insgesamt vier Personen teilnehmen.

Und auch wenn Sie sich die Unterhaltungsfenster der anderen Konferenzteilnehmer anschauen würden, würden Sie feststellen, dass Ken Myer nirgendwo aufgeführt wird:

![Lync-Fenster mit Teilnehmerliste (Screenshot)](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync-Fenster mit Teilnehmerliste (Screenshot)")

Dennoch ist Ken Myer in der Lage, mit seinem für Lync aktivierten Telefon am Audioteil der Konferenz teilzunehmen. Die Option **Rückruf unter** hat zwar funktioniert, die Benutzererfahrung ist jedoch suboptimal.

Es gibt mindestens zwei Möglichkeiten, um dieses Problem zu umgehen. Wenn Sie bereits auf diese Weise einer Konferenz beigetreten sind (wie Ken Myer), können Sie das Problem normalerweise beheben, indem Sie eine andere Vorgehensweise wählen. Wenn Sie beispielsweise eine Chatnachricht senden, werden im Unterhaltungsfenster nun alle Konferenzteilnehmer einschließlich Ihrer Person angezeigt:

![Lync-Unterhaltung und Teilnehmerliste (Screenshot)](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync-Unterhaltung und Teilnehmerliste (Screenshot)")

Von nun an sollten Sie in der Lage sein, in der erwarteten Weise an der Besprechung teilzunehmen.

Alternativ können Sie dieses Problem vermeiden, indem Sie die Art und Weise ändern, in der Sie an der Besprechung teilnehmen. Wenn Sie Lync Server nicht veranlassen müssen, ein für Lync Server aktiviertes Telefon anzurufen, sollten Sie damit beginnen, der Besprechung ohne Audioverbindung beizutreten. Aktivieren Sie hierfür die Option **Keine Audioteilnahme**, wenn das Dialogfeld **An Besprechungsaudio teilnehmen** angezeigt wird:

![Lync-Fenster für Nichtteilnahme an Besprechungsaudio (Screenshot)](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync-Fenster für Nichtteilnahme an Besprechungsaudio (Screenshot)")

Nachdem Sie die Verbindung zur Besprechung erfolgreich hergestellt haben, können Sie nun das für Lync Server aktivierte Telefon "einladen", ebenfalls an der Besprechung teilzunehmen. Zeigen Sie hierzu mit der Maus auf das Symbol **Personen**, und klicken Sie dann auf **Weitere Personen einladen**:

![Lync-Fenster zum Einladen weiterer Teilnehmer (Screenshot)](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync-Fenster zum Einladen weiterer Teilnehmer (Screenshot)")

Damit wird das Dialogfeld **Chatnachricht senden** angezeigt. Ignorieren Sie den Titel des Dialogfelds (Sie senden eigentlich keine Chatnachricht), und geben Sie die Telefonnummer des für Lync aktivierten Telefons ein:

![Dialogfeld zum Senden einer Chatnachricht (Screenshot)](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Dialogfeld zum Senden einer Chatnachricht (Screenshot)")

Nachdem Sie auf **OK** geklickt haben, ruft Lync Server die im Dialogfeld eingegebene Nummer an. Nachdem die Verbindung hergestellt wurde, verfügen Sie auf dem für Lync aktivierten Telefon über sämtliche Audiofunktionen, und Sie können die Liste der Konferenzteilnehmer sehen und damit interagieren.

