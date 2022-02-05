---
title: Virtuelle Besuche mit Teams - Integration in Cerner EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
  - Microsoft Teams
  - Microsoft Cloud for Healthcare
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - M365-collaboration
  - Teams_ITAdmin_Healthcare
  - microsoftcloud-healthcare
  - m365solution-healthcare
  - m365solution-scenario
appliesto:
  - Microsoft Teams
ms.reviewer: ansantam
description: 'Hier erfahren Sie, wie Sie den Connector Teams EHR integrieren, damit Anbieter im Gesundheitswesen in Ihrer Organisation virtuelle Visiten mit Patienten oder anderen Anbietern in Teams direkt vom Cerner EHR-System durchführen können.'
---

# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Virtuelle Besuche mit Teams - Integration in Cerner EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Der Connector Microsoft Teams Electronic Health Record (EHR)" erleichtert Klinikbetreibern das Starten eines virtuellen Besuchs mit einem Patienten oder die Konsultieren eines anderen Anbieters in Microsoft Teams direkt über das Cerner EHR-System. Das auf der Microsoft 365-Cloud Teams-Programm ermöglicht einfache, sichere Zusammenarbeit und Kommunikation mit Chat-, Video-, Sprach- und Gesundheitstools in einem einzigen Hub, der die Einhaltung von HIPAA, HITECH-Zertifizierung und mehr unterstützt.

Die Kommunikations- und Zusammenarbeitsplattform von Teams macht es für Klinikisten einfach, die Unübersichtlichkeit fragmentierter Systeme zu durchschneiden, sodass sie sich auf die Bereitstellung der bestmöglichen Behandlung konzentrieren können. Mit dem Teams EHR-Verbinder können Sie:

- Durchführen Teams Besuche von Ihrem Cerner EHR-System mit einem integrierten klinischen Workflow.
- Ermöglichen Sie es Patienten, an virtuellen Teams über E-Mails oder SMS-Benachrichtigungen teilnehmen.
- Zeigen Sie Verbrauchsdatenberichte und anpassbare Informationen zur Anrufqualität für mit EHR verbundene Besuche an.

In diesem Artikel wird beschrieben, wie Sie den EHR Teams Connector für die Integration in die Cerner-Plattform einrichten und konfigurieren. Darüber hinaus erhalten Sie einen Überblick über Teams Erfahrungen mit virtuellen Besuchen im Cerner EHR-System.

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!NOTE]
> Sprechen Sie mit Ihrem Cerner-Vertreter, und lesen Sie ihren Cerner-Integrationsleitfaden, bevor Sie die Integration aktivieren.

### <a name="prerequisites"></a>Voraussetzungen

Bevor Sie den Teams EHR-Connector in Ihrer Organisation im Gesundheitswesen integrieren können, müssen Sie über Folgendes verfügen:

- Ein aktives Abonnement Microsoft Teams eigenständiges EHR-Connectorangebot (nur beim Testen in einer EHR-Produktionsumgebung erzwungen).
- Die Benutzer verfügen über eine geeignete Microsoft 365 oder Office 365 Lizenz, die Teams umfasst.
- Teams in Ihrer Gesundheitsorganisation verbreitet und verwendet.
- Ihre Systeme erfüllen alle [Software- und Browseranforderungen für](../../hardware-requirements-for-the-teams-app.md) Teams.
- Cerner-Version November 2018 oder höher

## <a name="set-up-the-teams-ehr-connector"></a>Einrichten des Teams EHR-Verbinders

Das Konnektor-Setup erfordert Folgendes:

- [Starten des Konfigurationsportals für EHR-Connectors](#launch-the-ehr-connector-configuration-portal)
- [Eingeben von Konfigurationsinformationen](#enter-configuration-information)
- [Aktivieren von SMS-Benachrichtigungen (optional)](#enable-sms-notifications-optional)
- [Überprüfen und Beenden der Konfiguration](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Diese Schritte müssen vom globalen Microsoft 365 in Ihrer Organisation durchgeführt werden.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Starten des Konfigurationsportals für EHR-Connectors

Um zu beginnen, startet Microsoft 365 Administrator das [Konfigurationsportal für den EHR-Connector](https://ehrconnector.teams.microsoft.com) und meldet sich mit seinen Microsoft-Anmeldeinformationen an.

Ihr Microsoft 365 kann eine einzelne Abteilung oder mehrere Abteilungen konfigurieren, um die Integration zu testen. Konfigurieren Sie die Test- und Produktions-URL im Konfigurationsportal. Stellen Sie sicher, dass Sie die Integration aus der Cerner-Testumgebung testen, bevor Sie in die Produktion um stellen.

### <a name="enter-configuration-information"></a>Eingeben von Konfigurationsinformationen

Als Nächstes fügt Der Administrator Ihres Microsoft 365 eine Fast Health Interoperability Resources (FBRO)-Basis-URL von Cerner hinzu und gibt die Umgebung an. Konfigurieren Sie je nach Anforderungen Ihrer Organisation und den umgebungen, die Sie testen möchten, so viele F URL-Basis-URLs wie erforderlich.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Screenshot der Seite "Konfigurationsinformationen" im Teams EHR-Connectorkonfigurationsportals" lightbox="media/ehr-admin-cerner-configuration.png":::

- Die F ZAHL-Basis-URL ist eine statische Adresse, die Ihrem Server-FSTAT-API-Endpunkt entspricht. Eine Beispiel-URL ist `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Sie können die Integration für Test- und Produktionsumgebungen einrichten. Für die Ersteinrichtung sollten Sie den Connector in einer Testumgebung konfigurieren, bevor Sie in die Produktion um einstiegen.

Nachdem die F IMMER-Basis-URL überprüft und die Umgebung ausgewählt wurde, wählen Sie **Fertig aus**. Fügen Sie anschließend nach Bedarf weitere FGRA-Basis-URLs für andere Umgebungen hinzu.

Wählen **Sie Weiter** aus, um zum nächsten Schritt zu wechseln.

### <a name="enable-sms-notifications-optional"></a>Aktivieren von SMS-Benachrichtigungen (optional)

Führen Sie diesen Schritt aus, wenn Ihre Organisation möchte, dass Microsoft SMS-Benachrichtigungen für Ihre Patienten verwaltet. Wenn Sie SMS-Benachrichtigungen aktivieren, erhalten Ihre Patienten Bestätigungs- und Erinnerungsmeldungen für geplante virtuelle Besuche.

Zum Aktivieren von SMS-Benachrichtigungen geht Microsoft 365 Administrator wie folgt vor:

1. Aktivieren Sie auf der Seite SMS-Benachrichtigungen die beiden Kontrollkästchen für die Zustimmung für:

    - Erlauben Sie Microsoft, SMS-Benachrichtigungen an Patienten im Namen Ihrer Organisation zu senden.
    - Bestätigen Sie, dass Sie sicherstellen, dass die Teilnehmer dem Senden und Empfangen von SMS-Nachrichten zugestimmt haben.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Screenshot der Seite "SMS-Benachrichtigungen" mit Kontrollkästchen für die Zustimmung und der Option zum Generieren einer Telefonnummer" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. Wählen **Sie unter Ihre Telefonnummern** die Option **Neue Telefonnummer generieren** aus, um eine Telefonnummer für Ihre Organisation zu generieren. Dadurch wird der Vorgang zum Anfordern und Generieren einer neuen Telefonnummer gestartet. Dieser Vorgang kann bis zu 2 Minuten dauern.

    Nachdem die Telefonnummer generiert wurde, wird sie auf dem Bildschirm angezeigt. Diese Nummer wird verwendet, um SMS-Bestätigungen und Erinnerungen an Ihre Patienten zu senden. Die Zahl wurde bereitgestellt, ist aber noch nicht mit der F ZAHL-Basis-URL verknüpft. Dies ist im nächsten Schritt der Schritt.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Screenshot mit einem Beispiel für die generierte Telefonnummer" lightbox="media/ehr-admin-cerner-phone-number.png":::

    Wählen **Sie Fertig** und dann Weiter **aus**.

1. Wählen Sie zum Verknüpfen der Telefonnummer mit einer F ZAHL-Basis-URL **unter** Telefon SMS-Konfiguration  die Nummer aus. Verwenden Sie diese Option für jede F NICHT-Benachrichtigungsbasis-URL, für die Sie SMS-Benachrichtigungen aktivieren möchten.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Screenshot, der zeigt, wie eine Telefonnummer mit einer F ZAHL-Basis-URL linkiert wird." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Wenn Sie den Connector zum ersten Mal konfigurieren, wird die im früheren Schritt eingegebene F UNTR-Basis-URL angezeigt. Dieselbe Telefonnummer kann mit mehreren URLs der FSCHI-Basis verknüpft werden, was bedeutet, dass Patienten SMS-Benachrichtigungen von derselben Telefonnummer für verschiedene Organisationen und/oder Abteilungen erhalten.

     Wählen Sie **Weiter aus**.

### <a name="review-and-finish-the-configuration"></a>Überprüfen und Beenden der Konfiguration

Es werden Integrationsaufzeichnungen für patienten- und Anbieterstarts präsentiert. Diese Einträge sind erforderlich, um die Konfiguration für virtuellen Besuch in Cerner abschließen zu können. Weitere Informationen finden Sie im Cerner-Microsoft Teams zur Telehealth-Integration.

> [!NOTE]
> Ihr Microsoft 365-Administrator kann sich jederzeit beim Konfigurationsportal anmelden, um Integrationseinträge anzeigen und bei Bedarf Konfigurationseinstellungen ändern.

## <a name="launch-teams-virtual-visits"></a>Starten von virtuellen Besuchen in Teams

Nachdem Sie die Schritte für den EHR-Connector und die Cerner-Konfiguration abgeschlossen haben, kann Ihre Organisation Videobesuche mit ihrem Teams.

### <a name="virtual-visits-prerequisites"></a>Voraussetzungen für virtuelle Besuche

- Ihre Systeme müssen alle Software- [und Browseranforderungen für Teams](../../hardware-requirements-for-the-teams-app.md).
- Sie haben die Integrationseinrichtung zwischen der Cerner-Organisation und Ihrer Microsoft 365 abgeschlossen.

### <a name="provider-experience"></a>Anbietererfahrung

Dienstanbieter im Gesundheitswesen in Ihrer Organisation können virtuelle Besuche mithilfe von Teams über das PowerChart-Portal teilnehmen. Der Anbieter muss zu der Patientenakte navigieren, in der Teams Option verfügbar ist.

Von dort aus kann der Anbieter Informationen zu virtuellen Besuchen anzeigen, an virtuellen Besuchen teilnehmen und den Besprechungslink senden. Nach der einmal ausgeführten Anmeldung wird der Anbieter direkt zu dem virtuellen Termin in der Teams.

Hauptmerkmale der Anbietererfahrung:

- Anbieter können virtuelle Besuche mithilfe unterstützter Browser oder der App Teams teilnehmen.
- Anbieter können alle unterstützten Features Teams, einschließlich Bildschirmfreigabe, benutzerdefiniertem Hintergrund und Aufzeichnung.
- Anbieter können Updates von Patienten, die sich zu einem virtuellen Besuch für einen bestimmten Termin in PowerChart verbinden, in Echtzeit sehen.
- Die Anbieterinformationen sind für Patienten während des virtuellen Besuchs nicht sichtbar.

> [!NOTE]
> Alle im Besprechungschat eingegebenen Informationen, die für die Kontinuität oder Aufbewahrung von Krankenakten erforderlich sind, sollten vom Gesundheitswesen heruntergeladen, kopiert und notiert werden. Der Chat stellt weder eine juristische Kranken- noch eine festgelegte Datensatzsatz dar. Nachrichten aus dem Chat werden basierend auf den einstellungen gespeichert, die vom Administrator Microsoft Teams wurden.

### <a name="patient-experience"></a>Patientenerfahrung

Der Connector unterstützt Patienten bei der Teilnahme an virtuellen Visiten über einen Link in der SMS-Textnachricht. Zum Zeitpunkt des Termins können Patienten einen virtuellen Besuch starten, indem sie auf den Link in der SMS tippen.

Wichtige Features der Patientenerfahrung

- Patienten können an virtuellen Visiten in modernen Webbrowsern auf dem Desktop und mobilen Gerät teilnehmen, ohne die App Teams [installieren zu müssen](../mobile-browser-join.md).
- Die Patienten können mit einem einzigen Klick an virtuellen Visiten teilnehmen, und es ist kein anderes Konto oder keine Anmeldung erforderlich.
- Patienten müssen kein Microsoft-Konto erstellen oder sich anmelden, um einen virtuellen Besuch zu starten.
- Die Patienten werden in einem Wartebereich platziert, bis der Anbieter dem Termin beitritt und sie zu dem virtuellen Besuch zugibt.
- Patienten können ihr Video und Mikrofon im Wartebereich testen, bevor sie dem virtuellen Besuch beitreten.

## <a name="privacy-and-location-of-data"></a>Datenschutz und Speicherort der Daten

Teams Integration in EHR-Systeme wird die Datenmenge optimiert, die während der Integration und der virtuellen Visite verwendet und gespeichert wird. Die Lösung folgt den allgemeinen Grundsätzen und Richtlinien für den Datenschutz und das Datenmanagement von Teams, die unter Datenschutz für Teams aufgeführt sind.

Der Teams EHR-Connector enthält keine identifizierbaren persönlichen Daten oder Krankenakten von Patienten oder Gesundheitswesensanbietern vom EHR-System. Die einzigen Daten, die der EHR-Connector speichert, ist die eindeutige ID des EHR-Benutzers, die während Teams Besprechung verwendet wird.

Die eindeutige ID des EGA-Benutzers wird in einer der drei geografischen Regionen gespeichert, die unter [Wo Ihre Microsoft 365-Kundendaten gespeichert sind](/microsoft-365/enterprise/o365-data-locations) beschrieben sind. Alle Chats, Aufzeichnungen und anderen von Teams freigegebenen Daten werden gemäß den vorhandenen Speicherrichtlinien gespeichert. Weitere Informationen zum Speicherort von Daten in einer Teams Sie unter [Speicherort der Daten in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Teams EHR-Connectoradministratorberichte](ehr-admin-reports.md)
- [Erste Schritte mit Teams im Gesundheitswesen](teams-in-hc.md)
