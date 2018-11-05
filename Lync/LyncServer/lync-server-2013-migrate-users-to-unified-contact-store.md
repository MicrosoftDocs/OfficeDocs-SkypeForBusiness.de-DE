---
title: 'Lync Server 2013: Migrieren von Benutzern zum einheitlichen Kontaktspeicher'
TOCTitle: Migrieren von Benutzern zum einheitlichen Kontaktspeicher
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204737(v=OCS.15)
ms:contentKeyID: 49293408
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Benutzern zum einheitlichen Kontaktspeicher in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Die Kontakte eines Benutzers werden in den folgenden Fällen automatisch zum Exchange 2013-Server migriert:

  - Dem Benutzer muss eine Benutzerdiensterichtlinie zugewiesen worden sein, für die die Option "UcsAllowed" auf "True" gesetzt ist.

  - Dem Benutzer muss ein Exchange 2013-Postfach zur Verfügung gestellt worden sein, und der Benutzer muss sich mindestens ein Mal am Postfach angemeldet haben.

  - Der Benutzer meldet sich mithilfe eines Lync 2013-Rich-Clients an.

Wenn sich der Benutzer mit Lync 2010 oder einer früheren Clientversion anmeldet oder der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, wird die Benutzerdiensterichtlinie ignoriert, und die Kontakte des Benutzers verbleiben in Lync Server.

Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:

  - Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:
    
    HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP-URL\>\\UCS
    
    Sind die Kontakte des Benutzers in Exchange 2013 gespeichert, enthält dieser Schlüssel für "InUCSMode" den Wert 2165.

  - Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus. Geben Sie an der Befehlszeile der Lync Server-Verwaltungsshell Folgendes ein:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Ist **Test-CsUnifiedContactStore** erfolgreich, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.

