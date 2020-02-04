---
title: 'Lync Server 2013: Konfigurieren der Dienst Qualitätsrichtlinien für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc06f5079fc6876c85324af67bd22be12f85a3c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Konfigurieren von Dienst Qualitätsrichtlinien in lync Server 2013 für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-03-29_

Zusätzlich zur Angabe von Portbereichen für die Verwendung durch ihre lync-Clients müssen Sie auch getrennte Dienst Qualitätsrichtlinien erstellen, die auf Clientcomputer angewendet werden. (Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der lync 2013-Client und entweder Windows 7 oder Windows 8 ausgeführt wird.

Im folgenden Beispiel wird dieser Satz von Portbereichen zum Erstellen einer audiorichtlinie und einer Video Richtlinie verwendet:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Client Datenverkehrstyp</th>
<th>Port Start</th>
<th>Port Bereich</th>
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


Wenn Sie eine Quality of Service-audiorichtlinie für Windows 7-oder Windows 8-Computer erstellen möchten, melden Sie sich zuerst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Client Organisationseinheit erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.

3.  Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync-Audio**), und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **lync-Audio**) ein. Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest. Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.

7. Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem ausführbaren Namen** aus, geben Sie den Namen **lync. exe**ein, und klicken Sie dann auf **weiter**. Mit dieser Einstellung wird die Richtlinie angewiesen, nur den übereinstimmenden Datenverkehr vom lync-Client zu priorisieren.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-IP-Adresse** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.

9.  Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **die Quellportnummer**aus, und wählen Sie **aus diesem Quell Port oder-Bereich aus**. Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen. Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync-Video**).

  - Setzen Sie den DSCP-Wert auf **34** statt auf 46. (Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen, als den für Audio verwendeten.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **58000:58019**.

Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Verkehrs zu erstellen, führen Sie diese Substitutionen aus:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **lync Server-Anwendungsfreigabe**).

  - Setzen Sie den DSCP-Wert auf **24** anstatt auf 46. (Wiederum muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **42000:42019**.

Für eine Datei Übertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server-Dateiübertragungen**).

  - Stellen Sie den DSCP-Wert auf **14**ein. (Dieser Wert muss wiederum nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung. Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **42020:42039**.

Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Clientcomputern aktualisiert wurden. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpudate.exe /force

Diesen Befehl können Sie über ein beliebiges Befehlsfenster ausführen, das mit Administratoranmeldeinformationen ausgeführt wird. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten. Sie sollten nicht auf Server angewendet werden, auf denen lync Server ausgeführt wird.

Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern

Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, treten möglicherweise gelegentlich Probleme auf, bei denen DSCP-Werte als "$ 00" anstelle des konfigurierten Werts angezeigt werden. Dies erfolgt in der Regel auf Computern, auf denen mindestens einer der Netzwerkadapter nicht auf die Active Directory-Domäne zugreifen kann (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, werden aber nicht für Adapter gekennzeichnet, die nicht auf die Domäne zugreifen können.

Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer, einschließlich Adaptern, die keinen Zugriff auf Ihre Domäne haben, taggen möchten, müssen Sie der Registrierung einen Wert hinzufügen und diesen konfigurieren. Dazu können Sie die folgenden Schritte ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Wenn ein Registrierungsschlüssel mit der Bezeichnung **QoS** nicht angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Geben Sie nach dem Erstellen des neuen Schlüssels **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.

Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

