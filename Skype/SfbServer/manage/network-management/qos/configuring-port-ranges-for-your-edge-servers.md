---
title: Konfigurieren von Portbereichen und Quality of Service für Edge-Server
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel wird beschrieben, zum Konfigurieren von Portbereichen für Edge-Server und zum Konfigurieren von Quality of Service-Richtlinie für A / V-Edgeserver.
ms.openlocfilehash: 11fdb542c6256c21e169480194bc5154bf1c1428
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886374"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für die Edgeserver in Skype für Business Server

In diesem Artikel wird beschrieben, zum Konfigurieren von Portbereichen für Edge-Server und zum Konfigurieren von Quality of Service-Richtlinie für A / V-Edgeserver.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

Mit Edge-Servern müssen Sie keinen separaten Portbereiche für Audio-, Video- und Anwendungsfreigabe konfigurieren; dagegen müssen die Portbereiche für Edge-Server verwendet nicht die Portbereiche verwendet, die mit Ihren Servern Konferenz-, Anwendungs- und Vermittlungsserver übereinstimmen. Bevor wir mit unserem Beispiel fortzufahren, ist es wichtig, weisen Sie darauf hin, dass während diese Option vorhanden ist, es wird, dass Sie nicht die Portbereiche ändern, empfohlen wie dies einige Szenarien beeinträchtigen kann, wenn Sie den Portbereich 50000 verlassen.

Angenommen Sie, dass Sie Ihre Konferenz-, Anwendungs- und Mediation Server um verwenden Sie diese Portbereiche konfiguriert haben:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
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


Wie können Sie sehen, die Portbereiche für Audio-, Video- und Anwendungsfreigabe Start an Port 40803 und insgesamt 24732 Ports umfassen. Wenn Sie es vorziehen, können Sie diese verwenden, um einen bestimmten Edge-Server konfigurieren port insgesamt Werte durch einen Befehl wie den folgenden von innerhalb der Skype für Business Server-Verwaltungsshell ausführen:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Oder verwenden Sie den folgenden Befehl, um den Edge-Servern in Ihrer Organisation gleichzeitig zu konfigurieren:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Die aktuellen Porteinstellungen für Edge-Server können Sie überprüfen, mithilfe dieser Skype für Business Server Management Shell-Befehl:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Erneut, während wir diese Optionen angeben, wird dringend empfohlen, dass Sie Dinge lassen, wie sie für die Portkonfiguration sind.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Konfigurieren Sie eine QoS-Richtlinie für A / V-Edgeserver

Zusätzlich zum Erstellen von QoS-Richtlinien für die Konferenz-, Anwendungs- und Mediation Server, müssen Sie außerdem audio und video Richtlinien erstellen, für die interne Seite des A / V-Edgeserver. Auf Edge-Servern verwendeten Richtlinien unterscheiden sich jedoch von den Richtlinien, die auf Ihren Servern Konferenz-, Anwendungs- und Vermittlungsserver verwendet. Für die Konferenz-, Anwendungs- und Mediation Server müssen Sie einen Port Quellbereich angegeben; mit Edge-Servern müssen Sie einen Zielbereich Port angeben. Aus diesem Grund können nicht Sie einfach die Konferenz-, Anwendungs- und Mediation Server QoS-Richtlinien auf Edge-Servern anwenden: Diese Richtlinien einfach, funktionieren nicht. Stattdessen müssen Sie neue Richtlinien erstellen, und wenden Sie diese Richtlinien auf Ihrer Edge-Server.

Das folgende Verfahren beschreibt den Prozess zum Erstellen von Active Directory-Gruppenrichtlinie-Objekten, die zum Verwalten von Quality of Service auf Edge-Servern verwendet werden können. Natürlich ist es möglich, dass der Edgeserver eigenständigen Server sind, die nicht Active Directory-Konten verfügen. Wenn dies der Fall ist, können Sie lokale Gruppenrichtlinien verwenden, anstelle von Active Directory-Gruppenrichtlinie: der einzige Unterschied ist, dass Sie müssen diese mithilfe der Editor für lokale Gruppenrichtlinien lokalen Richtlinien erstellen, und den gleichen Satz von Richtlinien müssen einzeln auf jedem Edgeserver erstellen. Führen Sie die folgenden Schritte aus, um zu den Editor für lokale Gruppenrichtlinien auf einem Edgeserver:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **gpedit.msc ein**, und drücken Sie die EINGABETASTE.

Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten dann Sie an einem Computer anmelden, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde. In diesem Fall öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Die Gruppenrichtlinien-Verwaltungskonsole**), und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll. Angenommen, wenn alle Ihre Skype für Business Server-Computern in einer Organisationseinheit mit dem Namen Skype für Business Server befinden, sollte die neue Richtlinie in der Skype für Business Server OU erstellt werden.

2.  Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.

3.  Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das neue Gruppenrichtlinienobjekt im Feld **Name** (beispielsweise **Skype für Business Server Audio**), und klicken Sie dann auf **OK**.

4.  Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

Hier ist der Prozess identisch, unabhängig davon, ob Sie eine Active Directory-Richtlinie und einer lokalen Richtlinie erstellen:

1.  In den Gruppenrichtlinienverwaltungs-Editor oder den Editor für lokale Gruppenrichtlinien erweitern Sie **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

2.  Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie (z. B. **Skype für Business Server Audio**) in das Feld **Name** ein. Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**. Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

3.  Klicken Sie auf der nächsten Seite stellen Sie sicher, dass **Alle Anwendungen** aktiviert ist, und klicken Sie dann auf **Weiter**. Diese Einstellung weist das Netzwerk zum Nachschlagen für alle Pakete mit einem DSCP-Markierung der 46, nicht nur Pakete, die von einer bestimmten Anwendung erstellt.

4.  Stellen Sie auf der dritten Seite sicher, dass **alle Quell-IP-Adresse** und **einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**. Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.

5.  Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die zwei Netzwerkprotokolle von Skype für Business Server und seine Clientanwendungen am häufigsten verwendet.

6.  Wählen Sie unter der Überschrift **angeben die Ziel-Portnummer** **aus dieser Zielport oder der Bereich**. Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert. Angenommen, wenn Sie Ports 49152 über Ports 57500 für audio-Datenverkehr reserviert ist, geben Sie den Portbereich, der mit diesem Format: **49152:57500**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für den audio-Datenverkehr erstellt haben, sollten Sie eine zweite Policy für video-Datenverkehr erstellen. Führen Sie zum Erstellen einer Richtlinie für Video dieselbe grundlegende Prozedur, die Sie beim Erstellen der Richtlinie audio befolgt, wodurch dieser Platzhalter ein:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server-Video**).

  - Legen Sie den DSCP-Wert auf **34** anstelle von 46. (Beachten Sie, dass Sie keine DSCP-Wert von 34 verwenden. Die einzige Anforderung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr. Beispielsweise wenn Sie Ports 57501 und 65535 für Videodaten reserviert haben, setzen Sie den Portbereich hinzu: **57501:65535**. Dies sollte erneut, wie der Zielbereich Port konfiguriert werden.

Wenn Sie eine Richtlinie zur Verwaltung der Anwendungsfreigabe Anwendungsdatenverkehr erstellen möchten, müssen Sie eine dritte Richtlinie erstellen die folgenden Änderungen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server die Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert, auf **24** anstelle von 46. (In diesem Fall müssen Sie keinen DSCP-Wert von 24 verwenden. Die einzige Anforderung ist für die Verwendung eines anderen DSCP-Werts für die Anwendungsfreigabe, als Sie für Audio oder Video verwendet.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr. Beispielsweise wenn Sie Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich hinzu: **40803:49151**.

Die neuen Richtlinien erstellten werden nicht erst wirksam Gruppenrichtlinien auf Edge-Servern aktualisiert wurde. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpudate.exe /force

Dieser Befehl kann aus ausgeführt werden innerhalb der Skype für Business Server oder von einem beliebigen Befehlsfenster, das Administratoranmeldeinformationen ausgeführt wird. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Beachten Sie, dass Sie möglicherweise den Edge-Server neu starten, auch nach dem Ausführen von Gpudate.exe.

Um sicherzustellen, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert markiert sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren abschließen:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor, **HKEY\_lokale\_Computer**, erweitern Sie **SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **Tcpip**.

4.  Mit der rechten Maustaste **Tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**. Nach dem Erstellen des neuen Registrierungsschlüssels Geben Sie **QoS**, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Mit der rechten Maustaste **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nach dem Erstellen des neuen Registrierungswerts Geben Sie die **Authentifizierung auf Netzwerkebene nicht verwenden**, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **Verwenden Sie kein Authentifizierung auf Netzwerkebene**. Klicken Sie im Dialogfeld **Zeichenfolge bearbeiten** Geben Sie in das Feld **Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.
