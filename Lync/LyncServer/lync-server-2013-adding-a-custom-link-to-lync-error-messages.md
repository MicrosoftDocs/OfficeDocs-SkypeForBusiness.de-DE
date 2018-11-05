---
title: 'Lync Server 2013: Hinzufügen eines benutzerdefinierten Links zu Lync-Fehlermeldungen'
TOCTitle: Hinzufügen eines benutzerdefinierten Links zu Lync-Fehlermeldungen
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398979(v=OCS.15)
ms:contentKeyID: 52056471
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen eines benutzerdefinierten Links zu Lync-Fehlermeldungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Passen Sie Lync 2013-Fehlermeldungen an, indem Sie einen Link zu Ihrer eigenen Fehlerbehandlung oder Ihren Helpdeskinformationen hinzufügen. Verwenden Sie dafür das Cmdlet **New-CSClientPolicy** oder das Cmdlet **Set-CSClientPolicy** Lync Server-Verwaltungsshell mit dem Parameter "CustomLinkInErrorMessages". Der Text des benutzerdefinierten Links lautet: "Klicken Sie hier, um Supportthemen vom Administrator anzuzeigen" und kann nicht benutzerdefiniert angepasst werden.

Der folgende Befehl führt beispielsweise dazu, dass der benutzerdefinierte Link im Fußzeilenbereich jeder Lync 2013-Fehlermeldung angezeigt und das Linkziel auf http://contoso.com/help/LyncHelpDesk.aspx festgelegt wird:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Verwenden Sie **Grant-CSClientPolicy**, um Benutzern diese neue Richtlinie zuzuweisen. Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der Lync Server-Verwaltungsshell-Dokumentation.

