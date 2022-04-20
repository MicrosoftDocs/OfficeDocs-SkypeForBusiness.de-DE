---
title: Verwenden des Verbinder-Assistenten "Schichten" zum Verbinden von Schichten mit Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie den Connector-Assistenten "Schichten" verwenden, um Schichten in Teams mit Blue Yonder Workforce Management zu integrieren.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593668"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Verwenden des Verbinder-Assistenten "Schichten" zum Verbinden von Schichten mit Blue Yonder Workforce Management

## <a name="overview"></a>Übersicht

Mit dem Assistenten für schichtenverbinder im Microsoft 365 Admin Center können Sie die Schichten-App in Microsoft Teams in Ihr Mitarbeiterverwaltungssystem (WFM) integrieren. Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in Service und Produktion ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

Der Assistent konfiguriert den Shifts-Connector, erstellt eine Verbindung mit Ihrem WFM-System und wendet die von Ihnen ausgewählten Synchronisierungseinstellungen und Teamzuordnungen an. Synchronisierungseinstellungen bestimmen die Zeitplaninformationen, die zwischen Ihrem WFM-System und Schichten synchronisiert werden. Teamzuordnungen definieren die Synchronisierungsbeziehung zwischen Ihren WFM-Websites und Teams in Teams. Sie können vorhandene Teams und neue Teams zuordnen.

Sie können mehrere Verbindungen mit jeweils unterschiedlichen Synchronisierungseinstellungen einrichten. Wenn Ihre Organisation beispielsweise über mehrere Standorte mit unterschiedlichen Zeitplananforderungen verfügt, erstellen Sie eine Verbindung mit eindeutigen Synchronisierungseinstellungen für jeden Standort. Beachten Sie, dass eine WFM-Website zu einem bestimmten Zeitpunkt nur einem Team zugeordnet werden kann. Wenn eine WFM-Website bereits einem Team zugeordnet ist, kann sie keinem anderen Team zugeordnet werden.

Mit Ihrem WFM-System als Datensatzsystem können Ihre Mitarbeiter in Service und Produktion Schichten sehen und austauschen, deren Verfügbarkeit verwalten und Abwesenheitszeiten in Schichten auf ihren Geräten anfordern. Vorgesetzte in Service und Produktion können Ihr WFM-System weiterhin zum Einrichten von Zeitplänen verwenden.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrieren von Schichten in Blue Yonder Workforce Management

Derzeit unterstützt der Assistent den [Microsoft Teams Shifts-Verbinder für Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Mit diesem Connector können Sie Schichten in Blue Yonder Workforce Management (Blue Yonder WFM) integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten. In diesem Artikel führen wir Sie durch das Ausführen des Assistenten zum Einrichten einer Verbindung mit Blue Yonder WFM über den Connector.

> [!NOTE]
> Sie können PowerShell auch verwenden, um Schichten in Blue Yonder WFM zu integrieren. Weitere Informationen finden Sie unter [Verwenden von PowerShell, um Schichten mit Blue Yonder Workforce Management zu verbinden](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein Microsoft 365 globaler Administrator sein, um den Assistenten ausführen zu können.

### <a name="prerequisites"></a>Voraussetzungen
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Die Teams, die Sie zuordnen möchten, haben keine Zeitpläne. Wenn ein Team über einen vorhandenen Zeitplan verfügt, [entfernen Sie den Zeitplan aus dem Team](#remove-schedules-from-teams-you-want-to-map) , bevor Sie eine Blue Yonder WFM-Website zuordnen. Andernfalls werden doppelte Schichten angezeigt.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Entfernen von Zeitplänen aus Teams, die Sie zuordnen möchten
<a name="remove_schedules"> </a>

> [!NOTE]
> Führen Sie diesen Schritt aus, wenn Sie Blue Yonder WFM-Websites vorhandenen Teams zuordnen, die Zeitpläne haben. Wenn Sie Teams zuordnen, die keine Zeitpläne haben, oder wenn Sie neue Teams für die Zuordnung erstellen, können Sie diesen Schritt überspringen.

Verwenden Sie PowerShell, um Zeitpläne aus Teams zu entfernen.

1. Zuerst müssen Sie die PowerShell-Module installieren und einrichten. Führen Sie die Schritte zum [Einrichten Ihrer Umgebung](shifts-connector-powershell-manage.md#set-up-your-environment) aus.
1. Führen Sie den folgenden Befehl aus:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Um eine Liste der Szenarien für den `EntityType` Parameter abzurufen, führen Sie [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps) aus. Zeitplandaten werden für den von Ihnen angegebenen Datums- und Uhrzeitbereich entfernt.

Weitere Informationen finden Sie unter [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Ausführen des Assistenten

### <a name="get-started"></a>Erste Schritte

1. Wählen Sie im linken Navigationsbereich des [Microsoft 365 Admin Center](https://admin.microsoft.com/) **"Setup"** aus, und wechseln Sie dann zum Abschnitt **"Apps und E-Mail**".
1. Wählen Sie **Verbinden Ihrem Personalverwaltungssystem** aus. Hier erfahren Sie mehr über Schichtenconnectors und die Mitarbeiter- und Managererfahrung in Service und Produktion, wenn Sie Schichten mit Ihrem WFM-System verbinden.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Screenshot der Detailseite für den Verbinder-Assistenten &quot;Schichten&quot; im Microsoft 365 Admin Center." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Wenn Sie fertig sind, wählen Sie **Erste Schritte** aus.
1. Wählen Sie **"Weiter** " aus, um eine Blue Yonder-WFM-Verbindung zu erstellen.

### <a name="enter-connection-details"></a>Verbindungsdetails eingeben
<a name="connection_details"> </a>

1. Geben Sie der Verbindung auf der Seite "Verbindungsdetails" einen eindeutigen Namen. Es darf nicht länger als 128 Zeichen sein oder Sonderzeichen enthalten.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Screenshot der Seite &quot;Verbindungsdetails&quot; des Assistenten mit Verbindungseinstellungen." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Geben Sie Ihren Blue Yonder WFM-Dienstkontonamen sowie Kennwort- und Dienst-URLs ein.
1. Wenn Sie fertig sind, wählen Sie **"Weiter** " aus, um die Verbindung mit den von Ihnen eingegebenen Einstellungen zu testen.

### <a name="choose-sync-settings"></a>Synchronisierungseinstellungen auswählen
<a name="sync"> </a>

Wählen Sie auf der Seite "Synchronisierungseinstellungen" die Informationen aus, die von Blue Yonder WFM mit Schichten synchronisiert werden sollen, die Synchronisierungshäufigkeit und ob Benutzer von Schichten Änderungen an den Daten vornehmen können.

1. Geben Sie Ihr Microsoft 365-Systemkonto ein.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Screenshot der Seite &quot;Synchronisierungseinstellungen&quot; des Assistenten mit den Synchronisierungseinstellungen." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Wählen Sie unter **E-Mail-Benachrichtigungsempfänger** aus, wer E-Mail-Benachrichtigungen über diese Verbindung erhält. Sie können einzelne Benutzer und Gruppen hinzufügen. Die E-Mail-Benachrichtigungen enthalten Informationen über den Verbindungseinrichtungsstatus und alle Probleme oder Fehler, die nach dem Einrichten der Verbindung auftreten können.
1. Wählen Sie Ihre Synchronisierungseinstellungen aus:
    1. Wählen Sie unter **"Zeitplan und Schichten**" die Blue Yonder-WFM-Daten aus, die Benutzer sehen oder ändern können, und legen Sie dann die Synchronisierungshäufigkeit fest.
    2. Wählen Sie unter **"Anforderungen**" die Arten von Anforderungen aus, die Benutzer von Schichten anzeigen und erstellen können.

    > [!IMPORTANT]
    > Wenn Sie eine der folgenden Optionen ausgewählt haben, um offene Schichten, Offene Schichtanforderungen, Tauschanforderungen oder Abwesenheitsanforderungen zu deaktivieren, müssen Sie einen weiteren Schritt ausführen, um die Funktion in Schichten auszublenden.
    >
    > - Offene Schichten: **Schichtbenutzer sehen keine Blue Yonder WFM-Daten**
    > - Swapanforderungen: **Das Feature ist für alle Benutzer deaktiviert**.
    > - Abwesenheitsanforderungen: **Das Feature ist für alle Benutzer deaktiviert**.
    >
    > Nachdem Sie den Assistenten ausgeführt haben, stellen Sie sicher, dass Sie die Schritte im Abschnitt ["Offene Schichten deaktivieren", "Schichtanforderungen öffnen", "Tauschanforderungen" und "Abwesenheitsanforderungen](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) " weiter unten in diesem Artikel ausführen.
 
1. Wenn Sie ihre Einstellungen ausgewählt haben, wählen Sie **"Verbindung erstellen**" aus.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Zuordnen von Blue Yonder Workforce Management-Websites zu Teams
<a name="sites"> </a>

Wählen Sie die Blue Yonder WFM-Websites aus, die Sie mit Schichten verbinden möchten. Sie können bis zu 100 Websites auswählen.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Screenshot des Assistenten mit der Liste der WFM-Websites von Blue Yonder." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Ordnen Sie dann jede blue Yonder WFM-Website, die Sie ausgewählt haben, einem Team in Teams zu. Sie können eine Website einem vorhandenen Team zuordnen oder ein neues Team erstellen.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Screenshot des Bereichs mit der Suchteamoption und dem Erstellen einer neuen Teamoption." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>So ordnen Sie eine Website einem vorhandenen Team zu

1. Wählen Sie den Websitenamen aus.
2. Suchen Sie im Bereich nach dem Team, und wählen Sie es aus. Beachten Sie, dass Teams, die bereits einer Website in dieser Verbindung zugeordnet sind, nicht in der Suche angezeigt werden.
3. Wählen Sie die Zeitzone und die nächstgelegene Stadt aus.
4. Wählen Sie **"Speichern"** und dann " **Weiter**" aus.

#### <a name="to-map-a-site-to-a-new-team"></a>So ordnen Sie eine Website einem neuen Team zu

1. Wählen Sie den Websitenamen aus.
2. Wählen Sie im Bereich " **Neues Team erstellen" aus**. Sie werden zu einer neuen Registerkarte in Ihrem Browser weitergeleitet, auf der Sie ein neues Team in der Microsoft 365 Admin Center erstellen können.
    1. Geben Sie einen Namen und eine optionale Beschreibung für das Team ein.
    1. Fügen Sie einen oder mehrere Teambesitzer hinzu. Stellen Sie sicher, dass Sie das Microsoft 365 Systemkonto als Besitzer hinzufügen.
    1. Fügen Sie Teammitglieder hinzu.
    1. Fügen Sie eine Team-E-Mail-Adresse hinzu, und wählen Sie eine Datenschutzeinstellung aus.
    1. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **"Team hinzufügen"** aus. Wenn Ihr Team erstellt wurde, wählen Sie **"Schließen**" aus.
3. Zurück zum Assistenten, suchen Sie nach dem neuen Team, das Sie erstellt haben, und wählen Sie es aus.
4. Wählen Sie die Zeitzone und die nächstgelegene Stadt aus.
5. Wählen Sie **"Speichern"** und dann " **Weiter**" aus.

### <a name="review-and-finish"></a>Überprüfen und fertig stellen

Überprüfen Sie Ihre Einstellungen. Wenn Sie Änderungen an Teamzuordnungen vornehmen müssen, wählen Sie " **Bearbeiten** " aus, um dies zu tun. Wenn Sie fertig sind, wählen Sie **"Fertig stellen**" aus.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Screenshot der Seite &quot;Überprüfen&quot; des Assistenten mit Zuordnungen." lightbox="../../media/shifts-connector-wizard-review.png":::

Es wird eine Meldung angezeigt, die bestätigt, dass wir Ihre Anforderung zusammen mit einer Vorgangs-ID erhalten haben. Notieren Sie sich die Vorgangs-ID. Sie benötigen ihn, um den Setupstatus Ihrer Verbindung zu überprüfen.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Screenshot der Assistentenseite mit Bestätigungsmeldung und Vorgangs-ID." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

Der Assistent startet den Vorgang zum Einrichten der Verbindung und zum Zuordnen der Websites zu den ausgewählten Teams. Dieser Vorgang kann einige Zeit in Anspruch nehmen. Die ausgewählten Empfänger erhalten E-Mail-Benachrichtigungen über den Setupstatus.

Wählen Sie **"Fertig"** aus, um den Assistenten zu beenden.

Sie sind auf dem Weg, aber sie sind noch nicht fertig! Überprüfen Sie Unbedingt Ihre E-Mails. Sie erhalten eine Bestätigung, dass wir Ihre Anfrage erhalten haben, zusammen mit einem [Link](shifts-connector-powershell-manage.md#check-connection-setup-status) dazu, wie Sie den Setupstatus überprüfen können.

> [!NOTE]
> Wenn nach der Einrichtung ein Problem oder fehler in einer Verbindung auftritt, werden Sie per E-Mail benachrichtigt. Folgen Sie den Anweisungen in der E-Mail, um das Problem zu beheben.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deaktivieren von offenen Schichten, offenen Schichtanforderungen, Swapanforderungen und Abwesenheitsanfragen

> [!IMPORTANT]
> Führen Sie diese Schritte nur aus, wenn Sie eine der folgenden Optionen ausgewählt haben, um offene Schichten, Offene Schichtanforderungen, Tauschanforderungen oder Abwesenheitsanforderungen im Assistenten zu deaktivieren. Wenn Sie diesen Schritt abschließen, wird die Funktion in Schichten ausgeblendet.
>
> - Offene Schichten: **Schichtbenutzer sehen keine Blue Yonder WFM-Daten**
> - Swapanforderungen: **Das Feature ist für alle Benutzer deaktiviert**.
> - Abwesenheitsanforderungen: **Das Feature ist für alle Benutzer deaktiviert**.
>
> Ohne diesen zweiten Schritt sehen Benutzer die Funktion weiterhin in Schichten und erhalten die Fehlermeldung "Nicht unterstützter Vorgang", wenn sie versuchen, sie zu verwenden.

Verwenden Sie zum Ausblenden geöffneter Schichten, Swapanforderungen und Abwesenheitsanforderungen in Schichten den Graph-API [Ressourcentyp "Zeitplan](/graph/api/resources/schedule?view=graph-rest-1.0)", um die folgenden Parameter ```false``` für jedes Team festzulegen, das Sie einer Blue Yonder WFM-Website zugeordnet haben:

- Offene Schichten: ```openShiftsEnabled```
- Swapanforderungen:  ```swapShiftsRequestsEnabled```
- Abwesenheitsanforderungen: ```timeOffRequestsEnabled```

Um offene Schichtanforderungen in Schichten auszublenden, wechseln Sie zu **Einstellungen** in Schichten, und deaktivieren Sie dann die Einstellung "**Schichten** öffnen".

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Wenn Sie Änderungen an einer Verbindung vornehmen müssen
<a name="update_connection"> </a>

Nachdem eine Verbindung eingerichtet wurde, verwenden Sie PowerShell, um Änderungen daran vorzunehmen. Sie können z. B. Synchronisierungseinstellungen, Teamzuordnungen aktualisieren und die Synchronisierung für eine Verbindung deaktivieren. Eine schrittweise Anleitung finden [Sie unter Verwenden von PowerShell zum Verwalten Ihrer Schichtverbindung mit Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Schichtenverbinder](shifts-connectors.md)
- [Verwenden von PowerShell zum Verwalten Ihrer Schichtverbindung mit Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Verwalten der Schichten-App in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
