---
title: Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
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
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie eine Administratorrolle für den Server für beständigen Chat erstellen, um die Erstkonfiguration und Verwaltung von Diensten für beständigen Chat in Skype for Business Server 2015 zu ermöglichen.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802095"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie eine Administratorrolle für den Server für beständigen Chat erstellen, um die Erstkonfiguration und Verwaltung von Diensten für beständigen Chat in Skype for Business Server 2015 zu ermöglichen.
  
In Skype for Business Server müssen Benutzer, die bestimmte Aufgaben ausführen, als Mitglieder einer oder mehreren bestimmten Gruppen zugewiesen werden. Role-Based Zugriffssteuerung (RBAC) wird verwendet, um Berechtigungen zu gewähren, indem Benutzer vordefinierten Skype for Business Server-Administratorrollen zugewiesen werden. Diese Rollen entsprechen universellen Sicherheitsgruppen in Active Directory-Domänendiensten. Mitglieder der Sicherheitsgruppe "CsPersistentChatAdministrator" des Administrators für beständigen Chat erhalten Zugriff auf die Cmdlets für den Server für beständigen Chat, die entweder über die Skype for Business Server-Verwaltungsshell oder die Skype for Business Server-Systemsteuerung ausgeführt werden können.
  
Stellen Sie vor dem Konfigurieren und Verwalten des Servers für beständigen Chat sicher, dass die entsprechenden Benutzerrechte und -berechtigungen vorhanden sind und dass alle Benutzer, die als Administratoren für beständigen Chat fungieren, der Sicherheitsgruppe "Administrator für beständigen Chat" hinzugefügt werden.
  
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.

## <a name="create-a-persistent-chat-administrator"></a>Erstellen eines Administrators für beständigen Chat

Führen Sie die folgenden Schritte aus, um der Sicherheitsgruppe "CsPersistentChatAdministrator" einen Benutzer zur Sicherheitsgruppe "Administrator für beständigen Chat" hinzuzufügen:
  
1. Melden Sie sich mit einem Konto mit der Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe an einem Computer an, auf dem Active Directory-Benutzer und -Computer installiert wurden.
    
2. Klicken Sie auf "Start", "Alle Programme", "Verwaltung", und klicken Sie dann auf "Active Directory-Benutzer und -Computer".
    
3. Erweitern Sie in Active Directory Users and Computers den Namen Ihrer Domäne, und klicken Sie auf den Container "Users".
    
4. Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe "CsPersistentChatAdministrator", und klicken Sie dann auf "Eigenschaften".
    
5. Klicken Sie im Dialogfeld Eigenschaften auf der Registerkarte "Mitglieder" auf "Hinzufügen".
    
6. Geben Sie im Dialogfeld Benutzer, Computer, Kontakt oder Gruppen auswählen den Benutzernamen oder Anzeigenamen des Benutzers ein, der der Gruppe hinzugefügt werden soll, in das Feld "Geben Sie die zu verwendende Objektnamen ein, und klicken Sie dann auf OK".
    
7. Klicken Sie im Dialogfeld Eigenschaften auf OK.
    

