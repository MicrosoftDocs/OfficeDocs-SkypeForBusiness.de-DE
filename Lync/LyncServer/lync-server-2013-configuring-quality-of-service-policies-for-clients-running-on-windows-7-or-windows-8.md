---
title: 'Lync Server 2013: Konfigurieren von Quality of Service Policies für Clients, die auf Windows 7 oder Windows 8'
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
ms.openlocfilehash: 2cd058e2903160f1c9f4ea06e30959b63953ab01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534972"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Konfigurieren von Quality of Service Policies in lync Server 2013 für Clients, die auf Windows 7 oder Windows 8

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-03-29_

Zusätzlich zur Angabe von Portbereichen für die Verwendung durch ihre lync-Clients müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputern angewendet werden. (Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputern angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der lync 2013-Client und entweder Windows 7 oder Windows 8.

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


Um eine Quality of Service-audiorichtlinie für Windows 7 oder Windows 8 Computer zu erstellen, melden Sie sich zunächst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie im **Startmenü**auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Organisationseinheit "Client" erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen**.

3.  Geben Sie im Dialogfeld **neues GPO** in das Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync Audio**), und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **richtlinienbasierter QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (z. b. **lync-Audio**) ein. Klicken Sie auf ** 	DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7. Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem ausführbaren Namen** aus, und geben Sie den Namen **Lync.exe**ein, und klicken Sie dann auf **weiter**. Mit dieser Einstellung wird die Richtlinie angewiesen, nur übereinstimmenden Datenverkehr vom lync-Client zu priorisieren.

8.  Vergewissern Sie sich auf der dritten Seite, dass **Beliebige Quell-IP-Adresse** und **Beliebige Ziel-IP-Adresse** aktiviert sind, und klicken Sie dann auf **Weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer**an, **aus diesem Quell Port oder-Bereich aus**. Geben Sie im dazugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den audiodatenverkehr reserviert haben, geben Sie den Portbereich unter Verwendung dieses Formats ein: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Video**).

  - Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest. (Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen als den für Audio verwendeten.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, legen Sie den Portbereich auf folgenden Wert fest: **58000:58019**.

Wenn Sie sich entscheiden, eine Richtlinie zum Verwalten des Anwendungsfreigabe-Datenverkehrs zu erstellen, machen Sie diese Substitution:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert auf **24** statt auf 46 fest. (Auch hier muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf folgenden Wert fest: **42000:42019**.

Für eine Datei Übertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server Dateiübertragungen**).

  - Legen Sie den DSCP-Wert auf **14**fest. (Wieder muss dieser Wert nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung. Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf folgenden Wert fest: **42020:42039**.

Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Clientcomputern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

    Gpudate.exe /force

Dieser Befehl kann in jedem Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten. Sie sollten nicht auf Server angewendet werden, auf denen lync Server ausgeführt wird.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY \_ lokaler \_ Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein und drücken dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie dann Ihren Computer neu.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern

Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, treten möglicherweise gelegentlich Probleme auf, bei denen DSCP-Werte als $00 statt als konfigurierter Wert angezeigt werden. Dies tritt in der Regel auf Computern auf, auf denen einer oder mehrere Netzwerkadapter nicht auf Ihre Active Directory Domäne zugreifen können (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, Sie werden jedoch nicht für Adapter markiert, die nicht auf die Domäne zugreifen können.

Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer, einschließlich Adaptern, die keinen Zugriff auf Ihre Domäne haben, markieren möchten, müssen Sie einen Wert für die Registrierung hinzufügen und konfigurieren. Führen Sie dafür die folgenden Schritte aus:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY \_ lokaler \_ Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Wenn kein Registrierungsschlüssel mit dem Namen **QoS** angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Schlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.

Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

