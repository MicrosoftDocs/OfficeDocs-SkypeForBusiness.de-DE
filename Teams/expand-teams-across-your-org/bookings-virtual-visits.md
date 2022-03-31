---
title: Virtuelle Besuche mit Microsoft Teams und der Bookings-App
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Erfahren Sie, wie Sie virtuelle Besuche planen, verwalten und durchführen, indem Sie die Bookings-App in Teams.
ms.openlocfilehash: 0db414765a649192d96122ac69764fa279a8dac5
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556536"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Virtuelle Untersuchung mit Microsoft Teams und der Bookings-App

## <a name="overview"></a>Übersicht

Mit [Bookings-App](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) in Microsoft Teams können Organisationen virtuelle Termine für Mitarbeiter und Teilnehmer auf einfache Weise planen und verwalten. Verwenden Sie es zum Planen von Terminen wie Arztbesuchen, Finanzberatungen, Vorstellungsgesprächen, Kundensupport, virtuellen Ein treffen und Beratungsgesprächen, Sprechstunden für Bildungseinrichtungen und vieles mehr.

Die Bookings erleichtert die Verwaltung komplexer Planungsanforderungen einer Organisation. Die planenden Personen können mehrere Abteilungs- und Mitarbeiterkalender sowie die Kommunikation mit internen und externen Teilnehmern über eine einzige Lösung verwalten.

Die virtuellen Termine werden in Microsoft Teams stattfinden, die stabile Videokonferenzfunktionen bieten. Ein Arzt kann z. B. seinen Bildschirm freigeben und die Testergebnisse mit einem Patienten überprüfen. Oder ein Bankberater kann elektronische Signaturen für Dokumente anfordern, sodass er Transaktionen remote schließen kann.

Jeder virtuelle Termin enthält einen Link Teams Besprechung, der per E-Mail an die Teilnehmer gesendet wird. Dort können sie ganz einfach über einen Webbrowser oder über Teams beliebigen Gerät teilnehmen. Mithilfe automatisierter E-Mail-Erinnerungen können Sie die Anzahl nicht angezeigter E-Mails reduzieren und das Engagement von Kunden und Kunden verbessern.

Mit Bookings erhalten Sie eine Erfahrung, die auf Ihre Branche zugeschnitten ist. Im Folgenden finden Sie einige Beispiele für die Verwendung in Ihrer Organisation:

|Branche | Beispiele |
|---------|---------|
|Finanzdienstleistungen    |  Virtuelle Besuche für Remoteverkäufe und -dienste<br/>Planen und verwalten Sie Termine für Manager von Bankbeziehungen, Finanzberater und Ansprüche anpassende Mitarbeiter (um nur einige zu nennen), um Ihre Kunden mit gesteigerter Effizienz und Benutzerfreundlichkeit zu bedienen.  |
|Einzelhandel   | Virtuelle Anproben und Beratungsgespräche <br/>Planen und verwalten Sie Termine für Ihre Vertriebsmitarbeiter, Produktexperten und Designberater, um virtuelle Einpassungen und Beratungsgespräche mit Kunden zu führen.   |
|Gesundheitswesen   |  Virtuelle Visite für die Patientenpflege <br/>Planen und verwalten Sie Termine für die Mitglieder Ihres Pflegeteams, die sich mit Patienten oder anderen Gesundheitswesensanbietern treffen, um die medizinische Behandlung zu besprechen.   |

Dieser Artikel bietet Ihnen einen Überblick über das Planen, Verwalten und Durchführen virtueller Besuche mithilfe der Bookings-App in Teams.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

Wenn Sie ein Administrator sind, finden Sie unter Verwalten der [Bookings-App in Teams](../bookings-app-admin.md) Informationen zu den Voraussetzungen für die Verwendung der Bookings-App in Teams, zum Steuern des Zugriffs auf Bookings in Ihrer Organisation und zu empfohlenen Richtlinien- und Administratoreinstellungen.

Denken Sie daran, dass nur Planer in Ihrer Organisation die App Bookings installiert Teams. Mitarbeiter, die virtuelle Termine durchführen oder daran teilnehmen, benötigen die App nicht. Sie nehmen an Terminen über ihr Teams Kalender Outlook, oder sie verwenden den Besprechungslink in ihrer Buchungsbestätigungs-E-Mail.

## <a name="set-up-a-new-booking-calendar"></a>Einrichten eines neuen Buchungskalenders

### <a name="create-the-booking-calendar"></a>Erstellen des Buchungskalenders

Wechseln Teams Der Benutzer **zu Bookings** >  **Erste Schritte**, und wählen Sie dann **Neuer Buchungskalender aus**. Füllen Sie das Formular aus, und wählen Sie den relevanten Unternehmenstyp für Ihre Organisation aus.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Screenshot des Bildschirms "Neuer Buchungskalender" mit Geschäftstypen":::

Wenn Sie eine größere Organisation sind, sollten Sie erwägen, mehrere Buchungskalender zu erstellen, wenn Sie möchten, dass Teilnehmer eine Buchungs-E-Mail von einer bestimmten Abteilung statt von Ihrer gesamten Organisation erhalten.
Weitere Informationen finden Sie unter [Erstellen Bookings Kalenders](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Wenn Sie nicht zum ersten Mal in der Bookings-App arbeiten oder in einem vorhandenen Buchungskalender arbeiten möchten, wählen Sie in Bookings den Dropdownpfeil neben dem Namen Ihrer Organisation und dann Vorhandener Buchungskalender **aus.** Von hier aus können Sie nach dem gesuchten Suchen suchen.

### <a name="add-staff"></a>Mitarbeiter hinzufügen

Wechseln Sie im Buchungskalender zu Weitere **Optionen** (...) > **Einstellungen**, und wählen Sie dann Mitarbeiter **aus**. Fügen Sie Mitarbeiter hinzu, und weisen Sie jeder Person, die Sie hinzufügen, eine Rolle zu. Sie können bis zu 100 Mitarbeiter zu einem Buchungskalender hinzufügen.

Die Bookings-App ist in Outlook. Nachdem Sie Mitarbeiter hinzugefügt haben, können Sie die Verfügbarkeit des Kalenders dieser Person anzeigen und Buchungen für diese Person planen. Weitere Informationen finden Sie unter [Hinzufügen von Mitarbeitern und Anzeigen Bookings Kalenders](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Erstellen von Termintypen

Erstellen Sie bestimmte Termintypen, um die von Ihrer Organisation angebotenen Dienste zu repräsentieren und die Buchungserfahrung zu verbessern. Planer können dann mithilfe des Termintyps einen Besuch planen.

Wechseln Sie im Buchungskalender zu Weitere **Optionen (...) >** **Einstellungen**, wählen Sie Termintypen **und dann** **Termintyp hinzufügen aus**. Geben Sie einen Namen&mdash; ein, z. B. Konto öffnen, Verlängerung durch Verlängerung durch Verlängerung von Abonnements, Kreditberatung,&mdash; Steuervorbereitung und alle anderen Informationen und Einstellungen, die Sie wünschen.

Die von Ihnen hinzugefügten Informationen sind in der E-Mail-Bestätigung enthalten, die bei jeder Buchung dieses Termintyps an die Teilnehmer gesendet wird. Sie können E-Mail-Erinnerungen und andere Optionen festlegen, z. B. ob Teilnehmer über einen [mobilen](mobile-browser-join.md) Browser teilnehmen können, ohne die Besprechung herunterladen Teams.

Wenn Sie ein Bookings sind, können Sie bis zu vier Formulare verknüpfen, die die Teilnehmer jedes Mal ausfüllen können, wenn dieser Termintyp gebucht wird. Sie können z. B. fordern, dass Teilnehmer ein Registrierungsformular ausfüllen, bevor sie einem Besuch beitreten. Wenn Sie ein Formular verknüpfen möchten, wählen Sie **Formular verknüpfen aus**. Geben Sie die URL des Formulars ein, und wählen Sie dann **Link aus**. (Wenn Sie ein Formular zum ersten Mal verknüpfen, werden Sie aufgefordert, eine Gruppe Microsoft 365 zu erstellen, in der Formulare gespeichert werden. Wählen Sie **Gruppe erstellen aus** , um die Gruppe zu erstellen. Dieser Müssen Sie nur einmal für den Buchungskalender tun.)

Beachten Sie beim Arbeiten mit Formularen:

- Um Änderungen an einem Formular vorzunehmen, das bereits mit einem Termintyp verknüpft ist, wählen Sie das Formular im Termintyp oder innerhalb der Gruppe Microsoft 365 bei aus[https://forms.office.com](https://forms.office.com).
- Das Hochladen von Dateien in Formulare, die [](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) eine Frage zum Hochladen von Dateien enthalten, wird unterstützt, wenn alle Teilnehmer aus derselben Organisation kommen.

Wenn ein Planer den Termintyp verwendet, um einen Besuch zu planen, kann er auswählen, ob er das Formular einbeingt, es entfernt oder alle anderen Formulare hinzugefügt hat, die Sie mit dem Termintyp verknüpft haben. Teilnehmer müssen das Formular ausfüllen, bevor sie dem Besuch beitreten können.

Weitere Informationen finden Sie unter [Erstellen eines Termintyps](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-visit"></a>Planen eines Besuchs

Wählen Sie im Buchungskalender Neue **Buchung aus**. Wählen Sie einen Termintyp aus, und geben Sie dann die relevanten Informationen ein.

Dies umfasst die Kontaktinformationen der Teilnehmer, den Mitarbeiter, der den Dienst bereitstellen soll, interne Notizen, die nur die Mitarbeiter sehen können, E-Mail-Erinnerungen und die Angabe, ob der Teilnehmer über einen mobilen Browser teilnehmen kann. Wenn ein Formular mit dem Termintyp verknüpft ist, können Sie es hinzufügen, entfernen oder andere verknüpfte Formulare hinzufügen.

Die an den Teilnehmer gesendete E-Mail-Bestätigung enthält den Besprechungslink und eine Anlage, damit er den virtuellen Termin zu seinen Kalendern hinzufügen kann. Die Mitarbeiter erhalten außerdem eine E-Mail-Bestätigung und Besprechungs-Einladung. Wenn ein Formular in den Termin einbezogen wurde, können Bookings-Administratoren und Planer sehen, ob das Formular vom Teilnehmer vor dem Besuch ausgefüllt wurde, und die Antwort des Teilnehmers anzeigen.

Weitere Informationen finden Sie unter [Planen einer Buchung in der App Teams Bookings App](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-a-visit"></a>Durchführen eines Besuchs

Wechseln Sie Teams Kalender Outlook, wechseln Sie zur Buchung, und wählen Sie dann Teilnehmen oder Teams Besprechungslink  aus. Überprüfen Sie Ihre Audio- und Videoeinstellungen, und wählen Sie dann Jetzt **teilnehmen aus**. Weitere Informationen finden Sie unter [Durchführen eines Bookings Termins](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-visits-and-get-real-time-status-updates"></a>Besuche überwachen und Statusaktualisierungen in Echtzeit erhalten

Die [Warteschlangenansicht](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) in Bookings bietet Ihren Mitarbeitern ein Dashboard zur Überwachung aller virtuellen Termine für den Tag mit Updates in Echtzeit. Um die Warteschlange zu sehen, wechseln **Sie zur Registerkarte** Warteschlange in Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Screenshot der Warteschlangenansicht in der Bookings-App in Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Aus der Warteschlange können Planer eine neue Buchung hinzufügen, relevante Termindetails anzeigen und den ganzen Tag über den Terminstatus anzeigen. Wenn ein Patient dem Warteraum beitritt, ändert sich der Status, und die Wartezeit wird angezeigt und nachverfolgt. Die Ansicht wird automatisch mit farblich gekennzeichneten Aktualisierungen aktualisiert, sodass Änderungen leicht zu erkennen sind.

Mitarbeiter können sogar Direkt aus der Warteschlange an Terminen teilnehmen und diese verwalten.

> [!NOTE]
> Derzeit unterstützt die Bookings das Hinzufügen von bis zu 100 Mitarbeitern pro Buchungskalender. Wenn Sie die Graph zum Einrichten und Hinzufügen von Mitarbeitern zu einem Buchungskalender verwendet haben, wird dieser Grenzwert möglicherweise nicht erzwungen. In diesem **Szenario kann die** Registerkarte Warteschlange keine Inhalte für Kalender mit mehr als 100 Mitarbeitern rendern. Für eine optimale Erfahrung empfehlen wir, einem Buchungskalender nicht mehr als 100 Mitarbeiter hinzuzufügen. Wir arbeiten an einer Lösung dieser Einschränkung in zukünftigen Versionen.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Zusätzliche Funktionen mit der Bookings Web App

Die Bookings Web App bietet Ihnen zusätzliche Funktionen. So können Sie beispielsweise eine Selbstbedienungs-Onlinebuchungsseite veröffentlichen, auf der Personen Termine mit Ihren Mitarbeitern planen können. Wenn Sie auf die Bookings Web App zugreifen möchten, wechseln Sie zu Weitere **Optionen (...) >** **Öffnen Bookings Web App**.

Weitere Informationen finden Sie [unter Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-visits-usage"></a>Erhalten Sie Einblicke in die Nutzung virtueller Besuche

Der [Verwendungsbericht "](../teams-analytics-and-reports/virtual-visits-usage-report.md)Virtuelle Besuche" im Microsoft Teams Admin Center gibt Administratoren einen Überblick über Teams Aktivitäten "Virtuelle Besuche" in Ihrer Organisation. Der Bericht zeigt detaillierte Analysen für virtuelle Termine, einschließlich Bookings Besuchen.

Sie können wichtige Metriken wie Wartezeit des Wartebereichs und Dauer des Besuchs anzeigen. Verwenden Sie diese Informationen, um Einblicke in Nutzungstrends zu erhalten, um Sie bei der Optimierung virtueller Besuche zu unterstützen, um bessere Unternehmensergebnisse zu erzielen.

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Teilnahmeerfahrung für Teams virtuelle Besuche in mobilen Browsern](mobile-browser-join.md)

- [Teams bericht "Virtuelle Besuche"](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Erste Schritte mit Teams für Organisationen im Gesundheitswesen](healthcare/teams-in-hc.md)

- [Bookings-App in Teams Hilfedokumentation](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
