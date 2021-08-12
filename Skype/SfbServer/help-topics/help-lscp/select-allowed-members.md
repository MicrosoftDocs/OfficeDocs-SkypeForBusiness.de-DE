---
title: Auswählen zugelassener Mitglieder
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Das Erstellen und Verwalten von Chatrooms für beständige Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Ein Administrator für beständigen Chat kann "AllowedMembers" und "Creators" für jede Kategorie definieren und auch die Standardeinstellungen und -verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.
ms.openlocfilehash: 3f757d7c25a429279bbde3c63e717af9d1930cb9ea40076ac9aa5b9d9567356a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342170"
---
# <a name="select-allowed-members"></a>Auswählen zugelassener Mitglieder

Das Erstellen und Verwalten von Chatrooms für beständige Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Ein Administrator für beständigen Chat kann **"AllowedMembers"** und **"Creators"** für jede Kategorie definieren und auch die Standardeinstellungen und -verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.

Benutzer, Organisationseinheiten (OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, kann sie Benutzer, Organisationseinheiten und Benutzergruppen aus der Liste **der zugelassenen Mitglieder** der Kategorie als Chatroommanager und Mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen.

## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **"Zulässige Mitglieder auswählen"** können Sie die folgenden Aufgaben ausführen:

- [Konfigurieren von Kategorien](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Neue Features für Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server Systemsteuerung ausführen können, finden Sie unter [Verwalten Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

Fügen Sie in **"Mitgliedschaft"** im Abschnitt **"Zugelassene Mitglieder"** Benutzer und andere Active Directory Domain Services-Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms der Kategorie hinzugefügt werden dürfen. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).


Ausführliche Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie in der Planungsdokumentation unter "Übersicht über den [Server für beständigen Chat".](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) Ausführliche Informationen zum Arbeiten mit Konfigurationen des Servers für beständigen Chat finden Sie unter ["Konfigurieren des Servers für beständigen Chat"](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in der Bereitstellungsdokumentation und [verwalten von Lync Server 2013, Server für beständigen Chat](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Grundlegendes zur Persistent Chat-Mitgliedschaft](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)