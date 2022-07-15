---
title: Microsoft Teams – Benutzeraktivitätsbericht
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Teams-Benutzeraktivitätsbericht im Microsoft Teams Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Teams verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 88eb4f56c6891643bd862f425821327d14b95cb4
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825709"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Teams-Benutzeraktivitätsbericht gibt Einblicke in die Arten von Aktivitäten, die Benutzer in Ihrer Organisation in Teams ausführen. Sie können durch ungeplante Besprechungen (1:1 und Gruppenanrufe) sehen, wie viele Benutzer ungeplant kommunizieren. Sehen Sie, wie viele Besprechungen ein Teams-Benutzer organisiert hat und an Besprechungen, an der ein Teams-Benutzer teilgenommen hat. Details zu Bildschirm-, Video- und Audiominuten sowie Chatkommunikationsstatistiken anzeigen, z. B. wie viele Benutzer Kanalnachrichten beantworten und posten und wie viele Benutzer an 1:1- oder Gruppenchatnachrichten teilnehmen.

> [!NOTE]
> Die Möglichkeit zum Planen eines Benutzeraktivitätsberichts ist derzeit nicht verfügbar.

## <a name="view-the-user-activity-report"></a>Anzeigen des Benutzeraktivitätsberichts

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](../using-admin-roles.md).

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **die Option "Analyse" & Berichte** > **"Nutzungsberichte"** aus. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht"** die Option " **Teams-Benutzeraktivität**" aus.
2. Wählen Sie unter **"Datumsbereich**" einen Bereich und dann " **Bericht ausführen**" aus.

    ![Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Popups.](../media/teams-reports-user-activity-with-callouts.png "Screenshot des Teams-Benutzeraktivitätsberichts im Teams Admin Center mit Popups")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

| Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Teams-Benutzeraktivitätsbericht kann nach Trends in den letzten 7 Tagen, 30 oder 90 Tagen angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte spiegeln in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität wider. |
|**3**   |Zeitreihendatenpunkte im Diagramm zeigen unterschiedliche Nutzungsmetriken an, die auf dem Mandanten aggregiert werden. |
|**4**   |Tabellarische Daten stellten verschiedene Nutzungsmetriken dar, die pro Benutzer aggregiert wurden. |
|**5**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**6**   | Jede der Metriken, die in Graph auf Mandantenebene dargestellt werden. Filtern Sie, was im Diagramm angezeigt wird, indem Sie ein Element in der Legende auswählen. Wählen Sie **Kanalnachrichten**, **Antwortnachrichten**,  **Chatnachrichten** oder **organisierte Besprechungen** aus, um Informationen zu den einzelnen Nachrichten anzuzeigen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**7**   |In der Tabelle finden Sie eine Aufschlüsselung der Nutzung nach Benutzer.   <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Wählen Sie den Anzeigenamen aus, um zur Seite mit den Benutzerdetails im Microsoft Teams Admin Center zu wechseln.</li><li>**Kanalnachrichten** ist die Anzahl eindeutiger Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Antwortnachrichten** ist die Anzahl der eindeutigen Antwortnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li> <li>**Postnachrichten** ist die Anzahl der eindeutigen Beitragsnachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamkanal gepostet hat.</li><li>**Chatnachrichten** sind die Anzahl eindeutiger Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</li><li>**Dringende Nachrichten** sind die Anzahl dringender Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Chat gepostet hat.</li><li>**Die Gesamtanzahl der organisierten Besprechungen** ist die Summe der einmal geplanten, wiederkehrenden, ungeplanten und <em>nicht klassifizierten</em> Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die einmal geplant wurden** , sind die Anzahl der einmal geplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen, die in einer geplanten Terminserie organisiert werden** , sind die Anzahl der Besprechungsserien, die ein Benutzer während des angegebenen Zeitraums organisiert hat.</li><li>**Besprechungen organisiert adhoc** ist die Anzahl der ungeplanten Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert.</li><li>**Die Gesamtzahl der teilgenommenen Besprechungen** ist die Summe der einmaligen geplanten, wiederkehrenden, ungeplanten und <em>nicht klassifizierten</em> Besprechungen, an denen ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Besprechungen, an denen einmal geplant teilgenommen wurde** , ist die Anzahl der einmal geplanten Besprechungen, an denen ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Besprechungen, an der eine geplante Besprechungsserie teilgenommen hat** , ist die Anzahl der Besprechungsserien, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>Die Anzahl der ungeplanten **Besprechungen**, an der ein Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**1:1-Anrufe** sind die Anzahl von 1:1-Anrufen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Audiozeit** ist die Gesamtaudiozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Videozeit** ist die Gesamte Videozeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li><li>**Die Bildschirmfreigabezeit** ist die gesamte Bildschirmfreigabezeit (Minuten), an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</li>  <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teams-Aktivität teilgenommen hat.</li><li>**Andere Aktivitäten** nachverfolgen, wenn der Benutzer als aktiv betrachtet wird, aber für Chatnachrichten, 1:1-Anrufe, Kanalnachrichten, Besprechungen insgesamt und Besprechungen, die organisiert sind, der Wert Null hat. Beispiele für Aktionen sind, wenn ein Benutzer einen Kanalnachrichtenbeitrag öffnet, aber nicht darauf antwortet oder wenn ein Benutzer eine private Nachricht empfängt und diese liest, aber nicht darauf antwortet.</li> <li>**Nicht klassifizierte Besprechungen** sind solche, die nicht als geplante, wiederkehrende oder ungeplante Besprechungen identifiziert werden können. Diese sind nur wenige und können aufgrund unvollkommener Telemetrieinformationen oft nicht identifiziert werden.</li> </ul>**Gruppenanrufe** wurden durch von **Adhoc organisierte Besprechungen** ersetzt, und **Besprechungen nahmen an Adhoc teil**. Die Summe dieser beiden Werte entspricht der Summe, die von **Gruppenaufrufen** gemessen wurde.
|**8**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**9**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen Sie **"Nach Excel exportieren**" und dann auf der Registerkarte " **Downloads** " die Option **"Herunterladen** " aus, um den Bericht herunterzuladen, sobald er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten, die heruntergeladen werden sollen.](../media/teams-reports-export-to-csv.png) <br>Wenn Sie den Bericht in Excel anzeigen, wird auch eine **ID-Spalte** angezeigt, die die Benutzer-ID darstellt. Eine Benutzer-ID ist in der Regel eine alphanumerische Zeichenfolge. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisieren der benutzerspezifischen Daten

Um die Daten im Teams-Benutzeraktivitätsbericht anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen (unter Verwendung von MD5-Hashes) wie Anzeigename, E-Mail und AAD-ID im Bericht und deren Export ausgeblendet.

1. Wechseln Sie in Microsoft 365 Admin Center zu den **Organisationseinstellungen "Einstellungen**\>", und wählen Sie auf der Registerkarte "**Dienste**" die Option "**Berichte**" aus.
    
2. Wählen Sie **"Berichte**" und dann " **Verborgene Benutzer-, Gruppen- und Websitenamen in allen Berichten anzeigen"** aus. Diese Einstellung wird sowohl auf die Nutzungsberichte im Microsoft 365 Admin Center als auch auf das Teams Admin Center angewendet.
  
3. Wählen Sie **"Änderungen speichern" aus**.

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
