---
title: Konfigurieren einer QoS-Richtlinie für A/V-Edgeserver
TOCTitle: Konfigurieren einer QoS-Richtlinie für A/V-Edgeserver
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204681(v=OCS.15)
ms:contentKeyID: 49293222
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer QoS-Richtlinie für A/V-Edgeserver

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Neben den QoS-Richtlinien für Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen Sie auch Audio- und Videorichtlinien für die interne Seite Ihrer A/V-Edgeserver erstellen. Die auf Ihren Edgeservern verwendeten Richtlinien unterscheiden sich jedoch von den auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern verwendeten Richtlinien. Für die Konferenz-, Anwendungs- und Vermittlungsserver haben Sie einen Quellportbereich angegeben; bei Edgeservern müssen Sie einen Zielportbereich angeben. Daher können Sie die QoS-Richtlinien für Konferenz-, Anwendungs- und Vermittlungsserver nicht auf Ihre Edgeserver anwenden, diese Richtlinien funktionieren dort nicht. Stattdessen müssen Sie neue Richtlinien erstellen und diese ausschließlich auf Ihre Edgeserver anwenden.

Das folgende Verfahren beschreibt die Vorgehensweise beim Erstellen von Active Directory-Gruppenrichtlinienobjekten, die zum Verwalten der der Dienstqualität (Quality of Service, QoS) auf Edgeservern verwendet werden kann. Möglicherweise handelt es sich bei Ihren Edgeservern um Einzelserver ohne Active Directory-Konten. In diesem Fall können Sie die lokale Gruppenrichtlinie statt der Active Directory-Gruppenrichtlinie verwenden, mit dem Unterschied, dass Sie diese lokalen Richtlinien mit dem Editor für lokale Gruppenrichtlinien erstellen und auf jedem Edgeserver denselben Richtliniensatz einzeln erstellen müssen. Gehen Sie wie folgt vor, um auf einem Edgeserver den Editor für lokale Gruppenrichtlinien zu starten:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **gpedit.msc** ein, und drücken Sie die EINGABETASTE.

Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten Sie sich an einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert ist (klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, klicken Sie auf **Gruppenrichtlinienverwaltung**), und führen Sie dann folgende Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Beispiel: Wenn sich all Ihre Lync Server-Computer in einer Organisationseinheit mit dem Namen "Lync Server" befinden, sollte die neue Richtlinie in der Organisationseinheit "Lync Server" erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen**.

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (z. B. **Lync Server Audio**), und klicken Sie anschließend auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

Ab diesem Schritt sind die Vorgehensweisen beim Erstellen einer Active Directory-Richtlinie und einer lokalen Richtlinie identisch:

1.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor oder im Editor für lokale Gruppenrichtlinien **Computerkonfiguration**, **Richtlinien** und **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

2.  Geben Sie im Dialogfeld **Richtlinienbasierter QoS** auf der ersten Seite im Feld **Name** einen Namen für die neue Richtlinie ein (z. B. **Lync Server Audio**). Klicken Sie auf **DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

3.  Vergewissern Sie sich auf der nächsten Seite, dass **Anwendungstyp** aktiviert ist, und klicken Sie dann auf **Weiter**. Durch diese Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit der DSCP-Markierung 46 zu suchen, anstatt nur nach von einer bestimmten Anwendung erstellten Paketen.

4.  Vergewissern Sie sich auf der dritten Seite, dass **Beliebige Quell-IP-Adresse** und **Beliebige Ziel-IP-Adresse** aktiviert sind, und klicken Sie dann auf **Weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

5.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden von Lync Server und den dazugehörigen Clientanwendungen am häufigsten verwendeten Netzwerkprotokolle.

6.  Wählen Sie unter der Überschrift **Geben Sie die Zielportnummer an** die Option **An diese Zielportnummer bzw. diesen -bereich**. Geben Sie im dazugehörigen Textfeld den für Audioübertragungen reservierten Portbereich ein. Wenn Sie z. B. die Ports 49152 bis 57500 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audiodatenverkehr erstellt haben, sollten Sie eine zweite Richtlinie für Videodatenverkehr erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Video**).

  - Legen Sie den DSCP-Wert auf **34** statt "46" fest. (Sie müssen nicht unbedingt den DSCP-Wert 34 verwenden, der DSCP-Wert für Video muss sich lediglich von dem für Audio verwendeten Wert unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie z. B. die Ports 57501 bis 65535 für Video reserviert haben, legen Sie den Portbereich folgendermaßen fest: **57501:65535**. Auch dies sollte als Zielportbereich konfiguriert werden.

Wenn Sie eine Richtlinie für das Verwalten des Datenverkehrs bei der Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie mit folgenden Änderungen erstellen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert auf **24** statt "46" fest. (Auch hier muss nicht unbedingt der DSCP-Wert 24 verwendet werden, der DSCP-Wert für Video muss sich lediglich von den für Audio und Video verwendeten Werten unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie z. B. die Ports 40803 bis 49151 für Anwendungsfreigabe reserviert haben, legen Sie den Portbereich folgendermaßen fest: **40803:49151**.

Die neu erstellten Richtlinien werden erst wirksam, wenn auf Ihren Edgeservern die Gruppenrichtlinien aktualisiert wurden. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

    Gpudate.exe /force

Dieser Befehl kann in Lync Server oder in einem beliebigen Befehlsfenster eingegeben werden, das unter der Angabe von Administratoranmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Möglicherweise müssen Sie den Edgeserver auch nach der Ausführung von "Gpudate.exe" neu starten.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **Services** und schließlich **Tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein und drücken dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie dann Ihren Computer neu.

