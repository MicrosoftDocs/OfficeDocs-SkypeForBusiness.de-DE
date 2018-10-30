---
title: 'Lync Server 2013: Delegieren der administrativen Steuerung von Lync Server'
TOCTitle: Delegieren der administrativen Steuerung von Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520951(v=OCS.15)
ms:contentKeyID: 49293188
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Delegieren der administrativen Steuerung von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

In Lync Server 2013 werden Verwaltungsaufgaben über die neue Funktion für die rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC) an Benutzer delegiert. Bei der Installation von Lync Server werden verschiedene RBAC-Rollen erstellt. Diese Rollen entsprechen universellen Sicherheitsgruppen in Active Directory-Domänendienste. Die RBAC-Rolle "CsHelpDesk" entspricht beispielsweise der Gruppe "CsHelpDesk" im Container "Users" des Active Directory-Domänendiensts. Darüber hinaus sind jeder RBAC-Rolle eine Reihe von Windows PowerShell-Cmdlets in Lync Server zugeordnet. Diese Cmdlets stellen die Aufgaben dar, die von Benutzern mit der RBAC-Rolle ausgeführt werden können. Der Rolle "CsHelpDesk" sind z. B. die Cmdlets "Lock-CsClientPin" und "UnlockCsClientPin" zugewiesen, sodass Benutzer mit der Rolle "CsHelpDesk" zum Sperren und Aufheben der Sperrung von Benutzer-PINs berechtigt sind. Das Cmdlet "New-CsVoicePolicy" ist der Rolle "CsHelpDesk" jedoch nicht zugewiesen. Benutzer, denen die Rolle "CsHelpDesk" zugewiesen ist, können folglich keine neuen VoIP-Richtlinien erstellen.

## Anzeigen von Informationen über RBAC-Rollen

Führen Sie den folgenden Befehl in der Lync Server-Verwaltungsshell aus, um grundlegende Informationen zu Ihren RBAC-Rollen abzurufen:

    Get-CsAdminRole

Bedenken Sie, dass die Identität der RBAC-Rolle (z. B. "CsVoiceAdministrator") über eine direkte Zuordnung zu einer Sicherheitsgruppe im Container der Active Directory-Domänendienste "Users" verfügt.

Zum Abrufen einer Liste der Cmdlets, die einer Rolle zugewiesen sind, verwenden Sie einen Befehl wie den folgenden:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

## Zuweisen einer RBAC-Rolle zu einem Benutzer

Zum Zuweisen einer RBAC-Rolle zu einem Benutzer müssen Sie den Benutzer zur entsprechenden Active Directory-Sicherheitsgruppe hinzufügen. Beispiel: Um einem Benutzer die Rolle "CsLocationAdministrator" zuzuweisen, müssen Sie den Benutzer zur Gruppe "CsLocationAdministrator" hinzufügen. Zu diesem Zweck können Sie die folgenden Schritte ausführen:

**So weisen Sie einer Sicherheitsgruppe einen Benutzer zu**

1.  Melden Sie sich über ein Konto mit Berechtigung zum Ändern der Mitgliedschaft einer Active Directory-Gruppe an dem Computer an, auf dem "Active Directory-Benutzer und -Computer" installiert ist.

2.  Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **Active Directory-Benutzer und -Computer**.

3.  Erweitern Sie in "Active Directory-Benutzer und -Computer" den Namen Ihrer Domäne und klicken Sie auf den Container **Users**.

4.  Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe **CsLocationAdministrator** und klicken Sie dann auf **Eigenschaften**.

5.  Klicken Sie im Dialogfeld **Eigenschaften** auf die Registerkarte **Mitglieder** und anschließend auf **Hinzufügen**.

6.  Geben Sie im Dialogfeld **Benutzer, Computer, Kontakte oder Gruppen auswählen** im Feld **Geben Sie die zu verwendenden Objektnamen ein** den Benutzer- oder Anzeigenamen des Benutzers ein, der zur Gruppe hinzugefügt werden soll (z. B. **Ken Myer** ), und klicken Sie auf **OK** .

7.  Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

Verwenden Sie das Cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAdminRoleAssignment), um zu überprüfen, ob die RBAC-Rolle zugewiesen wurde. Übergeben Sie dem Cmdlet dabei die Eigenschaft "SamAccountName" (Active Directory-Anmeldename) des Benutzers. Führen Sie in der Lync Server-Verwaltungsshell beispielsweise den folgenden Befehl aus:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

