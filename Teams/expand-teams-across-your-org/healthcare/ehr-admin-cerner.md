---
title: Virtuelle Termine mit Teams - Integration in Cerner EHR
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
description: Erfahren Sie, wie Sie den Teams EHR-Connector integrieren, damit Gesundheitsdienstleister in Ihrer Organisation virtuelle Termine mit Patienten oder anderen Anbietern in Teams direkt aus dem Cerner EHR-System durchführen können.
ms.openlocfilehash: 8caa80bca9a7b8278aff9133f81bfa807e6727ed
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853296"
---
# <a name="virtual-appointments-with-teams---integration-into-cerner-ehr"></a>Virtuelle Termine mit Teams - Integration in Cerner EHR

Der Microsoft Teams EHR-Connector (Electronic Health Record) erleichtert Es Klinikern, einen virtuellen Patiententermin zu starten oder sich direkt aus dem Cerner EHR-System mit einem anderen Anbieter in Microsoft Teams zu beraten. Basierend auf der Microsoft 365 Cloud ermöglicht Teams eine einfache, sichere Zusammenarbeit und Kommunikation mit Chat-, Video-, Sprach- und Gesundheitstools in einem einzigen Hub, der die Einhaltung von HIPAA, HITECH-Zertifizierung und mehr unterstützt.

Die Kommunikations- und Zusammenarbeitsplattform von Teams macht es Klinikern leicht, die Unordnung fragmentierter Systeme zu durchbrechen, damit sie sich auf die bestmögliche Versorgung konzentrieren können. Mit dem Teams EHR-Verbinder haben Sie folgende Möglichkeiten:

- Führen Sie Teams virtuellen Termine aus Ihrem Cerner EHR-System mit einem integrierten klinischen Workflow durch.
- Ermöglichen Sie Patienten, über E-Mail- oder SMS-Benachrichtigungen an Teams virtuellen Terminen teilzunehmen.
- Anzeigen von Verbrauchsdatenberichten und anpassbaren Informationen zur Anrufqualität für mit der EGA verbundene Termine.

In diesem Artikel wird beschrieben, wie Sie den Teams EHR-Connector für die Integration in die Cerner-Plattform einrichten und konfigurieren. Außerdem erhalten Sie einen Überblick über die Teams virtuellen Terminerfahrung aus dem Cerner EHR System.

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!NOTE]
> Stellen Sie sicher, dass Sie mit Ihrem Cerner-Vertreter sprechen und Ihren Cerner-Integrationsleitfaden überprüfen, bevor Sie die Integration aktivieren.

### <a name="prerequisites"></a>Voraussetzungen

Bevor Sie den Teams EHR-Connector in Ihre Gesundheitsorganisation integrieren, müssen Sie über Folgendes verfügen:

- Ein aktives Abonnement für Microsoft Teams eigenständigen EHR-Connector-Angebot (wird nur beim Testen in einer Produktionsumgebung erzwungen).
- Benutzer verfügen über eine entsprechende Microsoft 365- oder Office 365-Lizenz, die Teams Besprechungen umfasst.
- Teams wird in Ihrer Gesundheitsorganisation übernommen und verwendet.
- Ihre Systeme erfüllen alle [Software- und Browseranforderungen](../../hardware-requirements-for-the-teams-app.md) für Teams.
- Cerner-Version November 2018 oder höher

## <a name="set-up-the-teams-ehr-connector"></a>Einrichten des Teams EHR-Connectors

Das Konnektor-Setup erfordert Folgendes:

- [Starten des EHR-Connectorkonfigurationsportals](#launch-the-ehr-connector-configuration-portal)
- [Eingeben von Konfigurationsinformationen](#enter-configuration-information)
- [Aktivieren von SMS-Benachrichtigungen (optional)](#enable-sms-notifications-optional)
- [Überprüfen und Beenden der Konfiguration](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Diese Schritte müssen vom Microsoft 365 globalen Administrator in Ihrer Organisation ausgeführt werden.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Starten des EHR-Connectorkonfigurationsportals

Um zu beginnen, startet Ihr Microsoft 365-Administrator das [Konfigurationsportal für den EHR-Connector](https://ehrconnector.teams.microsoft.com) und meldet sich mit ihren Microsoft-Anmeldeinformationen an.

Ihr Microsoft 365-Administrator kann eine einzelne Abteilung oder mehrere Abteilungen konfigurieren, um die Integration zu testen. Konfigurieren Sie die Test- und Produktions-URL im Konfigurationsportal. Stellen Sie sicher, dass Sie die Integration aus der Cerner-Testumgebung testen, bevor Sie in die Produktion wechseln.

### <a name="enter-configuration-information"></a>Eingeben von Konfigurationsinformationen

Als Nächstes fügt Ihr Microsoft 365-Administrator zum Einrichten der Integration eine FHIR-Basis-URL (Fast Health Interoperability Resources) von Cerner hinzu und gibt die Umgebung an. Konfigurieren Sie je nach Bedarf beliebig viele FHIR-Basis-URLs, je nach den Anforderungen Ihrer Organisation und den Umgebungen, die Sie testen möchten.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Screenshot der Seite &quot;Konfigurationsinformationen&quot; im Konfigurationsportal für Teams EHR-Connector." lightbox="media/ehr-admin-cerner-configuration.png":::

- Die FHIR-Basis-URL ist eine statische Adresse, die Ihrem Server-FHIR-API-Endpunkt entspricht. Eine Beispiel-URL ist `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Sie können die Integration für Test- und Produktionsumgebungen einrichten. Für die Ersteinrichtung empfehlen wir Ihnen, den Connector aus einer Testumgebung zu konfigurieren, bevor Sie in die Produktion wechseln.

Nachdem die FHIR-Basis-URL überprüft und die Umgebung ausgewählt wurde, wählen Sie **"Fertig"** aus. Fügen Sie dann bei Bedarf weitere FHIR-Basis-URLs für andere Umgebungen hinzu.

Wählen Sie **"Weiter** " aus, um zum nächsten Schritt zu wechseln.

### <a name="enable-sms-notifications-optional"></a>Aktivieren von SMS-Benachrichtigungen (optional)

Führen Sie diesen Schritt aus, wenn Ihre Organisation möchte, dass Microsoft SMS-Benachrichtigungen für Ihre Patienten verwaltet. Wenn Sie SMS-Benachrichtigungen aktivieren, erhalten Ihre Patienten Bestätigungs- und Erinnerungsnachrichten für geplante Termine.

Um SMS-Benachrichtigungen zu aktivieren, führt Ihr Microsoft 365 Administrator Folgendes aus:

1. Aktivieren Sie auf der Seite "SMS-Benachrichtigungen" beide Zustimmungskontrollkästchen für:

    - Microsoft das Senden von SMS-Benachrichtigungen an Patienten im Auftrag Ihrer Organisation erlauben.
    - Bestätigen Sie, dass Sie sicherstellen, dass die Teilnehmer dem Senden und Empfangen von SMS-Nachrichten zugestimmt haben.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Screenshot der Seite &quot;SMS-Benachrichtigungen&quot; mit den Kontrollkästchen &quot;Zustimmung&quot; und der Option zum Generieren einer Telefonnummer." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. Wählen **Sie unter "Ihre Telefonnummern**" **die Option "Neue Telefonnummer generieren** " aus, um eine Telefonnummer für Ihre Organisation zu generieren. Auf diese Weise wird der Vorgang zum Anfordern und Generieren einer neuen Telefonnummer gestartet. Dieser Vorgang kann bis zu 2 Minuten dauern.

    Nachdem die Telefonnummer generiert wurde, wird sie auf dem Bildschirm angezeigt. Diese Nummer wird verwendet, um Ihren Patienten SMS-Bestätigungen und Erinnerungen zu senden. Die Nummer wurde bereitgestellt, ist aber noch nicht mit der FHIR-Basis-URL verknüpft. Dies tun Sie im nächsten Schritt.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Screenshot mit einem Beispiel für die generierte Telefonnummer." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Wählen Sie **"Fertig"** und dann " **Weiter**" aus.

1. Um die Telefonnummer mit einer FHIR-Basis-URL zu verknüpfen, wählen Sie unter **Telefon Nummer** im Abschnitt **sms-Konfiguration** die Nummer aus. Führen Sie dies für jede FHIR-Basis-URL aus, für die Sie SMS-Benachrichtigungen aktivieren möchten.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Screenshot, der zeigt, wie eine Telefonnummer mit einer FHIR-Basis-URL verknüpft wird." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Wenn Sie den Connector zum ersten Mal konfigurieren, wird die FHIR-Basis-URL angezeigt, die im vorherigen Schritt eingegeben wurde. Dieselbe Telefonnummer kann mit mehreren FHIR-Basis-URLs verknüpft werden, was bedeutet, dass Patienten SMS-Benachrichtigungen von derselben Telefonnummer für verschiedene Organisationen und/oder Abteilungen erhalten.

     Wählen Sie **"Weiter**" aus.

### <a name="review-and-finish-the-configuration"></a>Überprüfen und Beenden der Konfiguration

Sie erhalten Integrationsdatensätze zum Starten von Patienten und Anbietern. Diese Datensätze sind erforderlich, um die Konfiguration virtueller Termine in Cerner abzuschließen. Weitere Informationen finden Sie im Leitfaden Cerner-Microsoft Teams Telehealth Integration.

> [!NOTE]
> Ihr Microsoft 365-Administrator kann sich jederzeit beim Konfigurationsportal anmelden, um Integrationsdatensätze anzuzeigen und ggf. Konfigurationseinstellungen zu ändern.

## <a name="launch-teams-virtual-appointments"></a>Starten Teams virtueller Termine

NachDem Sie die Schritte für denEHR-Connector und die Cerner-Konfigurationsschritte abgeschlossen haben, kann Ihre Organisation Videotermine mit Teams unterstützen.

### <a name="virtual-appointments-prerequisites"></a>Voraussetzungen für virtuelle Termine

- Ihre Systeme müssen alle [Software- und Browseranforderungen](../../hardware-requirements-for-the-teams-app.md) für Teams erfüllen.
- Sie haben das Integrationssetup zwischen der Cerner-Organisation und Ihrer Microsoft 365 Organisation abgeschlossen.

### <a name="provider-experience"></a>Anbietererfahrung

Gesundheitsdienstleister in Ihrer Organisation können über Teams aus dem PowerChart-Portal an Terminen teilnehmen. Der Anbieter muss zu der Patiententafel navigieren, auf der die Teams Option verfügbar ist.

Von dort aus kann der Anbieter Termininformationen anzeigen, an Terminen teilnehmen und den Besprechungslink senden. Nach der einmaligen Anmeldung wird der Anbieter direkt zum virtuellen Termin in Teams weitergeleitet.

Hauptmerkmale der Anbietererfahrung:

- Anbieter können über unterstützte Browser oder die Teams-App an Terminen teilnehmen.
- Anbieter können alle unterstützten Teams Besprechungsfeatures verwenden, einschließlich Bildschirmfreigabe, benutzerdefinierter Hintergrund und Aufzeichnung.
- Anbieter können Echtzeitupdates von Patienten sehen, die sich mit einem Termin für einen bestimmten Termin in PowerChart verbinden.
- Anbieterinformationen sind während des Termins für Patienten nicht sichtbar.

> [!NOTE]
> Alle im Besprechungschat eingegebenen Informationen, die für die Kontinuität oder Aufbewahrung von Krankenakten erforderlich sind, sollten vom Gesundheitsdienstleister heruntergeladen, kopiert und notiert werden. Der Chat stellt keine gesetzliche Krankenakte oder einen festgelegten Datensatz dar. Nachrichten aus dem Chat werden basierend auf den Vom Microsoft Teams-Administrator erstellten Einstellungen gespeichert.

### <a name="patient-experience"></a>Patientenerfahrung

Der Connector unterstützt Patienten beim Beitreten zu Terminen über einen Link in der SMS-Sms. Zum Zeitpunkt des Termins können Patienten einen Termin beginnen, indem sie auf den Link in der SMS-Sms tippen.

Wichtige Merkmale der Patientenerfahrung

- Patienten können über [moderne Webbrowser auf desktop- und mobilen Geräten an Terminen teilnehmen, ohne die Teams-App installieren zu müssen](../browser-join.md).
- Patienten können mit einem einzigen Klick an Terminen teilnehmen, und es ist kein anderes Konto oder keine Anmeldung erforderlich.
- Patienten müssen kein Microsoft-Konto erstellen oder sich anmelden, um einen Besuch zu starten.
- Die Patienten werden in einen Wartebereich gestellt, bis der Anbieter eintritt und sie zulässt.
- Patienten können ihr Video und Mikrofon im Wartebereich testen, bevor sie dem Termin beitreten.

## <a name="get-insight-into-virtual-appointments-usage"></a>Erhalten Sie Einblicke in die Nutzung virtueller Termine

Der [Nutzungsbericht "Virtuelle Besuche"](../../teams-analytics-and-reports/virtual-visits-usage-report.md) im Microsoft Teams Admin Center bietet Administratoren einen Überblick über Teams aktivitäten virtueller Termine in Ihrer Organisation. Der Bericht zeigt detaillierte Analysen zu virtuellen Terminen, einschließlich Teams EHR-integrierten Besprechungen, die von Ihrem EHR-System durchgeführt werden.

Sie können wichtige Metriken anzeigen, z. B. Wartezeit des Wartebereichs und Termindauer. Verwenden Sie diese Informationen, um Einblicke in Nutzungstrends zu erhalten, die Ihnen helfen, virtuelle Termine zu optimieren, um bessere Geschäftsergebnisse zu erzielen.

## <a name="privacy-and-location-of-data"></a>Datenschutz und Speicherort der Daten

Teams Integration in EHR-Systeme optimiert die Datenmenge, die bei integrations- und virtuellen Terminflüssen verwendet und gespeichert wird. Die Lösung folgt den allgemeinen Grundsätzen und Richtlinien für den Datenschutz und das Datenmanagement von Teams, die unter Datenschutz für Teams aufgeführt sind.

Der Teams EHR-Connector speichert oder überträgt weder identifizierbare personenbezogene Daten noch Gesundheitsdaten von Patienten oder Gesundheitsdienstleistern aus dem EHR-System. Die einzigen Daten, die der EHR-Connector speichert, sind die eindeutige ID des EHR-Benutzers, die während Teams Besprechungseinrichtung verwendet wird.

Die eindeutige ID des EGA-Benutzers wird in einer der drei geografischen Regionen gespeichert, die unter [Wo Ihre Microsoft 365-Kundendaten gespeichert sind](/microsoft-365/enterprise/o365-data-locations) beschrieben sind. Alle Chats, Aufzeichnungen und anderen Daten, die von Besprechungsteilnehmern in Teams freigegeben werden, werden gemäß vorhandenen Speicherrichtlinien gespeichert. Weitere Informationen zum Speicherort von Daten in Teams finden Sie unter [Speicherort der Daten in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Nutzungsbericht für Teams virtuelle Besuche](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR-Connector-Administratorberichte](ehr-admin-reports.md)
- [Erste Schritte mit Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)
