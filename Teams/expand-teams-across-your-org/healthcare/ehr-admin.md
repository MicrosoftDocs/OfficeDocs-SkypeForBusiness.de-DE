---
title: Virtuelle Termine mit Teams - Integration in Epic EHR
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
description: Erfahren Sie, wie Sie den Teams EHR-Connector integrieren, damit Gesundheitsdienstleister in Ihrer Organisation virtuelle Termine mit Patienten oder anderen Anbietern in Teams direkt aus dem Epic EHR-System durchführen können.
ms.openlocfilehash: baef8aeda05413ce2f307a4bbea7259490ecfb83
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853056"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>Virtuelle Termine mit Teams - Integration in Epic EHR

Der Microsoft Teams Electronic Health Record (EHR)-Connector erleichtert Es Klinikern, einen virtuellen Patiententermin oder eine Konsultation mit einem anderen Anbieter in Microsoft Teams direkt aus dem Epic EHR-System zu starten. Basierend auf der Microsoft 365 Cloud ermöglicht Teams eine einfache, sichere Zusammenarbeit und Kommunikation mit Chat-, Video-, Sprach- und Gesundheitstools in einem einzigen Hub, der die Einhaltung von HIPAA, HITECH-Zertifizierung und mehr unterstützt.

Die Kommunikations- und Zusammenarbeitsplattform von Teams macht es Klinikern leicht, die Unordnung fragmentierter Systeme zu durchbrechen, damit sie sich auf die bestmögliche Versorgung konzentrieren können. Mit dem Teams EHR-Verbinder haben Sie folgende Möglichkeiten:

- Starten Sie Teams virtuelle Termine aus Ihrem Epic EHR-System mit einem integrierten klinischen Workflow.
- Ermöglichen Sie den Patienten, über das Patientenportal oder per SMS an Teams virtuellen Terminen teilzunehmen.
- Unterstützen Sie andere Szenarien, z. B. Mehrere Teilnehmer, Gruppenbesuche und Dolmetscherdienste.
- Schreiben Sie Metadaten zurück in das EE-System über Teams virtuellen Termine, um aufzuzeichnen, wann Teilnehmer eine Verbindung herstellen, die Verbindung trennen und die automatische Überwachung und Aufzeichnung aktivieren.
- Anzeigen von Verbrauchsdatenberichten und anpassbaren Informationen zur Anrufqualität für mit der EGA verbundene Termine.

Schauen Sie sich dieses Video an, um eine Übersicht über die Verwaltung virtueller Termine über das EA-Portal zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

In diesem Artikel wird beschrieben, wie Sie den Teams EHR-Connector für die Integration in die Epic-Plattform in Ihrer Organisation im Gesundheitswesen einrichten und konfigurieren. Außerdem erhalten Sie einen Überblick über die Teams virtuellen Terminerfahrung aus dem Epic EHR-System.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie beginnen, müssen Sie einige Dinge tun, um sich auf die Integration vorzubereiten.

### <a name="get-familiar-with-the-integration-process"></a>Machen Sie sich mit dem Integrationsprozess vertraut

Lesen Sie die folgenden Informationen, um ein Verständnis des gesamten Integrationsprozesses zu erhalten.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Abbildung, die die Schritte im gesamten Integrationsprozess zusammenfasst.":::

||||||
|---------|---------|---------|---------|---------|
|**Aktion**: Sie [fordern den Zugriff auf die Teams-App an](#request-access-to-the-teams-app). <br> **Ergebnis**: Wir autorisieren Ihre Organisation für Tests.|**Aktion**: Wir erstellen ein öffentliches und privates Schlüsselzertifikat und laden sie nach Epic hoch. <br> **Ergebnis**: Epic synchronisiert das Öffentliche Schlüsselzertifikat.|**Aktion**: Sie führen die Konfigurationsschritte im EHR-Connectorkonfigurationsportal aus. <br> **Ergebnis**: Sie erhalten FDI-Einträge für die Epic-Konfiguration.| **Aktion**: Sie arbeiten mit Ihrem technischen Experten von Epic zusammen, um FDI-Einträge in Epic zu konfigurieren.<br> **Ergebnis**: Die Konfiguration wurde abgeschlossen. Bereit zum Testen.|**Aktion**: Sie führen die Tests in Ihrer Testumgebung aus.<br> **Ergebnis**: Vollständige Überprüfung der Abläufe und Entscheidung, in die Produktion zu wechseln.|

### <a name="request-access-to-the-teams-app"></a>Anfordern des Zugriffs auf die Teams-App

Sie müssen den Zugriff auf die Teams-App anfordern.

1. Fordern Sie an, die Teams-App im [Epic App Orchard Marketplace](https://apporchard.epic.com/Gallery?id=6153) herunterzuladen. Dadurch wird eine Anforderung von Epic an das Microsoft EHR-Connectorteam ausgelöst.
1. Nachdem Sie Ihre Anfrage gestellt haben, senden Sie eine E-Mail an [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) mit dem Namen Ihrer Organisation, der Mandanten-ID und der E-Mail-Adresse Ihres technischen Epic-Kontakts.
1. Das Microsoft EHR Connector-Team antwortet auf Ihre E-Mail mit der Bestätigung der Aktivierung.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Lesen Sie den Leitfaden Epic-Microsoft Teams Telehealth Integration

Überprüfen Sie den [Epic – Microsoft Teams Telemedizin-Integrationsleitfaden](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) mit Ihrem technischen Epic-Spezialisten. Stellen Sie sicher, dass alle Voraussetzungen erfüllt sind.

## <a name="prerequisites"></a>Voraussetzungen

- Ein aktives Abonnement für Microsoft Cloud for Healthcare oder ein Abonnement Microsoft Teams eigenständigen EHR-Connectorangebots (wird nur erzwungen, wenn sie in einer Produktions-EGV-Umgebung getestet werden).
- Epische Version November 2018 oder höher.
- Benutzer verfügen über eine entsprechende Microsoft 365- oder Office 365-Lizenz, die Teams Besprechungen umfasst.
- Teams wird in Ihrer Gesundheitsorganisation übernommen und verwendet.
- Ihre Systeme erfüllen alle [Software- und Browseranforderungen](../../hardware-requirements-for-the-teams-app.md) für Teams.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie die Schritte vor der Integration ausführen und alle Voraussetzungen erfüllt sind, bevor Sie mit der Integration vorankommen.

Die Integrationsschritte werden von den folgenden Personen in Ihrer Organisation ausgeführt:

- **Microsoft 365 globaler Administrator**: Die Hauptperson, die für die Integration verantwortlich ist. Der Administrator konfiguriert den Connector, aktiviert SMS (falls erforderlich) und fügt den Epic-Kundenanalysten hinzu, der die Konfiguration genehmigt.
- **Epic-Kundenanalyst**: Eine Person in Ihrer Organisation, die Anmeldeinformationen bei Epic hat. Sie genehmigen die vom Administrator eingegebenen Konfigurationseinstellungen und stellen Epic die Konfigurationsdatensätze bereit.

Der Microsoft 365-Administrator und Epic-Kundenanalyst kann dieselbe Person sein.

## <a name="set-up-the-teams-ehr-connector"></a>Einrichten des Teams EHR-Connectors

Das Konnektor-Setup erfordert Folgendes:

- [Starten des EHR-Connectorkonfigurationsportals](#launch-the-ehr-connector-configuration-portal)
- [Eingeben von Konfigurationsinformationen](#enter-configuration-information)
- [Aktivieren von SMS-Benachrichtigungen (optional)](#enable-sms-notifications-optional)
- [Genehmigen oder Anzeigen der Konfiguration](#approve-or-view-the-configuration)
- [Überprüfen und Beenden der Konfiguration](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Starten des EHR-Connectorkonfigurationsportals

Um zu beginnen, startet Ihr Microsoft 365-Administrator das [EHR-Connectorkonfigurationsportal](https://ehrconnector.teams.microsoft.com) und meldet sich mit ihren Microsoft 365 Anmeldeinformationen an.

Ihr Microsoft 365-Administrator kann eine einzelne Organisation oder mehrere Organisationen konfigurieren, um die Integration zu testen. Konfigurieren Sie die Test- und Produktions-URL im Konfigurationsportal. Stellen Sie sicher, dass Sie die Integration aus der Epic-Testumgebung testen, bevor Sie in die Produktion wechseln.

> [!NOTE]
> Ihr Microsoft 365-Administrator und Epic-Kundenanalyst müssen die Integrationsschritte im Konfigurationsportal ausführen. Wenden Sie sich für Epic-Konfigurationsschritte an den technischen Experten von Epic, der Ihrer Organisation zugewiesen ist.

### <a name="enter-configuration-information"></a>Eingeben von Konfigurationsinformationen

Als Nächstes führt Ihr Microsoft 365 Administrator folgende Schritte aus, um die Integration einzurichten:

1. Fügt eine FHIR-Basis-URL (Fast Health Interoperability Resources) von Ihrem technischen Experten von Epic hinzu und gibt die Umgebung an. Konfigurieren Sie je nach Bedarf beliebig viele FHIR-Basis-URLs, je nach den Anforderungen Ihrer Organisation und den Umgebungen, die Sie testen möchten.

    - Die FHIR-Basis-URL ist eine statische Adresse, die Ihrem Server-FHIR-API-Endpunkt entspricht. Eine Beispiel-URL ist `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - Sie können die Integration für Test- und Produktionsumgebungen einrichten. Für die Ersteinrichtung empfehlen wir Ihnen, den Connector aus einer Testumgebung zu konfigurieren, bevor Sie in die Produktion wechseln.

1. Fügt den Benutzernamen des Epic-Kundenanalysten hinzu, der die Konfiguration in einem späteren Schritt genehmigt.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Screenshot der Seite &quot;Konfiguration&quot; mit der genehmigenden Person, die hinzugefügt wird." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Aktivieren von SMS-Benachrichtigungen (optional)

> [!NOTE]
> SMS-Benachrichtigungen sind derzeit nur im USA verfügbar. Wir arbeiten daran, dieses Feature in zukünftigen Versionen von Teams in anderen Regionen verfügbar zu machen, und werden diesen Artikel aktualisieren, sobald er verfügbar ist.

Führen Sie diesen Schritt aus, wenn Ihre Organisation möchte, dass Microsoft SMS-Benachrichtigungen für Ihre Patienten verwaltet. Wenn Sie SMS-Benachrichtigungen aktivieren, erhalten Ihre Patienten Bestätigungs- und Erinnerungsnachrichten für geplante Termine.

Um SMS-Benachrichtigungen zu aktivieren, führt Ihr Microsoft 365 Administrator Folgendes aus:

1. Aktivieren Sie auf der Seite "SMS-Benachrichtigungen" beide Zustimmungskontrollkästchen für:

    - Microsoft das Senden von SMS-Benachrichtigungen an Patienten im Auftrag Ihrer Organisation erlauben.
    - Bestätigen Sie, dass Sie sicherstellen, dass die Teilnehmer dem Senden und Empfangen von SMS-Nachrichten zugestimmt haben.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Screenshot der Seite &quot;SMS-Benachrichtigungen&quot; mit den Kontrollkästchen &quot;Zustimmung&quot; und der Option zum Generieren einer Telefonnummer." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. Wählen **Sie unter "Ihre Telefonnummern**" **die Option "Neue Telefonnummer generieren** " aus, um eine Telefonnummer für Ihre Organisation zu generieren. Auf diese Weise wird der Vorgang zum Anfordern und Generieren einer neuen Telefonnummer gestartet. Dieser Vorgang kann bis zu 2 Minuten dauern.

    Nachdem die Telefonnummer generiert wurde, wird sie auf dem Bildschirm angezeigt. Diese Nummer wird verwendet, um Ihren Patienten SMS-Bestätigungen und Erinnerungen zu senden. Die Nummer wurde bereitgestellt, ist aber noch nicht mit der FHIR-Basis-URL verknüpft. Dies tun Sie im nächsten Schritt.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Screenshot mit einem Beispiel für die generierte Telefonnummer." lightbox="media/ehr-connector-epic-phone-number.png":::

    Wählen Sie **"Fertig"** und dann " **Weiter**" aus.

1. Um die Telefonnummer mit einer FHIR-Basis-URL zu verknüpfen, wählen Sie unter **Telefon Nummer** im Abschnitt **sms-Konfiguration** die Nummer aus. Führen Sie dies für jede FHIR-Basis-URL aus, für die Sie SMS-Benachrichtigungen aktivieren möchten.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Screenshot, der zeigt, wie eine Telefonnummer mit einer FHIR-Basis-URL verknüpft wird." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Wenn Sie den Connector zum ersten Mal konfigurieren, wird die FHIR-Basis-URL angezeigt, die im vorherigen Schritt eingegeben wurde. Dieselbe Telefonnummer kann mit mehreren FHIR-Basis-URLs verknüpft werden, was bedeutet, dass Patienten SMS-Benachrichtigungen von derselben Telefonnummer für verschiedene Organisationen und/oder Abteilungen erhalten.

1. Wählen Sie neben jeder FHIR-Basis-URL die **SMS-Einrichtung** aus, um die Arten von SMS-Benachrichtigungen einzurichten, die an Ihre Patienten gesendet werden sollen.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Screenshot der SMS-Setupeinstellungen." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **Bestätigungs-SMS**: Benachrichtigungen werden an Patienten gesendet, wenn ein Termin imEHR-System geplant, aktualisiert oder abgebrochen wird.
    - **Erinnerungs-SMS**: Benachrichtigungen werden gemäß dem von Ihnen angegebenen Zeitintervall und der geplanten Zeit des Termins an die Patienten gesendet.

    Klicken Sie auf **Speichern**.

1. Wählen Sie **Hochladen Zertifikat** aus, um ein Öffentliches Schlüsselzertifikat hochzuladen. Sie müssen ein Base64-codiertes CER-Zertifikat (nur öffentlicher Schlüssel) für jede Umgebung hochladen.

    Zum Empfangen von Termininformationen zum Senden von SMS-Benachrichtigungen ist ein Öffentliches Schlüsselzertifikat erforderlich. Das Zertifikat ist erforderlich, um zu überprüfen, ob die eingehenden Informationen von einer gültigen Quelle stammen.

    Wenn der Connector zum Senden von SMS-Erinnerungen verwendet wird, wird die Telefonnummer des Patienten von Epic in einer HL7v2-Nutzlast gesendet, wenn Termine in Epic erstellt werden. Diese Nummern werden für jeden Termin in der Geografie Ihrer Organisation gespeichert und bis zum Termin aufbewahrt. Weitere Informationen zum Konfigurieren von HL7v2-Nachrichten finden Sie im [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    Wählen Sie **"Weiter**" aus.

> [!NOTE]
> Ihr Microsoft 365-Administrator kann jederzeit alle SMS-Einstellungen aktualisieren. Beachten Sie, dass das Ändern von Einstellungen zu einer Unterbrechung des SMS-Diensts führen kann. Weitere Informationen zum Anzeigen von SMS-Berichten finden Sie [unter Teams EHR-Connector-Administratorberichten](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Genehmigen oder Anzeigen der Konfiguration

Der Epic-Kundenanalyst in Ihrer Organisation, der als Genehmiger hinzugefügt wurde, startet das [Konfigurationsportal für den EHR-Connector](https://ehrconnector.teams.microsoft.com) und meldet sich mit ihren Microsoft 365 Anmeldeinformationen an. Nach erfolgreicher Überprüfung wird die genehmigende Person aufgefordert, sich mit ihren Epic-Anmeldeinformationen anzumelden, um die Epic-Organisation zu validieren.

> [!Note]
> Wenn der Microsoft 365-Administrator und der Epic-Kundenanalyst dieselbe Person sind, müssen Sie sich dennoch bei Epic anmelden, um Ihren Zugriff zu überprüfen. Die Epic-Anmeldung wird nur verwendet, um Ihre FHIR-Basis-URL zu überprüfen. Microsoft speichert mit dieser Anmeldung keine Anmeldeinformationen und greift nicht auf EE-Daten zu.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Screenshot der Seite &quot;Konfiguration genehmigen&quot; oder &quot;Konfiguration anzeigen&quot; mit der Option &quot;Anmelden und genehmigen&quot;." lightbox="media/ehr-connector-epic-login-approve.png":::

Nach erfolgreicher Anmeldung bei Epic **muss** der Epic-Kundenanalyst die Konfiguration genehmigen. Wenn die Konfiguration nicht korrekt ist, kann sich Ihr Microsoft 365 Administrator beim Konfigurationsportal anmelden und die Einstellungen ändern.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Screenshot der Seite &quot;Konfiguration genehmigen&quot; oder &quot;Konfiguration anzeigen&quot; mit der Option &quot;Genehmigen&quot;." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Überprüfen und Beenden der Konfiguration

Wenn die Konfigurationsinformationen vom Epic-Administrator genehmigt wurden, werden Ihnen Integrationsdatensätze für den Start von Patienten und Anbietern angezeigt. Zu den Integrationsdatensätzen gehören:

- Patienten- und Anbieterdatensätze
- Direct SMS-Eintrag
- SMS-Konfigurationsdatensatz
- Konfigurationsdatensatz für Gerätetests

Der Epic-Kundenanalyst muss Epic diese Datensätze zur Verfügung stellen, um die Konfiguration virtueller Termine in Epic abzuschließen. Weitere Informationen finden Sie im [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> Der Microsoft 365- oder Epic-Kundenanalyst kann sich jederzeit beim Konfigurationsportal anmelden, um Integrationsdatensätze anzuzeigen und die Konfiguration der Organisation nach Bedarf zu ändern.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Screenshot der Seite &quot;Überprüfen und Fertig stellen&quot; mit Integrationsinformationen." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> Der Epic-Kundenanalyst muss den Genehmigungsprozess für jede FHIR-Basis-URL abschließen, die vom Microsoft 365-Administrator konfiguriert wird.

## <a name="launch-teams-virtual-appointments"></a>Starten Teams virtueller Termine

Nach Abschluss der Schritte für denEHR-Connector und der Epic-Konfiguration kann Ihre Organisation Videotermine mit Teams unterstützen.

### <a name="virtual-appointments-prerequisites"></a>Voraussetzungen für virtuelle Termine

- Ihre Systeme müssen alle [Software- und Browseranforderungen](../../hardware-requirements-for-the-teams-app.md) für Teams erfüllen.

- Sie haben das Integrationssetup zwischen der Epic-Organisation und Ihrer Microsoft 365 Organisation abgeschlossen.

### <a name="provider-experience"></a>Anbietererfahrung

Gesundheitsdienstleister aus Ihrer Organisation können über Teams ihrer Epic-Anbieter-Apps (Hyperspace, Haiku, Canto) an Terminen teilnehmen. Die Schaltfläche **Virtuellen Besuch beginnen** ist in den Fluss des Providers eingebettet.

Hauptmerkmale der Anbietererfahrung:

- Anbieter können über unterstützte Browser oder die Teams-App an Terminen teilnehmen.

- Anbieter müssen eine einmalige Anmeldung mit ihrem Microsoft 365 Konto durchführen, wenn sie zum ersten Mal an einem Termin teilnehmen.

- Nach der einmaligen Anmeldung wird der Anbieter direkt zum virtuellen Termin in Teams weitergeleitet. (Der Anbieter muss bei Teams angemeldet sein.

- Anbieter können Echtzeitupdates von Teilnehmern sehen, die für einen bestimmten Termin eine Verbindung herstellen und die Verbindung trennen. Anbieter können sehen, wann der Patient mit einem Termin verbunden ist.

  ![Anbietererfahrung eines Termins mit einem Patienten.](media/ehc-provider-experience-6.png)

> [!NOTE]
> Alle im Besprechungschat eingegebenen Informationen, die für die Kontinuität oder Aufbewahrung von Krankenakten erforderlich sind, sollten vom Gesundheitsdienstleister heruntergeladen, kopiert und notiert werden. Der Chat stellt keine gesetzliche Krankenakte oder einen festgelegten Datensatz dar. Nachrichten aus dem Chat werden basierend auf den Vom Microsoft Teams-Administrator erstellten Einstellungen gespeichert.

### <a name="patient-experience"></a>Patientenerfahrung

Der Connector unterstützt Patienten beim Teilnehmen an Terminen über MyChart Web und Mobile. Zum Zeitpunkt des Termins können Patienten über die Schaltfläche **"Virtuellen Besuch beginnen** " einen Termin aus MyChart starten.

Hauptmerkmale der Patientenerfahrung:

- Patienten können über [moderne Webbrowser auf desktop- und mobilen Geräten an Terminen teilnehmen, ohne die Teams-App installieren zu müssen](../browser-join.md).

- Patienten können mit einem einzigen Klick an Terminen teilnehmen, und es ist kein anderes Konto oder keine Anmeldung erforderlich.

- Patienten müssen kein Microsoft-Konto erstellen oder sich anmelden, um einen Termin zu starten.

- Die Patienten werden in einen Wartebereich gestellt, bis der Anbieter eintritt und sie zulässt.

- Patienten können ihr Video und Mikrofon im Wartebereich testen, bevor sie am Termin teilnehmen.

  ![Patientenerfahrung des Termins.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku und Canto sind Marken der Epic Systems Corporation.

## <a name="get-insight-into-virtual-appointments-usage"></a>Erhalten Sie Einblicke in die Nutzung virtueller Termine

Der [Nutzungsbericht "Virtuelle Besuche"](../../teams-analytics-and-reports/virtual-visits-usage-report.md) im Microsoft Teams Admin Center bietet Administratoren einen Überblick über Teams aktivitäten virtueller Termine in Ihrer Organisation. Der Bericht zeigt detaillierte Analysen zu virtuellen Terminen, einschließlich Teams EHR-integrierten Besprechungen, die von Ihrem EHR-System durchgeführt werden.

Sie können wichtige Metriken anzeigen, z. B. Wartezeit des Wartebereichs und Termindauer. Verwenden Sie diese Informationen, um Einblicke in Nutzungstrends zu erhalten, die Ihnen helfen, virtuelle Termine zu optimieren, um bessere Geschäftsergebnisse zu erzielen.

### <a name="privacy-and-location-of-data"></a>Datenschutz und Speicherort der Daten

Teams Integration in EHR-Systeme optimiert die Datenmenge, die bei integrations- und virtuellen Terminflüssen verwendet und gespeichert wird. Die Lösung folgt den allgemeinen Grundsätzen und Richtlinien für den Datenschutz und das Datenmanagement von Teams, die unter Datenschutz für Teams aufgeführt sind.

Der Teams EHR-Connector speichert oder überträgt weder identifizierbare personenbezogene Daten noch Gesundheitsdaten von Patienten oder Gesundheitsdienstleistern aus dem EHR-System. Die einzigen Daten, die vom EGA-Konnektor gespeichert werden, sind die eindeutigen IDs des EGA-Benutzers, die beim Einrichten der Teambesprechungen verwendet werden.

Die eindeutige ID des EGA-Benutzers wird in einer der drei geografischen Regionen gespeichert, die unter [Wo Ihre Microsoft 365-Kundendaten gespeichert sind](/microsoft-365/enterprise/o365-data-locations) beschrieben sind. Alle Chats, Aufzeichnungen und anderen Daten, die von Besprechungsteilnehmern in Teams freigegeben werden, werden gemäß vorhandenen Speicherrichtlinien gespeichert. Weitere Informationen zum Speicherort von Daten in Teams finden Sie unter [Speicherort der Daten in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Nutzungsbericht für Teams virtuelle Besuche](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR-Connector-Administratorberichte](ehr-admin-reports.md)
- [Erste Schritte mit Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)
