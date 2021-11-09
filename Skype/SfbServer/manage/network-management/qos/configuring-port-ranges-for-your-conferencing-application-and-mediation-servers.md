---
title: Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche und eine Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver konfigurieren.
ms.openlocfilehash: 9dfa3e7ccb5b69cd112911f700528cc6fc484d89
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856662"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver

In diesem Artikel wird beschrieben, wie Sie Portbereiche und eine Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver konfigurieren.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Um Quality of Service zu implementieren, sollten Sie identische Portbereiche für die Audio-, Video- und Anwendungsfreigabe auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern konfigurieren. Darüber hinaus dürfen sich diese Portbereiche in keiner Weise überlappen. Um ein einfaches Beispiel zu verwenden, verwenden Sie die Ports 10000 bis 10999 für Video auf Ihren Konferenzservern. Das bedeutet, dass Sie auch die Ports 10000 bis 10999 für Video auf Ihren Anwendungs- und Vermittlungsservern reservieren müssen. Wenn Sie dies nicht tun, funktioniert QoS nicht wie erwartet.

Nehmen Sie analog dazu an, dass die Ports 10000 bis 10999 für die Übertragung von Videos reserviert wurden, während für die Übertragung von Audiosignalen die Ports 10500 bis 11999 vorgesehen sind. Dies kann zu Problemen mit der Dienstqualität führen, weil sich die Portbereiche überschneiden. Bei QoS muss jede Modalität einen eindeutigen Satz von Ports aufweisen: Wenn Sie die Ports 10000 bis 10999 für Video verwenden, müssen Sie einen anderen Bereich verwenden (z. B. 11000 bis 11999 für Audio).

Standardmäßig überschneiden sich Audio- und Videoportbereiche in Skype for Business Server nicht. Die Portbereiche, die der Anwendungsfreigabe zugewiesen sind, überschneiden sich jedoch sowohl mit den Audio- als auch den Videoportbereichen. (Was wiederum bedeutet, dass keiner dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Konferenz-, Anwendungs- und Vermittlungsserver überprüfen, indem Sie die folgenden drei Befehle in der Skype for Business Server Verwaltungsshell ausführen:

  Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
  Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
  Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Wie Sie in den vorherigen Befehlen sehen können, werden jedem Porttyp – Audio, Video und Anwendungsfreigabe – zwei separate Eigenschaftswerte zugewiesen: der Portstart und die Portanzahl. Der Portstart gibt den ersten Port an, der für diese Modalität verwendet wird. Wenn der Start des Audioports beispielsweise gleich 50000 ist, bedeutet dies, dass der erste für Audiodatenverkehr verwendete Port Port 50000 ist. Wenn die Anzahl der Audioports 2 ist (was kein gültiger Wert ist, hier jedoch zu Veranschaulichungszwecken verwendet wird), bedeutet dies, dass nur zwei Ports für Audio zugewiesen werden. Wenn der erste Port Port 50000 ist und insgesamt zwei Ports vorhanden sind, bedeutet dies, dass der zweite Port Port 50001 sein muss (Portbereiche müssen zusammenhängend sein). Daher würde der Portbereich für Audio zwischen 50000 und 50001 (einschließlich) liegen.<BR><br>Beachten Sie ferner, dass Anwendungs- und Vermittlungsserver QoS nur für Audio unterstützen. Es ist nicht erforderlich, die Video- oder Anwendungsfreigabeports in Ihren Anwendungs- oder Vermittlungsservern zu ändern.

Wenn Sie die vorherigen drei Befehle ausführen, sehen Sie, dass die Standardportwerte für Skype for Business Server wie folgt konfiguriert sind:

<table>
<colgroup>
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

Wie bereits erwähnt, sollten Sie bei der Konfiguration Skype for Business Server Ports für QoS sicherstellen, dass: 1) Audioporteinstellungen auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern identisch sind. und 2) Portbereiche überlappen sich nicht. Wenn Sie sich die obige Tabelle genauer ansehen, werden Sie feststellen, dass die Portbereiche für die drei Servertypen identisch sind. Beispielsweise ist der Startaudioport auf Port 49152 für jeden Servertyp festgelegt, und die Gesamtzahl der Ports, die für Audio auf jedem Server reserviert sind, ist ebenfalls identisch: 8348. Die Portbereiche überschneiden sich jedoch: Audioports beginnen bei Port 49152, aber die Ports werden für die Anwendungsfreigabe reserviert. Um quality of Service optimal zu nutzen, sollte die Anwendungsfreigabe neu konfiguriert werden, um einen eindeutigen Portbereich zu verwenden. Beispielsweise können Sie die Anwendungsfreigabe so konfigurieren, dass sie an Port 40803 beginnt und 8348 Ports verwendet. (Warum 8348 Ports? Wenn Sie diese Werte zusammen hinzufügen – 40803 + 8348 –, bedeutet dies, dass die Anwendungsfreigabe die Ports 40803 bis Port 49150 verwendet. Da audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie Ihre Änderung mithilfe des Cmdlets Set-CsConferencingServer vornehmen. Diese Änderungen müssen nicht auf den Anwendungsservern oder auf den Vermittlungsservern durchgeführt werden, da sie keinen Datenverkehr von Anwendungsfreigaben verarbeiten. Sie müssen die Portwerte auf diesen Servern lediglich ändern, wenn Sie die Ports für die Übertragung von Audiosignalen neu zuweisen.

Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie einen Befehl wie den folgenden in der Skype for Business Server Verwaltungsshell aus:

  **Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348**

Wenn Sie diese Änderungen auf allen Konferenzservern vornehmen möchten, können Sie stattdessen folgenden Befehl ausführen:

  **Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_. Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}**

Nach dem Ändern der Porteinstellungen sollten Sie jeden von den Änderungen betroffenen Dienst beenden und dann neu starten.

Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen nicht notwendigerweise den gleichen Portbereich verwenden. Allerdings müssen auf allen Servern unbedingt eindeutige Portbereiche reserviert werden. Wenn Sie jedoch die gleichen Portbereiche auf allen Servern verwenden, wird dadurch die Verwaltung deutlich erleichtert.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren einer Quality of Service-Richtlinie in Skype for Business Server für Konferenz-, Anwendungs- und Vermittlungsserver

Das Konfigurieren von Portbereichen vereinfacht die Verwendung der Dienstqualität (Quality of Service), indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (z. B. der gesamte Audio-Datenverkehr) über dieselben Ports übermittelt wird. Dadurch ist es für das System einfacher, ein bestimmtes Paket zu identifizieren und zu markieren: Wenn der Port 49152 für den Audio-Datenverkehr reserviert ist, kann jedes beliebige Paket, das über den Port 49152 übermittelt wird, mit einem DSCP-Code markiert werden. Dieser Code gibt an, dass es sich dabei um ein Audiopaket handelt. Anschließend können diese Router das Paket als ein Audiopaket identifizieren und ihm eine höhere Priorität als unmarkierte Pakete verleihen (wie z. B. Pakete, die Dateien von einem Server zu einem anderen Server kopieren).

Die einfache Einschränkung von Ports auf eine bestimmte Art von Datenverkehr führt nicht dazu, dass die Pakete über die Ports, die mit dem entsprechenden DSCP-Code markiert sind, übermittelt werden. Zusätzlich zum Definieren von Portbereichen müssen Sie auch Quality of Service-Richtlinien erstellen, die den DSCP-Code angeben, der jedem Portbereich zugeordnet werden soll. Bei Skype for Business Server bedeutet dies in der Regel das Erstellen von zwei Richtlinien: eine für Audio und eine für Video.

Quality of Service-Richtlinien können am einfachsten mithilfe von Gruppenrichtlinien erstellt und verwaltet werden. (Dieselben Richtlinien können auch mithilfe lokaler Sicherheitsrichtlinien erstellt werden. Dies erfordert jedoch, dass Sie auf jedem Computer dieselbe Prozedur wiederholen.) Ihre anfänglichen QoS-Richtlinien (eine für Audio und eine für Video) sollten nur auf Skype for Business Server Computer angewendet werden, auf denen der Konferenzserver, anwendungsserver und/oder Vermittlungsserverdienste ausgeführt werden. Wenn sich alle diese Computer in derselben Active Directory-ORGANISATIONSEINHEIT befinden, können Sie dieser OE einfach das neue Gruppenrichtlinienobjekt (Group Policy Object, GPO) zuweisen. Alternativ können Sie andere Schritte ausführen, um die neue Richtlinie auf die angegebenen Computer zu adressieren. Beispielsweise können Sie die entsprechenden Computer in einer Sicherheitsgruppe platzieren und dann die Gruppenrichtliniensicherheitsfilterung verwenden, um das Gruppenrichtlinienobjekt nur auf diese Sicherheitsgruppe anzuwenden.

Um eine Quality of Service-Richtlinie für die Audioverwaltung zu erstellen, melden Sie sich bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (klicken Sie auf **"Start",** zeigen Sie auf **"Verwaltungstools",** und klicken Sie dann auf **"Gruppenrichtlinienverwaltung"),** und führen Sie dann das folgende Verfahren aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Skype for Business Server Computer in einer OE mit dem Namen Skype for Business Server befinden, sollte die neue Richtlinie in der Skype for Business Server OU erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **"Gruppenrichtlinienobjekt in dieser Domäne erstellen", und verknüpfen Sie es hier.**

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das neue Gruppenrichtlinienobjekt in das **Feld "Name"** ein (z. **B. Skype for Business Server QoS),** und klicken Sie dann auf **"OK".**

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **"Bearbeiten".**

5.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **"Richtlinienbasierter QoS"** auf der ersten Seite einen Namen für die neue Richtlinie (z. **B. Skype for Business Server QoS)** in das **Feld "Name"** ein. Klicken Sie auf **DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt sind, und klicken Sie dann auf **"Weiter".** Damit wird ganz einfach sichergestellt, dass alle Anwendungen mit den Paketen aus dem angegebenen Portbereich mit dem angegebenen DSCP-Code übereinstimmen.

8.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Beliebige Quell-IP-Adresse als auch eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **"Weiter".** Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

9.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.

10. Wählen Sie unter der Überschrift **"Quellportnummer angeben"** die Option **"Von diesem Quellport oder -bereich" aus.** Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports 49152 bis Ports 57500 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **49152:57500.** Klicken Sie auf **Fertig stellen**.

> [!NOTE]  
> Der DSCP-Wert 46 ist ein etwas beliebiger Wert: obwohl der DSCP-Wert 46 oft verwendet wird, um Audiopakete zu markieren, müssen Sie den DSCP-Wert 46 nicht zur Audiokommunikation verwenden. Wenn Sie QoS bereits implementiert haben und einen anderen DSCP-Code für Audio verwenden (z. B. DSCP 40), sollten Sie Ihre Quality of Service-Richtlinie so konfigurieren, dass sie denselben Code verwendet (d. h. 40 für Audio). Wenn Sie dabei sind, die Dienstqualität (Quality of Service) zu implentieren, wird empfohlen, den DSCP-Wert 46 für Audiodaten zu verwenden, da dieser Wert der am häufigsten verwendete Wert zur Markierung der Audiopakete ist.

Nachdem Sie die QoS-Richtlinie für den Audiodatenverkehr erstellt haben, sollten Sie eine zweite Richtlinie für Videodatenverkehr (und optional eine dritte Richtlinie für die Verwaltung des Anwendungsfreigabedatenverkehrs) erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. **B. Skype for Business Server Video).**

  - Legen Sie den DSCP-Wert auf **34** statt "46" fest. (Sie müssen nicht unbedingt den DSCP-Wert 34 verwenden, der DSCP-Wert für Video muss sich lediglich von dem für Audio verwendeten Wert unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 57501 bis 65535 für Video reserviert haben, legen Sie den Portbereich auf folgendes fest: **57501:65535**.

Wenn Sie eine Richtlinie für die Verwaltung des Datenverkehrs für die Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie erstellen, die die folgenden Ersetzungen vornimmt:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. **B. Skype for Business Server Anwendungsfreigabe).**

  - Legen Sie den DSCP-Wert auf **24** statt "46" fest. (Auch hier muss nicht unbedingt der DSCP-Wert 24 verwendet werden, der DSCP-Wert für Video muss sich lediglich von den für Audio und Video verwendeten Werten unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf folgendes fest: **40803:49151**.

Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Skype for Business Server Computern aktualisiert wurde. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

  **Gpupdate.exe /force**

Dieser Befehl kann in der Skype for Business Server Verwaltungsshell oder in einem beliebigen Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird. Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie anschließend auf **Als Administrator ausführen**, um das Befehlsfenster mit den Anmeldeinformationen des Administrators auszuführen.

Führen Sie folgende Schritte aus, um zu überprüfen, ob die neuen QoS-Richtlinien angewendet wurden:

1.  Klicken Sie auf einem Skype for Business Server Computer auf **"Start"** und dann auf **"Ausführen".**

2.  Geben **Sie** im Dialogfeld Ausführen **regedit ein,** und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **computer**, **HKEY \_ LOCAL \_ MACHINE**, **software**, expand **Policies**, expand **Microsoft**, expand **Windows**, und klicken Sie dann auf **QoS**. Unter **QoS** sollten die Registrierungsschlüssel für jede einzelne der gerade von Ihnen erstellten QoS-Richtlinien angezeigt werden. Wenn Sie beispielsweise zwei neue Richtlinien erstellt haben (eine mit dem Namen Skype for Business Server Audio QoS und die andere mit dem Namen Skype for Business Server Video QoS), sollten Registrierungseinträge für Skype for Business Server Audio QoS und Skype for Business Server Video QoS angezeigt werden.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben **Sie** im Dialogfeld Ausführen **regedit ein,** und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **"HKEY \_ LOCAL \_ MACHINE",** **"SYSTEM",** **"CurrentControlSet",** **"Dienste"** und dann **"Tcpip".**

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Geben Sie nach dem Erstellen des neuen **Registrierungsschlüssels QoS** ein, und drücken Sie dann die EINGABETASTE, um die Taste umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Geben Sie nach dem Erstellen des neuen Registrierungswerts **"NLA nicht verwenden"** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie nicht auf **"NLA verwenden".** Geben **Sie** im Dialogfeld Zeichenfolge bearbeiten im **Feld Wert** den Wert **1** ein, und klicken Sie dann auf **OK.**

7.  Schließen Sie den Registrierungs-Editor, und starten Sie ihren Computer neu.
