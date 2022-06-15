---
title: Virtuelle Termine mit Microsoft Teams und der Bookings-App
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
description: Erfahren Sie, wie Sie virtuelle Termine mithilfe der Bookings-App in Teams planen, verwalten und durchführen.
ms.openlocfilehash: a89eaa242cd62238d4e5c6c9d7a88f3a2e9ac62c
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103382"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Virtuelle Termine mit Microsoft Teams und der Bookings-App

## <a name="overview"></a>Übersicht

Die [Bookings-App](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) in Microsoft Teams bietet Organisationen eine einfache Möglichkeit, virtuelle Termine für Mitarbeiter und Teilnehmer zu planen und zu verwalten. Verwenden Sie es, um Termine wie Besuche im Gesundheitswesen, Finanzberatungen, Interviews, Kundensupport, virtuelle Ausstattungen und Beratungen, Bildungsbürozeiten und vieles mehr zu planen.

Die Bookings-App erleichtert die Verwaltung komplexer Planungsanforderungen jeder Organisation. Die planenden Personen können mehrere Abteilungs- und Mitarbeiterkalender sowie die Kommunikation mit internen und externen Teilnehmern über eine einzige Lösung verwalten.

Die virtuellen Termine werden über Microsoft Teams Besprechungen abgehalten, die stabile Videokonferenzfunktionen bieten. Beispielsweise kann ein Arzt den Bildschirm teilen und Testergebnisse mit einem Patienten überprüfen. Oder ein Bankberater kann elektronische Signaturen für Dokumente anfordern, sodass er Transaktionen remote schließen kann.

Jeder virtuelle Termin enthält einen Teams Besprechungslink, der per E-Mail an die Teilnehmer gesendet wird, wo sie einfach über einen Webbrowser oder in Teams auf jedem Gerät teilnehmen können. Automatisierte E-Mail-Erinnerungen tragen dazu bei, keine Anzeigen zu reduzieren und die Kunden- und Kundenbindung zu verbessern.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Mit Bookings erhalten Sie eine Erfahrung, die auf Ihre Branche zugeschnitten ist. Hier sind einige Beispiele dafür, wie Sie es in Ihrer Organisation verwenden können:

|Branche | Beispiele |
|---------|---------|
|Finanzdienstleistungen    |  Virtuelle Termine für Remote-Vertrieb und -Service<br/>Planen und verwalten Sie Termine für Bank-Relationship Manager, Finanzberater und Forderungsjustierer, um nur einige zu nennen, um Ihre Kunden mit erhöhter Effizienz und Komfort zu bedienen.  |
|Einzelhandel   | Virtuelle Anproben und Beratungsgespräche <br/>Planen und verwalten Sie Termine für Ihre Vertriebsmitarbeiter, Produktexperten und Designberater, um virtuelle Armaturen und Beratungen mit Kunden durchzuführen.   |
|Gesundheitswesen   |  Virtuelle Termine für die Patientenversorgung <br/>Planen und verwalten Sie Termine für Ihre Pflegeteammitglieder, um sich mit Patienten oder anderen Gesundheitsdienstleistern zu treffen, um die medizinische Versorgung zu besprechen.   |

In diesem Artikel erhalten Sie einen Überblick über das Planen, Verwalten und Durchführen virtueller Termine mithilfe der Bookings-App in Teams.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

Wenn Sie ein Administrator sind, lesen [Sie "Verwalten der Bookings-App in Teams](../bookings-app-admin.md)", um mehr über die Voraussetzungen für die Verwendung der Bookings-App in Teams, das Steuern des Zugriffs auf Bookings in Ihrer Organisation sowie die empfohlenen Richtlinien- und Administratoreinstellungen zu erfahren.

Denken Sie daran, dass die Bookings-App nur für Planer in Ihrer Organisation in Teams installiert sein muss. Mitarbeiter, die virtuelle Termine durchführen oder daran teilnehmen, benötigen die App nicht. Sie nehmen über ihren Teams oder Outlook Kalender oder über den Besprechungslink in ihrer Buchungsbestätigungs-E-Mail an Terminen teil.

## <a name="set-up-a-new-booking-calendar"></a>Einrichten eines neuen Buchungskalenders

### <a name="create-the-booking-calendar"></a>Erstellen des Buchungskalenders

Wechseln Sie in Teams zu **Bookings** >  **Erste Schritte** und wählen Sie dann **"Neuer Buchungskalender**" aus. Füllen Sie das Formular aus, und wählen Sie den relevanten Geschäftstyp für Ihre Organisation aus.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Screenshot des Bildschirms &quot;Neuer Buchungskalender&quot; mit Geschäftstypen":::

Wenn Sie eine größere Organisation sind, sollten Sie mehr als einen Buchungskalender erstellen, wenn Sie möchten, dass die Teilnehmer eine Buchungs-E-Mail von einer bestimmten Abteilung anstatt von Ihrer gesamten Organisation erhalten.
Weitere Informationen finden Sie unter ["Erstellen eines Bookings-Kalenders](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)".

> [!NOTE]
> Wenn Dies nicht das erste Mal in der Bookings-App ist oder Sie in einem vorhandenen Buchungskalender arbeiten möchten, wählen Sie in Bookings den Dropdownpfeil neben dem Namen Ihrer Organisation und dann " **Vorhandener Buchungskalender**" aus. Von hier aus können Sie nach dem gewünschten suchen.

### <a name="add-staff"></a>Mitarbeiter hinzufügen

Wechseln Sie im Buchungskalender zu **"Weitere Optionen** (...) > **Einstellungen**", und wählen Sie dann **"Mitarbeiter"** aus. Fügen Sie Mitarbeiter hinzu, und weisen Sie jeder person, die Sie hinzufügen, eine Rolle zu. Sie können einem Buchungskalender bis zu 100 Mitarbeiter hinzufügen.

Die Bookings-App lässt sich in Outlook integrieren. Nachdem Sie Mitarbeiter hinzugefügt haben, können Sie die Kalenderverfügbarkeit dieser Person anzeigen und Buchungen für diese Person planen. Weitere Informationen finden Sie unter [Hinzufügen von Mitarbeitern und Anzeigen eines Bookings-Kalenders](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Erstellen von Termintypen

Erstellen Sie bestimmte Termintypen, um die von Ihrer Organisation angebotenen Dienste darzustellen und die Buchungserfahrung anzupassen. Planer können dann den Termintyp verwenden, um einen Termin zu planen.

Wechseln Sie im Buchungskalender zu **"Weitere Optionen** (...) > **Einstellungen**", wählen Sie **"Termintypen**" und dann "**Termintyp hinzufügen"** aus. Geben Sie einen Namen&mdash;ein, z. B. Kontoeröffnung, Rezeptverlängerung, Kreditberatung, Steuervorbereitung&mdash;und alle anderen gewünschten Informationen und Einstellungen.

Die von Ihnen hinzugefügten Informationen sind in der E-Mail-Bestätigung enthalten, die bei jeder Buchung dieser Art von Termin an die Teilnehmer gesendet wird. Sie können E-Mail-Erinnerungen und andere Optionen festlegen, z. B. ob Teilnehmer [über einen Desktop- oder mobilen Browser teilnehmen](browser-join.md) können, ohne Teams herunterladen zu müssen.

Wenn Sie ein Bookings-Administrator sind, können Sie bis zu vier Formulare für Teilnehmer verknüpfen, die sie bei jeder Buchung dieses Termintyps ausfüllen können. Beispielsweise können Sie die Teilnehmer auffordern, ein Registrierungsformular auszufüllen, bevor sie an einem Termin teilnehmen. Um ein Formular zu verknüpfen, wählen Sie **"Formular verknüpfen" aus**. Geben Sie die URL des Formulars ein, und wählen Sie dann **"Link"** aus. (Wenn Sie zum ersten Mal ein Formular verknüpfen, werden Sie aufgefordert, eine Microsoft 365 Gruppe zum Speichern von Formularen zu erstellen. Wählen Sie **"Gruppe erstellen** " aus, um die Gruppe zu erstellen. Sie müssen dies nur einmal für den Buchungskalender tun.)

Beachten Sie beim Arbeiten mit Formularen Folgendes:

- Wenn Sie Änderungen an einem Formular vornehmen möchten, das bereits mit einem Termintyp verknüpft ist, wählen Sie das Formular im Termintyp oder in der Microsoft 365 Gruppe unter [https://forms.office.com](https://forms.office.com)aus.
- Das Hochladen von Dateien in Formulare, die eine [Frage zum Hochladen von Dateien](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) enthalten, wird unterstützt, wenn alle Teilnehmer aus derselben Organisation stammen.

Wenn ein Planer den Termintyp zum Planen eines Termins verwendet, kann er auswählen, ob das Formular eingeschlossen, entfernt oder andere Formulare hinzugefügt werden sollen, die Sie mit dem Termintyp verknüpft haben. Teilnehmer müssen das Formular ausfüllen, bevor sie am Termin teilnehmen.

> [!NOTE]
> Alle Informationen, die von Patienten in Forms als Teil von Bookings oder virtuellen Termindiensten bereitgestellt werden, die für die Kontinuität oder Aufbewahrung von Krankenakten erforderlich sind, sollten direkt in solchen Aufzeichnungen heruntergeladen, kopiert und/oder notiert werden. Dieser Dienst stellt weder eine gesetzliche Krankenakte noch eine festgelegte Datensatzgruppe dar.

Weitere Informationen finden Sie unter [Erstellen eines Termintyps](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-an-appointment"></a>Planen eines Termins

Wählen Sie im Buchungskalender " **Neue Buchung**" aus. Wählen Sie einen Termintyp aus, und füllen Sie dann die relevanten Informationen aus.

Dazu gehören Kontaktinformationen zu Teilnehmern, der Mitarbeiter, der den Dienst bereitstellt, interne Notizen, die nur Mitarbeiter sehen können, E-Mail-Erinnerungen und ob der Teilnehmer über einen mobilen Browser teilnehmen kann. Wenn ein Formular mit dem Termintyp verknüpft ist, können Sie es einschließen, entfernen oder andere verknüpfte Formulare hinzufügen.

Die an den Teilnehmer gesendete E-Mail-Bestätigung enthält den Besprechungslink und eine Anlage, damit er den virtuellen Termin zu ihrem Kalender hinzufügen kann. Mitarbeiter erhalten außerdem eine E-Mail-Bestätigung und eine Besprechungseinladung. Wenn ein Formular im Termin enthalten war, können Bookings-Administratoren und -Planer sehen, ob das Formular vom Teilnehmer vor dem Termin ausgefüllt wurde, und die Antwort des Teilnehmers anzeigen.

Weitere Informationen finden Sie [unter Planen einer Buchung in der Teams Bookings-App](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-an-appointment"></a>Durchführen eines Termins

Wechseln Sie in Ihrem Teams oder Outlook Kalender zur Buchung, und wählen Sie dann **"Teilnehmen"** oder den link "Teams Besprechung" aus. Überprüfen Sie Ihre Audio- und Videoeinstellungen, und wählen Sie dann " **Jetzt beitreten"** aus. Weitere Informationen finden Sie unter [Durchführen eines Bookings-Termins](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>Überwachen von Terminen und Abrufen von Statusupdates in Echtzeit

Die [Warteschlangenansicht](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) in Bookings bietet Ihren Mitarbeitern ein Dashboard, um alle virtuellen Termine für den Tag mit Updates in Echtzeit zu überwachen. Um die Warteschlange anzuzeigen, wechseln Sie zur Registerkarte **"Warteschlange** " in Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Screenshot der Warteschlangenansicht in der Bookings-App in Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

In der Warteschlange können Planer eine neue Buchung hinzufügen, relevante Termindetails anzeigen und den Terminstatus während des Tages anzeigen. Wenn ein Patient dem Wartezimmer beitritt, ändert sich der Status, und seine Wartezeit wird angezeigt und nachverfolgt. Die Ansicht wird automatisch mit farbcodierten Updates aktualisiert, sodass Änderungen leicht identifiziert werden können.

Mitarbeiter können sogar direkt aus der Warteschlange an Terminen teilnehmen und diese verwalten.

> [!NOTE]
> Derzeit unterstützt die Bookings-App das Hinzufügen von bis zu 100 Mitarbeitern pro Buchungskalender. Wenn Sie Graph APIs zum Einrichten und Hinzufügen von Mitarbeitern zu einem Buchungskalender verwendet haben, wird dieser Grenzwert möglicherweise nicht erzwungen. In diesem Szenario kann die Registerkarte **"Warteschlange** " keine Inhalte für Kalender mit mehr als 100 Mitarbeitern rendern. Für eine optimale Erfahrung empfehlen wir, dass Sie nicht mehr als 100 Mitarbeiter zu einem Buchungskalender hinzufügen. Wir arbeiten daran, diese Einschränkung in zukünftigen Versionen zu beheben.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Zusätzliche Funktionen mit der Bookings-Web-App

Die Bookings-Web-App bietet Ihnen zusätzliche Funktionen. Sie können z. B. eine Self-Serve-Onlinebuchungsseite veröffentlichen, auf der Personen Termine mit Ihren Mitarbeitern planen können. Um auf die Bookings-Web-App zuzugreifen, wechseln Sie zu **"Weitere Optionen** (...) > **Bookings-Web-App öffnen**".

Weitere Informationen finden Sie [unter Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-appointments-usage"></a>Erhalten Sie Einblicke in die Nutzung virtueller Termine

Der [Nutzungsbericht "Virtuelle Besuche"](../teams-analytics-and-reports/virtual-visits-usage-report.md) im Microsoft Teams Admin Center bietet Administratoren einen Überblick über Teams aktivitäten virtueller Termine in Ihrer Organisation. Der Bericht zeigt detaillierte Analysen zu virtuellen Terminen einschließlich Bookings-Terminen.

Sie können wichtige Metriken anzeigen, z. B. Wartezeit des Wartebereichs und Termindauer. Verwenden Sie diese Informationen, um Einblicke in Nutzungstrends zu erhalten, die Ihnen helfen, virtuelle Termine zu optimieren, um bessere Geschäftsergebnisse zu erzielen.

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Teilnahmeerfahrung für Teams virtueller Termine in mobilen Browsern](browser-join.md)

- [Nutzungsbericht für Teams virtuelle Besuche](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Erste Schritte mit Teams für Organisationen im Gesundheitswesen](healthcare/teams-in-hc.md)

- [Bookings-App in Teams Hilfedokumentation](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
