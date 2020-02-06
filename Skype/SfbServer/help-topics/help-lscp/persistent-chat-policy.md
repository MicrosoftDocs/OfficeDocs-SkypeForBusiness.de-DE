---
title: Richtlinie für beständigen Chat
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
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Sie können die Seite "beständiger Chat" der Gruppe "beständiger Chat" verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung. Wenn der Server für beständigen Chat nach Richtlinie für einen Benutzer aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem Client angezeigt.
ms.openlocfilehash: 6692ef8314c3eb1ef38ade8cdbee26d3d76410ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822508"
---
# <a name="persistent-chat-policy"></a>Richtlinie für beständigen Chat
 
Sie können die Seite " **beständiger Chat** " der Gruppe " **beständiger Chat** " verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung. Wenn der Server für beständigen Chat nach Richtlinie für einen Benutzer aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem Client angezeigt.
  
Die globale Richtlinie wird automatisch erstellt, wenn Sie den beständigen Chat Server bereitstellen, und Sie kann konfiguriert, aber nicht gelöscht werden. Da die globale Richtlinie für alle Benutzer gilt, muss Sie nicht pro Benutzer eingestellt werden.
  
Sie können mehrere Website-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzern für beständigen Chat Server ermöglichen. Pool-und Website-Server Richtlinien für persistente Chats setzen die globale Richtlinie für beständigen Chats außer Kraft, allerdings nur für Benutzer dieser Website. Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.
  
> [!NOTE]
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen. Ausführliche Informationen finden Sie unter [Hinzufügen von beständigem Chat Server zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Richtlinie für den beständigen Chat** können Sie die folgenden Aufgaben ausführen: Richtlinie für den Server für beständigen Chat aktivieren, Richtlinie für den Server für beständigen Chat verwalten.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>So konfigurieren Sie die globale Richtlinie für beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **beständigen Chat**und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.
    
   - Geben Sie in **Beschreibung**Details zu den Richtlinien für Benutzer an (beispielsweise globale Richtlinie für _centralSiteName_).
    
   - Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht explizit über eine Website Richtlinie oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>So erstellen Sie eine Richtlinie für beständigen Chat für eine Website

Für jede Website, die Sie bereitgestellt haben, können Sie eine Website spezifische Richtlinie für beständigen Chat erstellen.
  
Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.
    
5. Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
6. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).
    
   - Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)
    
   - Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>So erstellen Sie eine Benutzerrichtlinie für beständigen Chat

In der Skype for Business Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern in **Benutzern**zugewiesen werden können.
  
Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.
    
   - Geben Sie in **Beschreibung**Details zu den Benutzerrichtlinien an (beispielsweise Richtlinien für beständigen Chat für bestimmten Benutzer).
    
   - Zum Steuern des beständigen Chats für alle Benutzer, die nicht ausdrücklich über eine Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>So wenden Sie eine Benutzerrichtlinie für beständigen Chat auf ein Benutzerkonto an

Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie geeignete Richtlinien auf bestimmte Benutzer anwenden, um Sie für beständigen Chat Server zu aktivieren oder zu deaktivieren.
  
Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die ** \<automatischen\> ** Einstellungen wenden die standardmäßige effektive Richtlinie an. Diese Einstellungen werden vom Server automatisch übernommen.
  
6. Klicken Sie auf **Commit ausführen**.
    

