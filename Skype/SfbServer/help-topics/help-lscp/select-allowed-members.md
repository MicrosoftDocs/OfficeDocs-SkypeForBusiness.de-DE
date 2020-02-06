---
title: Auswählen zugelassener Mitglieder
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher. Ein beständiger Chat-Administrator kann AllowedMembers und Creators für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden. Beständige Chat Administratoren erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets.
ms.openlocfilehash: ad371fada6bbb7e8c9a2620eb5ec533cc60a0673
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822298"
---
# <a name="select-allowed-members"></a>Auswählen zugelassener Mitglieder

Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher. Ein beständiger Chat-Administrator kann **AllowedMembers** und **Creators** für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden. Beständige Chat Administratoren erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets.

Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller einer Kategorie definiert werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in dieser Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können Sie Benutzer, OUs und Benutzergruppen aus der **AllowedMembers** -Liste der Kategorie als Chatroom-Manager und Mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen.

## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Zugelassene Mitglieder auswählen** können Sie die folgenden Aufgaben ausführen:

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Details zu den verschiedenen Verfahren, die Sie mit der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

Fügen Sie unter **Mitgliedschaft**im Abschnitt **zulässige Mitglieder** Benutzer und andere Active Directory-Domänendienst Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms, die der Kategorie angehören, hinzugefügt werden dürfen. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).


Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter Übersicht über den [Server für beständigen Chat](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation. Details zum Arbeiten mit beständigen Chat Serverkonfigurationen finden Sie unter [Konfigurieren des beständigen Chat Servers](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Bereitstellungsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
