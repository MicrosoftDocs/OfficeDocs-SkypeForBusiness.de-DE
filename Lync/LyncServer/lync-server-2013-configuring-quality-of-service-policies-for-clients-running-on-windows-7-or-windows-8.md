---
title: Konfigurieren von QoS-Richtlinien für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden
TOCTitle: Konfigurieren von QoS-Richtlinien für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205371(v=OCS.15)
ms:contentKeyID: 49295844
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von QoS-Richtlinien für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden

 

_**Letztes Änderungsdatum des Themas:** 2016-03-29_

Sie müssen nicht nur Portbereiche für die Verwendung durch die Lync-Clients angeben, sondern auch separate QoS-Richtlinien (Quality of Service, Dienstqualität) erstellen, die auf die Clientcomputer angewendet werden. (Die für Konferenz-, Anwendungs- und Vermittlungsserver erstellten QoS-Richtlinien dürfen nicht auf Clientcomputer angewendet werden.) Diese Information gilt nur für Computer, auf denen der Lync 2013-Client und Windows 7 oder Windows 8 ausgeführt werden.

Im folgenden Beispiel werden die genannten Portbereiche verwendet, um eine Audio- und eine Videorichtlinie zu erstellen:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ des Clientdatenverkehrs</th>
<th>Portbeginn</th>
<th>Portbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Dateiübertragung</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Zum Erstellen einer QoS-Audiorichtlinie für Computer mit Windows\&nbsp;7 oder Windows 8 melden Sie sich zuerst auf einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert ist. Öffnen Sie die Gruppenrichtlinienverwaltung (zeigen Sie dazu im Startmenü auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann folgendes Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung den Container heraus, in der die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Clientcomputer in einer Organisationseinheit namens "Clients" befinden, sollten Sie die neue Richtlinie in dieser Organisationseinheit erstellen.

2.  Klicken Sie mit der rechten Maustaste auf den betreffenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen**.

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (z.\&nbsp;B. **Lync Audio**), und klicken Sie auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor den Knoten **Computerkonfiguration**, dann **Richtlinien** und anschließend **Windows-Einstellungen**. Klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **Richtlinienbasierter QoS** auf der Startseite im Feld **Name** einen Namen für die neue Richtlinie ein (z.\&nbsp;B. **Lync Audio**). Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46** fest. Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Vergewissern Sie sich auf der nächsten Seite, dass das Kontrollkästchen **Alle Anwendungen** aktiviert ist, und klicken Sie auf **Weiter**. Mit dieser Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit einem DSCP-Wert von 46 zu suchen, nicht nur nach Paketen, die von einer bestimmten Anwendung erstellt wurden.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl **Beliebige Quell-IP-Adresse** als auch **Beliebige Ziel-IP-Adresse** aktiviert ist, und klicken Sie dann auf **Weiter**. Diese beiden Einstellungen sorgen dafür, dass Pakete verarbeitet werden, unabhängig davon, welche Computer (IP-Adresse) diese Pakete gesendet hat und welcher sie empfängt.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die zwei am häufigsten von Lync Server und seinen Clientanwendungen verwendeten Netzwerkprotokolle.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer an** die Option **Von dieser Quellportnummer bzw. diesem -bereich** aus. Geben Sie im zugehörigen Textfeld den für Audioübertragungen reservierten Portbereich an. Wenn Sie beispielsweise Port 50020 bis einschließlich 50039 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen. Dazu führen Sie im Prinzip das gleiche Verfahren durch wie zum Erstellen einer Audiorichtlinie durch, abgesehen von folgenden Änderungen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z.\&nbsp;B. **Lync Video**).

  - Legen Sie den DSCP-Wert nicht auf **46** fest, sondern auf **34**. (Wie schon erwähnt, müssen Sie den DSCP-Wert 34 nicht unbedingt verwenden. Wichtig ist, dass Sie einen anderen DSCP-Wert zuweisen als den für Audio.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie z.\&nbsp;B. Port 58000 bis einschließlich 58019 für Video reserviert haben, legen Sie den Portbereich wie folgt fest: **58000:58019**.

Wenn Sie eine Richtlinie für die Verarbeitung des Datenverkehrs für die Anwendungsfreigabe erstellen möchten, verwenden Sie folgende Angaben:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z.\&nbsp;B. **Lync Server-Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert nicht auf **46** fest, sondern auf **24**. (Auch dieser Wert muss nicht 24 sein, Sie müssen nur einen anderen DSCP-Wert verwenden als den für Audio und den für Video.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendungsfreigabe. Wenn Sie z.\&nbsp;B. Port 42000 bis einschließlich 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich wie folgt fest: **42000:42019**.

Für eine Dateiübertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z.\&nbsp;B. **Lync Server-Dateiübertragungen**).

  - Legen Sie den DSCP-Wert auf **14** fest. (Auch dieser Wert muss nicht 14 sein, Sie müssen nur einen eindeutigen DSCP-Code verwenden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Dateiübertragungen. Wenn Sie beispielsweise Port 42020 bis einschließlich 42039 für Dateiübertragungen reserviert haben, legen Sie den Portbereich wie folgt fest: **42020:42039**.

Die von Ihnen erstellten neuen Richtlinien treten erst dann in Kraft, nachdem die Gruppenrichtlinie auf den Clientcomputern aktualisiert worden ist. Die Gruppenrichtlinie wird zwar regelmäßig automatisch aktualisiert, Sie können aber eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinie aktualisiert werden muss:

    Gpudate.exe /force

Sie können diesen Befehl in jedem beliebigen Befehlsfenster ausführen, das unter den Administrator-Anmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter den Anmeldeinformationen des Administrators klicken Sie im Startmenü mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Beachten Sie, dass diese Richtlinien für die Clientcomputer vorgesehen sind. Sie sollten nicht auf Server mit Lync Server angewendet werden.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert gekennzeichnet werden, sollten Sie außerdem auf jedem Computer einen neuen Registrierungseintrag erstellen. Führen Sie dazu das folgende Verfahren durch:

1.  Klicken Sie im Startmenü auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **regedit** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **services** und dann **Tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Geben Sie nach dem Erstellen des neuen Registrierungsschlüssels **QoS** ein, und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Geben Sie nach dem Erstellen des neuen Registrierungsschlüssels **NLA nicht verwenden** ein, und drücken Sie die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.

## Konfigurieren von Quality of Service auf Computern mit mehreren Netzwerkadaptern

Wenn Sie einen Computer mit mehreren Netzwerkadaptern haben, kann es gelegentlich vorkommen, dass DSCP-Werte als 0x00 angezeigt werden und nicht als der jeweils konfigurierte Wert. Das tritt typischerweise auf Computern auf, auf denen ein oder mehrere Netzwerkadapter nicht auf die Active Directory-Domäne zugreifen können (z.\&nbsp;B., wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen werden DSCP-Werte für die Adapter getagt, die auf die Domäne zugreifen können, aber nicht für Adapter, die nicht auf die Domäne zugreifen können.

Wenn DSCP-Werte für alle Netzwerkadapter auf einem Computer getagt werden sollen, auch für Adapter, die nicht auf Ihre Domäne zugreifen können, müssen Sie einen Wert in der Registrierung hinzufügen und konfigurieren. Dazu führen Sie folgendes Verfahren durch:

1.  Klicken Sie im Startmenü auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **regedit** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **services** und dann **Tcpip**.

4.  Wenn Sie keinen Registrierungsschlüssel mit der Bezeichnung **QoS** finden, klicken Sie mit der rechten Maustaste auf **Tcpip**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nach dem Erstellen des neuen Schlüssels geben Sie **QoS** ein und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Geben Sie nach dem Erstellen des neuen Registrierungsschlüssels **NLA nicht verwenden** ein, und drücken Sie die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.

Nach dem Erstellen und Konfigurieren des neuen Registrierungswerts müssen Sie Ihren Computer neu starten, damit die Änderungen wirksam werden.

