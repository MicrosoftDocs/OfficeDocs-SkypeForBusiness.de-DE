---
title: 'Lync Server 2013: Definieren der Standortrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definieren der Standortrichtlinie für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Jede Standortrichtlinie enthält die folgenden Informationen:

  - **Notfalldienste aktiviert**  
    Wenn dieser Wert **Ja**ist, ist der Client für E9-1-1 aktiviert. Wenn ein Client registriert wird, versucht er, einen Standort vom standortinformationsdienst abzurufen, und die Standortinformationen werden als Teil eines Notrufs aufgenommen.

<!-- end list -->

  - **Ort erforderlich**  
    Diese Einstellung wird nur verwendet, wenn " **Emergency Services Enabled** " auf " **Ja**" festgelegt ist.
    
    Sie können die Einstellung **Standort erforderlich** konfigurieren, um das Clientverhalten zu definieren. Wenn der Wert auf **Nein** festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Angabe eines Standorts aufgefordert wird. Wenn der Wert auf **Ja** festgelegt wird, bedeutet dies, dass der Benutzer zur Angabe eines Standorts aufgefordert wird; er kann die Aufforderung aber verwerfen. Wenn Sie den Wert auf **Disclaimer** setzen, wird der Benutzer aufgefordert, einen Speicherort einzugeben, und es wird auch ein Haftungsausschluss angezeigt, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
    <div>
    

    > [!NOTE]  
    > Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. 

    
    </div>

<!-- end list -->

  - **Haftungsausschluss der erweiterten Notfalldienste**  
    Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In lync Server 2013 können Sie mithilfe der ortungsrichtlinie verschiedene Haftungsausschlüsse für verschiedene Gebietsschemas oder verschiedene Gruppen von Benutzern festlegen.
    
    <div>
    

    > [!NOTE]  
    > Diese Einstellung für Standortrichtlinien unterscheidet sich von lync Server 2010, bei dem Sie das Cmdlet " <STRONG>festlegen-CsEnhancedEmergencyServiceDisclaimer</STRONG> " verwendet haben, um einen globalen Haftungsausschluss für die gesamte Organisation festzulegen. Wenn bereits ein globaler Haftungsausschluss vorhanden ist, müssen Sie diesen Haftungsausschluss in der Standortrichtlinie angeben. Das bedeutet, dass lync Server 2013 nur in der Standortrichtlinie angegebene Haftungsausschlüsse verwendet.

    
    </div>

<!-- end list -->

  - **Notfall Wahl Zeichenfolge**  
    Diese Wählzeichenfolge (abzüglich des führenden "+", aber einschließlich einer Normalisierung, die vom Wählplan des lync-Benutzers ausgeführt wird) bedeutet, dass ein Anruf ein Notruf ist. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
    
    <div>
    

    > [!NOTE]  
    > Wenn in Ihrer Organisation kein Präfix für den Zugriff auf externe Leitungen verwendet wird, müssen Sie keine entsprechende Normalisierungsregel für Wähleinstellungen erstellen, die der 911-Zeichenfolge vor dem Senden des Anrufs an ausgehendes Routing auf einem lync-Pool Server ein "+" hinzufügt. Das "+" wird dem lync-Client automatisch als Ergebnis der ortungsrichtlinie vorangestellt. Wenn Ihre Website jedoch ein externes Zugriffs Präfix verwendet, müssen Sie der entsprechenden Wähl Plan Richtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff abstreift und das "+" hinzufügt. Wenn Ihr Standort beispielsweise ein Präfix für den externen Zugriff von 9 verwendet und ein Benutzer 9&nbsp;911 anwählt, um einen Notruf zu tätigen, wird der Client seine Wähl Plan Richtlinie verwenden, um diese auf + 911 zu normalisieren, bevor die gewählte Nummer von den Routen am Standort des Anrufers ausgewertet wird. Profil.

    
    </div>

<!-- end list -->

  - **Notrufnummern-Zeichenfolgen Masken**  
    Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene **Notruf Zeichenfolge**übersetzt werden. So können Sie beispielsweise 112 hinzufügen, die für den größten Teil Europas die Notrufnummer ist. Ein Besucher von lync-Benutzern aus Europa weiß möglicherweise nicht, dass 911 die US-Notfallnummer ist, aber Sie können 112 anrufen und dasselbe Ergebnis erzielen. Geben Sie wie bei der Notruf Zeichenfolge keine "+" vor jeder Zahl ein, und wenn Sie die Zugriffscodes für externe Leitungen verwenden, stellen Sie sicher, dass in der Wähl Plan Richtlinie des Benutzers Normalisierungsregeln vorhanden sind, um die Zugriffscode Ziffer abzustreifen.

<!-- end list -->

  - **PSTN-Verwendung**  
    Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
    
    <div>
    

    > [!NOTE]  
    > Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Verwendung setzt die PSTN-Verwendungen außer Kraft, die der VoIP-Richtlinie des Benutzers zugewiesen sind. Dies gilt jedoch nur für Anrufe, die mit der Notrufwählzeichenfolge oder einer der Masken für Notrufwählzeichenfolgen abgesetzt werden.

    
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
    Gibt die Zeitspanne (in Stunden) zwischen Clientanforderungen für ein Standort Update vom standortinformationsdienst an. Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert lautet 4.

</div>

<span> </span>

</div>

</div>

</div>

