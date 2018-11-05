---
title: Verwenden von erweiterter Protokollierung für synthetische Transaktionen
TOCTitle: Verwenden von erweiterter Protokollierung für synthetische Transaktionen
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204798(v=OCS.15)
ms:contentKeyID: 49293607
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von erweiterter Protokollierung für synthetische Transaktionen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Anhand synthetischer Transaktionen (die in Microsoft Lync Server 2010 eingeführt wurden) können Administratoren überprüfen, ob Benutzer allgemeine Aufgaben wie z. B. das Anmelden beim System, das Austauschen von Chatnachrichten oder das Tätigen von Anrufen im Telefonfestnetz (Public Switched Telephone Network, PSTN) erfolgreich durchführen können. Diese Tests (die als Gruppe von Windows PowerShell-Cmdlets in Lync Server zur Verfügung stehen) können manuell von einem Administrator oder automatisch von einer Anwendung wie System Center Operations Manager durchgeführt werden.

In Lync Server 2010 haben sich synthetische Transaktionen als äußerst nützlich beim Identifizieren von Systemproblemen erwiesen. Mit dem Cmdlet **Test-CsRegistration** konnten Administratoren beispielsweise darauf aufmerksam gemacht werden, dass einige Benutzer Schwierigkeiten haben, sich bei Lync Server zu registrieren. Allerdings waren die synthetischen Transaktionen nicht sehr hilfreich dabei, den Administratoren die Gründe dafür zu liefern, warum es Schwierigkeiten mit der Lync Server-Registrierung gab. Dies war darauf zurückzuführen, dass synthetische Transaktionen keine detaillierten Protokollierungsinformationen bereitstellten, die Administratoren bei der Behandlung von Problemen mit Lync Server helfen konnten. Bestenfalls enthielt die ausführliche Ausgabe einer synthetischen Transaktion Schritt-für-Schritt-Informationen, anhand derer ein Administrator aufgrund seiner Erfahrung Vermutungen darüber anstellen konnte, wo wahrscheinlich ein Problem aufgetreten ist.

In Microsoft Lync Server 2013 wurden die synthetischen Transaktionen neu entworfen, um eine umfassende Protokollierung bereitzustellen. "Umfassende Protokollierung" bedeutet, dass für jede Aktivität, die eine synthetische Transaktion unternimmt, Informationen wie die folgenden aufgezeichnet werden:

  - Die Uhrzeit, zu der die Aktivität begann

  - Die Uhrzeit, zu der die Aktivität endetet

  - Die Aktion, die durchgeführt wurde (z. B. Erstellen, Beitreten zu oder Verlassen einer Konferenz, Anmelden bei Lync Server, Senden einer Chatnachricht usw.)

  - Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden

  - Meldungen zur SIP-Registrierung

  - Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden

  - Das Resultat der Aktivitätsausführung

Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert. Sie werden jedoch nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Stattdessen können Administratoren, die manuell eine synthetische Transaktion durchführen, den Parameter **OutLoggerVariable** verwenden, um eine Windows PowerShell-Variable anzugeben, in der diese Informationen gespeichert werden. Administratoren können das umfassende Protokoll dann mithilfe von Methoden entweder im XML- oder HTML-Format anzeigen und/oder speichern.

Lync Server 2010-Administratoren können beispielsweise das **Test-CsRegistration**-Cmdlet mit einem Befehl ähnlich dem folgenden ausführen:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Administratoren können den Parameter **OutLoggerVariable** gefolgt von einem Variablennamen ihrer Wahl einfügen:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest


> [!NOTE]
> Stellen Sie dem Variablennamen kein $-Zeichen voran. Verwenden Sie einen Variablennamen wie <STRONG>RegistrationTest</STRONG> und nicht <STRONG>$RegistrationTest</STRONG>.



Die Ausgabe des obigen Befehls ist ähnlich wie die folgende:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Für diesen Fehler sind jedoch viel ausführlichere Informationen verfügbar, als nur die obige Fehlermeldung. Sie können einen ähnlichen Befehl wie den folgenden verwenden, um auf diese Informationen im HTML-Format zuzugreifen und die in der Variablen **RegistrationTest** gespeicherten Informationen in einer HTML-Datei zu speichern:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Diese Dateien können dann mit Internet Explorer, Visual Studio oder einer beliebigen anderen Anwendung angezeigt werden, in der HTML-/XML-Dateien geöffnet werden können.

Synthetische Transaktionen, die in System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien bei Fehlern automatisch. Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung scheitert, bevor die synthetische Transaktion in Windows PowerShell geladen und ausgeführt werden kann.


> [!IMPORTANT]
> In Lync Server 2013 werden die Protokolldateien standardmäßig in einem Ordner gespeichert, der nicht freigegeben ist. Um den Zugriff auf diese Protokolle zu ermöglichen, sollten Sie diesen Ordner freigeben (z.&nbsp;B. <STRONG>\\atl-watcher-001.litwareinc.com\WatcherNode</STRONG>).


