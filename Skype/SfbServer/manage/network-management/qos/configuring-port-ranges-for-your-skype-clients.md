---
title: Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Quality of Service-Richtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 ausgeführt werden.
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814201"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Quality of Service-Richtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 ausgeführt werden.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Standardmäßig können Skype for #A0 jeden Port zwischen den Ports 1024 und 65535 verwenden, wenn sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche nicht automatisch für Clients aktiviert werden. Um Quality of Service verwenden zu können, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe eindeutiger Portbereiche neu zuweisen. Dies kann mithilfe des cmdlets Set-CsConferencingConfiguration werden.

> [!NOTE]  
> Endbenutzer können diese Änderungen nicht selbst vornehmen. Portänderungen können nur von Administratoren mithilfe des cmdlets Set-CsConferencingConfiguration werden.


Sie können bestimmen, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ausführen:

    Get-CsConferencingConfiguration

Wenn Sie seit der Installation von Skype for Business Server keine Änderungen an den Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen mit den folgenden Eigenschaftswerten erhalten:

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

Dies ist wichtig, da Skype for #A0 bei Verwendung dieser Eigenschaft auf "False" jeden verfügbaren Port zwischen den Ports 1024 und 65535 verwenden, wenn sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (z. B. ClientMediaPort oder ClientVideoPort). Wenn Sie die Verwendung auf eine bestimmte Gruppe von Ports beschränken möchten (und dies ist etwas, was Sie tun möchten, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst Clientmedienportbereiche aktivieren. Dies kann mithilfe des folgenden Befehls Windows PowerShell werden:

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


In der vorstehenden Tabelle stellen Clientportbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind. Beispielsweise wurde auf den Servern die Anwendungsfreigabe für die Verwendung der Ports 40803 bis 49151 konfiguriert. auf den Clientcomputern ist die Anwendungsfreigabe für die Verwendung der Ports 42000 bis 42019 konfiguriert. Dies geschieht in erster Linie, um die Verwaltung von QoS zu vereinfachen: Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen. (Auf den Clientcomputern können Sie beispielsweise die Anwendungsfreigabe für die Verwendung der Ports 10000 bis 10019 konfigurieren.) Es wird jedoch empfohlen, die Clientportbereiche zu einer Teilmenge ihrer Serverportbereiche zu machen.

Zudem haben Sie vielleicht festgestellt, dass auf den Servern 8348 Ports für die Anwendungsfreigabe reserviert wurden, auf den Clients jedoch lediglich 20 Ports. Dies wird ebenfalls empfohlen, ist aber keine schnelle Regel. Im Allgemeinen können Sie jeden verfügbaren Port als eine einzelne Kommunikationssitzung betrachten: Wenn in einem Portbereich 100 Ports verfügbar sind, kann der computer in Frage gestellte Computer zu einem bestimmten Zeitpunkt an mindestens 100 Kommunikationssitzungen teilnehmen. Da Server wahrscheinlich an weitaus mehr Unterhaltungen als Clients beteiligt sind, ist es sinnvoll, auf den Servern viel mehr Ports als auf den Clients zu öffnen. Wenn Sie auf einem Client 20 Ports für die Anwendungsfreigabe reservieren, bedeutet dies, dass ein Benutzer auf dem angegebenen Gerät an 20 Anwendungssitzungen gleichzeitig teilnehmen kann. Dies sollte für die allermeisten Benutzer ausreichend sein.

Zum Zuweisen der vorstehenden Portbereiche zu Ihrer globalen Auflistung von Konferenzkonfigurationseinstellungen können Sie den folgenden Skype for Business Server-Verwaltungsshell-Befehl verwenden:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Einzelne Benutzer müssen sich von Skype for Business abmelden und dann erneut anmelden, bevor diese Änderungen tatsächlich wirksam werden.

> [!NOTE]  
> Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Konfigurieren von Quality of Service-Richtlinien für Clients, die unter Windows 10 ausgeführt werden

Sie müssen nicht nur Portbereiche angeben, die von Ihren Skype for Business-Clients verwendet werden sollen, sondern auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputer angewendet werden. (Die für Konferenz-, Anwendungs- und Vermittlungsserver erstellten Quality of Service-Richtlinien sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der Skype for Business-Client und Windows 10 ausgeführt werden.

Im folgenden Beispiel wird diese Gruppe von Portbereichen zum Erstellen einer Audio- und Videorichtlinie verwendet:


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

Um eine Quality of Service-Audiorichtlinie für Windows 10-Computer zu erstellen, melden Sie sich zunächst an einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (klicken Sie **auf "Start",** zeigen Sie auf **"Verwaltung"** und dann auf **"Gruppenrichtlinienverwaltung"),** und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Organisationseinheit "Client" erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf "Gruppenrichtlinienobjekt in dieser Domäne erstellen" und verknüpfen **Sie es hier.**

3.  Geben Sie **im Dialogfeld Neues Gruppenrichtlinienobjekt** im Feld **"Name"** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **"OK".**

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **"Bearbeiten".**

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **"Computerkonfiguration",** erweitern Sie **"Windows-Einstellungen",** klicken Sie mit der rechten Maustaste auf **"Richtlinienbasierter QoS",** und klicken Sie dann auf "Neue Richtlinie **erstellen".**

6.  Geben Sie **im Dialogfeld Richtlinienbasiertes QoS** auf der ersten Seite einen Namen für die neue Richtlinie in das Feld **"Name"** ein. Klicken Sie auf **DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  On the next page, select **Only applications with this executable name,** enter **Lync.exe** as the name, and then click **Next**. Mit dieser Einstellung wird die Richtlinie angewiesen, nur den entsprechenden Datenverkehr vom Skype for Business-Client zu priorisieren.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl eine beliebige **Quell-IP-Adresse** als auch eine beliebige **Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **"Weiter".** Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die von Skype for Business Server und seinen Clientanwendungen am häufigsten verwendet werden.

10. Wählen Sie unter der **Überschrift "Quellportnummer angeben"** **aus diesem Quellport oder -bereich aus.** Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports 50020 bis 50039 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen.

  - Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest. (Wie bereits erwähnt, müssen Sie nicht den #A0 34 verwenden; Sie müssen einfach einen anderen #A1 zuweisen als den für Audio verwendeten.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 58000 bis 58019 für Video reserviert haben, legen Sie den Portbereich auf **58000:58019**.

Wenn Sie eine Richtlinie für die Verwaltung des Datenverkehrs zur Anwendungsfreigabe erstellen möchten, müssen Sie die folgenden Ersetzungen erstellen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Skype for Business Server-Anwendungsfreigabe).**

  - Legen Sie den Wert des **Dienstanbieters auf 24** statt auf 46. (Auch hier muss dieser Wert nicht 24 sein; er muss sich einfach von den #A0 unterscheiden, die für Audio und Video verwendet werden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf **42000:42019**.

Für eine Dateiübertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Skype for Business Server File Transfers).**

  - Legen Sie den Wert des DSCP auf **14 .** (Auch hier muss dieser Wert nicht 14 sein, sondern nur ein eindeutiger DSCP-Code.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung. Wenn Sie beispielsweise die Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf **42020:42039**.

Die von Ihnen erstellten neuen Richtlinien werden erst wirksam, wenn die Gruppenrichtlinie auf Den Clientcomputern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

    Gpupdate.exe /force

Dieser Befehl kann über ein beliebiges Befehlsfenster ausgeführt werden, das mit Administratoranmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten. Sie sollten nicht auf Server angewendet werden, auf denen Skype for Business Server ausgeführt wird.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben Sie **im Dialogfeld** Ausführen **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY \_ LOCAL \_ MACHINE**, **erweitern Sie SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste,** und erweitern Sie dann **Tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben **Sie "NLA** nicht verwenden" ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken **Sie auf "NLA nicht verwenden".** Geben Sie im **Dialogfeld Zeichenfolge** bearbeiten  im Feld "Wert" den Wert **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie Den Computer.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern

Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, können Sie gelegentlich Probleme auftreten, bei denen die Werte von DSCP anstelle des konfigurierten Werts als 0x00 angezeigt werden. Dies geschieht in der Regel auf Computern, auf denen mindestens einer der Netzwerkadapter nicht auf Ihre Active Directory-Domäne zugreifen kann (z. B. wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen werden die Werte von DSCP für die Adapter gekennzeichnet, die auf die Domäne zugreifen können, jedoch nicht für Adapter, die nicht auf die Domäne zugreifen können.

Wenn Sie die Werte von DSCP für alle Netzwerkadapter in einem Computer markieren möchten, einschließlich Adaptern, die keinen Zugriff auf Ihre Domäne haben, müssen Sie der Registrierung einen Wert hinzufügen und konfigurieren. Führen Sie dafür die folgenden Schritte aus:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben Sie **im Dialogfeld** Ausführen **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY \_ LOCAL \_ MACHINE**, **erweitern Sie SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste,** und erweitern Sie dann **Tcpip**.

4.  Wenn kein Registrierungsschlüssel mit der Bezeichnung **QoS** angezeigt wird, klicken Sie mit der rechten Maustaste auf **Tcpip,** zeigen Sie auf **"Neu",** und klicken Sie dann auf **"Schlüssel".** Nachdem der neue Schlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um die Taste umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben **Sie "NLA** nicht verwenden" ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken **Sie auf "NLA nicht verwenden".** Geben Sie im **Dialogfeld Zeichenfolge** bearbeiten  im Feld "Wert" den Wert **1** ein, und klicken Sie dann auf **OK**.

Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie Ihren Computer neu starten, damit die Änderungen wirksam werden.

## <a name="see-also"></a>Siehe auch

[Erstellen eines Gruppenrichtlinienobjekts in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
