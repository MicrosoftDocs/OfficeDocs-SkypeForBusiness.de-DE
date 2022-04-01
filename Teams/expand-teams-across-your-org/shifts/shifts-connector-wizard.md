---
title: Verwenden des Assistenten "Schichtenconnector", um Schichten mit der Personalverwaltung in Blue Yonder zu verbinden
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie den Connector-Assistenten für Schichten verwenden, um Schichten Teams Personalverwaltung von Blue Yonder zu integrieren.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593668"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Verwenden des Assistenten "Schichtenconnector", um Schichten mit der Personalverwaltung in Blue Yonder zu verbinden

## <a name="overview"></a>Übersicht

Mit dem Assistenten für Schichtenconnector im Microsoft 365 Admin Center können Sie die Schichten-App in Microsoft Teams ihr Personalverwaltungssystem (WFM) integrieren. Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in der Frontlinie ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

Der Assistent konfiguriert den Schichten-Connector, erstellt eine Verbindung mit Ihrem WFM-System und wendet die von Ihnen festgelegten Synchronisierungseinstellungen und Teamzuordnungen an. Die Synchronisierungseinstellungen bestimmen die Zeitplaninformationen, die zwischen Ihrem WFM-System und Schichten synchronisiert werden. Teamzuordnungen definieren die Synchronisierungsbeziehung zwischen Ihren WFM-Websites und Teams in Teams. Sie können vorhandene und neue Teams zuordnungen.

Sie können mehrere Verbindungen einrichten, die jeweils unterschiedliche Synchronisierungseinstellungen haben. Wenn Ihre Organisation beispielsweise über mehrere Standorte mit unterschiedlichen Zeitplananforderungen verfügt, erstellen Sie eine Verbindung mit eindeutigen Synchronisierungseinstellungen für jeden Standort. Denken Sie daran, dass eine WFM-Website immer nur einem Team zugeordnet werden kann. Wenn eine WFM-Website bereits einem Team zugeordnet ist, kann sie nicht einem anderen Team zugeordnet werden.

Wenn Ihr WFM-System das System für Aufzeichnungen ist, können Ihre Mitarbeiter in der Frontlinie Schichten sehen und tauschen, ihre Verfügbarkeit verwalten und in Schichten auf ihren Geräten Arbeitszeit anfordern. Frontline-Manager können Ihr WFM-System weiterhin zum Einrichten von Zeitplänen verwenden.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrieren von Schichten in die Personalverwaltung von Blue Yonder

Derzeit unterstützt der Assistent den Microsoft Teams [Schichten-Connector für Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Mit diesem Connector können Sie Schichten mit Blue Yonder Workforce Management (Blue Yonder WFM) integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten. In diesem Artikel wird erläutert, wie Sie den Assistenten ausführen, um eine Verbindung mit Blue Yonder WFM über den Connector herzustellen.

> [!NOTE]
> Sie können auch PowerShell verwenden, um Schichten in Blue Yonder WFM zu integrieren. Weitere Informationen finden Sie unter [Verwenden von PowerShell zum Verbinden von Schichten mit der Personalverwaltung von Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler Microsoft 365 sein, um den Assistenten ausführen zu können.

### <a name="prerequisites"></a>Voraussetzungen
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Die Teams, die Sie karten möchten, haben keine Zeitpläne. Wenn ein Team über einen vorhandenen Zeitplan [verfügt, entfernen](#remove-schedules-from-teams-you-want-to-map) Sie den Zeitplan aus dem Team, bevor Sie dem Team eine Blue Yonder WFM-Website zuordnungen. Andernfalls werden doppelte Schichten sehen.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Entfernen von Zeitplänen aus Teams, die Sie auf einer Karte anzeigen möchten
<a name="remove_schedules"> </a>

> [!NOTE]
> Führen Sie diesen Schritt aus, wenn Sie Blue Yonder WFM-Websites vorhandenen Teams mit Zeitplänen zuordnen möchten. Wenn Sie Teams ohne Zeitplan zuordnen oder wenn Sie neue Teams für die Zuordnung erstellen, können Sie diesen Schritt überspringen.

Verwenden Sie PowerShell, um Zeitpläne aus Teams zu entfernen.

1. Zuerst müssen Sie die PowerShell-Module installieren und die Einrichtung dafür einrichten. Führen Sie die Schritte zum [Einrichten Ihrer Umgebung aus](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Führen Sie den folgenden Befehl aus:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Führen Sie [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)`EntityType` aus, um eine Liste der Szenarien für den Parameter zu erhalten. Zeitplandaten werden für den von Ihnen angegebenen Datums- und Uhrzeitbereich entfernt.

Weitere Informationen finden Sie unter [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Ausführen des Assistenten

### <a name="get-started"></a>Erste Schritte

1. Wählen Sie in der linken Navigationsleiste [Microsoft 365 Admin Center](https://admin.microsoft.com/) die Option **Setup** aus, und wechseln Sie dann zum Abschnitt **Apps und E-Mail**.
1. Wählen **Verbinden Ihr Personalverwaltungssystem aus**. Hier erhalten Sie weitere Informationen zu Verbindern für Schichten und zur Frontline-Worker- und -Manager-Erfahrung, wenn Sie Schichten mit Ihrem WFM-System verbinden.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Screenshot der Detailseite für den Verbinder-Assistenten "Schichten" im Microsoft 365 Admin Center." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Wenn Sie fertig sind, wählen Sie **Erste Schritte**.
1. Wählen **Sie Weiter** aus, um eine Blue Yonder WFM-Verbindung zu erstellen.

### <a name="enter-connection-details"></a>Verbindungsdetails eingeben
<a name="connection_details"> </a>

1. Geben Sie auf der Seite Verbindungsdetails einen eindeutigen Namen für die Verbindung an. Er darf nicht länger als 128 Zeichen sein oder Sonderzeichen enthalten.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Screenshot der Seite "Verbindungsdetails" des Assistenten mit Verbindungseinstellungen" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Geben Sie den Namen, das Kennwort und die Dienst-URLs Ihres Blue Yonder WFM-Dienstkontos ein.
1. Wenn Sie fertig sind, **wählen Sie Weiter** aus, um die Verbindung mit den von Ihnen eingegebenen Einstellungen zu testen.

### <a name="choose-sync-settings"></a>Auswählen der Synchronisierungseinstellungen
<a name="sync"> </a>

Auf der Seite Synchronisierungseinstellungen wählen Sie die Zu synchronisierenden Informationen von Blue Yonder WFM zu Schichten, die Synchronisierungshäufigkeit und die Frage aus, ob Benutzer mit Schichten Änderungen an den Daten vornehmen können.

1. Geben Sie Ihr Microsoft 365-Systemkonto ein.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Screenshot der Seite "Synchronisierungseinstellungen" des Assistenten mit den Synchronisierungseinstellungen" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Wählen Sie **unter Empfänger von E-Mail-Benachrichtigungen** aus, wer E-Mail-Benachrichtigungen zu dieser Verbindung erhält. Sie können einzelne Benutzer und Gruppen hinzufügen. Die E-Mail-Benachrichtigungen enthalten Informationen zum Verbindungseinrichtungsstatus sowie alle Probleme oder Fehler, die nach dem Einrichten der Verbindung auftreten können.
1. Wählen Sie Ihre Synchronisierungseinstellungen aus:
    1. Wählen **Sie unter Zeitplan und** Schichten die Blue Yonder WFM-Daten aus, die Benutzer von Schichten sehen oder ändern können, und legen Sie dann die Synchronisierungshäufigkeit fest.
    2. Wählen **Sie unter** Anforderungen die Arten von Anforderungen aus, die Benutzer in Schichten sehen und erstellen können.

    > [!IMPORTANT]
    > Wenn Sie eine der folgenden Optionen zum Deaktivieren geöffneter Schichten, offener Schichtanforderungen, Tauschanfragen oder Anfragen für freie Zeit ausgewählt haben, müssen Sie noch einen weiteren Schritt zum Ausblenden der Funktion in Schichten tun.
    >
    > - Offene Schichten: **Schichtbenutzer sehen keine Blue Yonder WFM-Daten**
    > - Tauschanforderungen: **Das Feature ist für alle Benutzer deaktiviert.**
    > - Anfragen für freizeite Zeit: **Das Feature ist für alle Benutzer deaktiviert.**
    >
    > Nachdem Sie den Assistenten ausgeführt haben, stellen Sie sicher, dass Sie die Schritte im Abschnitt Deaktivieren geöffneter Schichten, geöffneter Schichtenanforderungen [,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) Tauschanforderungen und Anfragen für arbeits freie Zeit weiter unten in diesem Artikel ausführen.
 
1. Wenn Sie ihre Einstellungen ausgewählt haben, wählen Sie **Verbindung erstellen aus**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Zuordnung von Blue Yonder-Personalverwaltungswebsites zu Teams
<a name="sites"> </a>

Wählen Sie die Blue Yonder WFM-Websites aus, die Sie mit Schichten verbinden möchten. Sie können bis zu 100 Websites auswählen.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Screenshot des Assistenten mit einer Liste der Blue Yonder WFM-Websites" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Ordnen Sie dann jede ausgewählte Blue Yonder WFM-Website einem Team in Teams. Sie können eine Website einem vorhandenen Team zuordnungen, oder Sie können ein neues Team erstellen.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Screenshot des Bereichs mit der Option "Team suchen" und der Option "Neues Team erstellen"" lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>So ordnen Sie eine Website einem vorhandenen Team zu

1. Wählen Sie den Websitenamen aus.
2. Suchen Sie im Bereich nach dem Team, und wählen Sie es aus. Beachten Sie, dass Teams, die in dieser Verbindung bereits einer Website zugeordnet sind, bei der Suche nicht angezeigt werden.
3. Wählen Sie die Zeitzone und den nächstgelegenen Ort aus.
4. Wählen **Sie Speichern** und dann Weiter **aus**.

#### <a name="to-map-a-site-to-a-new-team"></a>So ordnen Sie eine Website einem neuen Team zu

1. Wählen Sie den Websitenamen aus.
2. Wählen Sie im Bereich die **Option Neues Team erstellen aus**. Sie erhalten eine neue Registerkarte in Ihrem Browser, auf der Sie ein neues Team im Team Microsoft 365 Admin Center.
    1. Geben Sie einen Namen und eine optionale Beschreibung für das Team ein.
    1. Fügen Sie einen oder mehrere Teambesitzer hinzu. Stellen Sie sicher, dass Sie Microsoft 365 Konto als Besitzer hinzufügen.
    1. Fügen Sie Teammitglieder hinzu.
    1. Fügen Sie eine Team-E-Mail-Adresse hinzu, und wählen Sie eine Datenschutzeinstellung aus.
    1. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Team hinzufügen aus**. Wenn Ihr Team erstellt wurde, wählen Sie **Schließen aus**.
3. Zurück Sie zum Assistenten, suchen Sie nach dem neuen Team, das Sie erstellt haben, und wählen Sie es aus.
4. Wählen Sie die Zeitzone und den nächstgelegenen Ort aus.
5. Wählen **Sie Speichern** und dann Weiter **aus**.

### <a name="review-and-finish"></a>Überprüfen und fertig stellen

Überprüfen Sie Ihre Einstellungen. Wenn Sie Änderungen an Teamzuordnungen vornehmen müssen, wählen Sie **Bearbeiten** aus, um dies zu tun. Wenn Sie fertig sind, wählen Sie Fertig **stellen aus**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Screenshot der Seite "Überprüfen" des Assistenten mit Zuordnungen" lightbox="../../media/shifts-connector-wizard-review.png":::

Es wird eine Meldung angezeigt, mit der Sie bestätigen können, dass wir Ihre Anfrage erhalten haben, zusammen mit einer Vorgangs-ID. Notieren Sie sich die Vorgangs-ID. Sie benötigen sie, um den Setupstatus Ihrer Verbindung zu überprüfen.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Screenshot der Seite des Assistenten mit Bestätigungsmeldung und Vorgangs-ID" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

Der Assistent startet den Vorgang zum Einrichten der Verbindung und Zuordnung der Websites zu den von Ihnen ausgewählten Teams. Dieser Vorgang kann einige Zeit dauern. Die von Ihnen gewählten Empfänger erhalten E-Mail-Benachrichtigungen zum Setupstatus.

Wählen Sie **Fertig aus** , um den Assistenten zu beenden.

Sie sind auf dem Weg, aber Sie sind noch nicht fertig! Überprüfen Sie unbedingt Ihre E-Mails. Sie erhalten eine Bestätigung, dass wir Ihre Anfrage erhalten haben, sowie einen [](shifts-connector-powershell-manage.md#check-connection-setup-status) Link, über den Sie den Setupstatus überprüfen können.

> [!NOTE]
> Wenn nach der Einrichtung in einer Verbindung ein Problem oder ein Fehler auftritt, werden Sie per E-Mail benachrichtigt. Folgen Sie den Anweisungen in der E-Mail, um das Problem zu beheben.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deaktivieren sie offene Schichten, offene Schichten, Tauschanfragen und Anfragen für freie Zeit.

> [!IMPORTANT]
> Führen Sie diese Schritte nur aus, wenn Sie im Assistenten eine der folgenden Optionen zum Deaktivieren von offenen Schichten, offenen Schichtanforderungen, Tauschanforderungen oder Anfragen für arbeits freie Zeit ausgewählt haben. Bei Abschluss dieses Schritts wird die Funktion in Schichten ausgeblendet.
>
> - Offene Schichten: **Schichtbenutzer sehen keine Blue Yonder WFM-Daten**
> - Tauschanforderungen: **Das Feature ist für alle Benutzer deaktiviert.**
> - Anfragen für freizeite Zeit: **Das Feature ist für alle Benutzer deaktiviert.**
>
> Ohne diesen zweiten Schritt wird den Benutzern weiterhin die Funktion in Schichten angezeigt, und wenn sie versuchen, sie zu verwenden, wird die Fehlermeldung "Nicht unterstützter Vorgang" angezeigt.

Verwenden Sie zum Ausblenden geöffneter Schichten, Tauschanforderungen und Anfragen für freie Zeitverschiebungen in Schichten den Ressourcentyp " [](/graph/api/resources/schedule?view=graph-rest-1.0) Graph-API ```false``` Schedule", um die folgenden Parameter für jedes Team zu definieren, das Sie einer Blue Yonder WFM-Website zugeordnet haben:

- Offene Schichten: ```openShiftsEnabled```
- Tauschanforderungen:  ```swapShiftsRequestsEnabled```
- Anfragen für freizeite Zeit: ```timeOffRequestsEnabled```

Um offene Schichtenanforderungen in Schichten auszublenden, wechseln **Sie in Einstellungen** zu Schicht, und deaktivieren Sie dann die Einstellung **Offene Schichten**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Wenn Sie Änderungen an einer Verbindung vornehmen müssen
<a name="update_connection"> </a>

Nachdem eine Verbindung eingerichtet wurde, verwenden Sie PowerShell, um Änderungen vorzunehmen. So können Sie beispielsweise Synchronisierungseinstellungen und Teamzuordnungen aktualisieren und die Synchronisierung für eine Verbindung deaktivieren. Eine Schritt-für-Schritt-Anleitung finden Sie unter Verwenden von [PowerShell zum Verwalten Ihrer Schichtenverbindung zur Personalverwaltung von Blue Yonder](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Verschiebt Verbinder](shifts-connectors.md)
- [Verwenden von PowerShell zum Verwalten Ihrer Schichtenverbindung zur Personalverwaltung von Blue Yonder](shifts-connector-powershell-manage.md)
- [Verwalten der Schichten-App in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
