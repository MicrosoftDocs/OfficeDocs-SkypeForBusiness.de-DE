---
title: Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Dienst Qualitätsrichtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 betrieben werden.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045888"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Clients in Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Dienst Qualitätsrichtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 betrieben werden.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Skype for Business Clientanwendungen können standardmäßig einen beliebigen Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden. Um die Dienstqualität zu verwenden, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe eindeutiger Portbereiche neu zuweisen. Dies kann mithilfe des Cmdlets "CsConferencingConfiguration" geschehen.

> [!NOTE]  
> Endbenutzer können diese Änderungen nicht selbst vornehmen. Port Änderungen können nur von Administratoren mithilfe des Cmdlets "CsConferencingConfiguration" vorgenommen werden.


Sie können bestimmen, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell ausführen:

    Get-CsConferencingConfiguration

Unter der Annahme, dass Sie seit der Installation von Skype for Business Server keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Wenn Sie sich die vorherige Ausgabe genauer ansehen, werden Sie zwei wichtige Aspekte feststellen. Zunächst ist die Eigenschaft ClientMediaPortRangeEnabled auf False gesetzt:

    ClientMediaPortRangeEnabled : False

Das ist wichtig, da, wenn diese Eigenschaft auf "false" festgelegt ist, Skype for Business Clients einen beliebigen verfügbaren Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort). Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies möchten Sie tun, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client-Medien Portbereiche aktivieren. Dies kann mithilfe des folgenden Windows PowerShell Befehls erfolgen:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Mit dem obigen Befehl werden die Client-Medienportbereiche für die globale Auflistung der Konferenzkonfigurationseinstellungen aktiviert. Diese Einstellungen können jedoch auch auf Standortebene und/oder Dienstebene (nur für den Konferenzserverdienst) angewendet werden. Um die Client-Medienportbereiche für einen bestimmten Standort oder Server zu aktivieren, geben Sie beim Aufruf von Set-CsConferencingConfiguration die Identität des Standorts oder Servers an:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Alternativ können Sie diesen Befehl verwenden, um Portbereiche für die gesamten Konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Der zweite wichtige Aspekt ist, dass für jeden Typ von Netzwerkdatenverkehr standardmäßig dieselben Medienportbereiche festgelegt werden, wie Sie in der Beispielausgabe sehen können:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Zur Implementierung des Quality of Service (QoS) muss jeder dieser Portbereiche identisch sein. Sie können diese Portbereiche z. B. wie folgt konfigurieren:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
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


In der obigen Tabelle stellen Client Portbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind. Auf den Servern wurde die Anwendungsfreigabe beispielsweise für die Verwendung von Ports 40803 bis 49151 konfiguriert; auf den Clientcomputern ist die Anwendungsfreigabe für die Verwendung von Ports 42000 bis 42019 konfiguriert. Auch dies geschieht in erster Linie, um die Verwaltung von QoS zu vereinfachen: Client-Ports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen. (Beispielsweise können Sie auf den Clientcomputern die Anwendungsfreigabe so konfigurieren, dass die Ports 10000 bis 10019 verwendet werden.) Es wird jedoch empfohlen, dass Sie Ihre Client Portbereiche als Teilmenge ihrer Server Portbereiche festlegen.

Zudem haben Sie vielleicht festgestellt, dass auf den Servern 8348 Ports für die Anwendungsfreigabe reserviert wurden, auf den Clients jedoch lediglich 20 Ports. Auch dies wird empfohlen, ist aber keine harte und schnelle Regel. Im Allgemeinen können Sie jeden verfügbaren Port in Betracht ziehen, eine einzelne Kommunikationssitzung darzustellen: Wenn Sie 100 Ports in einem Portbereich verfügbar haben, bedeutet dies, dass der fragliche Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann. Da Server wahrscheinlich an weitaus mehr Unterhaltungen als Clients beteiligt sind, ist es sinnvoll, auf den Servern viel mehr Ports als auf den Clients zu öffnen. Wenn Sie auf einem Client 20 Ports für die Anwendungsfreigabe reservieren, bedeutet dies, dass ein Benutzer auf dem angegebenen Gerät an 20 Anwendungssitzungen gleichzeitig teilnehmen kann. Dies sollte für die allermeisten Benutzer ausreichend sein.

Um die vorherigen Portbereiche ihrer globalen Sammlung von Konferenz Konfigurationseinstellungen zuzuweisen, können Sie den folgenden Skype for Business Server-Verwaltungsshell-Befehl verwenden:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Einzelne Benutzer müssen sich von Skype for Business abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.

> [!NOTE]  
> Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Konfigurieren von Quality of Service Policies für Clients, die unter Windows 10 betrieben werden

Zusätzlich zur Angabe von Portbereichen für die Verwendung durch Ihre Skype for Business Clients müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputern angewendet werden. (Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputern angewendet werden.) Diese Informationen gelten nur für Computer mit dem Skype for Business-Client und Windows 10.

Im folgenden Beispiel werden diese Sätze von Portbereichen zum Erstellen einer audiorichtlinie und einer Video Richtlinie verwendet:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
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

Um eine Quality of Service-audiorichtlinie für Windows 10-Computer zu erstellen, melden Sie sich zunächst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie im **Startmenü**auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Organisationseinheit "Client" erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **GPO in dieser Domäne erstellen, und verknüpfen Sie Sie hier**.

3.  Geben Sie im Dialogfeld **neues GPO** in das Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor den Knoten **Computer Konfiguration**, dann **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **richtlinienbasierter QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie ein. Klicken Sie auf ** 	DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem ausführbaren Namen**aus, geben Sie **lync. exe** als Namen ein, und klicken Sie dann auf **weiter**. Mit dieser Einstellung wird die Richtlinie angewiesen, nur übereinstimmenden Datenverkehr vom Skype for Business Client zu priorisieren.

8.  Stellen Sie auf der dritten Seite sicher, dass **jede Quell-IP-Adresse** und **jede Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer**an, **aus diesem Quell Port oder-Bereich aus**. Geben Sie im dazugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den audiodatenverkehr reserviert haben, geben Sie den Portbereich unter Verwendung dieses Formats ein: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen.

  - Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest. (Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen als den für Audio verwendeten.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für den Videodatenverkehr. Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, legen Sie den Portbereich auf den folgenden Wert fest: **58000:58019**.

Wenn Sie sich dafür entscheiden, eine Richtlinie zum Verwalten des Datenverkehrs für die Anwendungsfreigabe zu erstellen, müssen Sie diese Substitutionen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype for Business Server Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert auf **24** statt auf 46 fest. (Auch hier muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für den Videodatenverkehr. Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf den folgenden Wert fest: **42000:42019**.

Für eine Datei Übertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype for Business Server Dateiübertragungen**).

  - Legen Sie den DSCP-Wert auf **14**fest. (Wieder muss dieser Wert nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung. Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf den folgenden Wert fest: **42020:42039**.

Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Clientcomputern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

    Gpupdate.exe /force

Dieser Befehl kann in jedem Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten. Sie sollten nicht auf Server angewendet werden, auf denen Skype for Business Server ausgeführt wird.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start**, und klicken Sie dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem Sie den neuen Registrierungsschlüssel erstellt haben, geben Sie **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und Eboot Sie Ihren Computer.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern

Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, können gelegentlich Probleme auftreten, bei denen DSCP-Werte als "$ 00" und nicht als konfigurierter Wert angezeigt werden. Dies tritt in der Regel auf Computern auf, auf denen einer oder mehrere Netzwerkadapter nicht auf Ihre Active Directory Domäne zugreifen können (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, Sie werden jedoch nicht für Adapter markiert, die nicht auf die Domäne zugreifen können.

Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer markieren möchten, einschließlich Adapter, die keinen Zugriff auf Ihre Domäne haben, müssen Sie einen Wert für die Registrierung hinzufügen und konfigurieren. Führen Sie dafür die folgenden Schritte aus:

1.  Klicken Sie auf **Start**, und klicken Sie dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Wenn kein Registrierungsschlüssel mit dem Namen **QoS** angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**. Geben Sie nach dem Erstellen des neuen Schlüssels **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.

Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.

## <a name="see-also"></a>Siehe auch

[Erstellen eines Gruppenrichtlinienobjekts in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
