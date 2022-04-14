---
title: Nutzungsbericht für Microsoft Teams virtuelle Besuche
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
description: Erfahren Sie, wie Sie den Nutzungsbericht "Virtuelle Besuche" im Microsoft Teams Admin Center verwenden, um einen Überblick über virtuelle Terminaktivitäten in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853216"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Nutzungsbericht für Microsoft Teams virtuelle Besuche

Der Nutzungsbericht "Virtuelle Besuche" im Microsoft Teams Admin Center bietet Ihnen einen Überblick über Teams aktivitäten virtueller Termine in Ihrer Organisation. Sie können detaillierte Aktivitäten für virtuelle Termine anzeigen, die über die [Bookings-App](../expand-teams-across-your-org/bookings-virtual-visits.md) und den [Microsoft Teams EHR-Connector (Electronic Health Record)](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration) geplant werden.

Zum Anzeigen des Berichts müssen Sie ein globaler Administrator oder Teams Administrator sein.

Der Bericht enthält die folgenden Registerkarten. Die Informationen, die im Bericht angezeigt werden, hängen davon ab, ob Sie über eine Lizenz für die Bookings-App, den Teams EHR-Connector oder beides verfügen.

|Registerkarte |Beschreibung  |
|---------|---------|
|**[Virtuelle Besuche](#virtual-visits)**     |Zeigt die Gesamtzahl der virtuellen Termine mit einer Aufschlüsselung der Anzahl von Terminen, die mithilfe der Bookings-App geplant wurden, und Teams von Ihrem EEHR-System durchgeführten Besprechungen.         |
|**[Dauer](#duration)**     |Zeigt die durchschnittliche Dauer von Terminen und die durchschnittliche Wartezeit der Teilnehmer im Wartebereich an.         |
|**[Bookings](#bookings)**     |Zeigt die Anzahl der Über die Bookings App geplanten Termine an.         |
|**[EHR](#ehr)**     |Zeigt die Anzahl der Teams EHR-integrierten Termine, die von Ihrem EHR-System durchgeführt werden.         |  

Verwenden Sie diesen Bericht, um Einblicke in virtuelle Terminaktivitäten und Trends in Ihrer Organisation zu erhalten. Die Informationen können Ihnen helfen, virtuelle Termine zu optimieren, um bessere Geschäftsergebnisse zu erzielen.

## <a name="view-the-virtual-visits-usage-report"></a>Anzeigen des Nutzungsberichts für virtuelle Besuche

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **"Analytics & reportsUsage** > **"-Berichte** aus. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht**" die **Option "Nutzung virtueller Besuche"** aus.
2. Wählen Sie unter **"Datumsbereich**" einen Datumsbereich von 7 Tagen, 30 Tagen oder 90 Tagen aus. Wählen Sie dann " **Bericht ausführen" aus**.

> [!NOTE]
> Standardmäßig ist die Analyse für virtuelle Besuche aktiviert, und der Bericht ist verfügbar. Mithilfe dieses Berichts erteilen Sie Microsoft die Berechtigung zum Sammeln von Daten zu virtuellen Terminen in Ihrer Organisation. Informationen zu unseren Datenaufbewahrungsrichtlinien finden Sie [unter Datenaufbewahrung, -löschung und -vernichtung in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Wenn Sie den Bericht für Ihre Organisation deaktivieren möchten, können Sie dies in **Einstellungen** in der oberen rechten Ecke der Seite tun. Diese Einstellung kann zwischen 0 (null) und 2 Stunden dauern, bis sie nach dem Ändern wirksam wird.

## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="virtual-visits"></a>Virtuelle Besuche

Die hier angezeigten Diagramme hängen davon ab, ob Sie über eine Lizenz für die Bookings-App, den Teams EHR-Connector oder beides verfügen. Weitere Informationen finden Sie unter [Verwalten der Bookings-App](../bookings-app-admin.md) und [Integration in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) oder [Integration in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Screenshot der Registerkarte &quot;Virtuelle Besuche&quot; im Nutzungsbericht &quot;Virtuelle Besuche&quot; mit nummerierten Legenden." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte spiegeln in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität wider. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse ist die Anzahl der Termine.<br>Zeigen Sie mit der Maus auf den Punkt an einem bestimmten Datum, um die Anzahl der Termine an diesem Datum anzuzeigen.|
|**3**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen Sie beispielsweise **"Total Bookings Virtual Visits**" oder **"Total EHR Virtual Visits**" aus, um nur die jeweils zugehörigen Informationen anzuzeigen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**4**   |Die Tabelle enthält detaillierte Informationen zu jedem Termin, der während des ausgewählten Datumsbereichs stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu der sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teilnehmen oder wann die erste Aktivität in der Besprechung stattgefunden hat.  </li> <li>**Die Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit im Wartebereich** ist die Zeit zwischen dem ersten Beitritt eines Teilnehmers zum Wartebereich zu dem Zeitpunkt, zu dem derselbe Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist der Zeitunterschied zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Präsentation**: Wenn ein Mitarbeiter an der Besprechung teilnimmt, aber keine anderen Personen teilnehmen, und die Besprechung beendet wurde. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder den Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer** ist die Gesamtzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet** gibt an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul> |
|**5**   |Wählen Sie **Einstellungen** aus, um den **Analysebereich für virtuelle Besuche** zu öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen Sie **"In Excel exportieren**" und dann auf der Registerkarte "**Downloads**" die Option "**Herunterladen**" aus, um den Bericht herunterzuladen, sobald er bereit ist.|

### <a name="duration"></a>Dauer

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Screenshot der Registerkarte &quot;Dauer&quot; des Nutzungsberichts &quot;Virtuelle Besuche&quot; mit nummerierten Legenden." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte spiegeln in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität wider. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse entspricht der Anzahl von Minuten.<br>Zeigen Sie mit der Maus auf den Punkt eines bestimmten Datums, um die durchschnittliche Termindauer oder die durchschnittliche Wartezeit für den Wartebereich für ein bestimmtes Datum anzuzeigen.  |
|**3**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen Sie z. B. **die Durchschnittliche Dauer des virtuellen Besuchs** oder **die durchschnittliche Wartezeit für den Wartebereich** aus, um nur die jeweils zugehörigen Informationen anzuzeigen.For example, select Average Virtual Visit duration or Average lobby wait time to see only the info related to each one. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**4**   |Die Tabelle enthält detaillierte Informationen zu jedem Termin, der während des ausgewählten Datumsbereichs stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu der sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teilnehmen oder wann die erste Aktivität in der Besprechung stattgefunden hat.  </li> <li>**Die Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit im Wartebereich** ist die Zeit zwischen dem ersten Beitritt eines Teilnehmers zum Wartebereich zu dem Zeitpunkt, zu dem derselbe Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist der Zeitunterschied zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Präsentation**: Wenn ein Mitarbeiter an der Besprechung teilnimmt, aber keine anderen Personen teilnehmen, und die Besprechung beendet wurde. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder den Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer** ist die Gesamtzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet** gibt an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul>|
|**5**   |Wählen Sie **Einstellungen** aus, um den **Analysebereich für virtuelle Besuche** zu öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen Sie **"In Excel exportieren**" und dann auf der Registerkarte "**Downloads**" die Option "**Herunterladen**" aus, um den Bericht herunterzuladen, sobald er bereit ist.|
### <a name="bookings"></a>Bookings

Diese Registerkarte wird angezeigt, wenn Sie über eine Lizenz verfügen, die die Bookings-App enthält. Weitere Informationen finden [Sie unter Verwalten der Bookings-App](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Screenshot der Registerkarte Bookings des Nutzungsberichts &quot;Virtuelle Besuche&quot; mit nummerierten Legenden." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte spiegeln in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität wider. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse ist die Anzahl der Bookings Termine.<br>Zeigen Sie mit der Maus auf den Punkt an einem bestimmten Datum, um die Anzahl der Bookings Termine anzuzeigen, die an diesem Datum aufgetreten sind.|
|**3**   |Die Tabelle enthält detaillierte Informationen zu jedem Termin, der während des ausgewählten Datumsbereichs stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu der sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teilnehmen oder wann die erste Aktivität in der Besprechung stattgefunden hat.  </li> <li>**Die Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit im Wartebereich** ist die Zeit zwischen dem ersten Beitritt eines Teilnehmers zum Wartebereich zu dem Zeitpunkt, zu dem derselbe Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist der Zeitunterschied zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Präsentation**: Wenn ein Mitarbeiter an der Besprechung teilnimmt, aber keine anderen Personen teilnehmen, und die Besprechung beendet wurde. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder den Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer** ist die Gesamtzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet** gibt an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul>|
|**4**   |Wählen Sie **Einstellungen** aus, um den **Analysebereich für virtuelle Besuche** zu öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen Sie **"In Excel exportieren**" und dann auf der Registerkarte "**Downloads**" die Option "**Herunterladen**" aus, um den Bericht herunterzuladen, sobald er bereit ist.|
### <a name="ehr"></a>EHR

Diese Registerkarte wird angezeigt, wenn Sie über eine Lizenz verfügen, die den Teams EHR-Connector enthält. Weitere Informationen finden Sie [unter Integration in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) oder [Integration in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Screenshot der Registerkarte &quot;EGA&quot; des Nutzungsberichts &quot;Virtuelle Besuche&quot; mit nummerierten Legenden." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte spiegeln in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität wider. |
|**2**   |Die X-Achse ist der ausgewählte Datumsbereich für den Bericht. Die Y-Achse ist die Anzahl derEHR-Termine.<br>Zeigen Sie mit der Maus auf den Punkt an einem bestimmten Datum, um die Anzahl derEHR-Termine an diesem Datum anzuzeigen.|
|**3**   |Die Tabelle enthält detaillierte Informationen zu jedem Termin, der während des ausgewählten Datumsbereichs stattgefunden hat. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, zu der sowohl ein Mitarbeiter als auch ein Teilnehmer an der Besprechung teilnehmen oder wann die erste Aktivität in der Besprechung stattgefunden hat.  </li> <li>**Die Besprechungs-ID** ist die eindeutige ID der Besprechung.</li> <li>**Wartezeit im Wartebereich** ist die Zeit zwischen dem ersten Beitritt eines Teilnehmers zum Wartebereich zu dem Zeitpunkt, zu dem derselbe Teilnehmer oder ein anderer Teilnehmer von einem Mitarbeiter zur Besprechung zugelassen wird.</li><li>**Dauer** ist der Zeitunterschied zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person die Besprechung verlässt. Wenn sowohl ein Mitarbeiter als auch ein Teilnehmer nicht an der Besprechung teilnehmen, wird die Dauer als 0 (null) angezeigt.</li> <li>**Status** zeigt den Besprechungsstatus an. <ul><li>**Abgeschlossen**: Wenn ein oder mehrere Mitarbeiter und Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde. Oder wenn ein oder mehrere Teilnehmer an der Besprechung teilnehmen und die Besprechung beendet wurde.</li> <li> **Keine Präsentation**: Wenn ein Mitarbeiter an der Besprechung teilnimmt, aber keine anderen Personen teilnehmen, und die Besprechung beendet wurde. </li></ul> </li> <li>**Der Besprechungstyp** gibt an, ob der virtuelle Termin über die Bookings-App oder den Teams EHR-Connector geplant wurde.</li> <li>**Teilnehmer** ist die Gesamtzahl der Mitarbeiter und Teilnehmer an der Besprechung.</li> <li>**Sms gesendet** gibt an, ob eine SMS-Benachrichtigung an Teilnehmer gesendet wurde. </li> </li> </ul>|
|**4**   |Wählen Sie **Einstellungen** aus, um den **Analysebereich für virtuelle Besuche** zu öffnen. Von hier aus können Sie die Berichterstellung für virtuelle Besuche für Ihre Organisation deaktivieren oder aktivieren und Spalten in der Tabelle hinzufügen oder entfernen. Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen Sie **"In Excel exportieren**" und dann auf der Registerkarte "**Downloads**" die Option "**Herunterladen**" aus, um den Bericht herunterzuladen, sobald er bereit ist.|

> [!NOTE]
> Wenn Ihre Organisation an der privaten Vorschau teilnehmen möchte, damit Benutzer, die keine Administratoren sind, wie z. B. Entscheidungsträger im Unternehmen, Zugriff auf diesen Bericht haben und diesen anzeigen können, [wenden Sie sich an uns](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Verwandte Artikel

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Virtuelle Termine mit Teams und der Bookings-App](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Virtuelle Termine mit Teams - Integration in Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Virtuelle Termine mit Teams - Integration in Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
