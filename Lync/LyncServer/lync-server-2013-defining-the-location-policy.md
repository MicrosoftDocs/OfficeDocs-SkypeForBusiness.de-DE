---
title: 'Lync Server 2013: Definieren der Standortrichtlinie'
TOCTitle: Definieren der Standortrichtlinie
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398962(v=OCS.15)
ms:contentKeyID: 49295594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Standortrichtlinie für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Jede Standortrichtlinie enthält die folgenden Informationen:

  - **Notrufdienste aktiviert**  
    Wenn diese Einstellung auf **Ja** festgelegt ist, wird der Client für E9-1-1 aktiviert. Der Client versucht bei der Registrierung einen Standort vom Standortinformationsdienst zu beziehen. Diese Standortinformationen werden bei einem Notruf übermittelt.

<!-- end list -->

  - **Standort erforderlich**  
    Diese Einstellung wird nur verwendet, wenn **Notrufdienste aktiviert** auf **Ja** festgelegt wurde.
    
    Sie können die Einstellung **Standort erforderlich** konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung **Nein**, so wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung **Ja**, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung **Haftungsausschluss** wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn der Benutzer versucht, diese Aufforderung zu verwerfen, wird ebenfalls ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    

    > [!NOTE]
    > Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben.



<!-- end list -->

  - **Haftungsausschluss der erweiterten Notrufdienste**  
    Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In Lync Server 2013 können Sie mithilfe der Standortrichtlinie unterschiedliche Haftungsausschlüsse für verschiedene Gebietsschemas oder verschiedene Benutzergruppen festlegen.
    

    > [!NOTE]
    > Diese Standortrichtlinieneinstellung weicht von Lync Server 2010 ab, wo Sie mit dem <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG>-Cmdlet einen globalen Haftungsausschluss für die gesamte Organisation festgelegt haben. Falls bereits ein globaler Haftungsausschluss vorhanden ist, müssen Sie diesen Haftungsausschluss in der Standortrichtlinie angeben. Das heißt, Lync Server 2013 verwendet nur in der Standortrichtlinie angegebene Haftungsausschlüsse.



<!-- end list -->

  - **Notrufwählzeichenfolge**  
    Diese Wählzeichenfolge (ohne das vorangestellte Pluszeichen "+", aber einschließlich etwaiger Normalisierungen durch den Wählplan des Lync-Benutzers) kennzeichnet einen Anruf als Notruf. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
    

    > [!NOTE]
    > Wenn Ihre Organisation kein Präfix für den externen Zugriff auf Leitungen verwendet, müssen Sie keine entsprechende Normalisierungsregel für den Wählplan erstellen, mit der der Zeichenfolge 911 ein Pluszeichen "+" hinzugefügt wird, bevor der Anruf auf einem Lync-Poolserver an das Ausgangsrouting gesendet wird. Das Pluszeichen "+" wird vom Lync-Client aufgrund der Standortrichtlinie automatisch vorangestellt. Wenn an Ihrem Standort jedoch ein Präfix für den externen Zugriff verwendet wird, müssen Sie der betreffenden Wählplanrichtlinie eine Normalisierungsregel hinzufügen, mit der das Präfix für den externen Zugriff entfernt und das Pluszeichen "+" hinzugefügt wird. Wenn an Ihrem Standort beispielsweise 9 als Präfix für den externen Zugriff verwendet wird, und ein Benutzer "9 911" wählt, um einen Notruf abzusetzen, verwendet der Client die Wählplanrichtlinie, um die gewählte Nummer zu "+911" zu normalisieren, bevor sie von den Routen im Standortprofil des Anrufers ausgewertet wird.



<!-- end list -->

  - **Masken für Notrufwählzeichenfolge**  
    Eine durch Semikolons getrennte Liste mit Wählzeichenfolgen, die in die angegebene **Notrufwählzeichenfolge** übersetzt wird. Angenommen, Sie möchten "112" hinzufügen, die in Europa am weitesten verbreitete Notrufnummer. Ein Lync-Benutzer aus Europa auf Besuch weiß u. U. nicht, dass die US-Notrufnummer "911" lautet. Er kann jedoch "112" wählen und dasselbe Ergebnis erzielen. Wie bei der Notrufzeichenfolge verwenden Sie vor den Nummern kein Pluszeichen "+", und wenn Sie Codes für den Zugriff auf externe Leitungen verwenden, stellen Sie sicher, dass in der Wählplanrichtlinie des Benutzers Normalisierungsregeln vorhanden sind, die die Ziffer des Zugriffscodes entfernen.

<!-- end list -->

  - **PSTN-Verwendung**  
    Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
    

    > [!NOTE]
    > Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Verwendung setzt die PSTN-Verwendungen außer Kraft, die der VoIP-Richtlinie des Benutzers zugewiesen sind. Dies gilt jedoch nur für Anrufe, die mit der Notrufwählzeichenfolge oder einer der Masken für Notrufwählzeichenfolge abgesetzt werden.



<!-- end list -->

  - **Benachrichtigungs-URI**  
    Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.

<!-- end list -->

  - **Konferenz-URI**  
    Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll.

<!-- end list -->

  - **Konferenzmodus**  
    Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird.

<!-- end list -->

  - **Standortaktualisierungsintervall**  
    Gibt an, in welchen zeitlichen Abständen (in Stunden) Clientanforderungen für die Standortaktualisierung vom Standortinformationsdienst empfangen werden. Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert lautet 4 .

