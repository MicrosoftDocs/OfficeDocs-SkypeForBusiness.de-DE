---
title: Konfigurieren von Microsoft Lync Server 2013 zur Verwendung des einheitlichen Kontaktspeichers
TOCTitle: Konfigurieren von Microsoft Lync Server 2013 zur Verwendung des einheitlichen Kontaktspeichers
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49890781
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Microsoft Lync Server 2013 zur Verwendung des einheitlichen Kontaktspeichers

 

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Der einheitliche Kontaktspeicher ermöglicht es Benutzern, eine einzige Kontaktliste zu führen, deren Kontakte dann in vielen Anwendungen verfügbar sind (z. B. in Microsoft Lync 2013, Microsoft Outlook 2013 und Microsoft Outlook Web App 2013). Wenn Sie den einheitlichen Kontaktspeicher für einen Benutzer aktivieren, werden dessen Kontakte nicht in Microsoft Lync Server 2013 gespeichert und über das SIP-Protokoll abgerufen, sondern in Microsoft Exchange Server 2013 gespeichert und von Exchange-Webdiensten abgerufen.


> [!NOTE]
> Technisch gesehen werden die Kontaktinformationen in zwei Ordnern gespeichert, die sich im Exchange 2013-Postfach des Benutzers befinden. Die Kontakte selbst werden in einem Ordner mit dem Namen "Lync-Kontakte" gespeichert, der für Endbenutzer sichtbar ist. Die Metadaten zu den Kontakten werden in einem Unterordner gespeichert, der für Endbenutzer nicht sichtbar ist.



## Aktivieren des einheitlichen Kontaktspeichers für einen Benutzer

Wenn Sie Server-zu-Server-Authentifizierung zwischen Lync Server 2013 und Exchange 2013 bereits konfiguriert haben, dann haben Sie auch die Verwendung des einheitlichen Kontaktspeichers aktiviert – mehr Serverkonfiguration ist nicht erforderlich. Beim Benutzerkonto sind jedoch noch Konfigurationsschritte erforderlich, damit die Kontakte des Benutzers in den einheitlichen Kontaktspeicher verschoben werden. In der Standardeinstellung werden Benutzerkontakte nicht im einheitlichen Kontaktspeicher, sondern in Lync Server gespeichert.

Der Zugriff auf den einheitlichen Kontaktspeicher wird mithilfe von Lync Server-Benutzerdienste-Richtlinien verwaltet. Benutzerdienste-Richtlinien verfügen nur über eine einzige Eigenschaft (UcsAllowed), die angibt, wo die Kontakte eines Benutzers gespeichert werden. Wenn ein Benutzer von einer Benutzerdienste-Richtlinie verwaltet wird, in der "UcsAllowed" auf "True" ($True) gesetzt ist, werden die Kontakte des Benutzers im einheitlichen Kontaktspeicher gespeichert. Wenn die Eigenschaft "UcsAllowed" auf "False" ($False) gesetzt ist, werden seine Kontakte in Lync Server gespeichert.

Während der Installation von Lync Server 2013 wird auch eine einzelne (auf globaler Ebene konfigurierte) Benutzerdienste-Richtlinie installiert. Der Wert "UcsAllowed" in dieser Richtlinie ist auf "True" festgelegt, was bedeutet, dass Benutzerkontakte standardmäßig im einheitlichen Kontaktspeicher gespeichert werden (vorausgesetzt, dass dieser bereitgestellt und konfiguriert wurde). Wenn Sie alle Benutzerkontakte zum einheitlichen Kontaktspeicher migrieren möchten, müssen Sie nichts weiter tun.

Wenn Sie lieber nicht alle Kontakte zum einheitlichen Kontaktspeicher migrieren möchten, können Sie den einheitlichen Kontaktspeicher für alle Benutzer deaktivieren, indem Sie die Eigenschaft "UcsAllowed" in der globalen Richtlinie auf "False" setzen:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Nachdem Sie den einheitlichen Kontaktspeicher in der globalen Richtlinie deaktiviert haben, können Sie dann eine benutzerbezogene Richtlinie erstellen, die die Verwendung des einheitlichen Kontaktspeichers ermöglicht. Auf diese Weise können Sie einigen Benutzern erlauben, ihre Kontakte im einheitlichen Kontakspeicher abzulegen, während andere Benutzer ihre Kontakte weiterhin in Lync Server führen. Eine benutzerbezogene Benutzerdienste-Richtlinie können Sie mit einem Befehl erstellen, der wie folgt aussieht:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Nachdem Sie die neue Richtlinie erstellt haben, müssen Sie sie jedem Benutzer zuweisen, der Zugang zum einheitlichen Kontaktspeicher haben soll. Das Zuweisen von benutzerbezogenen Richtlinien zu Benutzern führen Sie mit Befehlen durch, die wie folgt aussehen:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Nachdem die Richtlinie einem Benutzer zugewiesen wurde, beginnt Lync Server damit, die Kontakte dieses Benutzers in den einheitlichen Benutzerspeicher zu migrieren. Nach Abschluss der Migration werden die Kontakte des Benutzers dann in Exchange statt in Lync Server gespeichert. Wenn der Benutzer während der Migration bei Lync 2013 angemeldet ist, wird er mithilfe einer angezeigten Meldung aufgefordert, sich von Lync ab- und dann wieder anzumelden, damit der Vorgang abgeschlossen werden kann. Die Kontakte von Benutzern, denen diese benutzerbezogene Richtlinie zugewiesen wurde, werden nicht zum einheitlichen Kontaktspeicher migriert. Der Grund ist, dass diese Benutzer von der globalen Richtlinie verwaltet werden und die Verwendung des einheitlichen Kontaktspeichers in der globalen Richtlinie deaktiviert wurde.

Mit dem [Test-CsUnifiedContactStore](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUnifiedContactStore)-Cmdlet in der Lync Server-Verwaltungsshell können Sie überprüfen, ob die Kontakte eines Benutzers erfolgreich zum einheitlichen Kontaktspeicher migriert wurden:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Wenn das Test-CsUnifiedContactStore-Cmdlet einen Erfolg meldet, bedeutet das, dass die Kontakte für den Benutzer "sip:kenmyer@litwareinc.com" zum einheitlichen Kontaktspeicher migriert wurden.

## Zurückverlegung aus dem einheitlichen Kontaktspeicher

Wenn Sie die Kontakte eines Benutzers aus dem einheitlichen Kontaktspeicher entfernen möchten (zum Beispiel weil der Benutzer wieder zurück zu Microsoft Lync Server 2010 wechselt und daher den einheitlichen Kontaktspeicher nicht mehr nutzen kann), müssen Sie zwei Schritte durchführen. Als Erstes müssen Sie dem Benutzer eine neue Benutzerdienste-Richtlinie zuweisen, die das Speichern von Kontakten im einheitlichen Kontaktspeicher verhindert (d. h. eine Richtlinie, in der die Eigenschaft "UcsAllowed" auf "$False" eingestellt ist). Wenn solch eine Richtlinie nicht vorhanden ist, können Sie mit dem folgenden Befehl eine erstellen:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Anschließend können Sie diese neue benutzerbezogene Richtlinie (NoUnifiedContactStore) mit dem folgenden Befehl zuweisen:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Dieser Befehl weist die neue Richtlinie dem Benutzer "Ken Myer" zu und verhindert auch, dass dessen Kontakte zum einheitlichen Kontaktspeicher migriert werden.


> [!NOTE]
> In manchen Fällen können Sie den gleichen Endeffekt erzielen, indem Sie einfach die Zuweisung der aktuellen Benutzerdienste-Richtlinie für den Benutzer aufheben. Das wäre zum Beispiel der Fall, wenn dem Benutzer "Ken Myer" eine benutzerbezogene Benutzerdienste-Richtlinie zugewiesen ist, die den einheitlichen Kontaktspeicher aktiviert, während die globale Richtlinie die Verwendung des einheitlichen Kontaktspeichers verbietet. In solch einem Fall können Sie die Zuweisung der benutzerbezogenen Benutzerdienste-Richtlinie für Ken aufheben. Ken würde dann automatisch von der globalen Richtlinie verwaltet werden und somit keinen Zugriff auf den einheitlichen Kontaktspeicher mehr besitzen.<BR>Wenn Sie eine vorhandene Zuweisung einer benutzerbezogenen Richtlinie wieder aufheben möchten, verwenden Sie den gleichen Befehl wie oben, nur dass Sie diesmal den Parameter "PolicyName" auf den Wert "Null" setzen:<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



Die Formulierung "\[...\] verhindert, dass die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert werden" sollten Sie bei der Arbeit mit dem einheitlichen Kontaktspeicher unbedingt wörtlich nehmen. Es reicht nicht aus, dem Benutzer Ken einfach nur eine neue Benutzerdienste-Richtlinie zuzuweisen, damit seine Kontakte aus dem einheitlichen Kontaktspeicher verlegt werden. Wenn sich ein Benutzer bei Lync Server 2013 anmeldet, prüft das System in der Benutzerdienste-Richtlinie des Benutzers nach, ob seine Kontakte im einheitlichen Kontaktspeicher gespeichert werden sollen. Wenn die Antwort "Ja" lautet (d. h. wenn die Eigenschaft "UcsAllowed" auf "$True" gesetzt ist), werden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert (falls sie sich nicht bereits dort befinden). Wenn die Antwort "Nein" lautet, ignoriert Lync Server einfach die Kontakte des Benutzers und macht mit der nächsten Aufgabe weiter. d. h., dass Lync Server nicht automatisch Kontakte aus dem einheitlichen Kontaktspeicher verschiebt – unabhängig davon, welchen Wert die Eigenschaft "UcsAllowed" hat.

Es bedeutet auch, dass Sie nach dem Zuweisen einer neuen Benutzerdienste-Richtlinie zu einem Benutzer das [Invoke-CsUcsRollback](https://docs.microsoft.com/en-us/powershell/module/skype/Invoke-CsUcsRollback)-Cmdlet ausführen müssen, damit die Kontakte des Benutzers aus Exchange 2013 wieder zurück nach Lync Server 2013 verschoben werden. Beispiel: Nachdem Sie dem Benutzer "Ken Myer" eine neue Benutzerdienste-Richtlinie zugewiesen haben, können Sie seine Kontakte mit dem folgenden Befehl aus dem einheitlichen Kontaktspeicher verlegen:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Wenn Sie die Benutzerdienste-Richtlinie ändern, ohne anschließend das Invoke-CsUcsRollback-Cmdlet auszuführen, bleiben die Kontakte von Ken im einheitlichen Kontaktspeicher. Und was wäre, wenn Sie das Invoke-CsUcsRollback-Cmdlet ausführen, ohne die Benutzerdienste-Richtlinie von Ken Myer zu ändern? In diesem Fall werden die Kontakte von Ken nur vorübergehend aus dem einheitlichen Kontaktspeicher entfernt. Achten Sie hierbei bitte auf das Wort "vorübergehend"\! Denn nachdem Kens Kontakte entfernt wurden, prüft Lync Server 2013 nach Ablauf von sieben Tagen wieder nach, welche Benutzerdienste-Richtlinie Ken zugewiesen ist. Wenn Ken weiterhin eine Richtlinie zugewiesen ist, die ihn für den einheitlichen Kontaktspeicher aktiviert, werden seine Kontakte automatisch wieder zurück in den Kontaktspeicher verschoben. Um die Kontakte dauerhaft aus dem einheitlichen Kontaktspeicher zu entfernen, müssen Sie nicht nur das Invoke-CsUcsRollback-Cmdlet ausführen, sondern zusätzlich auch seine Benutzerdienste-Richtlinie ändern.

Aufgrund der zahlreichen Variablen, die sich auf die Migration auswirken können, kann schwer geschätzt werden, wie viel Zeit erforderlich ist, bis Konten vollständig zum einheitlichen Kontaktspeicher migriert sind. Als allgemeine Regel lässt sich jedoch sagen, dass die Migration nicht unmittelbar in Kraft tritt: Auch wenn Sie nur sehr wenige Kontakte migrieren, kann es zehn Minuten oder länger dauern, bis die Verschiebung abgeschlossen ist.

