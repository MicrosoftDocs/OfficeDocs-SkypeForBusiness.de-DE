---
title: Delegieren der administrativen Steuerung von Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 64d1b33c7ee41c028d3af7454a131f67de2c9146
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214701"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegieren der administrativen Steuerung von Skype für Business Server 

In Skype für Business Server werden die administrative Aufgaben mithilfe des Features der rollenbasierten Zugriffssteuerung (RBAC) für Benutzer delegiert. Wenn Sie Skype für Business Server installieren, werden eine Anzahl von RBAC-Rollen für Sie erstellt. Diese Rollen entsprechen den allgemeinen Sicherheitsgruppen in den Active Directory-Domänendiensten. Beispielsweise entspricht die RBAC-Rolle "cshelpdesk" zur Gruppe "cshelpdesk" im Container "Users" in Active Directory Domain Services gefunden. Darüber hinaus ist jede RBAC-Rolle zugeordnet, mit einem Satz von Skype für Business Server Windows PowerShell-Cmdlets. Diese Cmdlets darstellen, die Aufgaben, die von Benutzern durchgeführt werden kann, die die angegebene RBAC-Rolle zugewiesen wurden. Die Rolle "cshelpdesk" wurde beispielsweise die Lock-CsClientPin und UnlockCsClientPin Cmdlets zugewiesen. Das bedeutet sperren und Entsperren des Benutzer-PIN-Nummern Benutzer, die die Rolle "cshelpdesk" zugewiesen wurden. Jedoch wurde die Rolle "cshelpdesk" nicht mit dem New-CsVoicePolicy-Cmdlet zugewiesen. Dies bedeutet, dass Benutzer, die die Rolle "cshelpdesk" zugewiesen wurden neue VoIP-Richtlinien nicht erstellen können.

## <a name="viewing-information-about-rbac-roles"></a>Anzeigen von Informationen zu RBAC-Rollen

Sie können grundlegende Informationen zu Ihren RBAC-Rollen abzurufen, durch den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell ausführen:

`Get-CsAdminRole`

Behalten Sie im Hinterkopf, die die Identität des RBAC-Rolle (z. B. "csvoiceadministrator") eine direkte Zuordnung zu einer Sicherheitsgruppe in den Container "Users" in Active Directory Domain Services gefunden wurde.

Um eine Liste der Cmdlets anzuzeigen, die einer Rolle zugewiesen sind, verwenden Sie einen Befehl wie den folgenden:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Zuweisen einer RBAC-Rolle zu einem Benutzer

Wenn eine RBAC-Rolle zu einem Benutzer zuweisen möchten, müssen Sie diesen Benutzer der entsprechenden Active Directory-Sicherheitsgruppe hinzufügen. Wenn die Rolle "CsLocationAdministrator", die einem Benutzer zuweisen möchten, müssen Sie beispielsweise diesen Benutzer der Gruppe CsLocationAdministrator hinzufügen. Kann erfolgen, indem Sie das folgende Verfahren ausführen:

1. Verwenden ein Konto mit Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe, melden Sie sich an einem Computer, auf dem Active Directory-Benutzer und-Computer installiert wurde.
2. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.
3. In Active Directory-Benutzer und-Computer erweitern Sie den Namen Ihrer Domäne, und klicken Sie auf den Container **Users** .
4. Maustaste auf die Sicherheitsgruppe **CsLocationAdministrator**, und klicken Sie dann auf **Eigenschaften**.
5. Klicken Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Mitglieder** auf **Hinzufügen**.
6. Klicken Sie im Dialogfeld **Auswahl von Benutzern, Computern, Kontakten oder Gruppen** Geben Sie den Namen oder Anzeigename des Benutzers, der Gruppe (beispielsweise Ken Myer) in das Feld **Geben Sie die zu verwendenden Objektnamen ein** hinzugefügt werden soll, und klicken Sie dann auf **OK**.
7. Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

Um sicherzustellen, dass die RBAC-Rolle zugewiesen wurde, verwenden Sie das Get-CsAdminRoleAssignment-Cmdlet, mit dem Cmdlet SamAccountName (Active Directory-Anmeldeinformationen Name) des Benutzers übergeben. Führen Sie beispielsweise folgenden Befehl in der Skype für Business Server-Verwaltungsshell aus:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
