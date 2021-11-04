---
title: Einrichtung von Administratoren für die Edu Microsoft Parents-App
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 'Microsoft Teams für EDU-Artikel : Dokumentvoraussetzungen und PowerShell-Einrichtung für die Eltern-App.'
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785148"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Bereitstellen der Eltern-App in Microsoft Teams

Mit der Eltern-App können Lehrkräfte mithilfe eines Teams-Chats, der auf die gesamte Bildungsorganisation verteilt wird, sichere Verbindungen mit den Eltern und Erziehungsberechtigten der Schüler/Studenten in ihren Klassen herstellen. Alle Daten zu Eltern und Erziehungsberechtigten werden mithilfe von School Data Sync bereitgestellt, sodass Lehrkräfte und IT-Mitarbeiter alles reibungslos einrichten können.

## <a name="requirements"></a>Anforderungen

### <a name="school-data-sync"></a>School Data Sync

- Sie benötigen School Data Sync (SDS), um die zugehörigen Kontaktinformationen jedes Schülers **oder Studenten zu** füllen.
  - [Bereitstellen von SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Wenn Sie Unterstützung beim Einrichten von SDS und Aktivieren von übergeordneten Kontakten in Ihrem Mandanten benötigen, wenden Sie sich über dies an das EDU-Kundenteam:
  - Abschließen des RFA-Prozesses [am FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - Öffnen eines Tickets beim [Support](https://aka.ms/sdssupport)

### <a name="teams-admins-center---policies"></a>Teams Admins Center – Richtlinien

- Der Kursbesitzer muss Chat aktiviert haben.
- Der Kursbesitzer muss über externen Zugriff mit Teams **verfügen, die nicht von einer Organisation verwaltet** werden. 
  - Diese Einstellung finden Sie unter Benutzer > externem Zugriff für die Mandantenebene. Wenn Sie dies für eine bestimmte Gruppe von Benutzern aktivieren möchten, lesen Sie die PowerShell unten.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Aktivieren von Partnerchats pro Benutzer

1. Installieren Sie die neueste Microsoft Teams PowerShell-Modul preview.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Führen Sie mit Anmeldeinformationen, die über Administratorrechte verfügen, den folgenden Befehl in einem Befehlsfenster aus:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Die Richtlinieneinstellung, die Teams Endbenutzerzugriff auf Benutzerebene (EnableTeamsConsumerAccess) aktiviert, ist standardmäßig für alle Richtlinien für externen Zugriff auf Benutzerebene aktiviert. Sowohl die Einstellung auf Mandantenebene (AllowTeamsConsumer) als auch die Richtlinieneinstellung auf Benutzerebene müssen aktiviert sein, damit ein Benutzer über externen Zugriff auf Teams Consumer verfügen kann. Wenn Sie nicht möchten, dass für jeden in Ihrem Mandanten Teams der externe Zugriff für Verbraucher aktiviert ist, sollten Sie die den Benutzern zugewiesenen Richtlinien für externen Zugriff auf Benutzerebene aktualisieren, bevor Sie die Einstellung auf Mandantenebene aktivieren.

Wenn Sie überprüfen müssen, welche Richtlinien für externen Zugriff auf Benutzerebene vorhanden sind und wem sie zugewiesen sind, können Sie die folgenden Schritte ausführen:
    
3. Überprüfen Sie, welche Richtlinien für externen Zugriff auf Benutzerebene vorhanden sind.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Überprüfen Sie für jede andere Richtlinie als die "Global"-Richtlinie, welche Benutzer die Richtlinie zugewiesen haben. Hinweis: Alle Benutzer, denen keine bestimmte Richtlinie zugewiesen ist, fallen auf die Richtlinie "Global" zurück.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Weitere PowerShell-Optionen

Da für alle Richtlinien für externen Zugriff auf Benutzerebene "EnableTeamsConsumerAccess" standardmäßig auf "true" festgelegt ist, können Sie, wenn Sie eine dieser Richtlinien aktualisieren möchten, um die Einstellung EnableTeamsConsumerAccess anzupassen, über die folgende PowerShell neue Richtlinien für den externen Zugriff mit angepassten Einstellungen erstellen oder Benutzer neuen oder vorhandenen Richtlinien erneut zuweisen:

- Erstellen Einer neuen Richtlinie für externen Zugriff (mit dieser Richtlinie wird eine neue Richtlinie für externen Zugriff erstellt und die Einstellungen definiert): [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Anpassen einer vorhandenen Richtlinie für externen Zugriff (Ändert die Einstellungen einer vorhandenen Richtlinie für externen Zugriff, einschließlich der globalen Richtlinie)): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Die folgenden Abonnementstandardeinstellungen können nicht geändert werden: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Wenn Sie die Richtlinieneinstellungen für Benutzer ändern müssen, denen diese Richtlinien zugewiesen sind, weisen Sie diesen Benutzern andere Richtlinien mit den richtigen Einstellungen zu.

- Zuweisen einer Richtlinie für externen Zugriff zu einem einzelnen Benutzer: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Zuweisen einer Richtlinie zu einer Gruppe von Benutzern: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Sobald Sie sicher sind, dass Ihre Richtlinien für externen Zugriff auf Benutzerebene für alle Benutzer richtig festgelegt sind Teams, können Sie die Einstellung auf Mandantenebene aktivieren, die den externen Consumerzugriff für den Mandanten mithilfe des folgenden Cmdlets steuert:

- Legen Sie die Verbundkonfigurationseinstellungen für Ihren Mandanten (AllowTeamsConsumer auf "true" festlegen) vor: [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Deaktivieren der Eltern-App

Die Eltern-App ist standardmäßig aktiviert, sodass alle Kursbesitzer die App in ihrem Kursteam sehen können. Die App kann auf Mandantenebene mithilfe von Zulassen [und Blockieren von Apps](manage-apps.md#allow-and-block-apps) im Microsoft Teams Admin Center deaktiviert werden. Wenn dies auf Mandantenebene deaktiviert ist, wird es für alle Benutzer blockiert, auch wenn die Berechtigung auf Benutzerebene aktiviert ist.

Dies kann auch auf Benutzerebene mithilfe von [App-Berechtigungsrichtlinien verwalten in Microsoft Teams] deaktiviert werden. (teams-app-permission-policies.md).

## <a name="more-information"></a>Weitere Informationen

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Zuweisen der Richtlinie zu einem Benutzer](/powershell/module/skype/grant-csexternalaccesspolicy)
