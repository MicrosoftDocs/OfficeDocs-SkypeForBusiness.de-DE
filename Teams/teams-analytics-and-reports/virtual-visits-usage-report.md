---
title: Microsoft Teams bericht "Virtuelle Besuche"
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Nutzungsbericht für virtuelle Besuche im Microsoft Teams Admin Center verwenden, um einen Überblick über die Aktivität "Virtuelle Besuche" in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f00a8e0837ad4603fe38f664f94716aa8016aa9
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929416"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams bericht "Virtuelle Besuche"

**Dies ist ein Vorschaufeature**.

Der Nutzungsbericht "Virtuelle Besuche" im Microsoft Teams Admin Center bietet Ihnen einen Überblick über Teams Aktivitäten für virtuelle Besuche in Ihrer Organisation. Sie können detaillierte Aktivitäten für virtuelle Termine anzeigen, die über die [Bookings-App](../expand-teams-across-your-org/bookings-virtual-visits.md) und den [EHR Microsoft Teams Connector (Electronic Health Record) geplant sind](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration).

Zum Anzeigen des Berichts müssen Sie ein globaler Administrator oder ein Teams sein.

Der Bericht enthält die folgenden Registerkarten. Die Im Bericht angezeigten Informationen hängen davon ab, ob Sie über eine Lizenz für die Bookings-App, den Teams EHR-Connector oder beides verfügen.

|TAB |Beschreibung  |
|---------|---------|
|**[Virtuelle Besuche](#virtual-visits)**     |Zeigt die Gesamtanzahl virtueller Besuche mit einer Aufschlüsselung der Anzahl der mit der Bookings-App geplanten Besuche und Teams EHR-integrierten Besprechungen an, die auf Ihrem EHR-System durchgeführt werden.         |
|**[Dauer](#duration)**     |Zeigt die durchschnittliche Dauer der Besuche und die durchschnittliche Wartezeit der Teilnehmer im Wartebereich an.         |
|**[Bookings](#bookings)**     |Zeigt die Anzahl der Über die Bookings-App geplanten Besuche an.         |
|**[EHR](#ehr)**     |Zeigt die Anzahl der Teams EHR-integrierten Besuche von Ihrem EHR-System an.         |  

Verwenden Sie diesen Bericht, um Einblicke in die Aktivität "Virtuelle Besuche" und die Trends in Ihrer Organisation zu erhalten. Die Informationen können Ihnen helfen, virtuelle Besuche zu optimieren, um bessere Unternehmensergebnisse zu erzielen.

## <a name="view-the-virtual-visits-usage-report"></a>Anzeigen des Nutzungsberichts für virtuelle Besuche

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option **Analytics &** >  **Berichten verwalten aus**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht die** Option Nutzung **virtueller Besuche aus**.
2. Wählen **Sie unter Datumsbereich** einen Datumsbereich von 7 Tagen, 30 Tagen oder 90 Tagen aus. Wählen Sie dann Bericht **ausführen aus**.

> [!NOTE]
> Standardmäßig ist die Analyse für virtuelle Besuche aktiviert, und der Bericht ist verfügbar. Mithilfe dieses Berichts erteilen Sie Microsoft die Berechtigung zum Sammeln von Daten zu virtuellen Besuchen in Ihrer Organisation. Informationen zu unseren Aufbewahrungsrichtlinien finden Sie unter Aufbewahrung[, Löschung und Löschung von Daten in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Wenn Sie den Bericht für Ihre Organisation deaktivieren möchten, können Sie dies **in Einstellungen** rechten oberen Ecke der Seite tun.


## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="virtual-visits"></a>Virtuelle Besuche

Die hier angezeigten Diagramme hängen davon ab, ob Sie über eine Lizenz für die Bookings-App, den Teams EHR-Connector oder beides verfügen. Weitere Informationen finden Sie unter [Verwalten der Bookings-App](../bookings-app-admin.md) und [Integration in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) oder [Integration in eine epische EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Screenshot der Registerkarte "Virtuelle Besuche" des Nutzungsberichts für virtuelle Besuche mit nummerierten Callouts." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat das Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse gibt die Anzahl der Besuche an.<br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Anzahl der Besuche an diesem Datum zu sehen.|
|**3**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen Sie beispielsweise Virtuelle **Buchungen** Gesamtbesuche oder Virtuelle **EHR-Besuche** aus, um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**4**   |Die Tabelle enthält detaillierte Informationen zu jedem Besuch, der im ausgewählten Datumsbereich stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu dem sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teil haben oder zu dem die erste Aktivität in der Besprechung eingetreten ist.  </li> <li>**Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit für** den Wartebereich ist die Zeit zwischen dem Beitritt eines Teilnehmers in den Wartebereich, bis der gleiche Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist die Zeitdifferenz zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (Null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer der Besprechung beitreten und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Anzeigen**: Wenn ein Mitarbeiter der Besprechung beitritt, aber keine anderen Personen teilnehmen, und die Besprechung wurde beendet. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer ist** die Gesamtanzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet gibt** an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul> |
|**5**   |Wählen **Einstellungen** aus, um den **Analysebereich Für virtuelle Besuche zu** öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen **Sie In Excel** exportieren aus, und wählen Sie dann auf der Registerkarte **Downloads** die  Option Herunterladen aus, um den Bericht herunterzuladen, wenn er bereit ist.|

### <a name="duration"></a>Dauer

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Screenshot der Registerkarte "Dauer" des Nutzungsberichts "Virtuelle Besuche" mit nummerierten Callouts." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat das Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse gibt die Anzahl der Minuten an.<br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die durchschnittliche Visitedauer oder die durchschnittliche Wartezeit für ein bestimmtes Datum zu sehen.  |
|**3**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen Sie z. B. **Durchschnittliche Dauer für virtuellen** Besuch oder **Durchschnittliche** Wartezeit für den Wartebereich aus, um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**4**   |Die Tabelle enthält detaillierte Informationen zu jedem Besuch, der im ausgewählten Datumsbereich stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu dem sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teil haben oder zu dem die erste Aktivität in der Besprechung eingetreten ist.  </li> <li>**Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit für** den Wartebereich ist die Zeit zwischen dem Beitritt eines Teilnehmers in den Wartebereich, bis der gleiche Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist die Zeitdifferenz zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (Null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer der Besprechung beitreten und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Anzeigen**: Wenn ein Mitarbeiter der Besprechung beitritt, aber keine anderen Personen teilnehmen, und die Besprechung wurde beendet. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer ist** die Gesamtanzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet gibt** an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul>|
|**5**   |Wählen **Einstellungen** aus, um den **Analysebereich Für virtuelle Besuche zu** öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen **Sie In Excel** exportieren aus, und wählen Sie dann auf der Registerkarte **Downloads** die  Option Herunterladen aus, um den Bericht herunterzuladen, wenn er bereit ist.|
### <a name="bookings"></a>Bookings

Diese Registerkarte wird angezeigt, wenn Sie über eine Lizenz verfügen, die die Bookings-App enthält. Weitere Informationen finden Sie unter [Verwalten der Bookings-App](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Screenshot der Registerkarte "Bookings" des Nutzungsberichts für virtuelle Besuche mit nummerierten Callouts" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat das Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse gibt die Anzahl der Bookings-Besuche an.<br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Anzahl der Bookings-Besuche zu sehen, die an diesem Datum stattgefunden haben.|
|**3**   |Die Tabelle enthält detaillierte Informationen zu jedem Besuch, der im ausgewählten Datumsbereich stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu dem sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teil haben oder zu dem die erste Aktivität in der Besprechung eingetreten ist.  </li> <li>**Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit für** den Wartebereich ist die Zeit zwischen dem Beitritt eines Teilnehmers in den Wartebereich, bis der gleiche Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist die Zeitdifferenz zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (Null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer der Besprechung beitreten und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Anzeigen**: Wenn ein Mitarbeiter der Besprechung beitritt, aber keine anderen Personen teilnehmen, und die Besprechung wurde beendet. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer ist** die Gesamtanzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet gibt** an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul>|
|**4**   |Wählen **Einstellungen** aus, um den **Analysebereich Für virtuelle Besuche zu** öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen **Sie In Excel** exportieren aus, und wählen Sie dann auf der Registerkarte **Downloads** die  Option Herunterladen aus, um den Bericht herunterzuladen, wenn er bereit ist.|
### <a name="ehr"></a>EHR

Diese Registerkarte wird angezeigt, wenn Sie über eine Lizenz verfügen, die den EHR Teams Connector enthält. Weitere Informationen finden Sie unter [Integration in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) oder [Integration in die Epische EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Screenshot der Registerkarte "EHR" des Verwendungsberichts "Virtuelle Besuche" mit nummerierten Callouts" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat das Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse gibt die Anzahl der EHR-Besuche an.<br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Anzahl der EHR-Besuche an diesem Datum zu sehen.|
|**3**   |Die Tabelle enthält detaillierte Informationen zu jedem Besuch, der im ausgewählten Datumsbereich stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu dem sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teil haben oder zu dem die erste Aktivität in der Besprechung eingetreten ist.  </li> <li>**Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit für** den Wartebereich ist die Zeit zwischen dem Beitritt eines Teilnehmers in den Wartebereich, bis der gleiche Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist die Zeitdifferenz zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (Null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer der Besprechung beitreten und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Anzeigen**: Wenn ein Mitarbeiter der Besprechung beitritt, aber keine anderen Personen teilnehmen, und die Besprechung wurde beendet. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer ist** die Gesamtanzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet gibt** an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul>|
|**4**   |Wählen **Einstellungen** aus, um den **Analysebereich Für virtuelle Besuche zu** öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen **Sie In Excel** exportieren aus, und wählen Sie dann auf der Registerkarte **Downloads** die  Option Herunterladen aus, um den Bericht herunterzuladen, wenn er bereit ist.|

> [!NOTE]
> Wenn Ihre Organisation an der privaten Vorschau für Benutzer ohne Administratorrechte teilnehmen möchte, z. B. Entscheidungsträger, die Zugriff auf diesen Bericht haben und diesen anzeigen können, kontaktieren Sie [uns](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Verwandte Artikel

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Virtuelle Besuche mit Teams und der Bookings-App](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Virtuelle Besuche mit Teams - Integration in die Epische EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Virtuelle Besuche mit Teams - Integration in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
