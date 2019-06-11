---
title: 'Lync Server 2013: Verwenden der Rich-Protokollierung für synthetische Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Verwenden der umfangreichen Protokollierung für synthetische Transaktionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Synthetische Transaktionen (eingeführt in Microsoft lync Server 2010) bieten Administratoren eine Möglichkeit, zu überprüfen, ob Benutzer in der Lage sind, häufige Aufgaben wie die Anmeldung am System, den Austausch von Sofortnachrichten oder Anrufe an ein festgelegtes Telefon erfolgreich abzuschließen. über das öffentlich geschaltete Telefonnetz (PSTN). Diese Tests (die als eine Reihe von lync Server-Windows PowerShell-Cmdlets verpackt sind) können manuell von einem Administrator durchgeführt werden, oder Sie können von einer Anwendung wie System Center Operations Manager automatisch ausgeführt werden.

In lync Server 2010 erwiesen sich synthetische Transaktionen als äußerst hilfreich, um Administratoren bei der Ermittlung von Problemen mit dem System zu unterstützen. So könnte beispielsweise das Cmdlet **Test-CsRegistration** Administratoren darauf hinweisen, dass einige Benutzer Schwierigkeiten bei der Registrierung bei lync Server hatten. Die synthetischen Transaktionen waren jedoch etwas weniger hilfreich, um Administratoren zu helfen, zu ermitteln, warum diese Benutzer Schwierigkeiten bei der Registrierung bei lync Server hatten. Dies war auf die Tatsache zurückzuführen, dass die synthetischen Transaktionen keine detaillierten Protokollierungsinformationen lieferten, die Administratoren bei der Behandlung von Problemen mit lync Server unterstützen könnten. Im besten Fall lieferte die ausführliche Ausgabe einer synthetischen Transaktion schrittweise Informationen, die es einem Administrator ermöglichen könnten, eine fundierte Vermutung darüber zu machen, wo ein Problem wahrscheinlich aufgetreten ist.

In Microsoft lync Server 2013 wurden synthetische Transaktionen neu entworfen, um eine umfangreiche Protokollierung bereitzustellen. "Umfangreiche Protokollierung" bedeutet, dass für jede Aktivität, die eine synthetische Transaktion durchführt, Informationen wie diese aufgezeichnet werden:

  - Der Zeitpunkt, zu dem die Aktivität gestartet wurde

  - Die Zeit, zu der die Aktivität endet

  - Die Aktion, die durchgeführt wurde (beispielsweise das Erstellen, verknüpfen oder verlassen einer Konferenz; Anmelden bei lync Server; senden einer Chatnachricht; usw.)

  - Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden

  - SIP-Registrierungsnachrichten

  - Ausnahmedaten Sätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden

  - Das Ergebnis der Ausführung der Aktivität

Diese Informationen werden jedes Mal automatisch generiert, wenn eine synthetische Transaktion ausgeführt wird. Die Informationen werden jedoch nicht automatisch in einer Protokolldatei angezeigt oder gespeichert. Stattdessen können Administratoren, die eine synthetische Transaktion manuell ausführen, mithilfe des OutLoggerVariable-Parameters eine Windows PowerShell-Variable angeben, in der die Informationen gespeichert werden. Von dort aus können Administratoren dann ein paar Methoden verwenden, die es Ihnen ermöglichen, das Rich-log im XML-oder HTML-Format zu speichern und/oder anzuzeigen.

Beispielsweise können lync Server 2010-Administratoren das Cmdlet **Test-CsRegistration** mithilfe eines Befehls wie den folgenden ausführen:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Administratoren haben die Möglichkeit, den OutLoggerVariable-Parameter und dann den Variablennamen Ihrer Auswahl einzuschließen:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Führen Sie den Variablennamen nicht mit dem $-Zeichen vor. Verwenden Sie einen Variablennamen wie "RegistrationTest" und nicht "$RegistrationTest".

Der vorhergehende Befehl gibt Inhalt ähnlich wie den folgenden aus:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Für diesen Fehler sind jedoch viel detailliertere Informationen verfügbar, als nur die oben gezeigte Fehlermeldung. Um auf diese Informationen im HTML-Format zuzugreifen, verwenden Sie einen ähnlichen Befehl, um die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Alternativ können Sie die ToXML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Diese Dateien können dann mit Internet Explorer, Visual Studio oder jeder anderen Anwendung angezeigt werden, die in der Lage ist, HTML/XML-Dateien zu öffnen.

Synthetische Transaktionen, die innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler. Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung fehlschlägt, bevor Windows PowerShell die synthetische Transaktion laden und ausführen kann.

> [!IMPORTANT]  
> Standardmäßig speichert lync Server 2013 Protokolldateien in einem Ordner, der nicht freigegeben ist. Damit diese Protokolle problemlos zugänglich sind, sollten Sie diesen Ordner freigeben (beispielsweise \\ \\ATL-Watcher-001. "litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

