---
title: 'Lync Server 2013: Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten'
TOCTitle: Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398847(v=OCS.15)
ms:contentKeyID: 52056456
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Fügen Sie einen Haftungsausschluss oder eine Warnung an den Anfang jeder Lync 2013-Chatunterhaltung über das Cmdlet **New-CSClientPolicy** oder das Cmdlet **Set-CSClientPolicy**Lync Server-Verwaltungsshell mit dem Parameter "IMWarning" hinzu.

Der Befehl im folgenden Beispiel fügt immer eine Sicherheitserinnerung über dem Unterhaltungsfenster hinzu, wenn eine neue Chatunterhaltung beginnt:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Verwenden Sie **Grant-CSClientPolicy**, um Benutzern diese neue Richtlinie zuzuweisen. Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der Lync Server-Verwaltungsshell-Dokumentation.

