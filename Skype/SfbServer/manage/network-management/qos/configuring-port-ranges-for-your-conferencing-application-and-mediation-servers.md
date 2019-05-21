---
title: Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Konferenz-, Anwendungs-und Vermittlungsserver
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche und eine Dienst Qualitätsrichtlinie für Konferenz-, Anwendungs-und Vermittlungsserver konfigurieren.
ms.openlocfilehash: e0bd6092792a9ed813aadecc004f58830bc5b133
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279462"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Konferenz-, Anwendungs-und Vermittlungsserver

In diesem Artikel wird beschrieben, wie Sie Portbereiche und eine Dienst Qualitätsrichtlinie für Konferenz-, Anwendungs-und Vermittlungsserver konfigurieren.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Zur Implementierung von Quality of Service sollten Sie identische Portbereiche für die Audio-, Video-und Anwendungsfreigabe auf Ihren Konferenz-, Anwendungs-und Vermittlungsservern konfigurieren. Darüber hinaus dürfen sich diese Portbereiche in keiner Weise überlappen. Wenn Sie ein einfaches Beispiel verwenden möchten, nehmen Sie an, dass Sie die Ports 10000 bis 10999 für Video auf Ihren Konferenzservern verwenden. Das bedeutet, dass Sie auch Ports 10000 bis 10999 für Video auf Ihren Anwendungs-und Vermittlungsservern reservieren müssen. Wenn dies nicht der Fall ist, funktioniert QoS nicht erwartungsgemäß.

Nehmen Sie entsprechend an, dass Sie die Ports 10000 bis 10999 für Video reservieren, und dann die Ports 10500 bis 11999 für Audio reservieren. Dies kann zu Problemen bei der Dienstqualität führen, da sich die Portbereiche überlappen. Bei QoS muss jede Modalität über einen eindeutigen Satz von Ports verfügen: Wenn Sie Ports 10000 bis 10999 für Video verwenden, müssen Sie einen anderen Bereich verwenden (beispielsweise 11000 bis 11999 für Audio).

Standardmäßig überlappen sich Audio-und Video-Portbereiche nicht in Skype for Business Server; die der Anwendungsfreigabe zugewiesenen Portbereiche überlappen sich jedoch sowohl mit dem Audio-als auch dem Video-Portbereich. (Was wiederum bedeutet, dass keiner dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Ihre Konferenz-, Anwendungs-und Vermittlungsserver überprüfen, indem Sie in der Skype for Business Server-Verwaltungsshell die folgenden drei Befehle ausführen:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Wie in den vorstehenden Befehlen zu sehen ist, werden jedem Porttyp – Audio, Video und Anwendungsfreigabe – zwei getrennte Eigenschaftswerte zugewiesen: der Port Start und die Portanzahl. Der Port Start gibt den ersten Port an, der für diese Modalität verwendet wird; Wenn beispielsweise der Audioport-Start gleich 50000 ist, bedeutet dies, dass der erste Port für den Audioverkehr Port 50000 ist. Wenn die Anzahl der Audioanschlüsse 2 ist (was kein gültiger Wert ist, aber hier zur Veranschaulichung verwendet wird), bedeutet dies, dass nur zwei Ports für Audio reserviert sind. Wenn der erste Port Port 50000 ist und insgesamt zwei Ports vorhanden sind, bedeutet dies, dass der zweite Port Port 50001 sein muss (Portbereiche müssen zusammenhängend sein). Infolgedessen wäre der Portbereich für Audio die Ports 50000 bis 50001 inklusive.<BR><br>Beachten Sie auch, dass Anwendungsserver und Vermittlungsserver nur QoS für Audio unterstützen. Sie müssen die Video-oder Anwendungsfreigabe Anschlüsse auf Ihren Anwendungsservern oder Vermittlungsservern nicht ändern.

Wenn Sie die vorstehenden drei Befehle ausführen, sehen Sie, dass die Standard Port Werte für Skype for Business Server wie folgt konfiguriert sind:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Eigenschaft</th>
<th>Konferenz Server</th>
<th>Anwendungs Server</th>
<th>Vermittlungsserver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Wie bereits erwähnt, sollten Sie bei der Konfiguration von Skype for Business Server-Ports für QoS sicherstellen, dass: 1) audioporteinstellungen für Ihre Konferenz-, Anwendungs-und Vermittlungsserver identisch sind. und, 2) die Portbereiche überlappen sich nicht. Wenn Sie die obige Tabelle genau betrachten, sehen Sie, dass die Portbereiche für die drei Servertypen identisch sind. So ist beispielsweise der Start-Audioport auf Port 49152 für jeden Servertyp eingestellt, und die Gesamtanzahl der für Audio reservierten Ports auf jedem Server ist ebenfalls identisch: 8348. Die Portbereiche überlappen sich jedoch: Audioanschlüsse beginnen bei Port 49152, aber auch die Ports, die für die Anwendungsfreigabe reserviert sind. Um die Qualität des Diensts optimal zu nutzen, sollte die Anwendungsfreigabe neu konfiguriert werden, um einen eindeutigen Portbereich zu verwenden. So können Sie beispielsweise die Anwendungsfreigabe so konfigurieren, dass Sie bei Port 40803 startet und 8348-Ports verwendet. (Warum 8348-Ports? Wenn Sie diese Werte zusammen--40803 + 8348-hinzufügen, bedeutet dies, dass die Anwendungsfreigabe Ports 40803 über Port 49150 verwendet. Da Audioanschlüsse erst nach Port 49152 gestartet werden, haben Sie keine überlappenden Portbereiche mehr.)

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderung mithilfe des Cmdlets "Satz-CsConferencingServer" vornehmen. Diese Änderung muss nicht auf Ihren Anwendungsservern oder auf Ihren Vermittlungsservern vorgenommen werden, da diese Server keinen Anwendungsfreigabe Verkehr verarbeiten. Sie müssen nur die Portwerte auf diesen Servern ändern, wenn Sie sich entscheiden, die für den Audioverkehr verwendeten Ports neu zuzuweisen.

Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie in der Skype for Business Server-Verwaltungsshell einen ähnlichen Befehl aus:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Wenn Sie diese Änderungen auf allen Konferenzservern vornehmen möchten, können Sie stattdessen diesen Befehl ausführen:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Nachdem Sie die Porteinstellungen geändert haben, sollten Sie jeden von den Änderungen betroffenen Dienst beenden und neu starten.

Es ist nicht zwingend erforderlich, dass Ihre Konferenzserver, Anwendungsserver und Vermittlungsserver exakt denselben Portbereich verwenden. die einzige echte Anforderung ist, dass Sie eindeutige Portbereiche auf allen ihren Servern beiseite legen. Die Verwaltung ist jedoch in der Regel einfacher, wenn Sie die gleichen Ports auf allen Servern verwenden.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren einer Quality of Service-Richtlinie in Skype for Business Server für Ihre Konferenz-, Anwendungs-und Vermittlungsserver

Durch die Konfiguration von Portbereichen wird die Verwendung von Quality of Service vereinfacht, indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (beispielsweise der gesamte Audioverkehr) durch denselben Satz von Ports übertragen wird. Dadurch ist es für das System einfach, ein gegebenes Paket zu erkennen und zu kennzeichnen: Wenn Port 49152 für den Audioverkehr reserviert ist, kann jedes Paket, das über Port 49152 reist, mit einem DSCP-Code gekennzeichnet werden, der angibt, dass es sich um ein audiopaket handelt. Dies ermöglicht es Routern wiederum, das Paket als audiopaket zu identifizieren und ihm eine höhere Priorität als nicht markierte Pakete zu geben (beispielsweise Pakete, mit denen eine Datei von einem Server auf einen anderen kopiert wird).

Die Beschränkung einer Reihe von Ports auf einen bestimmten Datenverkehr führt jedoch nicht dazu, dass Pakete, die mit dem entsprechenden DSCP-Code gekennzeichnet sind, durch diese Ports verlaufen. Neben dem Definieren von Portbereichen müssen Sie auch Quality of Service-Richtlinien erstellen, die den DSCP-Code angeben, der jedem Portbereich zugeordnet werden soll. Für Skype for Business Server bedeutet dies in der Regel das Erstellen von zwei Richtlinien: eine für Audio und eine für Video.

Dienst Qualitätsrichtlinien können mithilfe von Gruppenrichtlinien am einfachsten erstellt und verwaltet werden. (Dieselben Richtlinien können auch mithilfe von lokalen Sicherheitsrichtlinien erstellt werden. Dies erfordert jedoch, dass Sie auf jedem Computer dasselbe Verfahren wiederholen.) Ihre anfänglichen QoS-Richtlinien (eine für Audio-und eine für Video) sollten nur auf Skype for Business Server-Computer angewendet werden, auf denen der Konferenzserver, der Anwendungsserver und/oder die Vermittlungsserver Dienste ausgeführt werden. Wenn sich alle diese Computer in der gleichen Active Directory-Organisationseinheit befinden, können Sie der Organisationseinheit einfach das neue Gruppenrichtlinienobjekt (GPO) zuweisen. Sie können aber auch andere Schritte ausführen, um die neue Richtlinie auf die angegebenen Computer abzuzielen. So können Sie beispielsweise die entsprechenden Computer in einer Sicherheitsgruppe platzieren und dann die Gruppenrichtlinien-Sicherheitsfilterung verwenden, um das Gruppenrichtlinienobjekt nur für diese Sicherheitsgruppe anzuwenden.

Wenn Sie eine Quality of Service-Richtlinie für die Audioverwaltung erstellen möchten, melden Sie sich bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Skype for Business Server-Computer in einer OU mit dem Namen Skype for Business Server befinden, sollte die neue Richtlinie in der Skype for Business Server-OU erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.

3.  Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **Skype for Business Server QoS**), und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **richtlinienbasierter QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **Skype for Business Server QoS**) ein. Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest. Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.

7.  Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**. Dadurch wird einfach sichergestellt, dass alle Anwendungen Pakete aus dem angegebenen Portbereich mit dem angegebenen DSCP-Code abgleichen.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-als auch eine beliebige Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.

9.  Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **die Quellportnummer**aus, und wählen Sie **aus diesem Quell Port oder-Bereich aus**. Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 49152 über Ports 57500 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

> [!NOTE]  
> Der DSCP-Wert von 46 ist etwas willkürlich: Obwohl DSCP 46 häufig zum Markieren von Audiopaketen verwendet wird, müssen Sie DSCP 46 nicht für die Audiokommunikation verwenden. Wenn Sie bereits QoS implementiert haben und einen anderen DSCP-Code für Audio verwenden (beispielsweise DSCP 40), sollten Sie Ihre Dienst Qualitätsrichtlinie so konfigurieren, dass dieser Code verwendet wird (d. h., 40 für Audio). Wenn Sie gerade jetzt Quality of Service implementieren, empfiehlt es sich, DSCP 46 für Audio zu verwenden, einfach weil dieser Wert häufig zum Markieren von Audiopaketen verwendet wird.

Nachdem Sie die QoS-Richtlinie für den Audioverkehr erstellt haben, sollten Sie eine zweite Richtlinie für den Videoverkehr (und optional eine dritte Richtlinie für die Verwaltung des Anwendungsfreigabe Verkehrs) erstellen. Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype for Business Server-Video**).

  - Setzen Sie den DSCP-Wert auf **34** statt auf 46. (Beachten Sie, dass Sie keinen DSCP-Wert von 34 verwenden müssen. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 57501 bis 65535 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **57501:65535**.

Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs zu erstellen, müssen Sie eine dritte Richtlinie erstellen, die die folgenden Substitutionen vornimmt:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **Freigabe von Skype for Business Server-Anwendungen**).

  - Setzen Sie den DSCP-Wert auf **24** anstatt auf 46. (Sie müssen wiederum keinen DSCP-Wert von 24 verwenden. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für die Anwendungsfreigabe verwenden, als Sie für Audio oder Video verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **40803:49151**.

Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Skype for Business Server-Computern aktualisiert wurden. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpupdate.exe /force

Dieser Befehl kann in der Skype for Business Server-Verwaltungsshell oder in einem beliebigen Befehlsfenster, das unter Administratoranmeldeinformationen ausgeführt wird, ausgeführt werden. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Gehen Sie wie folgt vor, um zu überprüfen, ob die neuen QoS-Richtlinien angewendet wurden:

1.  Klicken Sie auf einem Skype for Business Server-Computer auf **Start**und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **Computer**, erweitern Sie **HKEY\_lokaler\_Computer**, erweitern Sie **Software**, erweitern Sie **Richtlinien**, erweitern Sie **Microsoft**, erweitern Sie **Windows**, und klicken Sie dann auf **QoS**. Unter **QoS** sollten Registrierungsschlüssel für jede der soeben erstellten QoS-Richtlinien angezeigt werden. Wenn Sie beispielsweise zwei neue Richtlinien (eine mit dem Namen Skype for Business Server Audio QoS und die andere mit dem Namen Skype for Business Server Video QoS) erstellt haben, sollten Sie Registrierungseinträge für Skype for Business Server Audio QoS und Skype for Business Server Video QoS sehen.

Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Geben Sie nach dem Erstellen des neuen Registrierungsschlüssels **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie Ihren Computer neu.
