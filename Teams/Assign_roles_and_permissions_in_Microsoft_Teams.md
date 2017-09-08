---
title: Zuweisen von Rollen und Berechtigungen in Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: "Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen."
ms.openlocfilehash: 9367148bb98e5b36f43c512e4955827a63fc8863
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Zuweisen von Rollen und Berechtigungen in Microsoft Teams
===============================================

Es gibt in Microsoft Teams zwei Rollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt. der Status „Besitzer“ gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden die Berechtigungen vererbt.

Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds:

|  |Teambesitzer  |Teammitglied  |
|---------|---------|---------|
|**Team erstellen**     |Ja        |Nein         |
|**Team verlassen**     |Ja         |Ja         |
|**Teamnamen/Teambeschreibung bearbeiten**      |Ja         |Nein         |
|**Team löschen**      |Ja         |Nein         |
|**Kanal hinzufügen**      |Ja         |Ja*         |
|**Kanalnamen/Kanalbeschreibung bearbeiten**      |Ja         |Ja*         |
|**Kanal löschen**      |Ja         |Ja*         |
|**Mitglieder hinzufügen**      |Ja**         |Nein         |
|**Registerkarten hinzufügen**      |Ja         |Ja*         |
|**Connectors hinzufügen**      |Ja         |Ja*         |
|**Bots hinzufügen**      |Ja         |Ja*         |
\* Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall verfügen Mitglieder nicht über den entsprechenden Zugriff.

\*\*Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied zum Status eines Besitzers hochstufen. Ein Besitzer kann auch seinen eigenen Status zu dem eines Mitglieds herabstufen.


| | |
|---------|---------|
|![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br>Hinweis     |Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen. Ein Team kann maximal zehn Besitzer haben.         |

<a name="permissions-to-create-teams"></a>Berechtigungen zum Erstellen von Teams
---------------------------

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Office 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams. Sie können dies genauer steuern und die Erstellung neuer Teams und damit die Erstellung neuer Office 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren.

Wenn Ihre Organisation daran interessiert ist, werden in der folgenden Anleitung die dazu erforderlichen Aufgaben beschrieben.

1.  Identifizieren oder erstellen Sie eine Sicherheitsgruppe (SG) von Benutzern, die über delegierte Berechtigungen zum Erstellen von Office 365-Gruppen verfügen sollen.

    a. **Aktion:** Richten Sie in Office 365 eine Sicherheitsgruppe ein, damit Sie Ihre Benutzer hinzufügen können, die Office 365-Gruppen erstellen können.

    b. Weitere Informationen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Office 365 Admin Center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).

2.  Überprüfen Sie, ob die firmenweite Steuerung für Benutzer zum Erstellen von Gruppen aktiviert ist.

    a. **Aktion:** Führen Sie das folgende PowerShell-Skript aus, und überprüfen Sie, ob der Parameter „UsersPermissiontoCreateGroupsEnabled“ auf **True** festgelegt ist.

    Connect-MsolService

    Get-MsolCompanyInformation

    b. Wenn hier nicht „True“ festgelegt ist, führen Sie das Cmdlet „Set-MsolCompanySettings“ aus, um **„True“ festzulegen**. Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True


    c. Weitere Informationen finden Sie unter: [Verwalten der Erstellung von Office 365-Gruppen](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).

<!-- -->

3.  Konfigurieren von Einstellungen für Office 365-Gruppen, um nur identifizierten Sicherheitsgruppen die Berechtigung zum Erstellen von Gruppen zu erteilen

    a. **Aktion:** Erstellen Sie ein Gruppeneinstellungsobjekt, das die Konfigurationseinstellungen der Gruppe enthält, der delegierte Berechtigungen zum Erstellen von Gruppen zugewiesen werden sollen. 

    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId der Gruppe, die Gruppen erstellen darf>"

    New-AzureADDirectorySetting -DirectorySetting $settings

    b. Weitere Informationen finden Sie unter: [Verwalten der Erstellung von Office 365-Gruppen](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)


||||
|---------|---------|---------|
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Entscheidungspunkt         |Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?         |
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Nächste Schritte         |Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann         |

