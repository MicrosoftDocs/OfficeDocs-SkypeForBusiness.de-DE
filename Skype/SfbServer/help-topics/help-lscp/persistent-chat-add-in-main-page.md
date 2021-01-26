---
title: Add-In für beständigen Chat – Hauptseite
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Sie können den Add-In-Abschnitt der Seite für beständigen Chat verwenden, um URLs Chatrooms zuzuordnen. Diese URLs werden im Client im Chatroom im Bereich zur Erweiterbarkeit von Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins Add-Ins hinzufügen, und Chatroommanager/Ersteller müssen Chatrooms einem der registrierten Add-Ins zuordnen, bevor Benutzer dieses Upgrade auf ihrem Client sehen können.
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803795"
---
# <a name="persistent-chat-add-in-main-page"></a>Add-In für beständigen Chat – Hauptseite

Sie können den **Add-In-Abschnitt** der Seite für beständigen **Chat** verwenden, um URLs Chatrooms zuzuordnen. Diese URLs werden im Client im Chatroom im Bereich zur Erweiterbarkeit von Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins Add-Ins hinzufügen, und Chatroommanager/Ersteller müssen Chatrooms einem der registrierten Add-Ins zuordnen, bevor Benutzer dieses Upgrade auf ihrem Client sehen können.

Add-Ins werden verwendet, um die Raumerfahrung zu erweitern. Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung verweist, die abfängt, wenn ein Aktienticker in einem Chatroom veröffentlicht wird, und zeigt den Aktienverlauf im Erweiterbarkeitsbereich an. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-In, um einen freigegebenen Kontext wie "Kopf-an-Kopf" oder "Thema des Tages" einzubetten.

Informationen zum Erstellen von Add-Ins für Chatrooms für beständigen Chat finden Sie unter "Konfigurieren von Add-Ins für Chatrooms für beständigen [Chat in Skype for Business Server 2015".](../../manage/persistent-chat/configure-add-ins.md) Wenn Sie ein Administrator für beständigen Chat sind, können Sie Add-Ins mithilfe der Systemsteuerung oder Windows PowerShell erstellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Add-In** können Sie die folgenden Aufgaben ausführen:

- [Konfigurieren von Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>So konfigurieren Sie Add-Ins für Chatrooms

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der Systemsteuerung verwenden können, finden Sie unter [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.

    Wählen Sie für mehrere Bereitstellungen des Pools für beständigen Chat den entsprechenden Pool aus der Dropdownliste aus.

4. Klicken Sie auf der Seite **Add-In** auf **Neu**.

5. Wählen **Sie in "Dienst** auswählen" den Dienst aus, der dem Serverpool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen Pool verschoben oder von unterschiedlichen Pools gemeinsam genutzt werden.

6. Führen Sie unter **Neues Add-In** Folgendes aus:

   - Geben Sie unter **Name** einen Namen für das neue Add-In an.

   - Geben Sie unter **URL** die URL an, die dem Add-In zugeordnet werden soll. Die URLs sind auf die Protokolle "http" und "https" beschränkt.

7. Klicken Sie auf **Commit ausführen**.

## <a name="see-also"></a>Weitere Informationen

Weitere Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie unter ["Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) ["Deploy Persistent Chat Server in Skype for Business Server 2015"](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und ["Manage Persistent Chat Server in Skype for Business Server 2015".](../../manage/persistent-chat/persistent-chat.md)


