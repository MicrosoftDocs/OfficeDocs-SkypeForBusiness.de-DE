---
title: Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Mediation Server
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel wird das Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Mediation Server beschrieben.
ms.openlocfilehash: 29685029580271462e090da7fa82cd8d416e83e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913363"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Mediation Server

In diesem Artikel wird das Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Mediation Server beschrieben.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Zum Implementieren der Quality of Service, sollten Sie identische Portbereiche für Audio-, Video- und die Anwendungsfreigabe auf Ihren Servern Konferenz-, Anwendungs- und Vermittlungsserver konfigurieren. Außerdem müssen diese Portbereiche keinerlei nicht überlappen. Um ein einfaches Beispiel zu verwenden, nehmen Sie an, mit denen Sie Ports 10000 über 10999 für Video auf Ihrem Konferenzserver. Dies bedeutet, dass Sie auch Ports 10000 über 10999 für Video auf Ihre Anwendung und Mediation Server reservieren müssen. Wenn Sie nicht der Fall ist, wird QoS nicht wie erwartet funktionieren.

Angenommen Sie, dass Sie Ports 10000 über 10999 für Video, aber Reserve Ports 10500 über 11999 für Audio reservieren. Dadurch kann Probleme für Quality of Service, entstehen, da der Port Überlappung ranges. Mit QoS, jede Modalität angegeben werden muss einen eindeutigen Satz von Ports haben: Wenn Sie Ports 10000 über 10999 für Video verwenden, müssen Sie einen anderen Bereich (beispielsweise 11000 über 11999, für Audio) verwenden.

In der Standardeinstellung überschneiden Audio- und Videodaten Portbereiche in Skype für Business Server sich nicht; die Anwendungsfreigabe überschneiden sich mit den Audio- und Videodaten Portbereiche jedoch die Portbereiche zugewiesen. (, Also wiederum, dass keine der folgenden Bereiche eindeutig sind.) Sie können die vorhandenen Portbereiche für die Konferenz-, Anwendungs- und Mediation Server durch Ausführen der folgenden drei Befehle in der Skype für Business Server-Verwaltungsshell überprüfen:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Wie Sie in den vorstehenden Befehlen sehen können, wird jeder Anschlusstyp – Audio-, Video- und Anwendungsfreigabe – zwei separate Eigenschaftswerte zugewiesen: der Anfang des Portbereichs und die Portanzahl. Der Anfang des Portbereichs gibt an, der ersten für diese Modalität verwendete Port. Beispielsweise ist audio Port starten, die das bedeutet, dass 50000 gleich der erste für audio-Datenverkehr verwendete Port Port 50000. Wenn die Portanzahl der audio-2 ist (Dies ist kein gültiger Wert, jedoch wird hier zur Veranschaulichung verwendet), die bedeutet, dass nur zwei Ports für Audio reserviert werden. Wenn der erste Port Port 50000 ist, und es zwei Ports insgesamt sind, bedeutet dies, dass der zweite Port muss Port 50001 (verwendeten Bereiche werden über Port) sein. Daher wäre der Portbereich für Audio Ports 50000 bis 50001, inklusive.<BR><br>Beachten Sie außerdem, dass Anwendungsserver und Vermittlungsserver nur QoS für Audio; unterstützen Sie müssen nicht Video oder Anwendungsfreigabe Ports in Ihrem Anwendungsserver oder Vermittlungsservern zu ändern.

Wenn Sie die drei vorstehenden Befehle ausführen, sehen Sie sich, dass mit, dass die Werte des Standardport für Skype für Business Server wie folgt konfiguriert sind:

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

Wie bereits erwähnt, beim Konfigurieren von Skype für Business Server-Ports für QoS, sollten Sie sicherstellen, dass: 1) audio Porteinstellungen identisch sind, über Ihre Konferenz-, Anwendungs- und Mediation Server; und 2) Portbereiche überschneiden sich nicht. Wenn Sie genau der obigen Tabelle betrachten, sehen Sie sich, dass die Portbereiche über die drei Servertypen identisch sind. Beispielsweise der Anfangs-audio Port Port 49152 für jeden Servertyp festgelegt wurde und die Gesamtzahl der Ports für die Audiodaten in jedem Server reserviert auch identisch ist: 8348. Jedoch der Port ranges Überlappung: Anschlüsse an Port 49152 starten, aber damit werden die Ports stillgelegte für die Anwendungsfreigabe. Um eine optimale Nutzung der Quality of Service zu machen, sollte die Anwendungsfreigabe konfiguriert werden, um einen eindeutigen Portbereich verwenden. Beispielsweise konnten Sie konfigurieren, Anwendungsfreigabe, um an Port 40803 starten und 8348 Ports verwenden. (Warum 8348 Ports? Wenn Sie diese Werte – addieren bedeutet 40803 + 8348--, Anwendungsfreigabe Ports 40803 über Port 49150 verwendet werden. Da audio Ports nicht erst Port 49152 beginnen, müssen nicht mehr Sie alle Bereiche port überlappende.)

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderung vornehmen, mit dem Cmdlet Set-CsConferencingServer. Diese Änderung wird nicht auf Ihren Anwendungsservern oder auf Ihren Servern Mediation getroffen werden müssen, da diese Server keine Anwendung sharing Datenverkehr verarbeiten. Sie müssen nur Portwerte auf diesen Servern ändern, wenn Sie die verwendeten Ports für audio-Datenverkehr zuweisen möchten.

Führen Sie einen Befehl wie diesen aus innerhalb der Skype für Business Server-Verwaltungsshell aus, um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Wenn Sie diese Änderungen auf allen portservern vornehmen möchten, können Sie stattdessen diesen Befehl ausführen:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Nach dem Ändern der Einstellungen für externe Ports, sollten Sie beenden und starten jeden Dienst, der die Änderungen auswirkt.

Es ist nicht zwingend erforderlich, dass der Konferenzserver, Anwendungsserver und Vermittlungsserver denselben Portbereich freigeben. die Anforderung nur dann true ist, dass Sie eindeutige Portbereiche auf allen Servern reserviert. Verwaltung in der Regel werden jedoch einfacher, wenn Sie auf allen Servern den gleichen Satz von Ports verwenden.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren Sie eine Richtlinie Quality of Service in Skype für Business Server für Ihre Server Konferenz-, Anwendungs- und Vermittlungsserver

Konfigurieren von Portbereichen erleichtert die Verwendung von Quality of Service, indem sichergestellt wird, dass der gesamte Datenverkehr eines angegebenen Typs (beispielsweise alle audio-Datenverkehr) den gleichen Satz von Ports durchläuft. Dies vereinfacht das System zu identifizieren, und markieren ein bestimmtes Paket: Wenn Port 49152 für audio-Datenverkehr reserviert ist, und klicken Sie dann auf Reisen über Port 49152 Pakete kann mit einem DSCP-Code, der angibt, dass dies ein audio Paket ist markiert werden. Dies ermöglicht wiederum Router das Paket als ein audio-Paket zu identifizieren und ihm einer höheren Priorität als nicht markierten Pakete (beispielsweise Pakete verwendet, um eine Datei von einem Server in eine andere zu kopieren).

Allerdings führt einschränken einfach eine Reihe von Ports in einen bestimmten Typ Datenverkehr nicht zu Pakete Reisen durch diese Ports mit den entsprechenden DSCP-Code markiert werden. Zusätzlich zur Portbereiche definieren, müssen Sie auch Quality of Service-Richtlinien erstellen, die angeben, den DSCP-Code jede Portbereich zugeordnet werden soll. Für Skype für Business Server, das in der Regel bedeutet zwei Richtlinien erstellen: Audio und Video.

Von QoS-Richtlinien sind am einfachsten erstellt und verwaltet wird, mithilfe von Gruppenrichtlinien. (Diese dieselben Richtlinien können auch erstellt werden mithilfe von lokalen Sicherheitsrichtlinien. Erfordert allerdings, die Sie das gleiche Verfahren auf jedem Computer wiederholen.) Nur für Skype für Business Server-Computer, die mit der Konferenzserver, Anwendungsserver und/oder Mediation Server-Dienste werden soll Ihrer ersten Satz von QoS-Richtlinien (eins für Audio) und einen für Video angewendet. Wenn alle diese Computer in derselben Active Directory-Organisationseinheit befinden, können Sie einfach das neue Gruppenrichtlinienobjekt (GPO) an diese Organisationseinheit zuweisen. Alternativ können Sie andere Schritte, die die neue Richtlinie für die angegebene Computer als Ziel nutzen; Beispielsweise können Sie die entsprechenden Computer in einer Sicherheitsgruppe platzieren und dann anwenden das Gruppenrichtlinienobjekt nur zu, Sicherheit mithilfe von Gruppenrichtlinien sicherheitsfilterung.

Um eine Richtlinie Quality of Service für die Verwaltung von Audio zu erstellen, melden Sie sich an einem Computer, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Die Gruppenrichtlinien-Verwaltungskonsole**), und schließen Sie die folgende Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll. Beispielsweise alle Ihre Skype für Business Server-Computern in einer Organisationseinheit mit dem Namen Skype für Business Server befinden, sollte dann die neue Richtlinie in der Skype für Business Server Organisationseinheit erstellt werden.

2.  Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.

3.  Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das neue Gruppenrichtlinienobjekt im Feld **Name** (beispielsweise **Skype für Business Server QoS**), und klicken Sie dann auf **OK**.

4.  Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  In den Gruppenrichtlinienverwaltungs-Editor, erweitern Sie **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie (z. B. **Skype für Business Server QoS**) in das Feld **Name** ein. Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**. Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie auf der nächsten Seite stellen Sie sicher, dass **Alle Anwendungen** aktiviert ist, und klicken Sie dann auf **Weiter**. Einfach wird sichergestellt, dass alle Anwendungen Pakete aus dem angegebenen Portbereich durch den angegebenen DSCP-Code übereinstimmt.

8.  Stellen Sie auf der dritten Seite sicher, dass beide **einer beliebigen Quell-IP-Adresse und einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**. Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.

9.  Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die zwei Netzwerkprotokolle von Skype für Business Server und seine Clientanwendungen am häufigsten verwendet.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer** **aus dieser Quellport oder der Bereich**. Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert. Angenommen, wenn Sie Ports 49152 über Ports 57500 für audio-Datenverkehr reserviert ist, geben Sie den Portbereich, der mit diesem Format: **49152:57500**. Klicken Sie auf **Fertig stellen**.

> [!NOTE]  
> Der DSCP-Wert von 46 ist etwas beliebig: Obwohl DSCP 46 zum Markieren von audiopaketen häufig verwendet wird, müssen Sie nicht für die Audiokommunikation DSCP 46 verwenden. Wenn Sie einen anderen DSCP-Code für Audio (beispielsweise DSCP 40) verwenden, und Sie QoS bereits implementiert haben, sollten Sie Ihre Richtlinie Quality of Service, denselben Code (d. h., 40 für Audio) verwenden, um konfigurieren. Wenn Sie jetzt implementieren Quality of Service, es wird empfohlen, dass Sie DSCP 46 einfach für Audio verwenden, da dieses Werts häufig verwendet wird, um audiopaketen zu kennzeichnen.

Nachdem Sie die QoS-Richtlinie für den audio-Datenverkehr erstellt haben, sollten Sie dann eine zweite Policy für video-Datenverkehr (und optional eine dritte Richtlinie zur Verwaltung der freigegebenen Anwendung-Datenverkehr) erstellen. Führen Sie zum Erstellen einer Richtlinie für Video dieselbe grundlegende Prozedur, die Sie beim Erstellen der Richtlinie audio befolgt, wodurch dieser Platzhalter ein:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server-Video**).

  - Legen Sie den DSCP-Wert auf **34** anstelle von 46. (Beachten Sie, dass Sie keine DSCP-Wert von 34 verwenden. Die einzige Anforderung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr. Beispielsweise wenn Sie Ports 57501 und 65535 für Videodaten reserviert haben, setzen Sie den Portbereich hinzu: **57501:65535**.

Wenn Sie eine Richtlinie zur Verwaltung der Anwendungsfreigabe Anwendungsdatenverkehr erstellen möchten, müssen Sie eine dritte Richtlinie erstellen die folgenden Änderungen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server die Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert, auf **24** anstelle von 46. (In diesem Fall müssen Sie keinen DSCP-Wert von 24 verwenden. Die einzige Anforderung ist für die Verwendung eines anderen DSCP-Werts für die Anwendungsfreigabe, als Sie für Audio oder Video verwendet.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr. Beispielsweise wenn Sie Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich hinzu: **40803:49151**.

Die neuen Richtlinien erstellten werden nicht erst wirksam Gruppenrichtlinien auf Ihre Skype für Business Server-Computern aktualisiert wurde. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpupdate.exe /force

Dieser Befehl kann aus ausgeführt werden innerhalb der Skype für Business Server-Verwaltungsshell oder eine beliebige Befehlsfenster, die unter den Anmeldeinformationen eines Farmadministrators ausgeführt wird. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Um sicherzustellen, dass die neuen QoS-Richtlinien angewendet wurden, führen Sie folgende Schritte aus:

1.  Klicken Sie auf einen Skype für Business Server-Computer klicken Sie auf **Start**, und klicken Sie dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.

3.  Im Registrierungs-Editor, erweitern Sie **Computer**, erweitern Sie **HKEY\_lokale\_Computer**, erweitern Sie **SOFTWARE**, erweitern Sie **Richtlinien**, erweitern Sie **Microsoft**, erweitern Sie **Windows**, und klicken Sie dann auf **QoS**. Unter **QoS** sollten Registrierungsschlüssel für jede der QoS-Richtlinien angezeigt werden, den, die Sie gerade erstellt haben. Angenommen, wenn Sie zwei neue Richtlinien (eine benannte Skype für Business Server Audio QoS) und die anderen benannten Skype für Business Server Video QoS erstellt haben, sollten Sie Registrierungseinträge Skype für Business Server Audio QoS und Skype für Business Server Video QoS finden Sie unter.

Um sicherzustellen, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert markiert sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren abschließen:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor, **HKEY\_lokale\_Computer**, erweitern Sie **SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **Tcpip**.

4.  Mit der rechten Maustaste **Tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**. Nach dem Erstellen des neuen Registrierungsschlüssels Geben Sie **QoS**, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Mit der rechten Maustaste **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nach dem Erstellen des neuen Registrierungswerts Geben Sie die **Authentifizierung auf Netzwerkebene nicht verwenden**, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf die **Authentifizierung auf Netzwerkebene nicht verwenden**. Klicken Sie im Dialogfeld **Zeichenfolge bearbeiten** Geben Sie in das Feld **Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.
