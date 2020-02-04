---
title: 'Lync Server 2013: Konfigurieren von lync Server für die Verwendung des einheitlichen Kontaktspeichers'
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
ms.openlocfilehash: 794d14172c5932436d46fbeb66ea1da4dd7a5e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Der Unified Contact Store ermöglicht es Benutzern, eine einzelne Kontaktliste zu verwalten und diese Kontakte dann in mehreren Anwendungen zur Verfügung zu haben, einschließlich Microsoft lync 2013, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013. Wenn Sie den Unified Contact Store für einen Benutzer aktivieren, werden die Kontakte des Benutzers nicht in Microsoft lync Server 2013 gespeichert und dann über das SIP-Protokoll abgerufen. Stattdessen werden seine Kontakte in Microsoft Exchange Server 2013 gespeichert und mithilfe von Exchange-Webdiensten abgerufen.

<div>


> [!NOTE]  
> Technisch gesehen werden die Kontaktinformationen in einem Paar von Ordnern gespeichert, die im Exchange 2013-Postfach des Benutzers gefunden werden. Die Kontakte selbst werden in einem Ordner namens lync-Kontakte gespeichert, der für Endbenutzer sichtbar ist. Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen lync Server 2013 und Exchange 2013 konfiguriert haben, haben Sie auch die Verwendung des einheitlichen Kontaktspeichers aktiviert. Es ist keine zusätzliche Serverkonfiguration erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. Standardmäßig werden Benutzer Kontakte in lync Server und nicht im Unified Contact Store aufbewahrt.

Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe von lync Server-Benutzer Dienst Richtlinien verwaltet. Benutzerdienst-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer von einer Richtlinie für Benutzer Dienste verwaltet wird, in der UcsAllowed auf "true" ($true) festgelegt wurde, werden die Kontakte des Benutzers im Unified Contact Store gespeichert. Wenn der Benutzer von einer Richtlinie für Benutzer Dienste verwaltet wird, in der UcsAllowed auf false ($false) festgelegt wurde, werden seine Kontakte in lync Server gespeichert.

Wenn Sie lync Server 2013 installieren, wird eine Richtlinie für einzelne Benutzer Dienste installiert, die auch im globalen Bereich konfiguriert ist. Der Wert „UcsAllowed“ in dieser Richtlinie ist auf „True“ festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dass dieser bereitgestellt und konfiguriert wurde). Wenn Sie alle Benutzerkontakte zum einheitlichen Kontaktspeicher migrieren möchten, müssen Sie nichts weiter tun.

Wenn Sie lieber nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die Eigenschaft „UcsAllowed“ in der globalen Richtlinie auf „False“ setzen:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Nachdem Sie den Unified Contact Store in der globalen Richtlinie deaktiviert haben, können Sie eine benutzerspezifische Richtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. auf diese Weise können einige Benutzer Ihre Kontakte im Unified Contact Store behalten, während andere Benutzer Ihre Kontakte weiterhin in lync Server behalten. Sie können eine Benutzer dienstrichtlinie pro Benutzer erstellen, indem Sie einen Befehl wie den folgenden verwenden:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen wie dem folgenden durch:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Nachdem die Richtlinie zugewiesen wurde, beginnt lync Server damit, die Kontakte des Benutzers in den Unified Contact Store zu migrieren. Nach Abschluss der Migration werden die Kontakte in Exchange anstatt in lync Server gespeichert. Wenn der Benutzer zu dem Zeitpunkt, zu dem die Migration abgeschlossen ist, bei lync 2013 angemeldet ist, wird ein Meldungsfeld angezeigt, in dem er oder Sie aufgefordert wird, sich bei lync abzumelden und dann erneut anzumelden, um den Prozess abzuschließen. Die Kontakte von Benutzern, denen diese benutzerbezogene Richtlinie zugewiesen wurde, werden nicht zum einheitlichen Kontaktspeicher migriert. Der Grund ist, dass diese Benutzer von der globalen Richtlinie verwaltet werden und die Verwendung des einheitlichen Kontaktspeichers in der globalen Richtlinie deaktiviert wurde.

Sie können überprüfen, ob die Kontakte eines Benutzers erfolgreich in den Unified Contact Store migriert wurden, indem Sie das Cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) in der lync Server-Verwaltungsshell ausführen:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Wenn das Cmdlet Test-CsUnifiedContactStore einen Erfolg meldet, bedeutet dies, dass die Kontakte für den Benutzer „sip:kenmyer@litwareinc.com“ zum einheitlichen Kontaktspeicher migriert wurden.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie die Kontakte eines Benutzers aus dem Unified Contact Store entfernen müssen (wenn der Benutzer beispielsweise auf Microsoft lync Server 2010 verlagert werden muss und daher den einheitlichen Kontaktspeicher nicht mehr verwenden kann), müssen Sie zwei Schritte ausführen. Zunächst müssen Sie dem Benutzer eine neue Richtlinie für Benutzer Dienste zuweisen, die verhindert, dass Kontakte im Unified Contact Store gespeichert werden. (Dies ist eine Richtlinie, bei der die UcsAllowed-Eigenschaft auf $false festgesetzt wurde.) Wenn Sie nicht über eine solche Richtlinie verfügen, können Sie Sie mithilfe eines Befehls wie den folgenden erstellen:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Dieser Befehl weist die neue Richtlinie dem Benutzer „Ken Myer“ zu und verhindert, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.

<div>


> [!NOTE]  
> In einigen Fällen können Sie denselben Nettoeffekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzer Dienste-Richtlinie des Benutzers aufheben. Das wäre z. B. der Fall, wenn dem Benutzer „Ken Myer“ eine benutzerbezogene Benutzerdienst-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In diesem Fall können Sie die Zuweisung der benutzerbezogenen dienstrichtlinie für Ken aufheben. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen.<BR>Wenn Sie eine zuvor zugewiesene Richtlinie für einzelne Benutzer aufheben möchten, verwenden Sie den gleichen Befehl wie zuvor, aber legen Sie diesen Parameter auf einen Nullwert fest:<BR>Grant-CsUserServicesPolicy –Identity „Ken Myer“ –PolicyName $Null



</div>

Die Terminologie "verhindert, dass Ken-Kontakte in den einheitlichen Kontaktspeicher migriert werden" ist wichtig, wenn Sie mit dem Unified Contact Store arbeiten. Wenn Sie einfach Ken eine neue Richtlinie für Benutzer Dienste zuweisen, werden die Kontakte nicht aus dem Unified Contact Store verschoben. Wenn sich ein Benutzer bei lync Server 2013 anmeldet, überprüft das System die Benutzer Dienste-Richtlinie des Benutzers, um festzustellen, ob seine Kontakte im Unified Contact Store aufbewahrt werden sollen. Wenn die Antwort ja lautet (das heißt, wenn die UcsAllowed-Eigenschaft auf $true festgesetzt ist), werden diese Kontakte in den Unified Contact Store migriert (vorausgesetzt, diese Kontakte sind noch nicht im Unified Contact Store). Wenn die Antwort nein lautet, ignoriert lync Server einfach die Kontakte des Benutzers und wechselt zur nächsten Aufgabe. Das bedeutet, dass lync Server die Kontakte eines Benutzers nicht automatisch aus dem Unified Contact Store verschieben wird, unabhängig vom Wert der UcsAllowed-Eigenschaft.

Das bedeutet auch, dass Sie nach dem Zuweisen des Benutzers zu einer neuen Richtlinie für Benutzer Dienste das [Invoke-CsUcsRollback-](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) Cmdlet ausführen müssen, um die Kontakte des Benutzers aus Exchange 2013 und zurück zu lync Server 2013 zu verschieben. Beispiel: Nachdem Sie dem Benutzer „Ken Myer“ eine neue Benutzerdienst-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Wenn Sie die Benutzerdienst-Richtlinie ändern, ohne anschließend das Cmdlet Invoke-CsUcsRollback auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort „vorübergehend“! Nachdem die Kontakte von Ken aus dem Unified Contact Store entfernt wurden, wartet lync Server 2013 7 Tage, und überprüfen Sie dann, welche Benutzer Dienste-Richtlinie Ken zugewiesen wurde. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.

Aufgrund der zahlreichen Variablen, die sich auf die Migration auswirken können, kann schwer geschätzt werden, wie viel Zeit erforderlich ist, bis Konten vollständig zum einheitlichen Kontaktspeicher migriert sind. Als allgemeine Regel lässt sich jedoch sagen, dass die Migration nicht unmittelbar in Kraft tritt: Auch wenn Sie nur sehr wenige Kontakte migrieren, kann es zehn Minuten oder länger dauern, bis die Verschiebung abgeschlossen ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

