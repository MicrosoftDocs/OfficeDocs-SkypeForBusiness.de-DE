---
title: Add-In für beständigen Chat – Hauptseite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Sie können den Bereich "Add-in" auf der Seite "beständiger Chat" verwenden, um URLs mit beständigen Chatrooms zu verknüpfen. Diese URLs werden im Client im Chatroom des Erweiterungsbereichs für Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins weitere Add-Ins hinzufügen und Verwalter und Ersteller von Chatrooms müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer dieses Upgrade in ihrem Client sehen können.
ms.openlocfilehash: 60cf60c6f6691725161182c5cc4e5c2fd38a0576
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822578"
---
# <a name="persistent-chat-add-in-main-page"></a>Add-In für beständigen Chat – Hauptseite

Sie können den Bereich " **Add-in** " auf der Seite " **beständiger Chat** " verwenden, um URLs mit beständigen Chatrooms zu verknüpfen. Diese URLs werden im Client im Chatroom des Erweiterungsbereichs für Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins weitere Add-Ins hinzufügen und Verwalter und Ersteller von Chatrooms müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer dieses Upgrade in ihrem Client sehen können.

Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern. Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung zeigt, die abfängt, wenn ein Börsenticker in einem Chatroom bereitgestellt wird, und den Aktienverlauf im Bereich "Erweiterbarkeit" anzeigt. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen freigegebenen Kontext einzubeziehen, beispielsweise "Top of mindi" oder "Tagesthema".

Informationen zum Erstellen von Add-Ins für beständige Chatrooms finden Sie unter [Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Wenn Sie ein beständiger Chat-Administrator sind, können Sie Add-Ins mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets erstellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Add-In** können Sie die folgenden Aufgaben ausführen:

- [Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>So konfigurieren Sie Add-ins für Chatrooms

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Systemsteuerung anwenden können, finden Sie unter [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.

    Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.

4. Klicken Sie auf der Seite **Add-In** auf **Neu**.

5. Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.

6. Gehen Sie unter **Neues Add-In** wie folgt vor:

   - Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.

   - Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.

7. Klicken Sie auf **Commit ausführen**.

## <a name="see-also"></a>Siehe auch

Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Bereitstellen eines beständigen Chat Servers in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und [Verwalten des beständigen Chat Servers in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


