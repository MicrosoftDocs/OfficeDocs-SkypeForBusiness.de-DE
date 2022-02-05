---
title: Auswählen zugelassener Mitglieder
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 'Das Erstellen und Verwalten von Chatrooms für beständige Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Ein Administrator für beständigen Chat kann "AllowedMembers" und "Creators" für jede Kategorie definieren und auch die Standardeinstellungen und Verhaltensweisen des Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.'
---

# <a name="select-allowed-members"></a>Auswählen zugelassener Mitglieder

Das Erstellen und Verwalten von Chatrooms für beständige Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Ein Administrator für **beständigen Chat kann "AllowedMembers** " und **"Creators** " für jede Kategorie definieren und auch die Standardeinstellungen und Verhaltensweisen des Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.

Benutzer, Organisationseinheiten (OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, kann sie Benutzer, Organisationseinheiten und Benutzergruppen aus der Liste **der zugelassenen Mitglieder** der Kategorie als Chatroommanager und Mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen.

## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **"Zulässige Mitglieder auswählen"** können Sie die folgenden Aufgaben ausführen:

- [Konfigurieren von Kategorien](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Neue Features für Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server Systemsteuerung ausführen können, finden Sie unter [Verwalten Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on), that are alloweded to be added as members of chat rooms belonging to the category. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).


Ausführliche Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie in der Planungsdokumentation [unter "Übersicht über den Server für beständigen Chat](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) ". Ausführliche Informationen zum Arbeiten mit Konfigurationen des Servers für beständigen Chat finden Sie unter ["Konfigurieren des Servers für beständigen Chat](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) " in der Bereitstellungsdokumentation und [verwalten von Lync Server 2013, Server für beständigen Chat](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Grundlegendes zur Persistent Chat-Mitgliedschaft](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)