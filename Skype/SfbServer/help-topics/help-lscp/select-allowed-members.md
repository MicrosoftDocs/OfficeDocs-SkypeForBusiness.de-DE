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
description: Das Erstellen und Verwalten von Chatrooms für beständigen Chat ist mit der richtigen Verwendung von Kategorien wesentlich einfacher. Ein Administrator für beständigen Chat kann "AllowedMembers" und "Creators" für jede Kategorie definieren und auch die Standardeinstellungen und Verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829135"
---
# <a name="select-allowed-members"></a>Auswählen zugelassener Mitglieder

Das Erstellen und Verwalten von Chatrooms für beständigen Chat ist mit der richtigen Verwendung von Kategorien wesentlich einfacher. Ein Administrator für beständigen Chat kann **"AllowedMembers"** und **"Creators"** für jede Kategorie definieren und auch die Standardeinstellungen und Verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für beständigen Chat erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell Cmdlets.

Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können sie Benutzer, Organisationsgruppen und Benutzergruppen aus der Liste **"AllowedMembers"** der Kategorie als Chatroommanager und -mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen.

## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite "Zulässige Mitglieder auswählen" können Sie die **folgenden Aufgaben** ausführen:

- [Konfigurieren von Kategorien](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [Neue Features für Persistent Chat Server](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Details zu den verschiedenen Verfahren, die Sie mithilfe der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter ["Verwalten von Skype for Business Server 2015".](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

Fügen Sie in  "Mitgliedschaft" im Abschnitt "Zulässige Mitglieder" Benutzer und andere Active Directory-Domänendienste-Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten und so weiter) hinzu, die als Mitglieder von Chatrooms hinzugefügt werden dürfen, die zur Kategorie gehören. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).


Ausführliche Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie in der Planungsdokumentation unter ["Übersicht](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) über den Server für beständigen Chat". Ausführliche Informationen zum Arbeiten mit Konfigurationen für den Server für beständigen Chat finden Sie unter [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.

## <a name="see-also"></a>Siehe auch

[Grundlegendes zur Persistent Chat-Mitgliedschaft](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
