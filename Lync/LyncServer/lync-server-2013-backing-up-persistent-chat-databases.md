---
title: Sichern von Datenbanken des beständigen Chats
TOCTitle: Sichern von Datenbanken des beständigen Chats
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945646(v=OCS.15)
ms:contentKeyID: 52056446
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sichern von Datenbanken des beständigen Chats

 

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Der Beständiger Chat-Chatroominhalt wird in der Beständiger Chat-Datenbank ("Mgc.mdf") gespeichert. Diese für das Unternehmen wichtigen Daten sollten regelmäßig gesichert werden. Neben dem Chatroominhalt werden in der Beständiger Chat-Datenbank auch Informationen zu den Prinzipalen (z. B. Benutzer und Benutzergruppen) sowie zu den Rollen und ihren Zugriffsberechtigungen für Chatrooms gespeichert.

Es gibt zwei Möglichkeiten zum Sichern von Beständiger Chat-Daten.

  - Die SQL Server-Sicherung

  - Das `Export-CsPersistentChatData`-Cmdlet, das Beständiger Chat-Daten als Datei exportiert

Die mithilfe der SQL Server-Sicherung erstellten Daten belegen sehr viel mehr – ca. 20 mal mehr – Speicherplatz als die Daten, die mit dem `Export-CsPersistentChatData`-Cmdlet exportiert werden. Die SQL Server-Sicherung ist aber vermutlich das Verfahren, mit dem Administratoren vertraut sind.

