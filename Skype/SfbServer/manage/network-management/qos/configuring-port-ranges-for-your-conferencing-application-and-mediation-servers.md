---
title: Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
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
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche und eine Richtlinie zur Dienstqualität für Konferenz-, Anwendungs- und Vermittlungsserver konfigurieren.
ms.openlocfilehash: 8c65e36528615aca181b6aac17aab844c1a4d206
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800125"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver

In diesem Artikel wird beschrieben, wie Sie Portbereiche und eine Richtlinie zur Dienstqualität für Konferenz-, Anwendungs- und Vermittlungsserver konfigurieren.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Zum Implementieren der Dienstqualität sollten Sie identische Portbereiche für Audio, Video und Anwendungsfreigabe auf Den Konferenz-, Anwendungs- und Vermittlungsservern konfigurieren. darüber hinaus dürfen sich diese Portbereiche in keinem Fall überschneiden. Um ein einfaches Beispiel zu verwenden, verwenden Sie die Ports 10000 bis 10999 für Video auf Ihren Konferenzservern. Das bedeutet, dass Sie auch die Ports 10000 bis 10999 für Video auf den Anwendungs- und Vermittlungsservern reservieren müssen. Andern falls nicht, funktioniert QoS nicht wie erwartet.

Nehmen Sie analog dazu an, dass die Ports 10000 bis 10999 für die Übertragung von Videos reserviert wurden, während für die Übertragung von Audiosignalen die Ports 10500 bis 11999 vorgesehen sind. Dies kann zu Problemen mit der Dienstqualität führen, weil sich die Portbereiche überschneiden. Bei QoS muss jede Modalität einen eindeutigen Satz von Ports haben: Wenn Sie die Ports 10000 bis 10999 für Video verwenden, müssen Sie einen anderen Bereich verwenden (z. B. 11000 bis 11999 für Audio).

Standardmäßig überlappen die Audio- und Videoportbereiche in Skype for Business Server nicht. Die der Anwendungsfreigabe zugewiesenen Portbereiche überschneiden sich jedoch mit den Audio- und Videoportbereichen. (Was wiederum bedeutet, dass keiner dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Ihre Konferenz-, Anwendungs- und Vermittlungsserver überprüfen, indem Sie die folgenden drei Befehle in der Skype for Business Server-Verwaltungsshell ausführen:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Wie Sie in den vorherigen Befehlen sehen können, werden jedem Porttyp – Audio, Video und Anwendungsfreigabe – zwei separate Eigenschaftswerte zugewiesen: der Portstart und die Portanzahl. Der Portstart gibt den ersten Port an, der für diese Modalität verwendet wird. Wenn der Start des Audioports beispielsweise gleich 50.000 ist, bedeutet dies, dass port 50000 der erste Port ist, der für den Audiodatenverkehr verwendet wird. Wenn die Anzahl der Audioports 2 ist (dies ist kein gültiger Wert, wird hier jedoch zur Veranschaulichung verwendet), bedeutet dies, dass nur zwei Ports für Audio zugewiesen werden. Wenn der erste Port Port 50000 ist und insgesamt zwei Ports zur Verfügung stehen, bedeutet dies, dass der zweite Port Port 50001 sein muss (Portbereiche müssen zusammenhängend sein). Der Portbereich für Audio würde also die Ports 50000 bis einschließlich 50001 sein.<BR><br>Beachten Sie ferner, dass Anwendungs- und Vermittlungsserver QoS nur für Audio unterstützen. Es ist nicht erforderlich, die Video- oder Anwendungsfreigabeports in Ihren Anwendungs- oder Vermittlungsservern zu ändern.

Wenn Sie die vorherigen drei Befehle ausführen, werden Sie sehen, dass die Standardportwerte für Skype for Business Server wie hier beschrieben konfiguriert sind:

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
<th>Konferenzserver</th>
<th>Anwendungsserver</th>
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

Wie bereits erwähnt, sollten Sie beim Konfigurieren von Skype for Business #A0 für QoS sicherstellen, dass: 1) Audioporteinstellungen auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern identisch sind. und 2) Portbereiche nicht überlappen. Wenn Sie sich die vorstehende Tabelle genauer betrachten, werden Sie sehen, dass die Portbereiche für die drei Servertypen identisch sind. Beispielsweise ist der Startaudioport auf Port 49152 auf jedem Servertyp festgelegt, und die Gesamtzahl der Ports, die für Audio auf jedem Server reserviert sind, ist ebenfalls identisch: 8348. Die Portbereiche überschneiden sich jedoch: Audioports beginnen an Port 49152, aber auch die Ports, die für die Anwendungsfreigabe festgelegt sind. Um die Dienstqualität optimal zu nutzen, sollte die Anwendungsfreigabe für die Verwendung eines eindeutigen Portbereichs neu konfiguriert werden. Beispielsweise können Sie die Anwendungsfreigabe so konfigurieren, dass sie an Port 40803 beginnt und 8348 Ports verwendet. (Warum 8348 Ports? Wenn Sie diese Werte zusammen hinzufügen – 40803 + 8348 –, bedeutet dies, dass die Anwendungsfreigabe die Ports 40803 bis Port 49150 verwendet. Da Audioports erst ab Port 49152 beginnen, werden keine überlappenden Portbereiche mehr verwendet.)

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderung mithilfe des cmdlets Set-CsConferencingServer nehmen. Diese Änderungen müssen nicht auf den Anwendungsservern oder auf den Vermittlungsservern durchgeführt werden, da sie keinen Datenverkehr von Anwendungsfreigaben verarbeiten. Sie müssen die Portwerte auf diesen Servern lediglich ändern, wenn Sie die Ports für die Übertragung von Audiosignalen neu zuweisen.

Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell aus:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Wenn Sie diese Änderungen auf allen Konferenzservern vornehmen möchten, können Sie stattdessen den folgenden Befehl ausführen:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Nach dem Ändern der Porteinstellungen sollten Sie jeden von den Änderungen betroffenen Dienst beenden und dann neu starten.

Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen nicht notwendigerweise den gleichen Portbereich verwenden. Allerdings müssen auf allen Servern unbedingt eindeutige Portbereiche reserviert werden. Wenn Sie jedoch die gleichen Portbereiche auf allen Servern verwenden, wird dadurch die Verwaltung deutlich erleichtert.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren einer Dienstqualitätsrichtlinie in Skype for Business Server für Ihre Konferenz-, Anwendungs- und Vermittlungsserver

Das Konfigurieren von Portbereichen vereinfacht die Verwendung der Dienstqualität (Quality of Service), indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (z. B. der gesamte Audio-Datenverkehr) über dieselben Ports übermittelt wird. Dadurch ist es für das System einfacher, ein bestimmtes Paket zu identifizieren und zu markieren: Wenn der Port 49152 für den Audio-Datenverkehr reserviert ist, kann jedes beliebige Paket, das über den Port 49152 übermittelt wird, mit einem DSCP-Code markiert werden. Dieser Code gibt an, dass es sich dabei um ein Audiopaket handelt. Anschließend können diese Router das Paket als ein Audiopaket identifizieren und ihm eine höhere Priorität als unmarkierte Pakete verleihen (wie z. B. Pakete, die Dateien von einem Server zu einem anderen Server kopieren).

Die einfache Einschränkung von Ports auf eine bestimmte Art von Datenverkehr führt nicht dazu, dass die Pakete über die Ports, die mit dem entsprechenden DSCP-Code markiert sind, übermittelt werden. Zusätzlich zum Definieren von Portbereichen müssen Sie auch Quality of Service-Richtlinien erstellen, die den zu jedem Portbereich zugeordneten Code für den Dienst für die Dienstqualität angeben. Für Skype for Business Server bedeutet dies in der Regel, zwei Richtlinien zu erstellen: eine für Audio und eine für Video.

Richtlinien für die Dienstqualität werden am einfachsten mithilfe von Gruppenrichtlinien erstellt und verwaltet. (Dieselben Richtlinien können auch mithilfe lokaler Sicherheitsrichtlinien erstellt werden. Dies erfordert jedoch, dass Sie dasselbe Verfahren auf jedem Computer wiederholen.) Ihr anfänglicher Satz von QoS-Richtlinien (eine für Audio und eine für Video) sollte nur auf Skype for Business Server-Computer angewendet werden, auf denen konferenzserver, Anwendungsserver und/oder Vermittlungsserverdienste ausgeführt werden. Wenn sich alle diese Computer in derselben Active Directory-OU befinden, können Sie dieser Organisationseinheit einfach das neue Gruppenrichtlinienobjekt (Group Policy Object, GPO) zuweisen. Alternativ können Sie andere Schritte ausführen, um die neue Richtlinie auf die angegebenen Computer zu zielen. Beispielsweise können Sie die entsprechenden Computer in einer Sicherheitsgruppe platzieren und dann die Gruppenrichtliniensicherheitsfilterung verwenden, um das Gruppenrichtlinienobjekt nur auf diese Sicherheitsgruppe anzuwenden.

Um eine Quality of Service-Richtlinie für die Audioverwaltung zu erstellen, melden Sie sich an einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (klicken Sie **auf "Start",** zeigen Sie auf **"Verwaltung"** und dann auf **"Gruppenrichtlinienverwaltung"),** und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Skype for Business Server-Computer in einer Organisationseinheit mit dem Namen Skype for Business Server befinden, sollte die neue Richtlinie in der Organisationseinheit Skype for Business Server erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf "Gruppenrichtlinienobjekt in dieser Domäne erstellen" und verknüpfen **Sie es hier.**

3.  Geben Sie im Dialogfeld **Neues** Gruppenrichtlinienobjekt im Feld **"Name"** einen Namen für das neue Gruppenrichtlinienobjekt ein (z. B. **Skype for Business Server QoS),** und klicken Sie dann auf **"OK".**

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

6.  Geben Sie auf der ersten Seite im richtlinienbasierten Dialogfeld **QoS** einen Namen für die neue Richtlinie (z. B. **Skype for Business Server QoS)** in das Feld **"Name"** ein. Klicken Sie auf **DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Stellen Sie auf der nächsten Seite sicher, **dass** alle Anwendungen ausgewählt sind, und klicken Sie dann auf **"Weiter".** Damit wird ganz einfach sichergestellt, dass alle Anwendungen mit den Paketen aus dem angegebenen Portbereich mit dem angegebenen DSCP-Code übereinstimmen.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl "Beliebige Quell-IP-Adresse" als auch **"Beliebige Ziel-IP-Adresse"** ausgewählt sind, und klicken Sie dann auf **"Weiter".** Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die von Skype for Business Server und seinen Clientanwendungen am häufigsten verwendet werden.

10. Wählen Sie unter der **Überschrift "Quellportnummer angeben"** **aus diesem Quellport oder -bereich aus.** Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie z. B. die Ports 49152 bis 57500 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich im folgenden Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

> [!NOTE]  
> Der DSCP-Wert 46 ist ein etwas beliebiger Wert: obwohl der DSCP-Wert 46 oft verwendet wird, um Audiopakete zu markieren, müssen Sie den DSCP-Wert 46 nicht zur Audiokommunikation verwenden. Wenn Sie QoS bereits implementiert haben und einen anderen -DSCP-Code für Audio verwenden (z. B. DSCP 40), sollten Sie Ihre Quality of Service-Richtlinie so konfigurieren, dass derselbe Code verwendet wird (d. h. 40 für Audio). Wenn Sie dabei sind, die Dienstqualität (Quality of Service) zu implentieren, wird empfohlen, den DSCP-Wert 46 für Audiodaten zu verwenden, da dieser Wert der am häufigsten verwendete Wert zur Markierung der Audiopakete ist.

Nachdem Sie die QoS-Richtlinie für Audiodatenverkehr erstellt haben, sollten Sie eine zweite Richtlinie für Videodatenverkehr (und optional eine dritte Richtlinie zum Verwalten des Anwendungsfreigabedatenverkehrs) erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Skype for Business Server Video).**

  - Legen Sie den DSCP-Wert auf **34** statt "46" fest. (Sie müssen nicht unbedingt den DSCP-Wert 34 verwenden, der DSCP-Wert für Video muss sich lediglich von dem für Audio verwendeten Wert unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 57501 bis 65535 für Video reserviert haben, legen Sie den Portbereich auf **57501:65535**.

Wenn Sie eine Richtlinie für die Verwaltung des Datenverkehrs zur Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie erstellen, die die folgenden Ersetzungen vor sich hat:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Skype for Business Server Application Sharing).**

  - Legen Sie den DSCP-Wert auf **24** statt "46" fest. (Auch hier muss nicht unbedingt der DSCP-Wert 24 verwendet werden, der DSCP-Wert für Video muss sich lediglich von den für Audio und Video verwendeten Werten unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf **40803:49151**.

Die von Ihnen erstellten neuen Richtlinien werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Skype for Business Server-Computern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

    Gpupdate.exe /force

Dieser Befehl kann in der Skype for Business Server-Verwaltungsshell oder in einem beliebigen Befehlsfenster ausgeführt werden, das mit Administratoranmeldeinformationen ausgeführt wird. Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie anschließend auf **Als Administrator ausführen**, um das Befehlsfenster mit den Anmeldeinformationen des Administrators auszuführen.

Führen Sie folgende Schritte aus, um zu überprüfen, ob die neuen QoS-Richtlinien angewendet wurden:

1.  Klicken Sie auf einem Computer mit Skype for Business Server auf **"Start"** und dann auf **"Ausführen".**

2.  Geben Sie **im** Dialogfeld Ausführen **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **Computer**, **erweitern Sie HKEY LOCAL \_ \_ MACHINE**, erweitern **Sie SOFTWARE**, **erweitern** Sie **"Richtlinien",** erweitern Sie Microsoft, erweitern **Sie Windows,** und klicken Sie dann **auf QoS**. Unter **QoS** sollten die Registrierungsschlüssel für jede einzelne der gerade von Ihnen erstellten QoS-Richtlinien angezeigt werden. Wenn Sie beispielsweise zwei neue Richtlinien erstellt haben (eine mit dem Namen Skype for Business Server Audio QoS und die andere mit dem Namen Skype for Business Server Video QoS), sollten Registrierungseinträge für Skype for Business Server Audio QoS und Skype for Business Server Video QoS angezeigt werden.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben Sie **im** Dialogfeld Ausführen **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY \_ LOCAL \_ MACHINE**, **erweitern Sie SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste,** und erweitern Sie dann **Tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben **Sie "NLA** nicht verwenden" ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken **Sie auf "NLA nicht verwenden".** Geben Sie im **Dialogfeld Zeichenfolge** bearbeiten  im Feld "Wert" den Wert **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.
