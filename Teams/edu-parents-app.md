---
title: Admin Einrichtung von Eltern in Teams für Education
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams Artikel zur Dokumentation der Voraussetzungen und der Einrichtung von Eltern in Teams für Education.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c26f70bb6592c418968b77c9ef2a495cb98648a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860796"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Einrichten der übergeordneten Verbindung in Microsoft Teams für Education

Die Elternverbindung in Teams für Education hilft Lehrkräften, sich mithilfe von Teams sicher mit den Eltern und Erziehungsberechtigten der Kursteilnehmer in ihren Kursteams zu verbinden und mit ihnen zu interagieren.

Dieser Artikel enthält Anleitungen für It-Experten im Bildungsbereich zu Anforderungen und zum Einrichten der übergeordneten Verbindung.

## <a name="share-guardian-and-educator-resources"></a>Freigeben von Ressourcen für Erziehungsberechtigte und Lehrkräfte

Hier sind einige Ressourcen, die IT-Administratoren mit Erziehungsberechtigten und Lehrkräften teilen können, wie sie mit der Elternverbindung beginnen können.

- Anleitungen zum Einrichten von Erziehungsberechtigten finden Sie [unter Verbinden mit Lehrkräften in Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Anleitungen zum Einrichten von Lehrkräften finden [Sie unter Kommunizieren mit Erziehungsberechtigten in Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Vorteile der übergeordneten Verbindung

Die Elternverbindung ermöglicht Es Lehrkräften und Erziehungsberechtigten, mit Teams zu chatten, per E-Mail zu anrufen.

- Teams Kontaktdaten des Erziehungsberechtigten bleiben mit SIS über School Data Sync (SDS) aktuell.
- Es funktioniert mit überwachtem Chat. Weitere Informationen finden Sie unter [Verwenden von überwachten Chats in Microsoft Teams](supervise-chats-edu.md).
  - Standardmäßig verfügen Erziehungsberechtigte über eingeschränkte Berechtigungen, sodass sie nicht mit Schülern chatten oder Benutzer aus Chats entfernen können.
  - Diese Einstellung kann vom Mandantenadministrator geändert werden.
- Lehrkräfte können Chats mit Erziehungsberechtigten initiieren.
  - Wenn der Erziehungsberechtigte nicht über ein Teams Verbraucherkonto verfügt, erhält er die erste Nachricht von der Lehrkraft und eine E-Mail-Einladung, um zu Teams zu wechseln.
- Lehrkräfte können auf die E-Mails eines Erziehungsberechtigten klicken, um sie per E-Mail mit ihrem systemeigenen E-Mail-Client zu senden.
- Lehrkräfte können auf die Telefonnummer eines Erziehungsberechtigten klicken, um sie innerhalb Teams anzurufen.

> [!IMPORTANT]
> Damit Sie die Funktionalität in Teams aufrufen können, benötigt Ihr Mandant Folgendes:
>
> - Pbx-Funktionen (Public Branch Exchange).
> - Verbindung mit dem PSTN.
>
> Microsoft 365 A1- und A3-Pläne enthalten weder PBX-Funktionen noch PSTN-Verbindungen. Sie können [Add-On-Lizenzen für jede dieser](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) Lizenzen erwerben.
>
> Microsoft 365 A5 Pläne enthalten nur Nebenstellenanlagenfunktionen, die Teams Telefonsystem verwenden. Sie müssen weiterhin [einen Teams Anrufplan erwerben oder eine Drittanbieterlösung verwenden](pstn-connectivity.md), um eine Verbindung mit externen Nummern im PSTN herzustellen.
>
> Weitere Informationen zu allen Optionen zum Abrufen der PSTN-Konnektivität finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).
>
> Weitere Informationen zum Teams der Anruflizenzierung finden Sie [unter Teams Add-On-Lizenzierungsoptionen](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## <a name="requirements"></a>Anforderungen

### <a name="school-data-sync"></a>School Data Sync

- Sie benötigen School Data Sync (SDS), um die **Kontaktinformationen** zu Eltern und Erziehungsberechtigten jedes Schülers aufzufüllen.
  - [Bereitstellen von SDS](/schooldatasync/parents-and-guardians-in-sds)

- Wenn Sie Unterstützung beim Einrichten von SDS und beim Auffüllen von **Kontakten** für Eltern und Erziehungsberechtigte für die Schüler/Studenten in Ihrem Mandanten benötigen, wenden Sie sich an das EDU Customer Success-Team:
  - Abschluss des RFA-Prozesses bei [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Öffnen eines Tickets beim [Support](https://aka.ms/sdssupport).

- Derzeit unterstützt SDS nur csv-basierte Datenerfassung für übergeordnete Kontakte. Sie können jedoch [PowerSchool-API-Synchronisierung](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) oder [OneRoster-API-Synchronisierung](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) für alle Listendaten verwenden und einfach übergeordnete Kontakte mithilfe von CSV hinzufügen.
  - Erstellen Sie ein zweites Synchronisierungsprofil mit dem [CSV-Synchronisierungsformat SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Ziehen Sie die beiden aufgefüllten [übergeordneten Dateien](/schooldatasync/parent-contact-sync-file-format) mit den restlichen v1-Dateien leer (nur die Kopfzeilen).
    - User.csv
    - Guardianrelationship.csv
  - Informationen zum Anzeigen eines Beispielsatzes der v1-CSV-Dateien finden Sie in den [Mindestens erforderlichen Attributen GitHub Dateien](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Wenn Sie das Abrufen der CSV-Dateien nach der ersten Synchronisierung automatisieren möchten, lesen Sie unser [CSV-Dateisynchronisierung-Automatisierungsdokument](/schooldatasync/csv-file-sync-automation).
  - Wenn Sie Hilfe beim Einrichten Ihrer SDS Datensynchronisierung benötigen, wenden Sie sich an [unser Kundenerfolgsteam](https://www.microsoft.com/fasttrack?rtc=1), oder [öffnen Sie ein Supportticket](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Teams Admin Center-Richtlinien

- Die Besitzer des Kursteams müssen Teams Chat aktiviert haben.
- Kursteambesitzer müssen über externen Zugriff verfügen, **wobei Teams Konten nicht von einer Organisation verwaltet werden**, die aktiviert ist.
  - Dies muss auf Mandanten- und Benutzerebene aktiviert sein. Die Einstellung auf Mandantenebene finden Sie unter **"Benutzer > externen Zugriff**" im Teams Admin Center. Auf diese Einstellung kann auch über PowerShell zugegriffen werden. Auf Richtlinien für den externen Zugriff auf Benutzerebene kann nur über PowerShell zugegriffen werden. Weitere Anleitungen finden Sie unten in den PowerShell-Befehlen.

#### <a name="parent-and-guardian-restrictions"></a>Einschränkungen für Eltern und Erziehungsberechtigte

Eltern und Erziehungsberechtigte werden in der Elternverbindung als *externe Benutzer* klassifiziert, was bedeutet, dass sie nicht über vollständige Mandantenrechte verfügen. Sie haben nur Zugriff auf den Chat oder die Chats, zu dem sie gehören, und die Dateien, Bilder und anderen Inhalte, die im Chat freigegeben wurden.

Bei externen Chats können sowohl interne als auch externe Benutzer Dem Chat Benutzer hinzufügen. Weitere Informationen zur externen Chaterfahrung finden [Sie unter Verwalten externer Besprechungen und Chats in Microsoft Teams](manage-external-access.md).

Außerdem können externe Benutzer die Anwesenheit (offline, verfügbar, beschäftigt usw.) der Benutzer Ihrer Organisation sehen, dies kann jedoch mithilfe von PowerShell deaktiviert werden, um die Privatsphäre der Benutzer zu schützen. Verwenden Sie in PowerShell [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) und set ``EnablePrivacyMode=true``.

Obwohl Eltern und Erziehungsberechtigte externe Benutzer sind, sind ihre Beiträge zu Chats auffindbar. Erfahren Sie, wie Sie eine Teams eDiscovery-Untersuchung durchführen, indem Sie "[Durchführen einer eDiscovery-Untersuchung von Inhalten in Microsoft Teams](ediscovery-investigation.md)" lesen.

> [!IMPORTANT]
> IT-Administratoren sollten alle Kursbesitzer über bewährte Methoden zum Freigeben von Schülerinformationen über Chats informieren, einschließlich Risiken für den Datenschutz von Kursteilnehmern.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Blockieren eines Elternteils oder Erziehungsberechtigten in einem Chat

Lehrkräfte können einen Erziehungsberechtigten in einem Chat blockieren, der in der Übergeordneten Verbindung initiiert wurde.

Der Klassenbesitzer kann:

1. Öffnen Sie die Profilkarte des Erziehungsberechtigten, wählen Sie die Ellipse aus, und **blockieren Sie den Benutzer**.
2. Entfernen Sie dann den Erziehungsberechtigten aus dem Chat.

Der blockierte Benutzer kann keine zusätzlichen Chats mit dem Klassenbesitzer starten.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Zulassen des externen Zugriffs mit Teams Konten, die nicht von einer Organisation verwaltet werden

Damit Lehrkräfte mit Eltern und Erziehungsberechtigten in Teams kommunizieren können, muss der IT-Administrator des Bildungsmandanten die Richtlinien des Mandanten aktualisieren, um externen Zugriff für Teams Konten außerhalb des Mandanten zu ermöglichen. Weitere Informationen zum Verwalten des externen Zugriffs erhalten [Sie unter Verwalten des externen Zugriffs in Microsoft Teams](manage-external-access.md).

Hier sind die Schritte zum Aktivieren des externen Zugriffs für Eltern und Erziehungsberechtigte.

1. Installieren Sie die neueste Microsoft Teams PowerShell-Modulvorschau.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Führen Sie unter Verwendung von Anmeldeinformationen mit Administratorrechten die folgenden Befehle aus:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    Die Richtlinieneinstellung, die den externen Zugriff mit Teams Konten aktiviert, die nicht von einer Organisation auf Benutzerebene () verwaltet werden,`EnableTeamsConsumerAccess` ist standardmäßig für alle Richtlinien für den externen Zugriff auf Benutzerebene aktiviert. Sowohl die Einstellung auf Mandantenebene als auch die Richtlinieneinstellung auf Benutzerebene müssen aktiviert sein, damit ein Benutzer externen Zugriff mit Teams Konten hat, die nicht von einer Organisation verwaltet werden. Wenn Sie nicht möchten, dass jeder Benutzer in Ihrem Mandanten diesen Zugriff aktiviert hat, sollten Sie sicherstellen, dass Ihre Einstellung auf Mandantenebene deaktiviert ist, aktualisieren Sie die den Benutzern zugewiesenen Richtlinien für den externen Zugriff auf Benutzerebene, und aktivieren Sie dann die Einstellung auf Mandantenebene.

    Führen Sie die folgenden Schritte aus, um zu überprüfen, welche Richtlinien für den externen Zugriff auf Benutzerebene vorhanden sind und wem sie zugewiesen sind:

3. Überprüfen Sie, ob Richtlinien für den externen Zugriff auf Benutzerebene vorhanden sind.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Überprüfen Sie für jede andere Richtlinie als die globale Richtlinie, welche Benutzer die Richtlinie zugewiesen haben.

   > [!NOTE]
   > Alle Benutzer, denen keine bestimmte Richtlinie zugewiesen ist, greifen auf die "globale" Richtlinie zurück. Allen neuen Benutzern, die dem Mandanten hinzugefügt werden, wird die Richtlinie "Global" zugewiesen.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Da alle Richtlinien für den externen Zugriff auf Benutzerebene standardmäßig auf "true" festgelegt sind `EnableTeamsConsumerAccess` , können Sie, wenn Sie die `EnableTeamsConsumerAccess` Einstellung für bestimmte Benutzer anpassen möchten, vorhandene Richtlinien für den externen Zugriff mit angepassten Einstellungen erstellen/ändern und/oder Benutzer mithilfe der folgenden PowerShell-Cmdlets neuen oder vorhandenen Richtlinien zuweisen:

- Erstellen einer neuen Richtlinie für den externen Zugriff: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Anpassen einer vorhandenen Richtlinie für den externen Zugriff (einschließlich der Richtlinie "Global"): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Die folgenden Standardrichtlinien für Abonnements können nicht geändert werden: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Die Richtlinie "FederationAndPICDefault" wurde standardmäßig allen Benutzern zugewiesen, neuen Benutzern wird nun standardmäßig die Richtlinie "Global" zugewiesen. Wenn Sie die Richtlinieneinstellungen für Benutzer ändern müssen, denen diese Standardrichtlinien für Abonnements zugewiesen sind, weisen Sie diesen Benutzern unterschiedliche Richtlinien mit den richtigen Einstellungen zu.

- Weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff zu: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Zuweisen einer Richtlinie zu einer Gruppe von Benutzern: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Sobald die Richtlinien für den externen Zugriff auf Benutzerebene für die Benutzer in Ihrem Mandanten ordnungsgemäß festgelegt wurden, können Sie die Einstellung auf Mandantenebene (`AllowTeamsConsumer`) für den Mandanten mithilfe des folgenden Cmdlets aktivieren:

- Festlegen der Verbundkonfigurationseinstellungen für Ihren Mandanten: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Aktivieren der Eltern-App im Teams Admin Center

Die Eltern-App ist standardmäßig deaktiviert, sodass sie für Kursteambesitzer erst in ihren Kursteams angezeigt wird, wenn sie über das Teams Admin Center zulässig ist. Die Eltern-App ist im Teams Admin Center mithilfe [von von Herausgebern blockierten Apps zulassen](manage-apps.md#apps-blocked-by-publishers) aktiviert.

Die App kann jederzeit auf Mandantenebene mithilfe von Apps im Teams Admin Center deaktiviert [und blockiert](manage-apps.md#allow-and-block-apps) werden. Wenn sie auf Mandantenebene deaktiviert ist, wird sie für alle Benutzer blockiert, auch wenn Berechtigungen auf Benutzerebene aktiviert sind.

Die Eltern-App kann auch auf Benutzerebene mithilfe von [Berechtigungsrichtlinien für "App verwalten" in Microsoft Teams](teams-app-permission-policies.md) deaktiviert werden.

## <a name="more-information"></a>Weitere Informationen

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
