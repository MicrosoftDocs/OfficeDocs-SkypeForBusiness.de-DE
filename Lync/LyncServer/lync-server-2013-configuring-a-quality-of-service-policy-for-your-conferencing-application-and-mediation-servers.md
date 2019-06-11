---
title: 'Lync Server 2013: Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a79835fb19f5a30a11eac4859f133aeec5c8cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-23_

Durch die Konfiguration von Portbereichen wird die Verwendung von Quality of Service vereinfacht, indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (beispielsweise der gesamte Audioverkehr) durch denselben Satz von Ports übertragen wird. Dadurch ist es für das System einfach, ein gegebenes Paket zu erkennen und zu kennzeichnen: Wenn Port 49152 für den Audioverkehr reserviert ist, kann jedes Paket, das über Port 49152 reist, mit einem DSCP-Code gekennzeichnet werden, der angibt, dass es sich um ein audiopaket handelt. Dies ermöglicht es Routern wiederum, das Paket als audiopaket zu identifizieren und ihm eine höhere Priorität als nicht markierte Pakete zu geben (beispielsweise Pakete, mit denen eine Datei von einem Server auf einen anderen kopiert wird).

Die Beschränkung einer Reihe von Ports auf einen bestimmten Datenverkehr führt jedoch nicht dazu, dass Pakete, die mit dem entsprechenden DSCP-Code gekennzeichnet sind, durch diese Ports verlaufen. Neben der Definition von Portbereichen müssen Sie auch Quality of Service-Richtlinien erstellen, die den DSCP-Code angeben, der jedem Portbereich zugeordnet werden soll. Für Microsoft lync Server 2013 bedeutet dies in der Regel das Erstellen von zwei Richtlinien: eine für Audio und eine für Video.

Dienst Qualitätsrichtlinien werden am einfachsten erstellt und mithilfe von Gruppenrichtlinien verwaltet. (Dieselben Richtlinien können auch mithilfe von lokalen Sicherheitsrichtlinien erstellt werden. Dies erfordert jedoch, dass Sie auf jedem Computer dasselbe Verfahren wiederholen.) Ihre anfänglichen QoS-Richtlinien (eine für Audio und eine für Video) sollten nur auf lync Server-Computern angewendet werden, auf denen der Konferenzserver, der Anwendungsserver und/oder die Vermittlungsserver Dienste ausgeführt werden. Wenn sich alle diese Computer in der gleichen Active Directory-Organisationseinheit befinden, können Sie der Organisationseinheit einfach das neue Gruppenrichtlinienobjekt (GPO) zuweisen. Sie können aber auch andere Schritte ausführen, um die neue Richtlinie auf die angegebenen Computer abzuzielen. So können Sie beispielsweise die entsprechenden Computer in einer Sicherheitsgruppe platzieren und dann die Gruppenrichtlinien-Sicherheitsfilterung verwenden, um das Gruppenrichtlinienobjekt nur für diese Sicherheitsgruppe anzuwenden.

Wenn Sie eine Quality of Service-Richtlinie für die Audioverwaltung erstellen möchten, melden Sie sich bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle lync Server-Computer in einer Organisationseinheit mit dem Namen lync Server befinden, sollte die neue Richtlinie in der lync Server-Organisationseinheit erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.

3.  Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt (beispielsweise **lync Server QoS**) ein, und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **lync Server QoS**) ein. Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest. Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.

7.  Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**. Dadurch wird einfach sichergestellt, dass alle Anwendungen Pakete aus dem angegebenen Portbereich mit dem angegebenen DSCP-Code abgleichen.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-IP-Adresse als auch eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.

9.  Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **die Quellportnummer**aus, und wählen Sie **aus diesem Quell Port oder-Bereich aus**. Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 49152 über Ports 57500 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

<div>


> [!NOTE]  
> Der DSCP-Wert von 46 ist etwas willkürlich: Obwohl DSCP 46 häufig zum Markieren von Audiopaketen verwendet wird, müssen Sie DSCP 46 nicht für die Audiokommunikation verwenden. Wenn Sie bereits QoS implementiert haben und einen anderen DSCP-Code für Audio verwenden (beispielsweise DSCP 40), sollten Sie Ihre Dienst Qualitätsrichtlinie so konfigurieren, dass dieser Code verwendet wird (d. h., 40 für Audio). Wenn Sie gerade jetzt Quality of Service implementieren, empfiehlt es sich, DSCP 46 für Audio zu verwenden, einfach weil dieser Wert häufig zum Markieren von Audiopaketen verwendet wird.



</div>

Nachdem Sie die QoS-Richtlinie für den Audioverkehr erstellt haben, sollten Sie eine zweite Richtlinie für den Videoverkehr erstellen (und optional eine dritte Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs). Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server-Video**).

  - Setzen Sie den DSCP-Wert auf **34** statt auf 46. (Beachten Sie, dass Sie keinen DSCP-Wert von 34 verwenden müssen. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 57501 bis 65535 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **57501:65535**.

Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs zu erstellen, müssen Sie eine dritte Richtlinie erstellen, indem Sie die folgenden Ersetzungen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **lync Server-Anwendungsfreigabe**).

  - Setzen Sie den DSCP-Wert auf **24** anstatt auf 46. (Sie müssen wiederum keinen DSCP-Wert von 24 verwenden. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für die Anwendungsfreigabe verwenden, als Sie für Audio oder Video verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **40803:49151**.

Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren lync Server-Computern aktualisiert wurden. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpupdate.exe /force

Dieser Befehl kann in der lync Server-Verwaltungsshell oder in einem beliebigen Befehlsfenster, das unter Administratoranmeldeinformationen ausgeführt wird, ausgeführt werden. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Gehen Sie wie folgt vor, um zu überprüfen, ob die neuen QoS-Richtlinien angewendet wurden:

1.  Klicken Sie auf einem lync Server-Computer auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **Computer**, erweitern Sie **HKEY\_lokaler\_Computer**, erweitern Sie **Software**, erweitern Sie **Richtlinien**, erweitern Sie **Microsoft**, erweitern Sie **Windows**, und klicken Sie dann auf **QoS**. Unter **QoS** sollten Registrierungsschlüssel für jede der soeben erstellten QoS-Richtlinien angezeigt werden. Wenn Sie beispielsweise zwei neue Richtlinien (eine mit dem Namen lync Server Audio QoS und die andere benannte lync Server-Video QoS) erstellt haben, sollten Sie Registrierungseinträge für die QoS von lync Server Audio QoS und für lync Server Video erstellen.

Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.

</div>

<span> </span>

</div>

</div>

</div>

