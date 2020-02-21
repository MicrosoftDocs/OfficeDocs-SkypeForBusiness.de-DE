---
title: 'Lync Server 2013: Konfigurieren einer Dienst Qualitätsrichtlinie für Ihre Konferenz-, Anwendungs-und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37462eb9f15553138dc6bb7285a5d0786dbc4b57
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren einer Dienst Qualitätsrichtlinie in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-23_

Das Konfigurieren von Portbereichen vereinfacht die Verwendung der Dienstqualität (Quality of Service), indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (z. B. der gesamte Audio-Datenverkehr) über dieselben Ports übermittelt wird. Dadurch ist es für das System einfacher, ein bestimmtes Paket zu identifizieren und zu markieren: Wenn der Port 49152 für den Audio-Datenverkehr reserviert ist, kann jedes beliebige Paket, das über den Port 49152 übermittelt wird, mit einem DSCP-Code markiert werden. Dieser Code gibt an, dass es sich dabei um ein Audiopaket handelt. Anschließend können diese Router das Paket als ein Audiopaket identifizieren und ihm eine höhere Priorität als unmarkierte Pakete verleihen (wie z. B. Pakete, die Dateien von einem Server zu einem anderen Server kopieren).

Die einfache Einschränkung von Ports auf eine bestimmte Art von Datenverkehr führt nicht dazu, dass die Pakete über die Ports, die mit dem entsprechenden DSCP-Code markiert sind, übermittelt werden. Zusätzlich zum Definieren der Portbereiche müssen auch Dienstqualitätsrichtlinien (Quality of Service Policies) erstellt werden, die den DSCP-Code angeben, der jedem Portbereich zugeordnet werden soll. Für Microsoft lync Server 2013 bedeutet das normalerweise das Erstellen von zwei Richtlinien: eine für Audio und eine für Video.

Dienst Qualitätsrichtlinien werden am einfachsten erstellt und mithilfe von Gruppenrichtlinien verwaltet. (Dieselben Richtlinien können auch mithilfe von lokalen Sicherheitsrichtlinien erstellt werden. Dies erfordert jedoch, dass Sie das gleiche Verfahren auf jedem einzelnen Computer wiederholen müssen.) Die anfänglichen QoS-Richtlinien (eine für Audio und eine für Video) sollten nur auf lync Server Computern angewendet werden, auf denen der Konferenzserver, der Anwendungsserver und/oder Vermittlungsserver Dienste ausgeführt werden. Wenn sich alle diese Computer in derselben Active Directory Organisationseinheit befinden, können Sie einfach das neue Gruppenrichtlinienobjekt (Group Policy Object, GPO) dieser Organisationseinheit zuweisen. Alternativ können Sie andere Schritte ausführen, um die neue Richtlinie auf die angegebenen Computer abzuzielen. Beispielsweise können Sie die entsprechenden Computer in einer Sicherheitsgruppe platzieren und dann das GPO mithilfe der Gruppenrichtlinien-Sicherheitsfilterung nur auf diese Sicherheitsgruppe anwenden.

Um eine Dienst Qualitätsrichtlinie für die Audioverwaltung zu erstellen, melden Sie sich an einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie im **Startmenü**auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Beispiel: Wenn sich all Ihre Lync Server-Computer in einer Organisationseinheit mit dem Namen "Lync Server" befinden, sollte die neue Richtlinie in der Organisationseinheit "Lync Server" erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen**.

3.  Geben Sie im Dialogfeld **neues GPO** in das Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync Server QoS**), und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **richtlinienbasierter QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie ein (beispielsweise **lync Server QoS**). Klicken Sie auf ** 	DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Deaktivieren Sie **Ausgehende Drosselungsrate angeben**, und klicken Sie auf **Weiter**.

7.  Vergewissern Sie sich, dass die Option **Alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **Weiter**. Damit wird ganz einfach sichergestellt, dass alle Anwendungen mit den Paketen aus dem angegebenen Portbereich mit dem angegebenen DSCP-Code übereinstimmen.

8.  Vergewissern Sie sich auf der dritten Seite, dass die beiden Optionen ****"Beliebige Quell-IP-Adresse" und "Beliebige Ziel-IP-Adresse" ausgewählt sind, und klicken Sie dann auf **Weiter**. Mit diesen beiden Einstellungen wird sichergestellt, dass die Pakete verwaltet werden, unabhängig davon, von welchem Computer (IP-Adresse) diese Pakete gesendet wurden und welcher Computer (IP-Adresse) diese Pakete erhalten wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer an** die Option **Von dieser Quellportnummer bzw. diesem -bereich** aus. Geben Sie im zugehörigen Textfeld den Typ des Portbereichs ein, der für die Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports ab Port 49152 bis zum Port 57500 für den Audiodatenverkehr reserviert haben, geben Sie den Portbereich mithilfe des folgenden Formats ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

<div>


> [!NOTE]  
> Der DSCP-Wert 46 ist ein etwas beliebiger Wert: obwohl der DSCP-Wert 46 oft verwendet wird, um Audiopakete zu markieren, müssen Sie den DSCP-Wert 46 nicht zur Audiokommunikation verwenden. Wenn Sie bereits die Dienstqualität implementiert haben und Sie einen anderen DSCP-Code für Audiodaten verwenden (z. B. DSCP-Wert 40), dann sollten Sie die Dienstqualitätsrichtlinie zur Verwendung desselben Codes (d. h. 40 für Audiodaten) konfigurieren. Wenn Sie dabei sind, die Dienstqualität (Quality of Service) zu implentieren, wird empfohlen, den DSCP-Wert 46 für Audiodaten zu verwenden, da dieser Wert der am häufigsten verwendete Wert zur Markierung der Audiopakete ist.



</div>

Nachdem Sie die Dienstqualitätsrichtlinie für den Audio-Datenverkehr erstellt haben, sollten Sie anschließend eine zweite Richtlinie für den Video-Datenverkehr erstellen (und optional eine dritte Richtlinie zur Verwaltung des Datenverkehrs im Zusammenhang mit der Anwendungsfreigabe). Befolgen Sie dieselben grundlegenden Anweisungen zum Erstellen einer Richtlinie für Videodaten wie bei der Erstellung einer Audiorichtline. Folgendes sollte ersetzt werden:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Video**).

  - Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest. (Beachten Sie, dass Sie den DSCP-Wert 34 nicht verwenden müssen. Es ist lediglich erforderlich, dass ein anderer DSCP-Wert für Videodaten als für Audiodaten verwendet werden soll.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Video-Datenverkehr. Wenn Sie beispielsweise die Ports ab Port 57501 bis 65535 für den Video-Datenverkehr reserviert haben, legen Sie den Portbereich folgendermaßen fest: **57501:65535**.

Wenn Sie eine Richtlinie zur Verwaltung des Datenverkehrs im Zusammenhang mit der Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie erstellen und dabei Folgendes ersetzen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert auf **24** statt "46" fest. (Auch hier muss nicht unbedingt der DSCP-Wert 24 verwendet werden, der DSCP-Wert für Video muss sich lediglich von den für Audio und Video verwendeten Werten unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie z. B. die Ports 40803 bis 49151 für Anwendungsfreigabe reserviert haben, legen Sie den Portbereich folgendermaßen fest: **40803:49151**.

Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren lync Server Computern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

    Gpupdate.exe /force

Dieser Befehl kann in der lync Server-Verwaltungsshell oder in einem beliebigen Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird. Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie anschließend auf **Als Administrator ausführen**, um das Befehlsfenster mit den Anmeldeinformationen des Administrators auszuführen.

Führen Sie folgende Schritte aus, um zu überprüfen, ob die neuen QoS-Richtlinien angewendet wurden:

1.  Klicken Sie auf einem Lync Server-Computer auf **Start**, und klicken Sie dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor den Knoten **Computer**, erweitern Sie **\_HKEY lokaler\_Computer**, erweitern Sie **Software**, erweitern Sie **Richtlinien**, erweitern Sie **Microsoft**, erweitern Sie **Windows**, und klicken Sie dann auf **QoS**. Unter **QoS** sollten die Registrierungsschlüssel für jede einzelne der gerade von Ihnen erstellten QoS-Richtlinien angezeigt werden. Wenn Sie beispielsweise zwei neue Richtlinien (eine mit dem Namen "lync Server Audio QoS" und den anderen benannten lync Server-Video-QoS) erstellt haben, sollten Sie Registrierungseinträge für lync Server QoS von Audio-QoS und lync Server-Video erstellen.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein und drücken dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie dann Ihren Computer neu.

</div>

<span> </span>

</div>

</div>

</div>

