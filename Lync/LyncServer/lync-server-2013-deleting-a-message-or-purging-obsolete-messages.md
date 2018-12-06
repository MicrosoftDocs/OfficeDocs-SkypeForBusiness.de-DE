---
title: 'Lync Server 2013: Löschen einer Nachricht oder Löschen von veralteten Nachrichten'
TOCTitle: Löschen einer Nachricht oder Löschen von veralteten Nachrichten
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215874(v=OCS.15)
ms:contentKeyID: 49293781
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Nachricht oder Löschen von veralteten Nachrichten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Ein Beständiger Chat-Administrator kann eine Nachricht aus einem Beständiger Chat-Raum löschen (und optional durch eine andere Nachricht ersetzen). Administratoren können auch als Teil der ständigen Wartung veraltete Nachrichten löschen, um das Anwachsen der Datenbank zu minimieren. Beispielsweise werden mit diesem Windows PowerShell-Befehl alle Nachrichten aus dem ITChatRoom-Chatroom gelöscht, die vom Benutzer kenmyer@litwareinc.com veröffentlicht wurden:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

Und mit diesem Beispiel werden alle entfernten Nachrichten durch den Hinweis ersetzt, dass die Nachricht nicht mehr verfügbar ist:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Weitere Informationen finden Sie in dem Hilfethema zum [Remove-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPersistentChatMessage)-Cmdlet.

