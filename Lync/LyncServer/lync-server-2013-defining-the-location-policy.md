---
title: 'Lync Server 2013: Definieren der ortungsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bdb3b556f5b9a8d552a3c48e300b8c4b7b19f5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504522"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definieren der ortungsrichtlinie für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Jede Standortrichtlinie enthält die folgenden Informationen:

  - **Notrufdienste aktiviert**  
    Wenn dieser Wert " **Yes**" lautet, ist der Client für E9-1-1 aktiviert. Wenn ein Client registriert wird, versucht er, einen Speicherort aus dem Standortinformationsdienst abzurufen, und enthält die Standortinformationen als Teil eines Notrufs.

<!-- end list -->

  - **Standort erforderlich**  
    Diese Einstellung wird nur verwendet, wenn **Emergency Services Enabled**   auf **Ja**festgelegt ist.
    
    Sie können die Einstellung **Standort erforderlich** konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung **Nein**, so wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung **Ja**, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung **Haftungsausschluss** wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn der Benutzer versucht, diese Aufforderung zu verwerfen, wird ebenfalls ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
    <div>
    

    > [!NOTE]  
    > Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben.

    
    </div>

<!-- end list -->

  - **Haftungsausschluss der erweiterten Notrufdienste**  
    Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In lync Server 2013 können Sie die ortungsrichtlinie verwenden, um unterschiedliche Haftungsausschlüsse für unterschiedliche Gebietsschemas oder unterschiedliche Benutzergruppen festzulegen.
    
    <div>
    

    > [!NOTE]  
    > Diese Standortrichtlinien Einstellung unterscheidet sich von lync Server 2010, wobei Sie das Cmdlet "Cmdlet <STRONG>festlegen</STRONG> " verwendet haben, um einen globalen Haftungsausschluss für die gesamte Organisation festzulegen. Falls bereits ein globaler Haftungsausschluss vorhanden ist, müssen Sie diesen Haftungsausschluss in der Standortrichtlinie angeben. Das bedeutet, dass lync Server 2013 nur in der ortungsrichtlinie angegebene Haftungsausschlüsse verwendet.

    
    </div>

<!-- end list -->

  - **Notrufwählzeichenfolge**  
    Diese Wählzeichenfolge (ohne das vorangestellte Pluszeichen "+", aber einschließlich etwaiger Normalisierungen durch den Wählplan des Lync-Benutzers) kennzeichnet einen Anruf als Notruf. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
    
    <div>
    

    > [!NOTE]  
    > Wenn in Ihrer Organisation kein Präfix für den Zugriff auf externe Leitungen verwendet wird, müssen Sie keine entsprechende Normalisierungsregel für den Wählplan erstellen, die vor dem Senden des Anrufs an das ausgehende Routing auf einem lync-Pool Server ein "+" zur Zeichenfolge "911" hinzufügt. Das "+" wird dem lync-Client als Ergebnis der ortungsrichtlinie automatisch vorangestellt. Wenn Ihre Website jedoch ein externes Zugriffs Präfix verwendet, müssen Sie der entsprechenden Wähl Plan Richtlinie eine Normalisierungsregel hinzufügen, mit der das Präfix für den externen Zugriff entfernt und das Pluszeichen "+" hinzugefügt wird. Wenn Ihr Standort beispielsweise ein externes Zugriffs Präfix von 9 verwendet und ein Benutzer 9 &nbsp; 911 zum Platzieren eines Notrufs wählt, verwendet der Client seine Wähl Plan Richtlinie, um diese auf + 911 zu normalisieren, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird.

    
    </div>

<!-- end list -->

  - **Masken für Notrufwählzeichenfolge**  
    Eine durch Semikolons getrennte Liste mit Wählzeichenfolgen, die in die angegebene **Notrufwählzeichenfolge** übersetzt wird. Angenommen, Sie möchten "112" hinzufügen, die in Europa am weitesten verbreitete Notrufnummer. Ein Lync-Benutzer aus Europa auf Besuch weiß u. U. nicht, dass die US-Notrufnummer "911" lautet. Er kann jedoch "112" wählen und dasselbe Ergebnis erzielen. Wie bei der Notrufzeichenfolge verwenden Sie vor den Nummern kein Pluszeichen "+", und wenn Sie Codes für den Zugriff auf externe Leitungen verwenden, stellen Sie sicher, dass in der Wählplanrichtlinie des Benutzers Normalisierungsregeln vorhanden sind, die die Ziffer des Zugriffscodes entfernen.

<!-- end list -->

  - **PSTN-Verwendung**  
    Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
    
    <div>
    

    > [!NOTE]  
    > Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Verwendung setzt die PSTN-Verwendungen außer Kraft, die der VoIP-Richtlinie des Benutzers zugewiesen sind. Dies gilt jedoch nur für Anrufe, die mit der Notrufwählzeichenfolge oder einer der Masken für Notrufwählzeichenfolge abgesetzt werden.

    
    </div>

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
    Gibt die Zeitspanne (in Stunden) zwischen Clientanforderungen für eine Standortaktualisierung aus dem Standortinformationsdienst an. Der Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert ist 4.

</div>

<span> </span>

</div>

</div>

</div>

