---
title: 'Lync Server 2013: Konfigurieren lync Server für die Verwendung des einheitlichen Kontaktspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21e39b9584dfc274e9cf525db85d50df6188fac0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Konfigurieren Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-07_

Mit dem einheitlichen Kontaktspeicher können Benutzer eine einzelne Kontaktliste verwalten und diese Kontakte dann in mehreren Anwendungen zur Verfügung stellen, einschließlich Microsoft lync 2013, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013. Wenn Sie den einheitlichen Kontaktspeicher für einen Benutzer aktivieren, werden die Kontakte des Benutzers nicht in Microsoft lync Server 2013 gespeichert und dann mithilfe des SIP-Protokolls abgerufen. Stattdessen werden seine Kontakte in Microsoft Exchange Server 2013 gespeichert und mithilfe von Exchange Webdienste abgerufen.

<div>


> [!NOTE]  
> Technisch gesehen werden Kontaktinformationen in einem Ordnerpaar gespeichert, die im Exchange 2013 Postfach des Benutzers gefunden werden. Die Kontakte selbst werden in einem Ordner namens lync Contacts gespeichert, der für Endbenutzer sichtbar ist. Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen lync Server 2013 und Exchange 2013 konfiguriert haben, haben Sie auch die Verwendung des einheitlichen Kontaktspeichers aktiviert. keine zusätzliche Serverkonfiguration erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. Standardmäßig werden Benutzer Kontakte in lync Server aufbewahrt und nicht im einheitlichen Kontaktspeicher.

Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe lync Server Richtlinien für Benutzer Dienste verwaltet. Benutzerdienste-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer von einer Benutzer dienstrichtlinie verwaltet wird, in der ucsallowed gesetzt auf true ($true) festgelegt wurde, werden die Kontakte des Benutzers im einheitlichen Kontaktspeicher gespeichert. Wenn der Benutzer von einer Benutzer dienstrichtlinie verwaltet wird, in der ucsallowed gesetzt auf false ($false) festgelegt wurde, werden seine Kontakte in lync Server gespeichert.

Bei der Installation von lync Server 2013 wird auch eine Richtlinie für einzelne Benutzer Dienste installiert (auf globaler Ebene konfiguriert). Der Wert ucsallowed gesetzt in dieser Richtlinie ist auf true festgelegt, was bedeutet, dass Benutzer Kontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (sofern diese bereitgestellt und konfiguriert wurden). Wenn Sie alle Ihre Benutzer Kontakte in den einheitlichen Kontaktspeicher migrieren möchten, müssen Sie überhaupt nichts tun.

Wenn Sie es vorziehen, nicht alle Kontakte in den einheitlichen Kontaktspeicher zu migrieren, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die ucsallowed gesetzt-Eigenschaft in der globalen Richtlinie auf false festlegen:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Nachdem Sie den einheitlichen Kontaktspeicher in der globalen Richtlinie deaktiviert haben, können Sie eine benutzerspezifische Richtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. auf diese Weise können einige Benutzer Ihre Kontakte im einheitlichen Kontaktspeicher behalten, während andere Benutzer Ihre Kontakte weiterhin in lync Server halten. Sie können eine Benutzer dienstrichtlinie auf Benutzerbasis erstellen, indem Sie einen Befehl wie den folgenden verwenden:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen durch, die wie folgt aussehen:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Nachdem die Richtlinie zugewiesen wurde lync Server startet die Migration der Benutzer Kontakte in den einheitlichen Kontaktspeicher. Nachdem die Migration abgeschlossen ist, werden die Kontakte des Benutzers in Exchange und nicht in lync Server gespeichert. Wenn der Benutzer bei Abschluss der Migration bei lync 2013 angemeldet ist, wird ein Meldungsfeld angezeigt, und er oder Sie wird aufgefordert, sich von lync abzumelden und sich dann wieder anzumelden, um den Prozess abzuschließen. Benutzern, denen diese benutzerbezogene Richtlinie nicht zugewiesen wurde, werden Ihre Kontakte nicht zum einheitlichen Kontaktspeicher migriert. Dies liegt daran, dass diese Benutzer von der globalen Richtlinie verwaltet werden und dass die Verwendung des einheitlichen Kontaktspeichers in der globalen Richtlinie deaktiviert wurde.

Sie können überprüfen, ob die Kontakte eines Benutzers erfolgreich zum einheitlichen Kontaktspeicher migriert wurden, indem Sie das [Test-CsUnifiedContactStore-](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) Cmdlet in der lync Server-Verwaltungsshell ausführen:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Wenn das Test-CsUnifiedContactStore-Cmdlet einen Erfolg meldet, bedeutet das, dass die Kontakte für den Benutzer "sip:kenmyer@litwareinc.com" zum einheitlichen Kontaktspeicher migriert wurden.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie die Kontakte eines Benutzers aus dem einheitlichen Kontaktspeicher entfernen müssen (beispielsweise, wenn der Benutzer auf Microsoft lync Server 2010 verlagert werden muss und somit nicht mehr den einheitlichen Kontaktspeicher verwenden kann), müssen Sie zwei Schritte ausführen. Zunächst müssen Sie dem Benutzer eine neue Benutzer Dienste-Richtlinie zuweisen, die das Speichern von Kontakten im einheitlichen Kontaktspeicher untersagt. (Das heißt, eine Richtlinie, bei der die ucsallowed gesetzt-Eigenschaft auf $false festgelegt wurde.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie eine mit einem Befehl wie dem folgenden erstellen:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Dieser Befehl weist die neue Richtlinie dem Benutzer "Ken Myer" zu und verhindert auch, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.

<div>


> [!NOTE]  
> In manchen Fällen können Sie den gleichen Endeffekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzerdienste-Richtlinie für den Benutzer aufheben. Das wäre zum Beispiel der Fall, wenn dem Benutzer "Ken Myer" eine benutzerbezogene Benutzerdienste-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In solch einem Fall können Sie die Zuweisung der benutzerbezogenen Benutzerdienste-Richtlinie für Ken aufheben. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen.<BR>Wenn Sie eine vorhandene Zuweisung einer benutzerbezogenen Richtlinie wieder aufheben möchten, verwenden Sie den gleichen Befehl wie oben, nur dass Sie diesmal den Parameter "PolicyName" auf den Wert "Null" setzen:<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

Die Terminologie "verhindert, dass Ken Kontakte zum einheitlichen Kontaktspeicher migriert werden" ist bei der Arbeit mit dem einheitlichen Kontaktspeicher wichtig zu beachten. Das einfache Zuweisen von Ken mit einer neuen Benutzer dienstrichtlinie werden seine Kontakte nicht aus dem einheitlichen Kontaktspeicher weiter verlagert. Wenn sich ein Benutzer bei lync Server 2013 anmeldet, überprüft das System die Benutzer Dienste-Richtlinie des Benutzers, um festzustellen, ob seine Kontakte im einheitlichen Kontaktspeicher aufbewahrt werden sollen. Wenn die Antwort ja lautet (wenn die ucsallowed gesetzt-Eigenschaft auf $true festgelegt ist), werden diese Kontakte zum einheitlichen Kontaktspeicher migriert (vorausgesetzt, diese Kontakte befinden sich noch nicht im einheitlichen Kontaktspeicher). Wenn die Antwort nein lautet, ignoriert lync Server einfach die Kontakte des Benutzers und wechselt zur nächsten Aufgabe. Das bedeutet, dass lync Server die Kontakte eines Benutzers nicht automatisch aus dem einheitlichen Kontaktspeicher verschiebt, unabhängig vom Wert der ucsallowed gesetzt-Eigenschaft.

Das bedeutet auch, dass Sie nach dem Zuweisen des Benutzers zu einer neuen Benutzer Dienste-Richtlinie das [Invoke-CsUcsRollback-](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) Cmdlet ausführen müssen, um die Kontakte des Benutzers aus Exchange 2013 und zurück in lync Server 2013 zu verlagern. Beispiel: Nachdem Sie dem Benutzer "Ken Myer" eine neue Benutzerdienste-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Wenn Sie die Benutzerdienste-Richtlinie ändern, ohne anschließend das Invoke-CsUcsRollback-Cmdlet auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort "vorübergehend"! Nachdem Ken Kontakte aus dem einheitlichen Kontaktspeicher entfernt wurden, warten lync Server 2013 7 Tage und überprüfen dann, welche Benutzer Dienste-Richtlinie Ken zugewiesen wurde. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.

Aufgrund der großen Anzahl von Variablen, die sich auf die Migration auswirken können, ist es schwierig abzuschätzen, wie lange es dauert, bis die Konten vollständig zum einheitlichen Kontaktspeicher migriert werden. In der Regel wird die Migration jedoch nicht sofort wirksam: selbst beim Migrieren einer kleinen Anzahl von Kontakten dauert es möglicherweise 10 Minuten oder länger, bis die Umstellung abgeschlossen ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

