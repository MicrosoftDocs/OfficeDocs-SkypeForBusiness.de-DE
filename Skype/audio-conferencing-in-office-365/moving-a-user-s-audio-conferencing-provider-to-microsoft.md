---
title: "Wechseln zu Microsoft als Audiokonferenzanbieter für einen Benutzer"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
description: "Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. "
---

# Wechseln zu Microsoft als Audiokonferenzanbieter für einen Benutzer

Damit die Benutzer in Ihrer Organisation Audiokonferenzen in Office 365 für Skype for Business und Microsoft Teams verwenden können, müssen ihnen **Audiokonferenz**-Lizenzen zugewiesen werden. Außerdem muss Microsoft als Audiokonferenzanbieter festgelegt werden. Weitere Informationen zu Lizenzen und Preisen finden Sie unter [Ausprobieren oder Kaufen der Audiokonferenzfunktion in Office 365](try-or-purchase-audio-conferencing-in-office-365.md).
  
## So wechseln Sie zu Microsoft als Audiokonferenzanbieter für einen Benutzer

Wenn eine **Audiokonferenz**-Lizenz einem Benutzer zugewiesen ist, für den kein Audiokonferenzanbieter festgelegt ist, wird automatisch Microsoft als Anbieter für den Benutzer festgelegt. Sie müssen nichts unternehmen. Wenn für den Benutzer bereits ein Audiokonferenzanbieter festgelegt ist, müssen Sie den Anbieter für den Benutzer ändern, nachdem Sie ihm eine **Audiokonferenz**-Lizenz zugewiesen haben.
  
Um Microsoft als Audiokonferenzanbieter für einen Benutzer festzulegen, dem eine **Audiokonferenz**-Lizenz zugewiesen ist, der aber einen anderen Audiokonferenzanbieter verwendet, gehen Sie so vor:
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie im **Skype for Business Admin Center** zu **Audiokonferenz**.
    
4. Wenn Sie durch ein Banner benachrichtigt werden, dass Benutzer vorhanden sind, denen eine **Audiokonferenz**-Lizenz zugewiesen ist und für die noch nicht Microsoft als Audiokonferenzanbieter festgelegt ist, klicken Sie auf **Klicken Sie hier, um sie zu verschieben**. Wenn Sie das Banner nicht sehen, klicken Sie im **Skype for Business Admin Center** auf **Benutzer**, und wählen Sie dann den Filter **Users ready to be moved to Audio Conferencing** (Benutzer, die zu Audiokonferenz verschoben werden können) aus.
    
5. Wählen Sie die Benutzer aus, die Sie verschieben möchten. Klicken Sie dann im Aktionsbereich auf **Bearbeiten**.
    
6. Wählen Sie **Microsoft** in der Liste **Anbietername** aus.
    
    > [!NOTE]
    > Wenn der Audiokonferenzanbieter für einen Benutzer in Microsoft geändert wird, ändern sich die Informationen zu Audiokonferenzen für den Benutzer. Wenn Sie diese Informationen aufbewahren möchten, zeichnen Sie sie an einer anderen Stelle auf, bevor Sie den Anbieter eines Benutzers ändern. 
  
7. Klicken Sie auf **Speichern**.
    
## Was sollte ich noch wissen?

- Wenn Sie den Benutzer in der Liste auswählen, können Sie die Standardinformationen zu Audiokonferenzen des Benutzers anzeigen, jedoch wird die PIN für Audiokonferenzen nicht angezeigt. Sie können die PIN für Audiokonferenzen zurücksetzen, indem Sie auf **Zurücksetzen** klicken.
    
- Wenn Sie die Einstellungen für Audiokonferenzen ändern möchten, können Sie den Benutzer in der Liste auswählen, auf **Bearbeiten** klicken und auf der Seite **Eigenschaften** Ihre Änderungen vornehmen.
    
## Verwandte Themen

[Einwahlkonferenzen in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)
  

