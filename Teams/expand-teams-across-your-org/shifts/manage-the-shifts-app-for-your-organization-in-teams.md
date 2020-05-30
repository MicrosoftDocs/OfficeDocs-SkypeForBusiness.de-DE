---
title: Verwalten der Schicht-App für Ihre Organisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Schichten-App in Microsoft Teams für Mitarbeiter in Service und Produktion in Ihrer Organisation einrichten und verwalten können.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416885"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams

> [!IMPORTANT]
> Gültig 30. Juni 2020, Microsoft StaffHub wird eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wird am 30. Juni 2020 nicht mehr für alle Benutzer funktionieren. Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet. Weitere Informationen finden Sie unter [Microsoft StaffHub wird eingestellt](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Übersicht über "Schichten"

Die Schichten-App in Microsoft Teams sorgt dafür, dass Mitarbeiter in Service und Produktion vernetzt und ihre Zeitpläne synchronisiert sind. Sie stellt eine mobile Lösung für eine schnelle und effektive Zeitverwaltung und Kommunikation für Teams dar. Mithilfe der Schichten-App können Mitarbeiter in Service und Produktion sowie deren Vorgesetzte ihre mobilen Geräte verwenden, um Arbeitszeitpläne zu verwalten und in Kontakt zu bleiben.

- Vorgesetzte erstellen, aktualisieren und verwalten Schichtzeitpläne für Teams. Sie können Nachrichten an eine Person ("Der Boden ist schmutzig") oder an das gesamte Team ("Der regionale Geschäftsführer kommt in 20 Minuten") senden. Sie können auch Richtliniendokumente, Bekanntmachungen und Videos senden. 
- Mitarbeiter können anstehende Schichten anzeigen, sie können sehen, wer für diesen Tag sonst noch eingeteilt ist, einen Schichtwechsel oder arbeitsfreie Zeit beantragen. 

Es ist wichtig zu wissen, dass "Schichten" zurzeit keine Gastbenutzer unterstützt. Dies bedeutet, dass Gäste eines Teams keinen Schichtplänen hinzugefügt werden können und diese auch nicht verwenden können, wenn der Gastzugriff in Microsoft Teams aktiviert ist. 

## <a name="availability-of-shifts"></a>Verfügbarkeit der Schichten-App

"Schichten" ist in allen Enterprise-SKUs verfügbar, die Microsoft Teams umfassen.

## <a name="location-of-shifts-data"></a>Speicherort von Daten der Schichten-App

Daten der Schichten-App werden aktuell in Azure in Rechenzentren in Nordamerika, Westeuropa und im asiatisch-pazifischen Raum gespeichert. Weitere Informationen zum Speicherort von Daten finden Sie unter [Wo befinden sich meine Daten?](http://o365datacentermap.azurewebsites.net/).

## <a name="set-up-shifts"></a>Einrichten von "Schichten"

### <a name="enable-or-disable-shifts-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" in Ihrer Organisation

"Schichten" ist standardmäßig für alle Microsoft Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](../../manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie in der Liste der Apps einen der folgenden Schritte aus:

    - Wenn Sie "Schichten" für Ihre Organisation deaktivieren möchten, suchen Sie nach der App "Schichten", wählen Sie sie aus, und klicken Sie dann auf **Blockieren**.
    - Wenn Sie "Schichten" für Ihre Organisation aktivieren möchten, suchen Sie nach der App "Schichten", wählen Sie sie aus, und klicken Sie dann auf **Zulassen**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" für bestimmte Benutzer in Ihrer Organisation

Wenn Sie die Nutzung von "Schichten" für bestimmte Benutzer in Ihrer Organisation zulassen oder blockieren möchten, stellen Sie sicher, dass die App für Ihre Organisation auf der Seite [Apps verwalten](../../manage-apps.md) aktiviert ist, und erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie diese den betreffenden Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Verwenden der FirstlineWorker App-Setup-Richtlinie, um "Schichten" in Microsoft Teams anzuheften

Mithilfe von App-Setup Richtlinien können Sie Microsoft Teams so anpassen, dass die Apps, die für die Benutzer in Ihrer Organisation am wichtigsten sind, hervorgehoben werden. Die in einer Richtlinie festgelegten Apps werden an die App-Leiste geheftet &mdash;das ist die seitliche Leiste bei Microsoft Teams-Desktop-Clients und am unteren Rand bei Microsoft Teams Mobile-Clients&mdash;, von wo die Benutzer schnell und einfach darauf zugreifen können. 
 
Microsoft Teams umfasst eine integrierte FirstlineWorker-App-Setup-Richtlinie, die Sie Mitarbeitern in Service und Produktion in Ihrem Unternehmen zuweisen können. Standardmäßig beinhaltet diese Richtlinie die Apps für Aktivität, Schichten, Chat und Anrufe. 

Wenn Sie die FirstlineWorker-Richtlinie anzeigen möchten, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams-App** > **-App-Setup-Richtlinien**.

![Screenshot der FirstlineWorker-App-Setup-Richtlinie](../../media/firstline-worker-app-setup-policy.png "Screenshot der FirstlineWorker-App-Setup-Richtlinie im Microsoft Teams Admin Center")

#### <a name="assign-the-firstlineworker-policy-to-users"></a>Zuweisen der FirstlineWorker-Richtlinie zu Benutzern

So weisen Sie die FirstlineWorker-App-Setup Richtlinie einem Benutzer zu:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Wählen Sie unter **App-Setup Richtlinie**die Option **FirstlineWorker**aus, und klicken Sie dann auf über **nehmen**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
3. Klicken Sie auf **Einstellungen bearbeiten**, wählen Sie unter **App-Setup Richtlinie**die Option **FirstlineWorker**aus, und klicken Sie dann auf über **nehmen**.  

Sie können auch die folgenden Schritte ausführen:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps.
2. Wählen Sie die FirstlineWorker-Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Nachdem Sie das Hinzufügen von Benutzern abgeschlossen haben, wählen Sie über **nehmen**aus.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a>Die FirstlineWorker App-Setup-Richtlinie Mitgliedern einer Gruppe zuweisen

Sie können die FirstlineWorker-App-Setup-Richtlinie Mitgliedern einer Gruppe wie z. B. einer Sicherheitsgruppe zuweisen, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](../../teams-powershell-overview.md).

In diesem Beispiel wird die FirstlineWorker-App-Setup-Richtlinie allen Mitgliedern der Gruppe "Contoso Firstline-Team" zugewiesen.

> [!NOTE]
> Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Abrufen der Mitglieder der gewählten Gruppe.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Die FirstlineWorker App-Setup-Richtlinie allen Mitgliedern der Gruppe zuweisen.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

## <a name="search-the-audit-log-for-shifts-events"></a>Durchsuchen des Überwachungsprotokolls nach Schichten Ereignissen

**(in der Vorschau)**

Sie können das Überwachungsprotokoll durchsuchen, um schichtaktivitäten in Ihrer Organisation anzuzeigen.  Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Anzeigen einer Liste der [schichtaktivitäten](../../audit-log-events.md#shifts-in-teams-activities) , die im Überwachungsprotokoll protokolliert werden, finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Teams](../../audit-log-events.md).

Bevor Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst die Überwachung im [Security & Compliance Center](https://protection.office.com)aktivieren. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Beachten Sie, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="related-topics"></a>Verwandte Themen

- [Hilfe zur Schichten-App für Mitarbeiter in Service und Produktion](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](../../assign-policies.md)
