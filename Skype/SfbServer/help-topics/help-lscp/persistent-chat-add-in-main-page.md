---
title: Add-In für beständigen Chat – Hauptseite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Den Add-in-Seite im Abschnitt beständigen Chat können beständigen Chat Rooms URLs zugeordnet. Diese URLs werden im Client im Chatroom des Erweiterungsbereichs für Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins weitere Add-Ins hinzufügen und Verwalter und Ersteller von Chatrooms müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer dieses Upgrade in ihrem Client sehen können.
ms.openlocfilehash: 53030c7cddd0b761aee60d6e0b476d708ac52ba5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911037"
---
# <a name="persistent-chat-add-in-main-page"></a>Add-In für beständigen Chat – Hauptseite

Den **Add-in -** Seite im Abschnitt **Beständigen Chat** können beständigen Chat Rooms URLs zugeordnet. Diese URLs werden im Client im Chatroom des Erweiterungsbereichs für Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins weitere Add-Ins hinzufügen und Verwalter und Ersteller von Chatrooms müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer dieses Upgrade in ihrem Client sehen können.

-Add-ins werden zur Erweiterung der Erfahrung im Raum verwendet. Ein typisches Add-in gehören eine URL, die auf einer Silverlight-Anwendung, die fängt ab, wenn ein Aktienticker in einem Chatroom gesendet wurde, und den vordefinierten Verlauf im Bereich Erweiterbarkeit zeigt zeigen. Weitere Beispiele umfassen Einbetten einer OneNote 2013 URL im Chatroom als ein Add-in einige freigegebenen Kontext, beispielsweise "Oben unter Sicherheitsgesichtspunkten" oder "Thema des Tages".

Add-ins für beständigen Chat Rooms erstellen, finden Sie unter [Configure-add-ins für beständigen Chat Rooms in Skype für Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Wenn Sie eine Persistent Chat Administrator sind, können Sie-add-ins mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets erstellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Add-In** können Sie die folgenden Aufgaben ausführen:

- [Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>So konfigurieren Sie Add-ins für Chatrooms

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Systemsteuerung anwenden können, finden Sie unter [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.

    Wählen Sie für Bereitstellungen mit mehreren Persistent Chat Server Pool den entsprechenden Pool aus der Dropdownliste aus.

4. Klicken Sie auf der Seite **Add-In** auf **Neu**.

5. Wählen Sie unter **Wählen Sie einen Dienst**Dienst entspricht dem Persistent Chat Server Pool, wenn Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.

6. Gehen Sie unter **Neues Add-In** wie folgt vor:

   - Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.

   - Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.

7. Klicken Sie auf **Commit ausführen**.

## <a name="see-also"></a>Siehe auch

Details zu Persistent Chat Server-Features und Funktionen, finden Sie unter [Planen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Persistent Chatserver in Skype für Business Server 2015 bereitstellen](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und [Verwalten Persistent Chat Server in Skype für Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


