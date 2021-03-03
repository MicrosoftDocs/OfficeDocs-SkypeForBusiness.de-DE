---
title: Konfigurieren von Benutzerrichtlinien für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie anfängliche Benutzerrichtlinien für den Server für beständigen Chat in Skype for Business Server 2015 erstellen. Benutzerrichtlinien für beständigen Chat bestimmen, ob Benutzer zugriff auf Chatrooms haben.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802115"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Konfigurieren von Benutzerrichtlinien für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie anfängliche Benutzerrichtlinien für den Server für beständigen Chat in Skype for Business Server 2015 erstellen. Benutzerrichtlinien für beständigen Chat bestimmen, ob Benutzer zugriff auf Chatrooms haben.
  
Sie können Benutzerrichtlinien für den Server für beständigen Chat auf den folgenden Ebenen verwalten: global, Standort oder Benutzer. Zunächst konfigurieren Sie die globale Richtlinie so, dass Einstellungen für den beständigen Chat für alle Benutzer in Ihrer Bereitstellung aktiviert werden, und erstellen dann zusätzliche Benutzer- und Standortrichtlinien, um zu steuern, ob der beständigen Chat für bestimmte Benutzer und Standorte aktiviert ist.
  
Dieses Thema enthält die folgenden Abschnitte:
  
- Konfigurieren der globalen Richtlinie
    
- Erstellen einer Standortrichtlinie
    
- Erstellen einer Benutzerrichtlinie
    
- Anwenden einer Richtlinie auf einen Benutzer oder eine Benutzergruppe
    
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.

## <a name="configure-the-global-policy"></a>Konfigurieren der globalen Richtlinie

So konfigurieren Sie die globale Richtlinie:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der Systemsteuerung von Skype for Business Server auf **"Beständiger Chat"** und dann auf "Richtlinie für **beständigen Chat".**
    
4. Klicken Sie in der Liste der Richtlinien auf **Global**, und klicken Sie dann auf **Bearbeiten** und **Details anzeigen**.
    
5. Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus: 
    
   - Geben Sie in **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten.
    
   - Geben **Sie** in "Beschreibung" Details dazu an, was die Benutzerrichtlinie ist (z. B. globale Richtlinie für _"centralSiteName")._
    
   - Aktivieren oder aktivieren Sie das Kontrollkästchen "Beständigen Chat aktivieren", um den beständigen **Chat** für alle Websites und Benutzer zu steuern, die nicht speziell über eine Standort- oder Benutzerrichtlinie gesteuert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-a-site-policy"></a>Erstellen einer Standortrichtlinie

Für jeden bereitgestellten Standort können Sie eine standortspezifische Richtlinie für beständigen Chat erstellen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. So erstellen Sie eine Standortrichtlinie:
  
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
    
## <a name="create-a-user-policy"></a>Erstellen einer Benutzerrichtlinie

Sie können benutzerspezifische Richtlinien erstellen, die die globale Richtlinie und alle Standortrichtlinien außer Kraft setzen, zu denen der Benutzer gehört. So erstellen Sie eine Benutzerrichtlinie:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
4. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.
    
   - Geben **Sie** in "Beschreibung" Details dazu an, was die Benutzerrichtlinie ist (z. B. Richtlinie für beständigen Chat für einen bestimmten Benutzer).
    
   - Aktivieren oder aktivieren Sie das Kontrollkästchen "Beständigen Chat aktivieren", um den beständigen **Chat** für alle Benutzer zu steuern, die nicht explizit über eine Benutzerrichtlinie gesteuert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Anwenden einer Richtlinie auf ein Benutzerkonto

Nachdem Sie Richtlinien erstellt haben, können Sie sie wie folgt auf ein Benutzerkonto anwenden:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen **Sie in "Skype for Business Server-Benutzer bearbeiten"** unter "Richtlinie für beständigen **Chat"** die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die **\<Automatic\>** Einstellungen wenden die standardmäßige effektive Richtlinie an. Diese Einstellungen werden automatisch vom Server angewendet.
  
6. Klicken Sie auf **Commit ausführen**.
    

