---
title: 'Lync Server 2013: Delegieren der administrativen Steuerung von Lync Server'
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
ms.openlocfilehash: 134d5a4abae1173cc1d74cecb876951cea6d72c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delegieren der administrativen Steuerung von Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

In lync Server 2013 werden administrative Aufgaben mithilfe des neuen Features rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) an Benutzer delegiert. Wenn Sie lync Server installieren, werden eine Reihe von RBAC-Rollen für Sie erstellt. Diese Rollen entsprechen den allgemeinen Sicherheitsgruppen in den Active Directory-Domänendiensten. Beispielsweise entspricht die RBAC-Rolle CsHelpDesk der CsHelpDesk-Gruppe, die im Container Benutzer in den Active Directory-Domänendiensten gefunden wurde. Darüber hinaus ist jede RBAC-Rolle einer Gruppe von lync Server-Windows PowerShell-Cmdlets zugeordnet. Diese Cmdlets stellen die Aufgaben dar, die von Benutzern ausgeführt werden können, denen die angegebene RBAC-Rolle zugewiesen wurde. Beispielsweise wurden der CsHelpDesk-Rolle die Cmdlets Lock-CsClientPin und UnlockCsClientPin zugewiesen. Das bedeutet, dass Benutzer, denen die CsHelpDesk-Rolle zugewiesen wurde, Benutzer-PIN-Nummern Sperren und entsperren können. Der CsHelpDesk-Rolle wurde jedoch nicht das Cmdlet New-CsVoicePolicy zugewiesen. Das bedeutet, dass Benutzer, denen die CsHelpDesk-Rolle zugewiesen wurde, keine neuen VoIP-Richtlinien erstellen können.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Anzeigen von Informationen zu RBAC-Rollen

Sie können grundlegende Informationen zu ihren RBAC-Rollen abrufen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:

    Get-CsAdminRole

Beachten Sie, dass die Identität der RBAC-Rolle (beispielsweise CsVoiceAdministrator) eine direkte Zuordnung zu einer Sicherheitsgruppe hat, die sich im Container Benutzer in den Active Directory-Domänendiensten befindet.

Wenn Sie eine Liste der Cmdlets anzeigen möchten, die einer Rolle zugewiesen wurden, verwenden Sie einen Befehl wie den folgenden:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Zuweisen einer RBAC-Rolle zu einem Benutzer

Wenn Sie einem Benutzer eine RBAC-Rolle zuweisen möchten, müssen Sie diesen Benutzer der entsprechenden Active Directory-Sicherheitsgruppe hinzufügen. Um beispielsweise die CsLocationAdministrator-Rolle einem Benutzer zuzuweisen, müssen Sie diesen Benutzer der Gruppe CsLocationAdministrator hinzufügen. Dies kann durchführen des folgenden Verfahrens erfolgen:

**So weisen Sie einen Benutzer einer Sicherheitsgruppe zu**

1.  Melden Sie sich bei einem Computer, auf dem Active Directory-Benutzer und-Computer installiert wurden, mit einem Konto an, das über die Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe verfügt.

2.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.

3.  Erweitern Sie in Active Directory-Benutzer und-Computer den Namen Ihrer Domäne, und klicken Sie auf den Container **Benutzer** .

4.  Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe **CsLocationAdministrator**, und klicken Sie dann auf **Eigenschaften**.

5.  Klicken Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Mitglieder** auf **Hinzufügen**.

6.  Geben Sie im Dialogfeld **Benutzer, Computer, Kontakte oder Gruppen auswählen** den Benutzernamen oder den Anzeigenamen des Benutzers ein, der der Gruppe hinzugefügt werden soll (beispielsweise **Ken Myers**), und klicken Sie dann im Feld **Geben Sie die zu verwendenden Objektnamen ein** , und klicken Sie dann auf **OK**.

7.  Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

Um zu überprüfen, ob die RBAC-Rolle zugewiesen wurde, verwenden Sie das Cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , und übergeben Sie dem Cmdlet den sAMAccountName (Active Directory-Anmeldename) des Benutzers. Führen Sie diesen Befehl beispielsweise in der lync Server-Verwaltungsshell aus:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

