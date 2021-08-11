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
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie eine Administratorrolle für den Server für beständigen Chat erstellen, um die anfängliche Konfiguration und Verwaltung von Diensten für beständigen Chat in Skype for Business Server 2015 zu aktivieren.'
ms.openlocfilehash: 61b601399f1e21fa36a7f7b9ead1a458b577179295c40154a78f861c6bc0c156
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337095"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie eine Administratorrolle für den Server für beständigen Chat erstellen, um die anfängliche Konfiguration und Verwaltung von Diensten für beständigen Chat in Skype for Business Server 2015 zu aktivieren.
  
In Skype for Business Server müssen Benutzer, die bestimmte Aufgaben ausführen, als Mitglieder einer oder mehrerer bestimmter Gruppen zugewiesen werden. Role-Based Zugriffssteuerung (Access Control, RBAC) wird verwendet, um Berechtigungen zu erteilen, indem Benutzer vordefinierten Skype for Business Server Administratorrollen zugewiesen werden. Diese Rollen entsprechen universellen Sicherheitsgruppen in Active Directory Domain Services. Mitgliedern der Sicherheitsgruppe "CsPersistentChatAdministrator" des Administrators für beständigen Chat wird Zugriff auf die Cmdlets des Servers für beständigen Chat gewährt, die mithilfe der Skype for Business Server Verwaltungsshell oder der Skype for Business Server Systemsteuerung ausgeführt werden können.
  
Bevor Sie den Server für beständigen Chat konfigurieren und verwalten, müssen Sie sicherstellen, dass die entsprechenden Benutzerrechte und Berechtigungen vorhanden sind und dass alle Benutzer, die als Administratoren für beständigen Chat fungieren, der Sicherheitsgruppe "Administrator für beständigen Chat" hinzugefügt werden.
  
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.

## <a name="create-a-persistent-chat-administrator"></a>Erstellen eines Administrators für beständigen Chat

Führen Sie die folgenden Schritte aus, um der Sicherheitsgruppe "CsPersistentChatAdministrator" einen Benutzer zur Sicherheitsgruppe "Administrator für beständigen Chat" hinzuzufügen:
  
1. Melden Sie sich mit einem Konto, das über die Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe verfügt, bei einem Computer an, auf dem Active Directory-Benutzer und -Computer installiert wurden.
    
2. Klicken Sie auf "Start", "Alle Programme", auf "Verwaltungstools" und dann auf "Active Directory-Benutzer und -Computer".
    
3. Erweitern Sie in Active Directory-Benutzer und -Computer den Namen Ihrer Domäne, und klicken Sie auf den Container "Benutzer".
    
4. Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe "CsPersistentChatAdministrator", und klicken Sie dann auf "Eigenschaften".
    
5. Klicken Sie im Dialogfeld <a0>Eigenschaften</a0> auf der Registerkarte <a1>Elemente</a1> auf <a2>Hinzufügen</a1>.
    
6. Geben Sie im Dialogfeld Benutzer,Computer,Kontakt oder Gruppen auswählen den Benutzernamen oder den Anzeigenamen des Benutzers ein, der der Gruppe hinzugefügt werden soll, und klicken Sie dann auf OK.
    
7. Klicken Sie im Dialogfeld Eigenschaften auf OK.
    

