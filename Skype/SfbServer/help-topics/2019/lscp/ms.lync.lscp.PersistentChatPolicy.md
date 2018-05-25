---
title: Richtlinie für beständigen Chat
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Die Seite Richtlinie für beständigen Chat, der Gruppe der beständigen Chat können Sie Richtlinien auf globaler Ebene sowie Pool, Standort oder Benutzer Ebene, einschließlich der Konfiguration der globale Richtlinie, und erstellen eine oder mehrere zusätzliche Benutzer- und Website Richtlinien für die Bereitstellung verwalten. Wenn Persistent Chat Server durch eine Richtlinie für einen Benutzer aktiviert ist, wird die Persistent Chat Server-Umgebung in ihrem Client angezeigt.
ms.openlocfilehash: 13f06436f3339da46e32557dff5290d5ad5541fd
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="persistent-chat-policy"></a>Richtlinie für beständigen Chat
 
Sie können die Seite **Richtlinie für beständigen Chat** , der Gruppe der **Beständigen Chat** zum Verwalten von Richtlinien auf globaler Ebene sowie Pool, Standort oder Benutzer Ebene, einschließlich der Konfiguration der globale Richtlinie, und erstellen eine oder mehrere zusätzliche Benutzer- und Website Richtlinien für Ihre Bereitstellung. Wenn Persistent Chat Server durch eine Richtlinie für einen Benutzer aktiviert ist, wird die Persistent Chat Server-Umgebung in ihrem Client angezeigt.
  
Die globale Richtlinie wird automatisch erstellt, wenn Sie Persistent Chat Server bereitstellen, und es kann so konfiguriert, aber nicht gelöscht werden. Da die globale Richtlinie für alle Benutzer gilt, muss es keinen pro Benutzer festgelegt werden soll.
  
Sie können erstellen und konfigurieren mehrere Standort- und Benutzerrichtlinien, die Benutzer zusammen mit der globalen Richtlinie für Persistent Chat Server aktivieren. Pools und der Website Persistent Chat Server-Richtlinien außer Kraft setzen die globale Richtlinie ein Persistent Chat Server, jedoch nur für Benutzer dieser Website. Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.
  
> [!NOTE]
> Zum Konfigurieren und Verwenden von Persistent Chat Server, müssen Sie zunächst mit dem Topologie-Generator Persistent Chat Server Support zur Topologie hinzugefügt werden, und die Topologie anschließend veröffentlichen. Weitere Informationen hierzu finden Sie unter [Persistent Chat Server hinzufügen, um Ihre Skype für Business Server 2015 Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Richtlinie für den beständigen Chat** können Sie die folgenden Aufgaben ausführen: Richtlinie für den Server für beständigen Chat aktivieren, Richtlinie für den Server für beständigen Chat verwalten.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>So konfigurieren Sie die globale Richtlinie für beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie auf **Beständiger Chat**in Skype Business Server-Systemsteuerung und klicken Sie dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:
    
  - Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.
    
  - Einzelheiten Sie im Feld **Beschreibung**über den was die Benutzerrichtlinie (beispielsweise globale Richtlinie für die _CentralSiteName_) ist.
    
  - Oder um beständigen Chat für alle Standorte und Benutzer, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Aktivieren beständigen Chat** .
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Erstellen Sie eine Richtlinie für beständigen Chat für eine Website

Für jeden Standort, den Sie bereitgestellt haben, können Sie eine standortspezifische Richtlinie für beständigen Chat erstellen.
  
Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.
    
5. Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
6. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
  - Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).
    
  - Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)
    
  - Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Erstellen Sie eine Benutzerrichtlinie für den beständigen Chat

In der Skype Business Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern unter **Benutzer**zugewiesen werden können.
  
Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
  - Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.
    
  - Einzelheiten Sie im Feld **Beschreibung**über den was die Benutzerrichtlinie (beispielsweise Richtlinie für beständigen Chat für bestimmte Benutzer) ist.
    
  - Klicken Sie zum beständigen Chat für alle Benutzer festlegen möchten, die nicht explizit über eine Benutzerrichtlinie gesteuert werden, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Aktivieren beständigen Chat** .
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Anwenden eine Richtlinie für beständigen Chat Benutzer auf ein Benutzerkonto

Wenn ein Benutzer für Skype für Business Server aktiviert wurde, können Sie geeignete Richtlinien auf bestimmte Benutzer zu aktivieren oder deaktivieren sie für Persistent Chat Server anwenden.
  
Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf einen oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**die Benutzerrichtlinie beständigen Chat, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die ** \<automatische\> ** Einstellungen die Standardrichtlinie für eine effektive gelten. Diese Einstellungen werden automatisch vom Server angewendet.
  
6. Klicken Sie auf **Commit ausführen**.
    

