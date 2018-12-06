---
title: 'Lync Server 2013: Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver'
TOCTitle: Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205076(v=OCS.15)
ms:contentKeyID: 49294678
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-06-23_

Das Konfigurieren von Portbereichen vereinfacht die Verwendung der Dienstqualität (Quality of Service), indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (z. B. der gesamte Audio-Datenverkehr) über dieselben Ports übermittelt wird. Dadurch ist es für das System einfacher, ein bestimmtes Paket zu identifizieren und zu markieren: Wenn der Port 49152 für den Audio-Datenverkehr reserviert ist, kann jedes beliebige Paket, das über den Port 49152 übermittelt wird, mit einem DSCP-Code markiert werden. Dieser Code gibt an, dass es sich dabei um ein Audiopaket handelt. Anschließend können diese Router das Paket als ein Audiopaket identifizieren und ihm eine höhere Priorität als unmarkierte Pakete verleihen (wie z. B. Pakete, die Dateien von einem Server zu einem anderen Server kopieren).

Die einfache Einschränkung von Ports auf eine bestimmte Art von Datenverkehr führt nicht dazu, dass die Pakete über die Ports, die mit dem entsprechenden DSCP-Code markiert sind, übermittelt werden. Zusätzlich zum Definieren der Portbereiche müssen auch Dienstqualitätsrichtlinien (Quality of Service Policies) erstellt werden, die den DSCP-Code angeben, der jedem Portbereich zugeordnet werden soll. Bei Microsoft Lync Server 2013 bedeutet dies normalerweise, dass zwei Richtlinien erstellt werden: eine Richtlinie für Audiodaten und eine für Videodaten.

Dienstqualitätsrichtlinien können mithilfe der Gruppenrichtlinie ganz einfach erstellt und verwaltet werden. (Diese gleichen Richtlinien können auch mithilfe lokaler Sicherheitsrichtlinien erstellt werden. Dafür müssen Sie dasselbe Verfahren auf jedem einzelnen Computer ausführen.) Ihre initilalen QoS-Richtlinien (eine für Audio- und eine für Videodaten) sollte nur auf Lync Server-Computern mit den Diensten für Konferenzserver, Anwendungsserver und/oder Vermittlungsserver angwendet werden. Wenn sich alle diese Computer in derselben Active Directory-Organisationseinheit befinden, können Sie dieser Organisationseinheit das neue Gruppenrichtlinienobjekt (GPO) einfach zuweisen. Alternativ können Sie andere Schritte ausführen, um den angegebenen Computern die neue Richtlinie vorzugeben. Beispielsweise können Sie die entsprechenden Computer einer Sicherheitsgruppe zuordnen, dann die Sicherheitsfilter der Gruppenrichtlinie verwenden, um die Gruppenrichtlinienobjekte (GPO) nur für diese Sicherheitsgruppe anzuwenden.

Zur Erstellung einer Dienstqualitätsrichtlinie zur Verwaltung von Audiodaten müssen Sie sich bei einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert ist. Klicken Sie zum Öffnen der Gruppenrichtlinienverwaltung auf **Start** , zeigen Sie auf **Verwaltung** und klicken Sie dann auf **Gruppenrichtlinienverwaltung** . Führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung die Container, in denen die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Lync Server-Computer in einer Organisationseinheit mit der Bezeichnung "Lync Server" befinden, sollte die neue Richtlinie in der Lync Server-Organisationseinheit erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen** .

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** den Namen für das neue Gruppenrichtlinienobjekt in das Feld **Name** (z. B. **Lync Server QoS** ) ein und klicken Sie anschließend auf **OK** .

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten** .

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **Computerkonfiguration** , erweitern Sie **Richtlinien** , erweitern Sie **Windows-Einstellungen** , klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS** , und klicken Sie dann auf **Neue Richtlinie erstellen** .

6.  Geben Sie auf der Startseite im Dialogfeld **Richtlinienbasierter QoS** den Namen der neuen Richtlinie (z. B. **Lync Server QoS** ) in das Feld **Name** ein. Wählen Sie **DSCP-Wert angeben** aus und legen Sie den Wert auf **46** fest. Deaktivieren Sie **Ausgehende Drosselungsrate angeben** und klicken Sie auf **Weiter** .

7.  Vergewissern Sie sich, dass die Option **Alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **Weiter** . Damit wird ganz einfach sichergestellt, dass alle Anwendungen mit den Paketen aus dem angegebenen Portbereich mit dem angegebenen DSCP-Code übereinstimmen.

8.  Vergewissern Sie sich auf der dritten Seite, dass die beiden Optionen "Beliebige Quell-IP-Adresse" und "Beliebige Ziel-IP-Adresse" ausgewählt sind, und klicken Sie dann auf **Weiter** . Mit diesen beiden Einstellungen wird sichergestellt, dass die Pakete verwaltet werden, unabhängig davon, von welchem Computer (IP-Adresse) diese Pakete gesendet wurden und welcher Computer (IP-Adresse) diese Pakete erhalten wird.

9.  Wählen Sie auf der vierten Seite die Optionen **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Lync Server und den zugehörigen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer an** die Option **Von dieser Quellportnummer bzw. diesem -bereich** aus. Geben Sie im zugehörigen Textfeld den Typ des Portbereichs ein, der für die Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports ab Port 49152 bis zum Port 57500 für den Audiodatenverkehr reserviert haben, geben Sie den Portbereich mithilfe des folgenden Formats ein: **49152:57500** . Klicken Sie auf **Fertig stellen** .


> [!NOTE]
> Der DSCP-Wert 46 ist ein etwas beliebiger Wert: obwohl der DSCP-Wert 46 oft verwendet wird, um Audiopakete zu markieren, müssen Sie den DSCP-Wert 46 nicht zur Audiokommunikation verwenden. Wenn Sie bereits die Dienstqualität implementiert haben und Sie einen anderen DSCP-Code für Audiodaten verwenden (z. B. DSCP-Wert 40), dann sollten Sie die Dienstqualitätsrichtlinie zur Verwendung desselben Codes (d. h. 40 für Audiodaten) konfigurieren. Wenn Sie dabei sind, die Dienstqualität (Quality of Service) zu implentieren, wird empfohlen, den DSCP-Wert 46 für Audiodaten zu verwenden, da dieser Wert der am häufigsten verwendete Wert zur Markierung der Audiopakete ist.



Nachdem Sie die Dienstqualitätsrichtlinie für den Audio-Datenverkehr erstellt haben, sollten Sie anschließend eine zweite Richtlinie für den Video-Datenverkehr erstellen (und optional eine dritte Richtlinie zur Verwaltung des Datenverkehrs im Zusammenhang mit der Anwendungsfreigabe). Befolgen Sie dieselben grundlegenden Anweisungen zum Erstellen einer Richtlinie für Videodaten wie bei der Erstellung einer Audiorichtline. Folgendes sollte ersetzt werden:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Video** ).

  - Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest. (Beachten Sie, dass Sie den DSCP-Wert 34 nicht verwenden müssen. Es ist lediglich erforderlich, dass ein anderer DSCP-Wert für Videodaten als für Audiodaten verwendet werden soll.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Video-Datenverkehr. Wenn Sie beispielsweise die Ports ab Port 57501 bis 65535 für den Video-Datenverkehr reserviert haben, legen Sie den Portbereich folgendermaßen fest: **57501:65535** .

Wenn Sie eine Richtlinie zur Verwaltung des Datenverkehrs im Zusammenhang mit der Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie erstellen und dabei Folgendes ersetzen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server-Anwendungsfreigabe** ).

  - Legen Sie den DSCP-Wert auf **24** anstatt auf 46 fest. (Auch dieses Mal muss der DSCP-Wert 24 nicht verwendet werden. Es ist lediglich erforderlich, dass ein anderer DSCP-Wert zur Anwendungsfreigabe als für Audio- bzw. Videodaten verwendet wird.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für den Video-Datenverkehr. Wenn Sie beispielsweise die Ports ab Port 40803 bis Port 49151 zur Anwendungsfreigabe reserviert haben, legen Sie den Portbereich folgendermaßen fest: **40803:49151** .

Die zwei von Ihnen neu erstellten Richtlinien werden erst wirksam, wenn die Gruppenrichtlinie auf den Lync Server-Computern aktualisiert wurde. Obwohl die Gruppenrichtlinie regelmäßig automatisch aktualisiert wird, können Sie mit dem folgenden Befehl eine Aktualisierung der Gruppenrichtlinie auf jedem Computer erzwingen, auf dem die Gruppenrichtlinie aktualisiert werden soll:

    Gpupdate.exe /force

Dieser Befehl kann innerhalb der Lync Server-Verwaltungsshell oder in jedem Befehlsfenster mit den Anmeldeinformationen des Administrators ausgeführt werden. Klicken Sie auf **Start** , klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und klicken Sie anschließend auf **Als Administrator ausführen** , um das Befehlsfenster mit den Anmeldeinformationen des Administrators auszuführen.

Führen Sie folgende Schritte aus, um zu überprüfen, ob die neuen QoS-Richtlinien angewendet wurden:

1.  Klicken Sie auf einem Lync Server-Computer auf **Start** , und klicken Sie dann auf **Ausführen** .

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **Computer** , erweitern Sie dann **HKEY\_LOCAL\_MACHINE** , erweitern Sie **SOFTWARE** , erweitern Sie **Richtlinien** , erweitern Sie **Microsoft** , erweitern Sie **Windows** und klicken Sie dann auf **QoS** . Unter **QoS** sollten die Registrierungsschlüssel für jede einzelne der gerade von Ihnen erstellten QoS-Richtlinien angezeigt werden. Wenn Sie beispielsweise zwei neue Richtlinien erstellt haben (eine mit der Bezeichnung "Lync Server Audio QoS" und die andere mit der Bezeichnung "Lync Server Video QoS"), sollten die Einträge für "Lync Server Audio QoS" und "Lync Server Video Qos" registriert werden.

Damit sichergestellt werden kann, dass die Netzwerkpakete mit dem entsprechenden DSCP-Wert markiert sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren durchführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen** .

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_LOCAL\_MACHINE** , erweitern Sie **SYSTEM** , erweitern Sie **CurrentControlSet** , erweitern Sie **Dienste** , und erweitern Sie dann **Tcpip** .

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** , zeigen Sie dann auf **Neu** , und klicken Sie anschließend auf **Schlüssel** . Geben Sie **QoS** ein, nachdem der neue Registrierungsschlüssel erstellt wurde, und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS** , zeigen Sie auf **Neu** , und klicken Sie dann auf **Zeichenfolgenwert** . Geben Sie **NLA nicht verwenden** ein, nachdem der neue Registrierungswert erstellt wurde, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden** . Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wert** **1** ein und klicken Sie anschließend auf **OK** .

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.

