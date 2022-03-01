---
title: Einrichtung von Eltern in Teams für Education
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams Artikel Dokumentierung der Voraussetzungen und Einrichtung von "Eltern" in Teams für Education.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af6433cb3e5ca0e1849322bdd128915e826e219b
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2022
ms.locfileid: "63040063"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Einrichten der übergeordneten Verbindung in Microsoft Teams für Education

Die Elternverbindung in Teams für Education hilft Lehrkräften, sich mithilfe von Teams-Chats sicher mit den Eltern und Erziehungsberechtigten der Kursteilnehmer in ihren Kursteams zu verbinden und zu interagieren. Dieser wird auf die gesamte Organisation des Lehrers verteilt. Alle Daten zu Eltern und Erziehungsberechtigten werden mithilfe von School Data Sync bereitgestellt, sodass it-Mitarbeiter alles reibungslos einrichten können.

Nachdem Eltern und Erziehungsberechtigte eingerichtet wurden, können sie mit den Lehrkräften ihrer Schüler/Studenten chatten, indem Teams chatten. Anleitungen dazu, wie Sie Eltern und Erziehungsberechtigte mit Lehrkräften in Verbindung Verbinden, finden Sie unter Zusammenarbeit mit [Lehrkräften in Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

Eltern funktioniert auch mit "Überwachter Chat". Eltern und Erziehungsberechtigte haben keine vollständigen Teams-Berechtigungen, was bedeutet, dass sie keine Unterhaltungen mit Schülern/Studenten beginnen oder Benutzer mit Vollzugriff (z. B. Lehrkräfte) aus Chats entfernen können. Weitere Informationen zu überwachten Chats finden Sie unter [Verwenden überwachter Chats in Microsoft Teams](supervise-chats-edu.md).

## <a name="requirements"></a>Anforderungen

### <a name="school-data-sync"></a>School Data Sync

- Sie benötigen School Data Sync (SDS), um die Kontaktinformationen für Eltern und Erziehungsberechtigte jedes Schülers oder Studenten **zu** füllen.
  - [Bereitstellen von SDS](/schooldatasync/parents-and-guardians-in-sds)

- Wenn Sie Unterstützung beim Einrichten von SDS sowie beim Auffüllen von Kontakten mit Eltern und Erziehungsberechtigten für die Schüler/Studenten in Ihrem Mandanten benötigen, wenden Sie sich über die hier angezeigten Aufgaben an das EDU Customer Success-Team:
  - Abschließen des RFA-Prozesses [am FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Öffnen eines Tickets beim [Support](https://aka.ms/sdssupport)

- Derzeit unterstützt SDS nur die CSV-basierte Datenaufnahme für übergeordnete Kontakte. Sie können jedoch [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) oder [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) für alle Daten der Liste verwenden und mit CSV nur übergeordnete Kontakte hinzufügen.
  - Erstellen Sie ein zweites Synchronisierungsprofil im [SDS v1-CSV-Synchronisierungsformat](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Ziehen Sie die beiden [aufgefüllten übergeordneten](/schooldatasync/parent-contact-sync-file-format) Dateien, in die die restlichen v1-Dateien leer sind (nur die Kopfzeilen).
    - User.csv
    - Guardianrelationship.csv
  - Informationen zum Anzeigen eines Beispielsets für die CSV-Dateien in v1 finden Sie unter Erforderliche [Mindestattribute für GitHub Dateien](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Wenn Sie das Pullen der CSV-Dateien nach der ersten Synchronisierung automatisieren möchten, lesen Sie unser Dokument zur Synchronisierung von [CSV-Dateien](/schooldatasync/csv-file-sync-automation).
  - Wenn Sie Hilfe beim Einrichten Ihrer SDS-Datensynchronisierung erhalten möchten, erreichen Sie unser Customer [Success-Team](https://www.microsoft.com/fasttrack?rtc=1) , oder [öffnen Sie ein Supportticket](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams Admin Center – Richtlinien

- Kursteambesitzer müssen einen Teams chatten.
- Kursteambesitzer müssen über externen Zugriff verfügen **, Teams die nicht von einer Organisation verwaltet** werden.
  - Dies muss auf Mandanten- und Benutzerebene aktiviert sein. Die Einstellung auf Mandantenebene finden Sie unter Benutzer **> externen Zugriff** im Teams Admin Center. Auf diese Einstellung kann auch über PowerShell zugegriffen werden. Auf Richtlinien für externen Zugriff auf Benutzerebene kann nur über PowerShell zugegriffen werden. Weitere Anleitungen finden Sie unten in den PowerShell-Befehlen.

> [!NOTE]
>Eltern und Erziehungsberechtigte werden im Feature "Eltern" als externe Benutzer klassifiziert, was bedeutet, dass sie nicht über vollständige Mandantenrechte verfügen. Sie haben nur Zugriff auf den Chat oder die Chats, zu dem sie hinzugefügt werden, sowie auf Dateien, Bilder und andere im Chat freigegebene Inhalte.
>
>Darüber hinaus können externe Benutzer die Anwesenheitseinstellungen (offline, verfügbar, beschäftigt usw.) der Benutzer Ihrer Organisation sehen, dies kann jedoch mit PowerShell deaktiviert werden, um die Privatsphäre der Benutzer zu schützen. Verwenden Sie in PowerShell [Set-CsPrivacyConfiguration, und](/powershell/module/skype/set-csprivacyconfiguration?view=skype-ps) legen Sie auf .``EnablePrivacyMode=true``
>
>Obwohl Eltern und Erziehungsberechtigte externe Benutzer sind, können sie ihre Beiträge zu Chats finden. Unter Durchführen einer [eDiscovery-Untersuchung Teams eDiscovery eine eDiscovery-Untersuchung von Inhalten in einem Microsoft Teams](ediscovery-investigation.md).

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Zulassen des externen Zugriffs mit Teams, die nicht von einer Organisation verwaltet werden

Damit Lehrkräfte mit Eltern und Erziehungsberechtigten in Teams kommunizieren können, muss der IT-Administrator des Education-Mandanten die Richtlinien des Mandanten aktualisieren, um externen Zugriff für Teams-Konten außerhalb des Mandanten zu ermöglichen. Weitere Informationen zum Verwalten des externen Zugriffs finden Sie unter [Verwalten des externen Zugriffs in Microsoft Teams](manage-external-access.md).

Hier sind die Schritte zum Aktivieren des externen Zugriffs für Eltern und Erziehungsberechtigte.

1. Installieren Sie die neueste Microsoft Teams PowerShell-Modulvorschau.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Führen Sie die folgenden Befehle aus, indem Sie Anmeldeinformationen mit Administratorrechten verwenden:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    Die Richtlinieneinstellung, mit der der externe Zugriff mit Teams-Konten aktiviert wird, die nicht von einer Organisation auf Benutzerebene (`EnableTeamsConsumerAccess`) verwaltet werden, ist für alle Richtlinien für externen Zugriff auf Benutzerebene standardmäßig aktiviert. Sowohl die Einstellung auf Mandantenebene als auch die Richtlinieneinstellung auf Benutzerebene müssen aktiviert sein, damit ein Benutzer über externen Zugriff mit Teams Konten verfügen kann, die nicht von einer Organisation verwaltet werden. Wenn dieser Zugriff nicht für jeden Benutzer in Ihrem Mandanten aktiviert sein soll, sollten Sie sicherstellen, dass die Einstellung auf Mandantenebene deaktiviert ist, die den Benutzern zugewiesenen Richtlinien für externen Zugriff auf Benutzerebene aktualisieren und dann die Einstellung auf Mandantenebene aktivieren.

    Um zu überprüfen, welche Richtlinien für externen Zugriff auf Benutzerebene vorhanden sind und wem sie zugewiesen sind, können Sie die folgenden Schritte ausführen:

3. Überprüfen Sie, ob Richtlinien für externen Zugriff auf Benutzerebene vorhanden sind.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Überprüfen Sie für jede andere Richtlinie als die "Global"-Richtlinie, welche Benutzer die Richtlinie zugewiesen haben.

   > [!NOTE]
   > Alle Benutzer, denen keine bestimmte Richtlinie zugewiesen ist, werden auf die Richtlinie "Global" zurückfallen. Allen neuen Benutzern, die dem Mandanten hinzugefügt werden, wird die Richtlinie "Global" zugewiesen.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Da alle Richtlinien für externen Zugriff auf Benutzerebene standardmäßig auf "true" festgelegt sind, `EnableTeamsConsumerAccess` können Sie vorhandene Richtlinien für externen Zugriff mit angepassten Einstellungen erstellen/ändern und/oder Benutzer mithilfe der folgenden PowerShell-Cmdlets `EnableTeamsConsumerAccess` neuen oder vorhandenen Richtlinien erneut zuweisen:

- Erstellen einer neuen Richtlinie für externen Zugriff: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Anpassen einer vorhandenen Richtlinie für externen Zugriff (einschließlich der Richtlinie "Global): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Die folgenden Standardrichtlinien für Abonnements können nicht geändert werden: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. Die Richtlinie "FederationAndPICDefault" wurde standardmäßig allen Benutzern zugewiesen, neuen Benutzern wird nun standardmäßig die Richtlinie "Global" zugewiesen. Wenn Sie die Richtlinieneinstellungen für Benutzer ändern müssen, denen diese Standardrichtlinien für Abonnements zugewiesen sind, weisen Sie diesen Benutzern andere Richtlinien mit den richtigen Einstellungen zu.

- Zuweisen einer Richtlinie für externen Zugriff zu einem einzelnen Benutzer: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Zuweisen einer Richtlinie zu einer Gruppe von Benutzern: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Nachdem die Richtlinien für externen Zugriff auf Benutzerebene für die Benutzer in Ihrem Mandanten ordnungsgemäß festgelegt wurden, können Sie die Einstellung auf Mandantenebene (`AllowTeamsConsumer`) für den Mandanten mithilfe des folgenden Cmdlets aktivieren:

- Festlegen der Verbundkonfigurationseinstellungen für Ihren Mandanten: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Aktivieren der Eltern-App im Teams Admin Center

Da die Eltern-App standardmäßig deaktiviert ist, können Kursteambesitzer sie erst in ihren Kursteams sehen, wenn sie über das Teams Admin Center zugelassen ist. Die Eltern-App wird im Teams Admin Center mit der Verwendung von von Herausgebern [blockierten Apps zulassen aktiviert](manage-apps.md#apps-blocked-by-publishers).

Sie können die App jederzeit auf Mandantenebene mithilfe von Zulassen und Blockieren von [Apps im Teams](manage-apps.md#allow-and-block-apps) Admin Center deaktivieren. Wenn sie auf Mandantenebene deaktiviert ist, wird sie für alle Benutzer blockiert, auch wenn Berechtigungen auf Benutzerebene aktiviert sind.

Die Eltern-App kann auch auf Benutzerebene deaktiviert werden, indem Sie die Berechtigungsrichtlinien für die [App in](teams-app-permission-policies.md) Microsoft Teams.

## <a name="more-information"></a>Weitere Informationen

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
