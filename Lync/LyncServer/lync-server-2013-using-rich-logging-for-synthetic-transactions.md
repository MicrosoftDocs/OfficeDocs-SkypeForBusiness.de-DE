---
title: 'Lync Server 2013: Verwenden der umfangreichen Protokollierung für synthetische Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fd1cfd26e1b5d56a6043e13d348e73e3c2b108
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Verwenden der umfangreichen Protokollierung für synthetische Transaktionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Synthetische Transaktionen (in Microsoft lync Server 2010 eingeführt) bieten Administratoren die Möglichkeit zu überprüfen, ob Benutzer in der Lage sind, allgemeine Aufgaben wie das Anmelden am System, das Austauschen von Chatnachrichten oder das tätigen von Anrufen an ein Telefon erfolgreich abzuschließen. im Festnetz (Public Switched Telephone Network, PSTN). Diese Tests (die als eine Gruppe von lync Server Windows PowerShell-Cmdlets verpackt sind) können manuell von einem Administrator ausgeführt werden, oder Sie können von einer Anwendung wie System Center Operations Manager automatisch durchgeführt werden.

In lync Server 2010 erwiesen sich synthetische Transaktionen als äußerst hilfreich bei der Unterstützung von Administratoren bei der Identifizierung von Problemen mit dem System. Beispielsweise könnte das **Test-CsRegistration-** Cmdlet Administratoren darauf hinweisen, dass sich einige Benutzer bei der Registrierung bei lync Server Schwierigkeiten hatten. Die synthetischen Transaktionen waren jedoch etwas weniger hilfreich, um Administratoren bei der Entscheidung zu unterstützen, warum sich diese Benutzer bei der Registrierung bei lync Server Schwierigkeiten hatten. Dies liegt daran, dass die synthetischen Transaktionen keine detaillierten Protokollierungsinformationen bereitgestellt haben, die Administratoren bei der Behandlung von Problemen mit lync Server unterstützen könnten. Bestenfalls enthielt die ausführliche Ausgabe einer synthetischen Transaktion Schritt-für-Schritt-Informationen, anhand derer ein Administrator aufgrund seiner Erfahrung Vermutungen darüber anstellen konnte, wo wahrscheinlich ein Problem aufgetreten ist.

In Microsoft lync Server 2013 wurden synthetische Transaktionen neu entworfen, um eine umfangreiche Protokollierung bereitzustellen. "Umfassende Protokollierung" bedeutet, dass für jede Aktivität, die eine synthetische Transaktion unternimmt, Informationen wie die folgenden aufgezeichnet werden:

  - Die Uhrzeit, zu der die Aktivität begann

  - Die Uhrzeit, zu der die Aktivität endetet

  - Die Aktion, die ausgeführt wurde (beispielsweise erstellen, hinzufügen oder verlassen einer Konferenz; Anmelden bei lync Server; senden einer Sofortnachricht; usw.)

  - Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden

  - Meldungen zur SIP-Registrierung

  - Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden

  - Das Resultat der Aktivitätsausführung

Diese Informationen werden jedes Mal automatisch generiert, wenn eine synthetische Transaktion ausgeführt wird. Die Informationen werden jedoch nicht automatisch in einer Protokolldatei angezeigt oder gespeichert. Stattdessen können Administratoren, die eine synthetische Transaktion manuell durchführen, den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell Variable anzugeben, in der die Informationen gespeichert werden. Von dort aus können Administratoren dann ein paar Methoden verwenden, mit denen Sie das umfangreiche Protokoll im XML-oder HTML-Format speichern und/oder anzeigen können.

Beispielsweise können lync Server 2010 Administratoren das Cmdlet **Test-CsRegistration** ausführen, indem Sie einen Befehl wie den folgenden verwenden:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Administratoren können den Parameter OutLoggerVariable gefolgt von einem Variablennamen ihrer Wahl einfügen:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Stellen Sie dem Variablennamen kein $-Zeichen voran. Verwenden Sie einen Variablennamen wie RegistrationTest und nicht $RegistrationTest.

Die Ausgabe des obigen Befehls ist ähnlich wie die folgende:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Für diesen Fehler sind jedoch viel ausführlichere Informationen verfügbar, als nur die obige Fehlermeldung. Sie können einen ähnlichen Befehl wie den folgenden verwenden, um auf diese Informationen im HTML-Format zuzugreifen und die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Diese Dateien können dann mit Internet Explorer, Visual Studio oder einer beliebigen anderen Anwendung angezeigt werden, die HTML/XML-Dateien öffnen kann.

Synthetische Transaktionen, die von innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler. Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung fehlschlägt, bevor Windows PowerShell die synthetische Transaktion laden und ausführen kann.

> [!IMPORTANT]  
> Standardmäßig speichert lync Server 2013 Protokolldateien in einem Ordner, der nicht freigegeben ist. Damit diese Protokolle leicht zugänglich sind, sollten Sie diesen Ordner freigeben (beispielsweise \\ \\ATL-Watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

