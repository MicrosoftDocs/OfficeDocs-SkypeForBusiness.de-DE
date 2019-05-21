---
title: Delegieren der administrativen Kontrolle von Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 1775fc4f02b7efa9ec26b962154f0aa90b59b296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279207"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegieren der administrativen Kontrolle von Skype for Business Server 

In Skype for Business Server werden administrative Aufgaben mithilfe der rollenbasierten Zugriffssteuerungsfunktion (Role-Based Access Control, RBAC) an Benutzer delegiert. Wenn Sie Skype for Business Server installieren, werden eine Reihe von RBAC-Rollen für Sie erstellt. Diese Rollen entsprechen den allgemeinen Sicherheitsgruppen in den Active Directory-Domänendiensten. Beispielsweise entspricht die RBAC-Rolle CsHelpDesk der CsHelpDesk-Gruppe, die im Container Benutzer in den Active Directory-Domänendiensten gefunden wurde. Darüber hinaus ist jede RBAC-Rolle einem Satz von Windows PowerShell-Cmdlets für Skype for Business Server zugeordnet. Diese Cmdlets stellen die Aufgaben dar, die von Benutzern ausgeführt werden können, denen die angegebene RBAC-Rolle zugewiesen wurde. Beispielsweise wurden der CsHelpDesk-Rolle die Cmdlets Lock-CsClientPin und UnlockCsClientPin zugewiesen. Das bedeutet, dass Benutzer, denen die CsHelpDesk-Rolle zugewiesen wurde, Benutzer-PIN-Nummern Sperren und entsperren können. Der CsHelpDesk-Rolle wurde jedoch nicht das Cmdlet New-CsVoicePolicy zugewiesen. Das bedeutet, dass Benutzer, denen die CsHelpDesk-Rolle zugewiesen wurde, keine neuen VoIP-Richtlinien erstellen können.

## <a name="viewing-information-about-rbac-roles"></a>Anzeigen von Informationen zu RBAC-Rollen

Sie können grundlegende Informationen zu ihren RBAC-Rollen abrufen, indem Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ausführen:

`Get-CsAdminRole`

Beachten Sie, dass die Identität der RBAC-Rolle (beispielsweise CsVoiceAdministrator) eine direkte Zuordnung zu einer Sicherheitsgruppe hat, die sich im Container Benutzer in den Active Directory-Domänendiensten befindet.

Wenn Sie eine Liste der Cmdlets anzeigen möchten, die einer Rolle zugewiesen wurden, verwenden Sie einen Befehl wie den folgenden:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Zuweisen einer RBAC-Rolle zu einem Benutzer

Wenn Sie einem Benutzer eine RBAC-Rolle zuweisen möchten, müssen Sie diesen Benutzer der entsprechenden Active Directory-Sicherheitsgruppe hinzufügen. Um beispielsweise die CsLocationAdministrator-Rolle einem Benutzer zuzuweisen, müssen Sie diesen Benutzer der Gruppe CsLocationAdministrator hinzufügen. Dies kann durchführen des folgenden Verfahrens erfolgen:

1. Melden Sie sich bei einem Computer, auf dem Active Directory-Benutzer und-Computer installiert wurden, mit einem Konto an, das über die Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe verfügt.
2. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.
3. Erweitern Sie in Active Directory-Benutzer und-Computer den Namen Ihrer Domäne, und klicken Sie auf den Container **Benutzer** .
4. Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe **CsLocationAdministrator**, und klicken Sie dann auf **Eigenschaften**.
5. Klicken Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Mitglieder** auf **Hinzufügen**.
6. Geben Sie im Dialogfeld **Benutzer, Computer, Kontakte oder Gruppen auswählen** den Benutzernamen oder den Anzeigenamen des Benutzers ein, der der Gruppe hinzugefügt werden soll (beispielsweise Ken Myers), und klicken Sie dann im Feld **Geben Sie die zu verwendenden Objektnamen ein** , und klicken Sie dann auf **OK**.
7. Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

Um zu überprüfen, ob die RBAC-Rolle zugewiesen wurde, verwenden Sie das Cmdlet Get-CsAdminRoleAssignment, und übergeben Sie dem Cmdlet den sAMAccountName (Active Directory-Anmeldename) des Benutzers. Führen Sie diesen Befehl beispielsweise in der Skype for Business Server-Verwaltungsshell aus:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
