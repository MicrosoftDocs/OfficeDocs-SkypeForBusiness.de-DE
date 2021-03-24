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
description: Das Erstellen und Verwalten von Chatrooms für beständigen Chat ist mit der richtigen Verwendung von Kategorien wesentlich einfacher. Ein Administrator für beständigen Chat kann AllowedMembers und Creators für jede Kategorie definieren und auch die Standardeinstellungen und Verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107991"
---
# <a name="select-allowed-members"></a>Auswählen zugelassener Mitglieder

Das Erstellen und Verwalten von Chatrooms für beständigen Chat ist mit der richtigen Verwendung von Kategorien wesentlich einfacher. Ein Administrator für beständigen Chat kann **AllowedMembers** und **Creators** für jede Kategorie definieren und auch die Standardeinstellungen und Verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.

Benutzer, Organisationseinheiten (OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können sie Benutzer, Organisationsgruppen und Benutzergruppen aus der **Liste "AllowedMembers"** der Kategorie als Chatroommanager und Mitglieder auswählen, um den Raum zu verwalten und daran teilzunehmen.

## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite Zulässige **Mitglieder** auswählen ausführen:

- [Konfigurieren von Kategorien](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Neue Features für Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Weitere Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter [Manage Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

Fügen Sie im  Abschnitt Mitgliedschaft im Abschnitt Zulässige Mitglieder Benutzer und andere Active Directory-Domänendiensteprinzipale (Benutzer, Verteilergruppen, Organisationseinheiten und so weiter) hinzu, die als Mitglieder von Chatrooms hinzugefügt werden dürfen, die zur Kategorie gehören. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).


Ausführliche Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie unter [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in der Planungsdokumentation. Ausführliche Informationen zum Arbeiten mit Konfigurationen des Servers für beständigen Chat finden Sie unter [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in der Bereitstellungsdokumentation und [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Grundlegendes zur Persistent Chat-Mitgliedschaft](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)