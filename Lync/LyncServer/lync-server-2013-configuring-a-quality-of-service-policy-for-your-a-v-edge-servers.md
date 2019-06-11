---
title: Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Zusätzlich zum Erstellen von QoS-Richtlinien für Ihre Konferenz-, Anwendungs-und Vermittlungsserver müssen Sie auch Audio-und Video Richtlinien für die interne Seite Ihrer A/V-Edgeserver erstellen. Die auf Ihren Edgeserver verwendeten Richtlinien unterscheiden sich jedoch von den Richtlinien, die auf Ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden. Für Konferenz-, Anwendungs-und Vermittlungsserver haben Sie einen Quellportbereich angegeben. bei Edge-Servern müssen Sie einen Ziel Portbereich angeben. Aus diesem Grund können Sie die QoS-Richtlinien für Konferenz-, Anwendungs-und Vermittlungsserver nicht einfach auf Ihre Edge-Server anwenden: Diese Richtlinien funktionieren einfach nicht. Stattdessen müssen Sie neue Richtlinien erstellen und diese Richtlinien nur auf Ihre Edgeserver anwenden.

Im folgenden Verfahren wird das Verfahren zum Erstellen von Active Directory-Gruppenrichtlinienobjekten beschrieben, die zum Verwalten von Quality of Service auf Edge-Servern verwendet werden können. Natürlich ist es möglich, dass Ihre Edgeserver eigenständige Server sind, die keine Active Directory-Konten haben. Wenn dies der Fall ist, können Sie anstelle der Active Directory-Gruppenrichtlinie lokale Gruppenrichtlinien verwenden: der einzige Unterschied besteht darin, dass Sie diese lokalen Richtlinien mit dem Editor für lokale Gruppenrichtlinien erstellen müssen, und Sie müssen einzeln denselben Satz von Richtlinien auf jedem Edgeserver erstellen. Gehen Sie wie folgt vor, um den Editor für lokale Gruppenrichtlinien auf einem Edgeserver zu starten:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Text **gpedit. msc** ein, und drücken Sie dann die EINGABETASTE.

Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten Sie sich an einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie in diesem Fall die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle lync Server-Computer in einer Organisationseinheit mit dem Namen lync Server befinden, sollte die neue Richtlinie in der lync Server-Organisationseinheit erstellt werden.

2.  Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.

3.  Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync Server-Audio**), und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

Von hier aus ist der Prozess identisch, unabhängig davon, ob Sie eine Active Directory-Richtlinie oder eine lokale Richtlinie erstellen:

1.  Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor oder im Editor für lokale Gruppenrichtlinien **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

2.  Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **lync Server-Audio**) ein. Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest. Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.

3.  Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**. Mit dieser Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit einer DSCP-Kennzeichnung von 46 zu suchen, nicht nur von Paketen, die von einer bestimmten Anwendung erstellt wurden.

4.  Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-IP-Adresse** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.

5.  Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.

6.  Wählen Sie unter der Überschrift **die Zielportnummer**aus, und wählen Sie **aus diesem Ziel Port oder-Bereich aus**. Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise Ports 49152 über Ports 57500 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für den Audioverkehr erstellt haben, sollten Sie eine zweite Richtlinie für den Videoverkehr erstellen. Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server-Video**).

  - Setzen Sie den DSCP-Wert auf **34** statt auf 46. (Beachten Sie, dass Sie keinen DSCP-Wert von 34 verwenden müssen. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für Video verwenden, als Sie für Audio verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 57501 bis 65535 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **57501:65535**. Dies sollte wiederum als Ziel Portbereich konfiguriert werden.

Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs zu erstellen, müssen Sie eine dritte Richtlinie erstellen, indem Sie die folgenden Ersetzungen vornehmen:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **lync Server-Anwendungsfreigabe**).

  - Setzen Sie den DSCP-Wert auf **24** anstatt auf 46. (Sie müssen wiederum keinen DSCP-Wert von 24 verwenden. Die einzige Voraussetzung ist, dass Sie einen anderen DSCP-Wert für die Anwendungsfreigabe verwenden, als Sie für Audio oder Video verwendet haben.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie beispielsweise Ports 40803 bis 49151 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **40803:49151**.

Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Edge-Servern aktualisiert wurden. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpudate.exe /force

Dieser Befehl kann auf dem lync-Server oder in einem beliebigen Befehlsfenster, das unter Administratoranmeldeinformationen ausgeführt wird, ausgeführt werden. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Beachten Sie, dass Sie den Edge-Server möglicherweise auch nach dem Ausführen von gpudate. exe neu starten müssen.

Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.

4.  Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf **keine Verwendung von NLA**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.

</div>

<span> </span>

</div>

</div>

</div>

