---
title: Richtlinie für beständigen Chat – Hauptseite
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
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Sie können die Seite "Richtlinie für beständigen Chat" der Gruppe für beständigen Chat verwenden, um Richtlinien auf globaler, Pool-, Standort- oder Benutzerebene zu verwalten. Dazu gehören das Konfigurieren der globalen Standardrichtlinie und das Erstellen einer oder mehrerer zusätzlicher Benutzer- und Standortrichtlinien für Ihre Bereitstellung. Wenn ein Benutzer per Richtlinie für den Server für beständigen Chat aktiviert ist, wird die Umgebung des Servers für beständigen Chat auf dem Client angezeigt.
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819305"
---
# <a name="persistent-chat-policy-main-page"></a>Richtlinie für beständigen Chat – Hauptseite
 
Sie können die Seite "Richtlinie für beständigen **Chat"** der Gruppe für beständigen **Chat** verwenden, um Richtlinien auf globaler, Pool-, Standort- oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und der Erstellung einer oder mehrerer zusätzlicher Benutzer- und Standortrichtlinien für Ihre Bereitstellung. Wenn ein Benutzer per Richtlinie für den Server für beständigen Chat aktiviert ist, wird die Umgebung für den Server für beständigen Chat auf dem Client angezeigt.
  
> [!NOTE]
> In der Topologie gelten Standortrichtlinien für den Server für beständigen Chat global, pro Benutzerpool, pro Standort oder pro Benutzer. 
  
Die globale Richtlinie wird bei der Bereitstellung des Servers für beständigen Chat automatisch erstellt und kann zwar konfiguriert, aber nicht gelöscht werden. Da die globale Richtlinie für alle Benutzer gilt, muss sie nicht pro Benutzer festgelegt werden.
  
Sie können mehrere Standort- und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzer für den Server für beständigen Chat aktivieren. Pool- und Standortrichtlinien für den Server für beständigen Chat setzen die globale Richtlinie für den Server für beständigen Chat außer Kraft, jedoch nur für Benutzer dieses Standorts. Benutzerrichtlinien setzen globale Richtlinien, Poolrichtlinien und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.
  
> [!NOTE]
> Zum Konfigurieren und Verwenden des Servers für beständigen Chat müssen Sie zunächst den Topologie-Generator verwenden, um der Topologie Unterstützung für den Server für beständigen Chat hinzuzufügen, und dann die Topologie veröffentlichen. Weitere Informationen finden Sie unter Hinzufügen eines Servers für beständigen Chat zu Ihrer [Skype for Business Server 2015-Topologie.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md) 
  
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite "Richtlinie für beständigen **Chat"** ausführen: Aktivieren und Verwalten der Richtlinie für den Server für beständigen Chat.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>So konfigurieren Sie die globale Richtlinie für beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der Systemsteuerung von Skype for Business Server auf **"Beständiger Chat"** und dann auf "Richtlinie für **beständigen Chat".**
    
4. Klicken Sie in der Liste der Richtlinien auf **Global**, und klicken Sie dann auf **Bearbeiten** und **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:
    
   - Geben Sie in **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten.
    
   - Geben **Sie** in "Beschreibung" Details dazu an, was die Benutzerrichtlinie ist (z. B. globale Richtlinie für _"centralSiteName")._
    
   - Aktivieren oder aktivieren Sie das Kontrollkästchen "Beständigen Chat aktivieren", um den beständigen **Chat** für alle Websites und Benutzer zu steuern, die nicht speziell über eine Standort- oder Benutzerrichtlinie gesteuert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>So erstellen Sie eine Richtlinie für beständigen Chat für einen Standort

Für jeden bereitgestellten Standort können Sie eine standortspezifische Richtlinie für beständigen Chat erstellen.
  
Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.
    
5. Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
6. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. "Redmond").
    
   - Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)
    
   - Aktivieren oder aktivieren Sie das Kontrollkästchen "Beständigen Chat aktivieren", um den beständigen **Chat** für alle Websites zu steuern, die nicht speziell über eine Standortrichtlinie gesteuert werden.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>So erstellen Sie eine Benutzerrichtlinie für beständigen Chat

In der Skype for Business Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern in Benutzer zugewiesen werden **können.**
  
Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.
    
   - Geben **Sie** in "Beschreibung" Details dazu an, was die Benutzerrichtlinie ist (z. B. Richtlinie für beständigen Chat für einen bestimmten Benutzer).
    
   - Aktivieren oder aktivieren Sie das Kontrollkästchen "Beständigen Chat aktivieren", um den beständigen **Chat** für alle Benutzer zu steuern, die nicht explizit über eine Benutzerrichtlinie gesteuert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>So wenden Sie eine Benutzerrichtlinie für beständigen Chat auf ein Benutzerkonto an

Wenn ein Benutzer für Skype for Business aktiviert wurde, können Sie entsprechende Richtlinien auf bestimmte Benutzer anwenden, um sie für den Server für beständigen Chat zu aktivieren oder zu deaktivieren.
  
Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen **Sie in "Lync Server-Benutzer bearbeiten"** unter "Richtlinie für beständigen **Chat"** die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die **\<Automatic\>** Einstellungen wenden die standardmäßige effektive Richtlinie an. Diese Einstellungen werden automatisch vom Server angewendet.
  
6. Klicken Sie auf **Commit ausführen**.
    

