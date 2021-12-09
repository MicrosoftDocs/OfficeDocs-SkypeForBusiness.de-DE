---
title: Einrichtung durch Administratoren für die Microsoft EDU Parents-App in Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams edu-Artikel zum Dokumentieren der Voraussetzungen und des Setups für die Eltern-App.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4865372f442160734fec980428c6f6309cc0ad7f
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355744"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Bereitstellen der Eltern-App in Microsoft Teams

Die Eltern-App hilft Lehrkräften, sich mithilfe von Teams-Chats sicher mit den Eltern und Erziehungsberechtigten der Kursteilnehmer in ihren Kursteams zu verbinden und sich damit zu verbinden. Dieser wird auf die Organisation des Lehrers verteilt. Alle Daten zu Eltern und Erziehungsberechtigten werden mithilfe von School Data Sync bereitgestellt, sodass it-Mitarbeiter alles reibungslos einrichten können.

## <a name="requirements"></a>Anforderungen

### <a name="school-data-sync"></a>School Data Sync

- Sie benötigen School Data Sync (SDS), um die Kontaktinformationen der Eltern und Erziehungsberechtigten jedes Schülers oder Studenten **zu** füllen.
  - [Bereitstellen von SDS](/schooldatasync/parents-and-guardians-in-sds)

- Wenn Sie Unterstützung beim Einrichten von SDS  sowie beim Auffüllen von Kontakten mit Eltern und Erziehungsberechtigten für die Schüler/Studenten in Ihrem Mandanten benötigen, wenden Sie sich über die hier angezeigten Aufgaben an das EDU Customer Success-Team:
  - Abschließen des RFA-Prozesses [am FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - Öffnen eines Tickets beim [Support](https://aka.ms/sdssupport)

### <a name="teams-admin-center---policies"></a>Teams Admin Center – Richtlinien

- Kursteambesitzer müssen einen Teams haben.
- Kursteambesitzer müssen über externen Zugriff mit Teams **verfügen, die nicht von einer Organisation verwaltet** werden.
  - Dies muss auf Mandanten- und Benutzerebene aktiviert werden. Die Einstellung auf Mandantenebene finden Sie unter Benutzer **> externen Zugriff** im Teams Admin Center. Auf diese Einstellung kann auch über PowerShell zugegriffen werden. Auf Richtlinien für externen Zugriff auf Benutzerebene kann nur über PowerShell zugegriffen werden. Weitere Anleitungen finden Sie unten in den PowerShell-Befehlen.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Aktivieren des externen Zugriffs mit Teams, die nicht von einer Organisation verwaltet werden

1. Installieren Sie die neueste Microsoft Teams PowerShell-Modul preview.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Führen Sie die folgenden Befehle aus, indem Sie Anmeldeinformationen mit Administratorrechten verwenden:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Die Richtlinieneinstellung, die externen Zugriff mit Teams-Konten ermöglicht, die nicht von einer Organisation auf Benutzerebene verwaltet werden (), ist standardmäßig für alle Richtlinien für externen Zugriff auf `EnableTeamsConsumerAccess` Benutzerebene aktiviert. Sowohl die Einstellung auf Mandantenebene als auch die Richtlinieneinstellung auf Benutzerebene müssen aktiviert sein, damit ein Benutzer über externen Zugriff mit Teams Konten verfügen kann, die nicht von einer Organisation verwaltet werden. Wenn dieser Zugriff nicht für jeden Benutzer in Ihrem Mandanten aktiviert sein soll, sollten Sie sicherstellen, dass die Einstellung auf Mandantenebene deaktiviert ist, die den Benutzern zugewiesenen Richtlinien für externen Zugriff auf Benutzerebene aktualisieren und dann die Einstellung auf Mandantenebene aktivieren.

Um zu überprüfen, welche Richtlinien für externen Zugriff auf Benutzerebene vorhanden sind und wem sie zugewiesen sind, können Sie die folgenden Schritte ausführen:
    
3. Überprüfen Sie, welche Richtlinien für externen Zugriff auf Benutzerebene vorhanden sind.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Überprüfen Sie für jede andere Richtlinie als die "Global"-Richtlinie, welche Benutzer die Richtlinie zugewiesen haben.

   > [!NOTE]
   > Alle Benutzer, denen keine bestimmte Richtlinie zugewiesen ist, werden auf die Richtlinie "Global" zurückfallen. Allen neuen Benutzern, die dem Mandanten hinzugefügt werden, wird die Richtlinie "Global" zugewiesen.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Da alle Richtlinien für externen Zugriff auf Benutzerebene standardmäßig auf "true" festgelegt sind, können Sie vorhandene Richtlinien für externen Zugriff mit angepassten Einstellungen erstellen/ändern und/oder Benutzer mithilfe der folgenden `EnableTeamsConsumerAccess` PowerShell-Cmdlets neuen oder vorhandenen Richtlinien erneut `EnableTeamsConsumerAccess` zuweisen:

- Erstellen einer neuen Richtlinie für externen Zugriff: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Anpassen einer vorhandenen Richtlinie für externen Zugriff (einschließlich der Richtlinie "Global): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Die folgenden Standardrichtlinien für Abonnements können nicht geändert werden: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. Die Richtlinie "FederationAndPICDefault" wurde standardmäßig allen Benutzern zugewiesen, neuen Benutzern wird nun standardmäßig die Richtlinie "Global" zugewiesen. Wenn Sie die Richtlinieneinstellungen für Benutzer ändern müssen, denen diese Standardrichtlinien für Abonnements zugewiesen sind, weisen Sie diesen Benutzern andere Richtlinien mit den richtigen Einstellungen zu.

- Zuweisen einer Richtlinie für externen Zugriff zu einem einzelnen Benutzer: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Zuweisen einer Richtlinie zu einer Gruppe von Benutzern: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Nachdem die Richtlinien für externen Zugriff auf Benutzerebene für die Benutzer in Ihrem Mandanten ordnungsgemäß festgelegt wurden, können Sie die Einstellung auf Mandantenebene ( ) für den Mandanten mit dem folgenden `AllowTeamsConsumer` Cmdlet aktivieren:

- Festlegen der Verbundkonfigurationseinstellungen für Ihren Mandanten: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="enabling-the-parents-app"></a>Aktivieren der Eltern-App

Da die Eltern-App standardmäßig deaktiviert ist, können Kursteambesitzer die App erst dann in ihren Kursteams sehen, wenn die App über das Teams Admin Center zugelassen wird. Die App kann über das Teams Admin Center zugelassen werden, indem Sie [Von Herausgebern blockierte Apps zulassen verwenden.](manage-apps.md#apps-blocked-by-publishers)

Sie können die App jederzeit auf Mandantenebene mithilfe von Zulassen und Blockieren von [Apps](manage-apps.md#allow-and-block-apps) im Teams Admin Center deaktivieren. Wenn die App auf Mandantenebene deaktiviert ist, wird sie für alle Benutzer blockiert, auch wenn Berechtigungen auf Benutzerebene aktiviert sind.

Die App kann auch auf Benutzerebene mithilfe von Richtlinien für [App-Berechtigungen verwalten in Microsoft Teams.](teams-app-permission-policies.md)

## <a name="more-information"></a>Weitere Informationen

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
