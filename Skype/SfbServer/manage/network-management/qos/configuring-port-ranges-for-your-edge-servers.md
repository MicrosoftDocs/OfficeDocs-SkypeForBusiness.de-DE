---
title: Konfigurieren von Portbereichen und einer Dienstqualität für Ihre Edgeserver
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche für Edge-Server konfigurieren und wie Sie eine Dienst Qualitätsrichtlinie für Ihre a/V-Edgeserver konfigurieren.
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817434"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver in Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Portbereiche für Edge-Server konfigurieren und wie Sie eine Dienst Qualitätsrichtlinie für Ihre a/V-Edgeserver konfigurieren.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Bei Edge-Servern müssen Sie keine separaten Portbereiche für Audio-, Video-und Anwendungsfreigaben konfigurieren. Ebenso müssen die für Edgeserver verwendeten Portbereiche nicht den Portbereichen entsprechen, die mit ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden. Bevor wir mit unserem Beispiel fortfahren, ist es wichtig zu betonen, dass diese Option zwar vorhanden ist, aber wir empfehlen, die Portbereiche nicht zu ändern, da sich dies negativ auf einige Szenarien auswirken kann, wenn Sie den 50000-Portbereich verschieben.

Angenommen, Sie haben Ihre Konferenz-, Anwendungs-und Vermittlungsserver so konfiguriert, dass Sie diese Portbereiche verwenden:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pakettyp</th>
<th>Port wird gestartet</th>
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


Wie Sie sehen können, beginnen Ihre Portbereiche für Audio-, Video-und Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732-Ports. Wenn Sie es vorziehen, können Sie einen bestimmten Edgeserver so konfigurieren, dass diese Gesamt Port Werte verwendet werden, indem Sie in der Skype for Business Server-Verwaltungsshell einen ähnlichen Befehl ausführen:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Oder verwenden Sie den folgenden Befehl, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Sie können die aktuellen Porteinstellungen für Ihre Edgeserver mithilfe dieses Befehls für die Skype for Business Server-Verwaltungsshell überprüfen:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Auch wenn wir diese Optionen zur Verfügung stellen, empfehlen wir Ihnen dringend, die Einstellungen für die Port-Konfiguration zu belassen.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Konfigurieren einer QoS-Richtlinie für Ihre a/V-Edgeserver

Zusätzlich zum Erstellen von QoS-Richtlinien für Ihre Konferenz-, Anwendungs-und Vermittlungsserver müssen Sie auch Audio-und Video Richtlinien für die interne Seite Ihrer A/V-Edgeserver erstellen. Die auf Ihren Edgeserver verwendeten Richtlinien unterscheiden sich jedoch von den Richtlinien, die auf Ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden. Für Konferenz-, Anwendungs-und Vermittlungsserver haben Sie einen Quellportbereich angegeben. bei Edge-Servern müssen Sie einen Ziel Portbereich angeben. Aus diesem Grund können Sie die QoS-Richtlinien für Konferenz-, Anwendungs-und Vermittlungsserver nicht einfach auf Ihre Edge-Server anwenden: Diese Richtlinien funktionieren einfach nicht. Stattdessen müssen Sie neue Richtlinien erstellen und diese Richtlinien nur auf Ihre Edgeserver anwenden.

Im folgenden Verfahren wird das Verfahren zum Erstellen von Active Directory-Gruppenrichtlinienobjekten beschrieben, die zum Verwalten von Quality of Service auf Edge-Servern verwendet werden können. Natürlich ist es möglich, dass Ihre Edgeserver eigenständige Server sind, die keine Active Directory-Konten haben. Wenn dies der Fall ist, können Sie anstelle der Active Directory-Gruppenrichtlinie lokale Gruppenrichtlinien verwenden: der einzige Unterschied besteht darin, dass Sie diese lokalen Richtlinien mit dem Editor für lokale Gruppenrichtlinien erstellen müssen, und Sie müssen einzeln denselben Satz von Richtlinien auf jedem Edgeserver erstellen. Gehen Sie wie folgt vor, um den Editor für lokale Gruppenrichtlinien auf einem Edgeserver zu starten:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Text **gpedit. msc**ein, und drücken Sie dann die EINGABETASTE.

Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten Sie sich an einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie in diesem Fall die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Skype for Business Server-Computer in einer OU mit dem Namen Skype for Business Server befinden, sollte die neue Richtlinie in der Skype for Business Server-OU erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.

3.  Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **Skype for Business Server-Audio**), und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

Von hier aus ist der Prozess identisch, unabhängig davon, ob Sie eine Active Directory-Richtlinie oder eine lokale Richtlinie erstellen:

1.  Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor oder im Editor für lokale Gruppenrichtlinien **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

2.  Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **Skype for Business Server-Audio**) ein. Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest. Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.

3.  Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**. Mit dieser Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit einer DSCP-Kennzeichnung von 46 zu suchen, nicht nur von Paketen, die von einer bestimmten Anwendung erstellt wurden.

4.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.

5.  Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.

6.  Wählen Sie unter der Überschrift **die Zielportnummer**aus, und wählen Sie **aus diesem Ziel Port oder-Bereich aus**. Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 49152 über Ports 57500 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für den Audioverkehr erstellt haben, sollten Sie eine zweite Richtlinie für den Videoverkehr erstellen. Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype for Business Server-Video**).

  - Setzen Sie den DSCP-Wert auf **34** statt auf 46. (Beachten Sie, dass Sie keinen DSCP-Wert von 34 verwenden müssen. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 57501 bis 65535 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **57501:65535**. Dies sollte wiederum als Ziel Portbereich konfiguriert werden.

Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs zu erstellen, müssen Sie eine dritte Richtlinie erstellen, die die folgenden Substitutionen vornimmt:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **Freigabe von Skype for Business Server-Anwendungen**).

  - Setzen Sie den DSCP-Wert auf **24** anstatt auf 46. (Sie müssen wiederum keinen DSCP-Wert von 24 verwenden. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für die Anwendungsfreigabe verwenden, als Sie für Audio oder Video verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **40803:49151**.

Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Edge-Servern aktualisiert wurden. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpudate.exe /force

Dieser Befehl kann innerhalb des Skype for Business-Servers oder in einem beliebigen Befehlsfenster, das unter Administratoranmeldeinformationen ausgeführt wird, ausgeführt werden. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Beachten Sie, dass Sie den Edge-Server möglicherweise auch nach dem Ausführen von gpudate. exe neu starten müssen.

Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Geben Sie nach dem Erstellen des neuen Registrierungsschlüssels **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **keine Verwendung von NLA**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie Ihren Computer neu.
