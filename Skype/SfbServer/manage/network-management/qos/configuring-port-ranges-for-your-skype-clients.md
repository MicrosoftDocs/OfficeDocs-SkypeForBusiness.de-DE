---
title: Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Portbereiche für Clients, die auf Windows-10 für Ihre Clients und Konfigurieren von Quality of Service-Richtlinien in Skype für Business Server konfigurieren.
ms.openlocfilehash: 112d5a42b3bf4ac89bf7adc98b3ca56e8797482e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223227"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für Clients in Skype für Business Server

In diesem Artikel wird beschrieben, wie Portbereiche für Clients, die auf Windows-10 für Ihre Clients und Konfigurieren von Quality of Service-Richtlinien in Skype für Business Server konfigurieren.

## <a name="configure-port-ranges"></a>Konfigurieren von Portbereichen

In der Standardeinstellung Skype Business-Clientanwendungen können einen beliebigen Port zwischen verwenden ports 1024 und 65535, wenn in einer kommunikationssitzung; beteiligt Dies ist, da bestimmte Portbereiche für Clients nicht automatisch aktiviert werden. Um die Quality of Service verwenden, jedoch müssen Sie die verschiedenen Typen von Datenverkehr (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) neu zuordnen zu einer Reihe von eindeutigen Portbereiche. Dies kann mithilfe des Cmdlets Set-CsConferencingConfiguration erfolgen.

> [!NOTE]  
> Endbenutzer können nicht diese Änderungen selbst vornehmen. Port kann nur durch Administratoren mit dem Cmdlet Set-CsConferencingConfiguration geändert werden.


Sie können bestimmen, welche Portbereiche derzeit für kommunikationssitzungen verwendet werden, durch den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell ausführen:

    Get-CsConferencingConfiguration

Unter der Annahme, dass Sie seit der Installation von Skype für Business Server keine Änderungen an den konferenzeinstellungen vorgenommen haben, sollten Sie ähnliche Informationen erhalten, die diese Eigenschaftswerte enthalten:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Wenn Sie die vorherigen Ausgabe genau betrachten, sehen Sie zwei Aspekte von Bedeutung. Zunächst wird die Parameter ClientMediaPortRangeEnabled-Eigenschaft auf False festgelegt:

    ClientMediaPortRangeEnabled : False

Das ist wichtig, da, wenn diese Eigenschaft auf False festgelegt ist, Skype für Business Clients zwischen jeden anderen verfügbaren Port verwenden, 1024 ports und 65535, wenn in einer kommunikationssitzung; beteiligt Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort). Wenn Sie einen angegebenen Satz von Ports Verwendung einschränken möchten (und dies Was möchten Sie tun ist, wenn Sie, zum Implementieren der Quality planen of Service), müssen Sie zuerst Client Media Portbereiche aktivieren. Dies kann mithilfe des folgenden Windows PowerShell-Befehls:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Mit dem vorstehende Befehl ermöglicht Client Media Portbereiche für die globale Auflistung der konferenzkonfigurationseinstellungen. Diese Einstellungen können jedoch auch auf Standortebene und/oder die auf Dienstebene (nur für den Konferenzserver Dienst) angewendet werden. Geben Sie die Identität dieser Website oder Server aktivieren, um clientmediendaten Bereiche für einen bestimmten Standort oder Server, port, beim Aufruf von Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Alternativ können Sie diesen Befehl verwenden, um Portbereiche für alle konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Zweitens von Bedeutung, den Sie bemerken ist, dass die Beispielausgabe sehen, dass standardmäßig die Medien Bereiche legen für jeden Typ von Netzwerkdatenverkehr port identisch sind:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Um QoS zu implementieren, müssen alle diese Portbereiche eindeutig sein. Beispielsweise können Sie die Portbereiche wie folgt konfigurieren:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ des Clientdatenverkehrs</th>
<th>Anfang des Portbereichs</th>
<th>Portbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Dateiübertragung</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


In der obigen Tabelle darstellen clientportbereiche eine Teilmenge der die Portbereiche für Ihre Server konfiguriert. Beispielsweise wurde auf den Servern, die Anwendungsfreigabe so konfiguriert, dass Ports 40803 bis 49151 verwenden; auf den Clientcomputern ist die Anwendungsfreigabe konfiguriert 42000 über 42019 Ports verwenden. Hierzu auch erfolgt hauptsächlich zum Vereinfachen der Verwaltung von QoS: Clientports müssen nicht unbedingt eine Teilmenge der auf dem Server verwendeten Ports darstellen. (Beispielsweise konnte auf den Clientcomputern Sie konfigurieren, beispielsweise Ports 10000 über 10019 zu verwenden, um die Anwendungsfreigabe.) Es wird jedoch empfohlen, dass Sie Ihre Client herstellen Port ranges eine Teilmenge der serverportbereiche.

Darüber hinaus Sie möglicherweise bemerkt, dass 8348 Ports für die Anwendungsfreigabe auf den Servern stillgelegte wurden, aber nur 20 Ports für die Anwendungsfreigabe auf den Clients stillgelegte wurden. Dies zu, wird empfohlen, aber es ist keine Codestrukturen Regel. Im Allgemeinen können Sie jeden verfügbaren Port zur Darstellung einer einzelnen kommunikationssitzung berücksichtigen: bei 100 Ports in einem Portbereich zur Verfügung, die bedeutet, dass der betreffende Computer teilnehmen konnten, maximal 100 kommunikationssitzungen an jedem beliebigen Zeitpunkt. Da Server wahrscheinlich als Clients viele weitere Unterhaltungen teilnimmt, ist es sinnvoll, viele weitere Ports auf den Servern als auf Clients zu öffnen. Einstellung Aside 20 Ports für die Anwendungsfreigabe auf einem Client bedeutet, dass ein Benutzer in 20 anwendungsfreigabesitzungen auf dem angegebenen Gerät und alle gleichzeitig teilnehmen konnten. Die sollte für den Großteil Ihrer Benutzer ausreichend nachweisen.

Um die obigen Portbereiche Ihrer globalen Auflistung der konferenzkonfigurationseinstellungen zuzuweisen, können Sie die folgenden Skype für Business Server Management Shell-Befehl verwenden:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle konferenzkonfigurationseinstellungen zuzuweisen:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Einzelne Benutzer müssen Abmelden von Skype für Unternehmen und dann erneut anmelden, bevor diese Änderungen tatsächlich in Kraft treten.

> [!NOTE]  
> Sie können auch die Medien clientportbereiche aktivieren, und weisen Sie diese Portbereiche mit einem einzigen Befehl. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Konfigurieren von Quality of Service-Richtlinien für Clients, die auf Windows-10

Zusätzlich zur Portbereiche für die Verwendung durch Ihre Skype für Business Clients angeben, müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputer angewendet wird. (Die Quality of Service-Richtlinien für Konferenz-, Anwendungs- und Mediation Server erstellt sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für die Skype für Business-Client und Windows-10-Computern.

Im folgenden Beispiel wird mit dieser Gruppe von Portbereiche auf um eine Audio- und eine videorichtlinie zu erstellen:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ des Clientdatenverkehrs</th>
<th>Anfang des Portbereichs</th>
<th>Portbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Dateiübertragung</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

Zum Erstellen einer audio Quality of Service-Richtlinie für Windows 10 Computer zuerst melden Sie sich an einem Computer, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Die Gruppenrichtlinien-Verwaltungskonsole**), und führen Sie dann die folgende Schritte aus:

1.  Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll. Beispielsweise sollte alle Client-Computer in einer Organisationseinheit mit dem Namen Clients befinden, die neue Richtlinie in der Organisationseinheit Client erstellt werden.

2.  Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.

3.  Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** Geben Sie im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.

4.  Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5.  In den Gruppenrichtlinienverwaltungs-Editor, erweitern Sie **Computerkonfiguration**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6.  Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie in das Feld **Name** ein. Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**. Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie auf der nächsten Seite stellen Sie sicher, dass **Alle Anwendungen** aktiviert ist, und klicken Sie dann auf **Weiter**. Diese Einstellung weist das Netzwerk zum Nachschlagen für alle Pakete mit einem DSCP-Markierung der 46, nicht nur Pakete, die von einer bestimmten Anwendung erstellt.

8.  Stellen Sie auf der dritten Seite sicher, dass **alle Quell-IP-Adresse** und **einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**. Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.

9.  Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die zwei Netzwerkprotokolle von Skype für Business Server und seine Clientanwendungen am häufigsten verwendet.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer** **aus dieser Quellport oder der Bereich**. Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert. Angenommen, wenn Sie Ports 50020 über reserviert ports 50039 audio Datenverkehr Geben Sie den Portbereich, der mit diesem Format: **50020:50039**. Klicken Sie auf **Fertig stellen**.

Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie klicken Sie dann eine zweite Richtlinie für Video erstellen. Führen Sie zum Erstellen einer Richtlinie für Video dieselbe grundlegende Prozedur, die Sie beim Erstellen der Richtlinie audio befolgt, wodurch dieser Platzhalter ein:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen an.

  - Legen Sie den DSCP-Wert auf **34** anstelle von 46. (Wie bereits erwähnt, müssen Sie nicht den DSCP-Wert 34 verwenden; Sie können einen anderen DSCP-Wert als der für die Audiodaten verwendeten einfach müssen zuweisen.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr. Beispielsweise wenn Sie Ports 58000 über 58019 für Video reserviert haben, setzen Sie den Portbereich hinzu: **58000:58019**.

Wenn Sie eine Richtlinie zur Verwaltung der Anwendungsfreigabe Anwendungsdatenverkehr erstellen möchten, stellen Sie dieser Platzhalter:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server die Anwendungsfreigabe**).

  - Legen Sie den DSCP-Wert, auf **24** anstelle von 46. (Erneut, dieser Wert muss nicht unbedingt 24 sein; es einfach identisch sein als die DSCP-Werte für Audio und Video verwendet.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr. Beispielsweise wenn Sie Ports 42000 über 42019 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich hinzu: **42000:42019**.

Für eine dateiübertragungsrichtlinie:

  - Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server Dateiübertragungen**).

  - Legen Sie den DSCP-Wert auf **14**. (In diesem Fall dieser Wert muss nicht 14 sein; einfach das Ereignis muss einen eindeutigen DSCP-Code.)

  - Verwenden Sie den zuvor konfigurierten Portbereich für Anwendung. Beispielsweise wenn Sie Ports 42020 über 42039 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich hinzu: **42020:42039**.

Die neuen Richtlinien erstellten werden nicht erst wirksam Gruppenrichtlinien auf den Clientcomputern aktualisiert wurde. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

    Gpudate.exe /force

Diesen Befehl können Sie über ein beliebiges Befehlsfenster ausführen, das mit Administratoranmeldeinformationen ausgeführt wird. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

Überwachungsfunktionen Sie benötigen, beachten Sie, dass diese Richtlinien auf Ihren Clientcomputern ausgerichtet werden sollen. Sie sollten nicht auf Servern mit Skype für Business Server angewendet werden.

Um sicherzustellen, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert markiert sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren abschließen:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor, **HKEY\_lokale\_Computer**, erweitern Sie **SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **Tcpip**.

4.  Mit der rechten Maustaste **Tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**. Nach dem Erstellen des neuen Registrierungsschlüssels Geben Sie **QoS**, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Mit der rechten Maustaste **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nach dem Erstellen des neuen Registrierungswerts Geben Sie die **Authentifizierung auf Netzwerkebene nicht verwenden**, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf die **Authentifizierung auf Netzwerkebene nicht verwenden**. Klicken Sie im Dialogfeld **Zeichenfolge bearbeiten** Geben Sie in das Feld **Wert** **1** ein, und klicken Sie dann auf **OK**.

7.  Schließen Sie den Registrierungs-Editor und Eboot Ihrem Computer.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Konfigurieren von Quality of Service auf Computern mit mehreren Netzwerkadaptern

Wenn Sie einen Computer, der mehrere Netzwerkadapter verfügt verfügen, können Sie gelegentlich ausführen zu Problemen, an die DSCP-Werte als 0 x 00 angezeigt werden, anstatt den konfigurierten Wert. Dies tritt in der Regel auf Computern, auf dem eine oder mehrere der Netzwerkadapter nicht auf Ihrer Active Directory-Domäne zugreifen sind (z. B., wenn diese Adapter für ein privates Netzwerk verwendet werden). In solchen Fällen, werden DSCP-Werte für den Adapter gekennzeichnet, die auf die Domäne zugreifen können, aber nicht für Adapter, die Zugriff auf die Domäne können nicht gekennzeichnet.

Wenn Sie Tag DSCP-Werte für alle Netzwerkadapter in einem Computer, einschließlich Adapter, die an Ihre Domäne keinen Zugriff haben möchten müssen Sie zum Hinzufügen und konfigurieren einen Wert in der Registrierung. Können Sie das folgende Verfahren abschließen erfolgen:

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor, **HKEY\_lokale\_Computer**, erweitern Sie **SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **Tcpip**.

4.  Wenn Sie einen Registrierungsschlüssel mit der Bezeichnung **QoS** dann **Tcpip**mit der rechten Maustaste nicht angezeigt werden, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Schlüssel erstellt wurde, geben Sie **QoS**, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

5.  Mit der rechten Maustaste **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nach dem Erstellen des neuen Registrierungswerts Geben Sie die **Authentifizierung auf Netzwerkebene nicht verwenden**, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Doppelklicken Sie auf die **Authentifizierung auf Netzwerkebene nicht verwenden**. Klicken Sie im Dialogfeld **Zeichenfolge bearbeiten** Geben Sie in das Feld **Wert** **1** ein, und klicken Sie dann auf **OK**.

Nach dem Erstellen und konfigurieren den neuen Registrierungswert, müssen Sie zum Neustart des Computers, damit die Änderungen wirksam werden.

## <a name="see-also"></a>Siehe auch

[Erstellen eines Gruppenrichtlinienobjekts in Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)