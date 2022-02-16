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
description: Erfahren Sie, wie Sie den Connector Teams EHR integrieren, um es Anbietern im Gesundheitswesen in Ihrer Organisation zu ermöglichen, virtuelle Visiten mit Patienten oder anderen Anbietern in Teams direkt vom Cerner EHR-System aus durchführen zu lassen.
ms.openlocfilehash: e7d104e4541462c94ddb95805ae7ec2a8619bf5b
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2022
ms.locfileid: "62763699"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Virtuelle Besuche mit Teams - Integration in Cerner EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Der Microsoft Teams Connector für elektronische Krankenakten (EHR) erleichtert Klinikbetreibern das Starten eines virtuellen Patientenbesuchs oder das Konsultieren eines anderen Anbieters in Microsoft Teams direkt vom Cerner EHR-System. Das auf der Microsoft 365-Cloud Teams-Programm ermöglicht einfache, sichere Zusammenarbeit und Kommunikation mit Chat-, Video-, Sprach- und Gesundheitstools in einem einzigen Hub, der die Einhaltung von HIPAA, HITECH-Zertifizierung und mehr unterstützt.

Die Kommunikations- und Zusammenarbeitsplattform von Teams macht es klinikieren, die Unübersichtlichkeit fragmentierter Systeme zu durchschneiden, sodass sie sich auf die Bereitstellung der bestmöglichen Behandlung konzentrieren können. Mit dem Teams EHR-Verbinder können Sie:

- Durchführen Teams Besuche von Ihrem Cerner EHR-System mit einem integrierten klinischen Workflow.
- Ermöglichen Sie Patienten die Teilnahme an virtuellen Teams-Mails oder SMS-Benachrichtigungen.
- Zeigen Sie Verbrauchsdatenberichte und anpassbare Informationen zur Anrufqualität für mit EHR verbundene Besuche an.

In diesem Artikel wird beschrieben, wie Sie den EHR Teams Connector für die Integration in die Cerner-Plattform einrichten und konfigurieren. Außerdem erhalten Sie einen Überblick über die Erfahrung Teams virtuellen Besuche vom Cerner EHR-System.

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!NOTE]
> Sprechen Sie mit Ihrem Cerner-Vertreter, und lesen Sie ihren Cerner-Integrationsleitfaden, bevor Sie die Integration aktivieren.

### <a name="prerequisites"></a>Voraussetzungen

Bevor Sie den Teams EHR-Connector in Ihrer Organisation im Gesundheitswesen integrieren können, müssen Sie über Folgendes verfügen:

- Ein aktives Abonnement für Microsoft Teams EHR-Connector (wird nur beim Testen in einer EHR-Produktionsumgebung erzwungen).
- Benutzer verfügen über eine geeignete Microsoft 365 oder Office 365 Lizenz, die Teams umfasst.
- Teams in Ihrer Gesundheitsorganisation verbreitet und verwendet.
- Ihre Systeme erfüllen alle [Software- und Browseranforderungen für](../../hardware-requirements-for-the-teams-app.md) Teams.
- Cerner-Version November 2018 oder höher

## <a name="set-up-the-teams-ehr-connector"></a>Einrichten des EHR Teams Verbinders

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

Als Nächstes fügt Ihr Microsoft 365-Administrator eine Fast Health Interoperability Resources (FBRO)-Basis-URL von Cerner hinzu und gibt die Umgebung an. Konfigurieren Sie je nach Anforderungen Ihrer Organisation und den umgebungen, die Sie testen möchten, so viele F URL-Basis-URLs wie erforderlich.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Screenshot der Seite "Konfigurationsinformationen" im Teams EHR-Connectorkonfigurationsportals." lightbox="media/ehr-admin-cerner-configuration.png":::

- Die F ZAHL-Basis-URL ist eine statische Adresse, die Ihrem Server-FSTAT-API-Endpunkt entspricht. Eine Beispiel-URL ist `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Sie können die Integration für Test- und Produktionsumgebungen einrichten. Für die Ersteinrichtung sollten Sie den Connector in einer Testumgebung konfigurieren, bevor Sie in die Produktion um einstiegen.

Nachdem die F IMMER-Basis-URL überprüft und die Umgebung ausgewählt wurde, wählen Sie **Fertig aus**. Fügen Sie anschließend nach Bedarf weitere FGRA-Basis-URLs für andere Umgebungen hinzu.

Wählen **Sie Weiter** aus, um zum nächsten Schritt zu wechseln.

### <a name="enable-sms-notifications-optional"></a>Aktivieren von SMS-Benachrichtigungen (optional)

Führen Sie diesen Schritt aus, wenn Ihre Organisation möchte, dass Microsoft SMS-Benachrichtigungen für Ihre Patienten verwaltet. Wenn Sie SMS-Benachrichtigungen aktivieren, erhalten Ihre Patienten Bestätigungs- und Erinnerungsmeldungen für geplante Besuche.

Zum Aktivieren von SMS-Benachrichtigungen geht Microsoft 365 Administrator wie folgt vor:

1. Aktivieren Sie auf der Seite SMS-Benachrichtigungen die beiden Kontrollkästchen für die Zustimmung für:

    - Erlauben Sie Microsoft, SMS-Benachrichtigungen an Patienten im Namen Ihrer Organisation zu senden.
    - Bestätigen Sie, dass Sie sicherstellen, dass die Teilnehmer dem Senden und Empfangen von SMS-Nachrichten zugestimmt haben.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Screenshot der Seite "SMS-Benachrichtigungen" mit Kontrollkästchen für die Zustimmung und der Option zum Generieren einer Telefonnummer" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. Wählen **Sie unter Ihre Telefonnummern** die Option **Neue Telefonnummer generieren** aus, um eine Telefonnummer für Ihre Organisation zu generieren. Dadurch wird der Vorgang zum Anfordern und Generieren einer neuen Telefonnummer gestartet. Dieser Vorgang kann bis zu 2 Minuten dauern.

    Nachdem die Telefonnummer generiert wurde, wird sie auf dem Bildschirm angezeigt. Diese Nummer wird verwendet, um SMS-Bestätigungen und Erinnerungen an Ihre Patienten zu senden. Die Zahl wurde bereitgestellt, ist aber noch nicht mit der F ZAHL-Basis-URL verknüpft. Dies ist im nächsten Schritt der Schritt.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Screenshot mit einem Beispiel für die generierte Telefonnummer" lightbox="media/ehr-admin-cerner-phone-number.png":::

    Wählen **Sie Fertig** und dann Weiter **aus**.

1. Zum Verknüpfen der Telefonnummer mit einer F ZAHL-Basis-URL wählen Sie **unter** Telefon SMS-Konfiguration  die Nummer aus. Verwenden Sie diese Option für jede F NICHT-Benachrichtigungsbasis-URL, für die Sie SMS-Benachrichtigungen aktivieren möchten.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Screenshot, der zeigt, wie eine Telefonnummer mit einer F ZAHL-Basis-URL linkiert wird." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Wenn Sie den Connector zum ersten Mal konfigurieren, wird die im früheren Schritt eingegebene F UNTR-Basis-URL angezeigt. Dieselbe Telefonnummer kann mit mehreren URLs der FSCHI-Basis verknüpft werden, was bedeutet, dass Patienten SMS-Benachrichtigungen von derselben Telefonnummer für verschiedene Organisationen und/oder Abteilungen erhalten.

     Wählen Sie **Weiter aus**.

### <a name="review-and-finish-the-configuration"></a>Überprüfen und Beenden der Konfiguration

Es werden Integrationsaufzeichnungen für patienten- und Anbieterstarts präsentiert. Diese Einträge sind erforderlich, um die Konfiguration virtueller Besuche in Cerner abschließen zu können. Weitere Informationen finden Sie im Cerner-Microsoft Teams zur Telehealth-Integration.

> [!NOTE]
> Ihr Microsoft 365-Administrator kann sich jederzeit beim Konfigurationsportal anmelden, um Integrationseinträge anzeigen und bei Bedarf Konfigurationseinstellungen ändern.

## <a name="launch-teams-virtual-visits"></a>Starten Teams virtueller Besuche

Nachdem Sie die Schritte für den EHR-Connector und die Cerner-Konfiguration abgeschlossen haben, ist Ihre Organisation bereit, Videobesuche mit ihrem Teams.

### <a name="virtual-visits-prerequisites"></a>Voraussetzungen für virtuelle Besuche

- Ihre Systeme müssen alle Software- [und Browseranforderungen für Teams](../../hardware-requirements-for-the-teams-app.md).
- Sie haben die Integrationseinrichtung zwischen der Cerner-Organisation und Ihrer Microsoft 365 abgeschlossen.

### <a name="provider-experience"></a>Anbietererfahrung

Dienstanbieter im Gesundheitswesen in Ihrer Organisation können mithilfe von Teams über das PowerChart-Portal an Besuchen teilnehmen. Der Anbieter muss zu der Patientenakte navigieren, in der Teams Option verfügbar ist.

Von dort aus kann der Anbieter Informationen zu besuchen, an Besuchen teilnehmen und den Besprechungslink senden. Nach der einmal ausgeführten Anmeldung wird der Anbieter direkt zu dem virtuellen Termin in der Teams.

Hauptmerkmale der Anbietererfahrung:

- Anbieter können mit unterstützten Browsern oder der App für Teams teilnehmen.
- Anbieter können alle unterstützten Features Teams, einschließlich Bildschirmfreigabe, benutzerdefiniertem Hintergrund und Aufzeichnung.
- Anbieter können Updates von Patienten, die zu einem Besuch für einen bestimmten Termin kommen, in PowerChart in Echtzeit sehen.
- Die Anbieterinformationen sind für Patienten während des Besuchs nicht sichtbar.

> [!NOTE]
> Alle im Besprechungschat eingegebenen Informationen, die für die Kontinuität oder Aufbewahrung von Krankenakten erforderlich sind, sollten vom Gesundheitswesen heruntergeladen, kopiert und notiert werden. Der Chat stellt weder eine juristische Kranken- noch eine festgelegte Datensatzsatz dar. Nachrichten aus dem Chat werden basierend auf den einstellungen gespeichert, die vom Administrator Microsoft Teams wurden.

### <a name="patient-experience"></a>Patientenerfahrung

Der Connector unterstützt Patienten, die Visiten über einen Link in der SMS-Textnachricht beitreten. Zum Zeitpunkt des Termins können Patienten einen Besuch starten, indem sie auf den Link in der SMS tippen.

Wichtige Features der Patientenerfahrung

- Patienten können über moderne Webbrowser auf dem Desktop und mobilen Gerät an Besuchen teilnehmen, ohne [die App Teams installieren zu müssen](../mobile-browser-join.md).
- Patienten können mit einem einzigen Klick an Visiten teilnehmen, und es ist kein anderes Konto oder keine Anmeldung erforderlich.
- Die Patienten müssen kein Microsoft-Konto erstellen oder sich anmelden, um einen Besuch zu starten.
- Die Patienten werden in einem Wartebereich platziert, bis der Anbieter ihnen beitritt und sie zugibt.
- Patienten können ihr Video und Mikrofon im Wartebereich testen, bevor sie dem Besuch beitreten.

## <a name="privacy-and-location-of-data"></a>Datenschutz und Speicherort der Daten

Teams Integration in EHR-Systeme optimiert die Datenmenge, die während der Integration und der Flüsse für virtuelle Besuche verwendet und gespeichert wird. Die Lösung folgt den allgemeinen Grundsätzen und Richtlinien für den Datenschutz und das Datenmanagement von Teams, die unter Datenschutz für Teams aufgeführt sind.

Der Teams EHR-Connector enthält keine identifizierbaren persönlichen Daten oder Krankenakten von Patienten oder Gesundheitswesensanbietern vom EHR-System. Die einzigen Daten, die der EHR-Connector speichert, ist die eindeutige ID des EHR-Benutzers, die während Teams Besprechung verwendet wird.

Die eindeutige ID des EGA-Benutzers wird in einer der drei geografischen Regionen gespeichert, die unter [Wo Ihre Microsoft 365-Kundendaten gespeichert sind](/microsoft-365/enterprise/o365-data-locations) beschrieben sind. Alle Chats, Aufzeichnungen und anderen Daten, die von Teams Besprechungsteilnehmern freigegeben werden, werden gemäß den vorhandenen Speicherrichtlinien gespeichert. Weitere Informationen zum Speicherort von Daten in Teams finden Sie unter Speicherort [von Daten in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Teams EHR-Connectoradministratorberichte](ehr-admin-reports.md)
- [Erste Schritte mit Teams im Gesundheitswesen](teams-in-hc.md)
