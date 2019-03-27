---
title: Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie eine Administratorrolle für Persistent Chat Server zum Aktivieren von anfängliche Konfiguration und Verwaltung von Persistent Chat-Dienste in Skype für Business Server 2015 zu erstellen.'
ms.openlocfilehash: fb8a222f65f6fe579d3600df15a53bb84f65de66
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874067"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie eine Administratorrolle für Persistent Chat Server zum Aktivieren von anfängliche Konfiguration und Verwaltung von Persistent Chat-Dienste in Skype für Business Server 2015 zu erstellen.
  
In Skype für Business Server müssen Benutzer, die bestimmte Aufgaben als Mitglieder von einer oder mehreren bestimmten Gruppen zugewiesen werden. Role-Based Access Control (RBAC) wird verwendet, um Berechtigungen gewähren, indem Sie die Zuweisung von Benutzern zu vordefinierten Skype für Business Server Administratorrollen. Diese Rollen entsprechen den allgemeinen Sicherheitsgruppen in den Active Directory-Domänendiensten. Mitglied der Sicherheitsgruppe Persistent Chat Administrator Rolle "cspersistentchatadministrator", werden die Cmdlets Persistent Chat Server Zugriff auf die Verwendung der Skype für Business Server-Verwaltungsshell oder die Skype für Unternehmen ausgeführt werden können Server-Systemsteuerung.
  
Bevor Sie den Server für beständigen Chat konfigurieren und verwalten, sollten Sie sicherstellen, dass die entsprechenden Rechte und Berechtigungen vorhanden sind und dass alle Benutzer, die als Administratoren für den beständigen Chat fungieren sollen, der Administrator-Sicherheitsgruppe für den beständigen Chat hinzugefügt werden.
  
> [!NOTE] 
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

Führen Sie zum Hinzufügen eines Benutzers zur Persistent Chat Administrator-Sicherheitsgruppe Rolle "cspersistentchatadministrator", die folgenden Schritte aus:
  
1. Melden Sie sich über ein Konto mit Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe an dem Computer an, auf dem „Active Directory-Benutzer und -Computer“ installiert ist.
    
2. Klicken Sie nacheinander auf Start, Alle Programme, Verwaltung und Active Directory-Benutzer und -Computer.
    
3. Erweitern Sie in „Active Directory-Benutzer und -Computer“ den Namen Ihrer Domäne und klicken Sie auf den Container „Users“.
    
4. Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe „CsPersistentChatAdministrator“ und dann auf „Eigenschaften“.
    
5. Klicken Sie im Dialogfeld „Eigenschaften“auf die Registerkarte „Mitglieder“ und anschließend auf „Hinzufügen“.
    
6. Geben Sie im Dialogfeld „Benutzer, Computer, Kontakte oder Gruppen auswählen“ im Feld „Geben Sie die zu verwendenden Objektnamen ein“ den Benutzer- oder Anzeigenamen des Benutzers ein, der zur Gruppe hinzugefügt werden soll, und klicken Sie auf „OK“.
    
7. Klicken Sie im Dialogfeld „Eigenschaften“ auf „OK“.
    

