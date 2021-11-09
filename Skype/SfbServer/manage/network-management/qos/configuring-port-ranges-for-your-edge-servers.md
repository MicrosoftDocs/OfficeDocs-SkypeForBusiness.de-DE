---
title: Konfigurieren von Portbereichen und einer Dienstqualität für Ihre Edgeserver
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche für Edgeserver konfigurieren und wie Sie eine Quality of Service-Richtlinie für Ihre A/V-Edgeserver konfigurieren.
ms.openlocfilehash: ae955eb8863f561cc1837b7f0319f7424f13e99c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829939"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver in Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Portbereiche für Edgeserver konfigurieren und wie Sie eine Quality of Service-Richtlinie für Ihre A/V-Edgeserver konfigurieren.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Bei Edgeservern müssen Sie keine separaten Portbereiche für die Audio-, Video- und Anwendungsfreigabe konfigurieren. Ebenso müssen die für Edgeserver verwendeten Portbereiche nicht mit den Portbereichen übereinstimmen, die mit Ihren Konferenz-, Anwendungs- und Vermittlungsservern verwendet werden. Bevor wir mit unserem Beispiel fortfahren, ist es wichtig zu betonen, dass diese Option zwar vorhanden ist, es jedoch empfohlen wird, die Portbereiche nicht zu ändern, da sich dies negativ auf einige Szenarien auswirken kann, wenn Sie den Portbereich von 50000 verlassen.

Angenommen, Sie haben Ihre Konferenz-, Anwendungs- und Vermittlungsserver so konfiguriert, dass diese Portbereiche verwendet werden:


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Pakettyp</th>
<th>Startport</th>
<th>Anzahl der reservierten Ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Video</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Summen</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Wie Sie sehen können, beginnen Ihre Portbereiche für Audio, Video und Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732 Ports. Wenn Sie möchten, können Sie einen bestimmten Edgeserver so konfigurieren, dass er diese allgemeinen Portwerte verwendet, indem Sie einen Befehl ähnlich dem folgenden in der Skype for Business Server-Verwaltungsshell ausführen:

  **Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730**

Oder führen Sie den folgenden Befehl aus, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:

  **Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_. Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}**

Sie können die aktuellen Porteinstellungen für Ihre Edgeserver überprüfen, indem Sie den folgenden Befehl Skype for Business Server Verwaltungsshell verwenden:

  **Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount**

Auch wenn wir diese Optionen bereitstellen, empfehlen wir dringend, die Elemente für die Portkonfiguration zu belassen.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Konfigurieren einer QoS-Richtlinie für Ihre A/V-Edgeserver

Neben den QoS-Richtlinien für Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen Sie auch Audio- und Videorichtlinien für die interne Seite Ihrer A/V-Edgeserver erstellen. Die auf Ihren Edgeservern verwendeten Richtlinien unterscheiden sich jedoch von den auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern verwendeten Richtlinien. Für die Konferenz-, Anwendungs- und Vermittlungsserver haben Sie einen Quellportbereich angegeben. bei Edgeservern müssen Sie einen Zielportbereich angeben. Aus diesem Grund können Sie die QoS-Richtlinien für Konferenz-, Anwendungs- und Vermittlungsserver nicht einfach auf Ihre Edgeserver anwenden: Diese Richtlinien funktionieren einfach nicht. Stattdessen müssen Sie neue Richtlinien erstellen und diese ausschließlich auf Ihre Edgeserver anwenden.

Das folgende Verfahren beschreibt die Vorgehensweise beim Erstellen von Active Directory-Gruppenrichtlinienobjekten, die zum Verwalten der der Dienstqualität (Quality of Service, QoS) auf Edgeservern verwendet werden kann. Möglicherweise handelt es sich bei Ihren Edgeservern um Einzelserver ohne Active Directory-Konten. In diesem Fall können Sie die lokale Gruppenrichtlinie statt der Active Directory-Gruppenrichtlinie verwenden, mit dem Unterschied, dass Sie diese lokalen Richtlinien mit dem Editor für lokale Gruppenrichtlinien erstellen und auf jedem Edgeserver denselben Richtliniensatz einzeln erstellen müssen. Gehen Sie folgendermaßen vor, um den Editor für lokale Gruppenrichtlinien auf einem Edgeserver zu starten:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben Sie im Dialogfeld **"Ausführen"** **"gpedit.msc"** ein, und drücken Sie dann die EINGABETASTE.

Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten Sie sich auf einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie in diesem Fall die Gruppenrichtlinienverwaltung (klicken Sie auf **"Start",** zeigen Sie auf **"Verwaltungstools",** und klicken Sie dann auf **"Gruppenrichtlinienverwaltung"),** und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Skype for Business Server Computer in einer OE mit dem Namen Skype for Business Server befinden, sollte die neue Richtlinie in der Skype for Business Server OU erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **"Gruppenrichtlinienobjekt in dieser Domäne erstellen", und verknüpfen Sie es hier.**

3.  Geben Sie im Dialogfeld **Neues** Gruppenrichtlinienobjekt einen Namen für das neue Gruppenrichtlinienobjekt in das **Feld Name** ein (z. **B. Skype for Business Server Audio),** und klicken Sie dann auf **"OK".**

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **"Bearbeiten".**

Ab diesem Schritt sind die Vorgehensweisen beim Erstellen einer Active Directory-Richtlinie und einer lokalen Richtlinie identisch:

1.  Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor oder im Editor für lokale Gruppenrichtlinien **Computerkonfiguration**, **Richtlinien** und **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.

2.  Geben Sie im Dialogfeld **"Richtlinienbasierter QoS"** auf der ersten Seite einen Namen für die neue Richtlinie (z. **B. Skype for Business Server Audio)** in das **Feld "Name"** ein. Klicken Sie auf **DSCP-Wert angeben** und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

3.  Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt sind, und klicken Sie dann auf **"Weiter".** Durch diese Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit der DSCP-Markierung 46 zu suchen, anstatt nur nach von einer bestimmten Anwendung erstellten Paketen.

4.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Beliebige Quell-IP-Adresse** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **"Weiter".** Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.

5.  Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.

6.  Wählen Sie unter der Überschrift **"Zielportnummer angeben"** die Option **"Von diesem Zielport oder -bereich" aus.** Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports 49152 bis Ports 57500 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **49152:57500.** Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audiodatenverkehr erstellt haben, sollten Sie eine zweite Richtlinie für Videodatenverkehr erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. **B. Skype for Business Server Video).**

  - Legen Sie den DSCP-Wert auf **34** statt "46" fest. (Sie müssen nicht unbedingt den DSCP-Wert 34 verwenden, der DSCP-Wert für Video muss sich lediglich von dem für Audio verwendeten Wert unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 57501 bis 65535 für Video reserviert haben, legen Sie den Portbereich auf folgendes fest: **57501:65535**. Auch dies sollte als Zielportbereich konfiguriert werden.

Wenn Sie eine Richtlinie für die Verwaltung des Datenverkehrs für die Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie erstellen, die die folgenden Ersetzungen vornimmt:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. **B. Skype for Business Server Anwendungsfreigabe).**

  - Legen Sie den DSCP-Wert auf **24** statt "46" fest. (Auch hier muss nicht unbedingt der DSCP-Wert 24 verwendet werden, der DSCP-Wert für Video muss sich lediglich von den für Audio und Video verwendeten Werten unterscheiden.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise die Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf folgendes fest: **40803:49151**.

Die neu erstellten Richtlinien werden erst wirksam, wenn auf Ihren Edgeservern die Gruppenrichtlinien aktualisiert wurden. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:

 **Gpudate.exe /force**

Dieser Befehl kann innerhalb des Skype for Business Server oder in einem beliebigen Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird. Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Möglicherweise müssen Sie den Edgeserver auch nach der Ausführung von "Gpudate.exe" neu starten.

Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:

1.  Klicken Sie auf **Start** und anschließend auf **Ausführen**.

2.  Geben **Sie** im Dialogfeld Ausführen **regedit ein,** und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **"HKEY \_ LOCAL \_ MACHINE",** **"SYSTEM",** **"CurrentControlSet",** **"Dienste"** und dann **"Tcpip".**

4.  Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Geben Sie nach dem Erstellen des neuen **Registrierungsschlüssels QoS** ein, und drücken Sie dann die EINGABETASTE, um die Taste umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Geben Sie nach dem Erstellen des neuen Registrierungswerts **"NLA nicht verwenden"** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **NLA nicht verwenden**. Geben **Sie** im Dialogfeld Zeichenfolge bearbeiten im **Feld Wert** den Wert **1** ein, und klicken Sie dann auf **OK.**

7.  Schließen Sie den Registrierungs-Editor, und starten Sie ihren Computer neu.
