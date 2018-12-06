---
title: 'Lync Server 2013: Hinzufügen von Domänen von Benutzern und Benutzergruppen zur Chatroomkategorie'
TOCTitle: Hinzufügen von Domänen von Benutzern und Benutzergruppen zur Chatroomkategorie
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215884(v=OCS.15)
ms:contentKeyID: 49295820
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen von Domänen von Benutzern und Benutzergruppen zur Chatroomkategorie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Informationen zum Hinzufügen größerer Benutzergruppen zu einem Chatroom finden Sie unter [Konfigurieren von Kategorien in Lync Server 2013](lync-server-2013-configure-categories.md) und [Verwalten von Kategorien](manage-categories.md) in der Bereitstellungsdokumentation. Mit dem folgenden Befehl werden beispielsweise alle Benutzer in der Organisationseinheit "NorthAmericaUsers" in Active Directory zum Chatroom "NorthAmerica" hinzugefügt:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

Mit dem folgenden Befehl werden alle Mitglieder der Finanzdistributionsgruppe zum selben Chatroom hinzugefügt:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

