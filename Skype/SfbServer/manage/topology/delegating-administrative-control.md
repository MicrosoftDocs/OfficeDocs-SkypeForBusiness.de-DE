---
title: Delegieren der administrativen Steuerung von Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832795"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegieren der administrativen Steuerung von Skype for Business Server 

In Skype for Business Server werden Verwaltungsaufgaben mithilfe der rollenbasierten Zugriffssteuerungsfunktion an Benutzer delegiert. Bei der Installation von Skype for Business Server werden eine Reihe von rollen rbAC-Rollen für Sie erstellt. Diese Rollen entsprechen universellen Sicherheitsgruppen in Active Directory-Domänendiensten. Beispielsweise entspricht die Rollen-RBAC-Rolle "CsHelpDesk" der Gruppe "CsHelpDesk", die sich im Container "Users" in den Active Directory Domain Services befindet. Darüber hinaus ist jede rbAC-Rolle einem Satz von Skype for Business Server-Windows PowerShell zugeordnet. Diese Cmdlets stellen die Aufgaben dar, die von Benutzern ausgeführt werden können, denen die angegebene rollen rbAC-Rolle zugewiesen wurde. Beispielsweise wurde der Rolle "CsHelpDesk" die Cmdlets "Lock-CsClientPin" und "UnlockCsClientPin" zugewiesen. Das bedeutet, dass Benutzer, denen die Rolle "CsHelpDesk" zugewiesen wurde, benutzer-PIN-Nummern sperren und entsperren können. Die Rolle "CsHelpDesk" wurde jedoch nicht dem cmdlet New-CsVoicePolicy zugewiesen. Das bedeutet, dass Benutzer, denen die Rolle "CsHelpDesk" zugewiesen wurde, keine neuen Sprachrichtlinien erstellen können.

## <a name="viewing-information-about-rbac-roles"></a>Anzeigen von Informationen zu rollen rbAC-Rollen

Sie können grundlegende Informationen zu Ihren rollensteuerungsrollen abrufen, indem Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ausführen:

`Get-CsAdminRole`

Beachten Sie, dass die Identität der Rollengruppenadministratorrolle (z. B. "CsVoiceAdministrator") über eine direkte Zuordnung zu einer Sicherheitsgruppe verfügt, die sich im Container "Users" in den Active Directory Domain Services befindet.

Verwenden Sie zum Anzeigen einer Liste der Cmdlets, die einer Rolle zugewiesen wurden, einen Befehl wie den folgenden:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Zuweisen einer rollen rollenaktiven Rolle zu einem Benutzer

Um einem Benutzer eine rollen rbAC-Rolle zuzuordnen, müssen Sie diesen Benutzer der entsprechenden Active Directory-Sicherheitsgruppe hinzufügen. Um beispielsweise einem Benutzer die Rolle "CsLocationAdministrator" zuzuordnen, müssen Sie diesen Benutzer der Gruppe "CsLocationAdministrator" hinzufügen. Dazu können Sie das folgende Verfahren durchführen:

1. Melden Sie sich mit einem Konto mit der Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe an einem Computer an, auf dem Active Directory-Benutzer und -Computer installiert wurden.
2. Klicken **Sie auf "Start",** **"Alle Programme",** **"Verwaltung"** und dann auf **"Active Directory-Benutzer und -Computer".**
3. Erweitern Sie in Active Directory Users and Computers den Namen Ihrer Domäne, und klicken Sie auf den **Container "Users".**
4. Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe **"CsLocationAdministrator",** und klicken Sie dann auf **"Eigenschaften".**
5. Klicken Sie **im Dialogfeld Eigenschaften** auf der Registerkarte **"Mitglieder"** auf **"Hinzufügen".**
6. Geben Sie im Dialogfeld **Benutzer, Computer,** Kontakte oder Gruppen auswählen den Benutzernamen oder Anzeigenamen des Benutzers ein, der  der Gruppe hinzugefügt werden soll (z. B. Ken Myer) in das Feld "Geben Sie die Zu verwendende Objektnamen ein, und klicken Sie dann auf **OK".**
7. Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

Verwenden Sie das Cmdlet Get-CsAdminRoleAssignment, und übergeben Sie das Cmdlet "SamAccountName" (Active Directory-Anmeldename) des Benutzers, um zu überprüfen, ob die Rollengruppenrolle zugewiesen wurde. Führen Sie beispielsweise diesen Befehl in der Skype for Business Server-Verwaltungsshell aus:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
