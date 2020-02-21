---
title: 'Lync Server 2013: Delegieren der administrativen Steuerung von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93985818c62b195227323f4c0f6d5030db1f16f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delegieren der administrativen Steuerung von lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

In lync Server 2013 werden administrative Aufgaben an Benutzer mithilfe der neuen Funktion für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) delegiert. Bei der Installation von lync Server werden eine Reihe von RBAC-Rollen für Sie erstellt. Diese Rollen entsprechen universellen Sicherheitsgruppen in Active Directory-Domänendienste. Beispielsweise entspricht die RBAC-Rolle "cshelpdesk" der "cshelpdesk"-Gruppe, die im Container Users in Active Directory-Domänendienste gefunden wird. Darüber hinaus ist jede RBAC-Rolle einer Gruppe von lync Server Windows PowerShell-Cmdlets zugeordnet. Diese Cmdlets stellen die Aufgaben dar, die von Benutzern ausgeführt werden können, denen die gegebene RBAC-Rolle zugewiesen wurde. Beispielsweise wurde der "cshelpdesk"-Rolle die Cmdlets Lock-CsClientPin und UnlockCsClientPin zugewiesen. Das bedeutet, dass Benutzer, denen die "cshelpdesk"-Rolle zugewiesen wurde, Benutzer-PIN-Nummern Sperren und entsperren können. Der "cshelpdesk"-Rolle wurde jedoch das Cmdlet New-CsVoicePolicy nicht zugewiesen. Das bedeutet, dass Benutzer, denen die "cshelpdesk"-Rolle zugewiesen wurde, keine neuen VoIP-Richtlinien erstellen können.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Anzeigen von Informationen zu RBAC-Rollen

Sie können grundlegende Informationen zu ihren RBAC-Rollen abrufen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:

    Get-CsAdminRole

Beachten Sie, dass die Identität der RBAC-Rolle (beispielsweise CsVoiceAdministrator) eine direkte Zuordnung zu einer Sicherheitsgruppe hat, die im Container "Benutzer" in Active Directory-Domänendienste gefunden wird.

Um eine Liste der Cmdlets anzuzeigen, die einer Rolle zugewiesen wurden, verwenden Sie einen Befehl wie den folgenden:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Zuweisen einer RBAC-Rolle zu einem Benutzer

Um einem Benutzer eine RBAC-Rolle zuzuweisen, müssen Sie diesen Benutzer der entsprechenden Active Directory Sicherheitsgruppe hinzufügen. Um beispielsweise die CsLocationAdministrator-Rolle einem Benutzer zuzuweisen, müssen Sie diesen Benutzer der Gruppe CsLocationAdministrator hinzufügen. Dies kann durch Ausführen des folgenden Verfahrens geschehen:

**So weisen Sie einen Benutzer einer Sicherheitsgruppe zu**

1.  Melden Sie sich mit einem Konto, das über die Berechtigung zum Ändern der Mitgliedschaft einer Active Directory Gruppe verfügt, an einem Computer an, auf dem Active Directory Benutzer und Computer installiert wurden.

2.  Klicken Sie im **Startmenü**auf **Alle Programme**, dann auf **Verwaltung**, und klicken Sie dann auf **Benutzer und Computer Active Directory**.

3.  Erweitern Sie in Active Directory Benutzer und Computer den Namen Ihrer Domäne, und klicken Sie auf den Container **Benutzer** .

4.  Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe **CsLocationAdministrator**, und klicken Sie dann auf **Eigenschaften**.

5.  Klicken Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Mitglieder** auf **Hinzufügen**.

6.  Geben Sie im Dialogfeld **Benutzer, Computer, Kontakte oder Gruppen auswählen** in das Feld **Geben Sie die zu verwendenden Objektnamen ein** den Benutzernamen oder den Anzeigenamen des Benutzers ein, der der Gruppe hinzugefügt werden soll (beispielsweise **Ken Myers**), und klicken Sie dann auf **OK**.

7.  Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

Um sicherzustellen, dass die RBAC-Rolle zugewiesen wurde, verwenden Sie das Cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , und übergeben Sie das Cmdlet sAMAccountName (Active Directory Anmeldename) des Benutzers. Führen Sie diesen Befehl beispielsweise in der lync Server-Verwaltungsshell aus:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

