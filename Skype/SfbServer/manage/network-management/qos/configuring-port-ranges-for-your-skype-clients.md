---
title: Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients
ms.reviewer: null
'ms:assetid': 287d5cea-7ada-461c-9b4a-9da2af315e71
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)'
'ms:contentKeyID': 48183694
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Quality of Service-Richtlinien in Skype for Business Server für Clients konfigurieren, die auf Windows 10 ausgeführt werden.'
---

# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Quality of Service-Richtlinien in Skype for Business Server für Clients konfigurieren, die auf Windows 10 ausgeführt werden.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Standardmäßig können Skype for Business Clientanwendungen jeden Port zwischen ports 1024 und 65535 verwenden, wenn sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche nicht automatisch für Clients aktiviert werden. Um Quality of Service zu verwenden, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe eindeutiger Portbereiche zuweisen. Dies kann mithilfe des Cmdlets Set-CsConferencingConfiguration erfolgen.

> [!NOTE]  
> Endbenutzer können diese Änderungen nicht selbst vornehmen. Portänderungen können nur von Administratoren mithilfe des Cmdlets Set-CsConferencingConfiguration vorgenommen werden.


Sie können ermitteln, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell ausführen:

**Get-CsConferencingConfiguration**

Unter der Annahme, dass Sie seit der Installation Skype for Business Server keine Änderungen an den Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen abrufen, die diese Eigenschaftswerte enthalten:

ClientMediaPortRangeEnabled : False<br/>
ClientAudioPort : 5350<br/>
ClientAudioPortRange : 40<br/>
ClientVideoPort : 5350<br/>
ClientVideoPortRange : 40<br/>
ClientAppSharingPort : 5350<br/>
ClientAppSharingPortRange : 40<br/>
ClientFileTransferPort : 5350<br/>
ClientTransferPortRange : 40<br/>

Wenn Sie sich die vorherige Ausgabe genauer ansehen, werden Sie zwei wichtige Aspekte feststellen. Zunächst ist die Eigenschaft ClientMediaPortRangeEnabled auf False gesetzt:

**ClientMediaPortRangeEnabled : False**

Dies ist wichtig, da Skype for Business Clients, wenn diese Eigenschaft auf "False" festgelegt ist, einen beliebigen verfügbaren Port zwischen den Ports 1024 und 65535 verwenden, wenn sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (z. B. ClientMediaPort oder ClientVideoPort). Wenn Sie die Verwendung auf einen bestimmten Satz von Ports beschränken möchten (und dies ist etwas, was Sie tun möchten, wenn Sie quality of Service implementieren möchten), müssen Sie zuerst Clientmedienportbereiche aktivieren. Dies kann mit dem folgenden Befehl Windows PowerShell erfolgen:

**Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

Mit dem obigen Befehl werden die Client-Medienportbereiche für die globale Auflistung der Konferenzkonfigurationseinstellungen aktiviert. Diese Einstellungen können jedoch auch auf Standortebene und/oder Dienstebene (nur für den Konferenzserverdienst) angewendet werden. Um die Client-Medienportbereiche für einen bestimmten Standort oder Server zu aktivieren, geben Sie beim Aufruf von Set-CsConferencingConfiguration die Identität des Standorts oder Servers an:

**Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True**

Alternativ können Sie diesen Befehl verwenden, um Portbereiche für die gesamten Konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

Der zweite wichtige Aspekt ist, dass für jeden Typ von Netzwerkdatenverkehr standardmäßig dieselben Medienportbereiche festgelegt werden, wie Sie in der Beispielausgabe sehen können:

ClientAudioPort : 5350<br/>
ClientVideoPort : 5350<br/>
ClientAppSharingPort : 5350<br/>
ClientFileTransferPort : 5350<br/>

Zur Implementierung des Quality of Service (QoS) muss jeder dieser Portbereiche identisch sein. Sie können diese Portbereiche z. B. wie folgt konfigurieren:


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Client-Datenverkehrstyp</th>
<th>Anfang des Portbereichs</th>
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


In der obigen Tabelle stellen Clientportbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind. Beispielsweise wurde die Anwendungsfreigabe auf den Servern so konfiguriert, dass die Ports 40803 bis 49151 verwendet werden. Auf den Clientcomputern ist die Anwendungsfreigabe für die Verwendung der Ports 42000 bis 42019 konfiguriert. Auch dies geschieht in erster Linie, um die Verwaltung von QoS zu vereinfachen: Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen. (Beispielsweise können Sie auf den Clientcomputern die Anwendungsfreigabe so konfigurieren, dass beispielsweise die Ports 10000 bis 10019 verwendet werden.) Es wird jedoch empfohlen, die Clientportbereiche zu einer Teilmenge ihrer Serverportbereiche zu machen.

Zudem haben Sie vielleicht festgestellt, dass auf den Servern 8348 Ports für die Anwendungsfreigabe reserviert wurden, auf den Clients jedoch lediglich 20 Ports. Auch dies wird empfohlen, ist aber keine feste und schnelle Regel. Im Allgemeinen können Sie jeden verfügbaren Port als eine einzige Kommunikationssitzung betrachten: Wenn 100 Ports in einem Portbereich verfügbar sind, bedeutet dies, dass der betreffende Computer an maximal 100 Kommunikationssitzungen zu einem bestimmten Zeitpunkt teilnehmen kann. Da Server wahrscheinlich an weitaus mehr Unterhaltungen als Clients beteiligt sind, ist es sinnvoll, auf den Servern viel mehr Ports als auf den Clients zu öffnen. Wenn Sie auf einem Client 20 Ports für die Anwendungsfreigabe reservieren, bedeutet dies, dass ein Benutzer auf dem angegebenen Gerät an 20 Anwendungssitzungen gleichzeitig teilnehmen kann. Dies sollte für die allermeisten Benutzer ausreichend sein.

Um ihrer globalen Sammlung von Konferenzkonfigurationseinstellungen die vorherigen Portbereiche zuzuweisen, können Sie den folgenden Befehl Skype for Business Server Verwaltungsshell verwenden:

**Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

Einzelne Benutzer müssen sich von Skype for Business abmelden und sich dann erneut anmelden, bevor diese Änderungen tatsächlich wirksam werden.

> [!NOTE]  
> Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Konfigurieren von Quality of Service-Richtlinien für Clients, die auf Windows 10

Zusätzlich zur Angabe von Portbereichen für die Verwendung durch Ihre Skype for Business-Clients müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputer angewendet werden. (Die für Konferenz-, Anwendungs- und Vermittlungsserver erstellten Quality of Service-Richtlinien sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der Skype for Business-Client und Windows 10 ausgeführt werden.

Im folgenden Beispiel werden diese Portbereiche verwendet, um eine Audio- und eine Videorichtlinie zu erstellen:


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Client-Datenverkehrstyp</th>
<th>Anfang des Portbereichs</th>
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

Um eine Quality of Service-Audiorichtlinie für Windows 10 Computer zu erstellen, melden Sie sich zunächst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (klicken Sie auf **"Start**", zeigen Sie auf **"Verwaltungstools**", und klicken Sie dann auf **"Gruppenrichtlinienverwaltung**"), und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Clientcomputer in einer OE namens "Clients" befinden, sollte die neue Richtlinie in der Client-OU erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf " **Gruppenrichtlinienobjekt in dieser Domäne erstellen", und verknüpfen Sie es hier**.

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** im Feld " **Name** " einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **"OK**".

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **"Bearbeiten**".

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor die **Computerkonfiguration**, erweitern Sie **Windows Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasiertes QoS**, und klicken Sie dann auf **"Neue Richtlinie erstellen**".

6.  Geben Sie im Dialogfeld **"Richtlinienbasierter QoS** " auf der ersten Seite einen Namen für die neue Richtlinie in das **Feld "Name** " ein. Klicken Sie auf **DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Wählen Sie auf der nächsten Seite **"Nur Anwendungen mit diesem ausführbaren Namen**" aus, geben **SieLync.exe** als Namen ein, und klicken Sie dann auf **"Weiter**". Diese Einstellung weist die Richtlinie an, nur den übereinstimmenden Datenverkehr vom Skype for Business-Client zu priorisieren.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine beliebige Quell-IP-Adresse** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **"Weiter**". Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **"Quellportnummer angeben**" **die Option "Von diesem Quellport oder -bereich" aus**. Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports 50020 bis Ports 50039 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen.

  - Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest. (Wie bereits erwähnt, müssen Sie nicht den DSCP-Wert 34 verwenden; Sie müssen einfach einen anderen DSCP-Wert als den für Audio verwendeten zuweisen.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 58000 bis 58019 für Video reserviert haben, legen Sie den Portbereich auf folgendes fest: **58000:58019**.

Wenn Sie eine Richtlinie für die Verwaltung des Datenverkehrs für die Anwendungsfreigabe erstellen möchten, nehmen Sie diese Ersetzungen vor:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. **B. Skype for Business Server Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert auf **24** anstelle von 46 fest. (Auch hier muss dieser Wert nicht 24 sein; er muss einfach von den DSCP-Werten für Audio und Video abweichen.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf **42000:42019** fest.

Für eine Dateiübertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. **B. Skype for Business Server Dateiübertragungen**).

  - Legen Sie den DSCP-Wert auf **14** fest. (Auch hier muss dieser Wert nicht 14 sein; er muss einfach ein eindeutiger DSCP-Code sein.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung. Wenn Sie beispielsweise die Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf **42020:42039** fest.

Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Clientcomputern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

**Gpupdate.exe /force**

Dieser Befehl kann von jedem Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten. Sie sollten nicht auf Server angewendet werden, auf denen Skype for Business Server ausgeführt wird.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **"HKEYLOCALMACHINE\_\_**", "**SYSTEM**", "**CurrentControlSet**", "**Dienste**" und dann "**Tcpip**".

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Geben Sie nach dem Erstellen des neuen **Registrierungsschlüssels QoS** ein, und drücken Sie dann die EINGABETASTE, um die Taste umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Geben Sie nach dem Erstellen des neuen Registrierungswerts **"NLA nicht verwenden"** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken **Sie auf "NLA nicht verwenden"**. In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie Ihren Computer.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern

Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, können Gelegentlich Probleme auftreten, bei denen DSCP-Werte als 0x00 anstelle des konfigurierten Werts angezeigt werden. Dies geschieht in der Regel auf Computern, auf denen mindestens einer der Netzwerkadapter nicht auf Ihre Active Directory-Domäne zugreifen kann (z. B. wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, aber nicht für Adapter, die nicht auf die Domäne zugreifen können.

Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer markieren möchten, einschließlich Adaptern, die keinen Zugriff auf Ihre Domäne haben, müssen Sie der Registrierung einen Wert hinzufügen und konfigurieren. Führen Sie dafür die folgenden Schritte aus:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **"HKEYLOCALMACHINE\_\_**", "**SYSTEM**", "**CurrentControlSet**", "**Dienste**" und dann "**Tcpip**".

4.  Wenn kein Registrierungsschlüssel mit der Bezeichnung **QoS** angezeigt wird, klicken Sie mit der rechten Maustaste auf **Tcpip**, zeigen Sie auf **"Neu"**, und klicken Sie dann auf **"Schlüssel**". Geben Sie nach dem Erstellen der neuen Taste **QoS** ein, und drücken Sie die EINGABETASTE, um die Taste umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Geben Sie nach dem Erstellen des neuen Registrierungswerts **"NLA nicht verwenden"** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken **Sie auf "NLA nicht verwenden"**. In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.

Nach dem Erstellen und Konfigurieren des neuen Registrierungswerts müssen Sie ihren Computer neu starten, damit die Änderungen wirksam werden.

## <a name="see-also"></a>Siehe auch

[Erstellen eines Gruppenrichtlinienobjekts in Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
