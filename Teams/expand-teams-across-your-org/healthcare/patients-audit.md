---
title: 'Überwachungs-Patienten-App für Teams IT- und Complianceadministratoren '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Informationen zum Überwachen der Patienten-App für Teams-Administratoren
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3cf850b8ae7312fa6c43f879baefb617f48d30b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096189"
---
# <a name="audit-logs-for-patients-app"></a>Überwachungsprotokolle für die Patienten-App

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Microsoft Teams ersetzt. Die Daten der Patienten-App werden in dem Gruppenpostfach der Office 365-Gruppe gespeichert, das zum Team gehört. Alle der Patienten-App zugeordneten Daten bleiben in dieser Gruppe erhalten, auf sie kann aber nicht mehr über die Benutzeroberfläche zugegriffen werden. Benutzer können ihre Listen mithilfe der App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) neu erstellen.
>
>Mit der Listen-App können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen. Sehen Sie sich die Vorlage "Patienten" in der Listen-App an, um die ersten Schritte zu unternehmen. Weitere Informationen zum Verwalten der Listen-App in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Mit einem Überwachungsprotokoll für die Aktivität der Patienten-App können Reaktionsteams nach Vorfällen Änderungen an den elektronischen Krankenakten (Electronic Medical Records, EMR) oder patientenärzten Informationen (Patient Healthcare Information, PHI) eines Patienten überprüfen und feststellen, ob Änderungen oder Verbesserungen der Richtlinie oder des Verfahrens für den PHI-Zugriff in Produktivitätstools erforderlich sind. Die Überwachungsprotokollereignisse behandeln Aktionen, die über die Benutzeroberfläche der Patienten-App ausgeführt werden.

## <a name="meet-hipaa-requirements"></a>Erfüllen der HIPAA-Anforderungen

Gemäß den HIPAA-Richtlinien müssen Anbieter des Gesundheitswesens Aufzeichnungen über alle Zugriffe auf PHI speichern, damit die Änderungen überwacht werden können. Microsoft engagiert sich für unternehmensweite Kunden, die Microsoft Teams verwenden, und unterstützt sie dabei, die HIPAA-Anforderungen und -Steuerelemente zu erfüllen. Der Zugriff auf PHI über die Patienten-App wird vollständig nachverfolgt, und Protokolle werden im Microsoft 365 Compliance Center verfügbar gemacht, wie im Funktionsartikel [Überwachungsprotokollsuche](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) beschrieben.

> [!IMPORTANT]
> Die Belastung durch die Aufrechterhaltung der Privatsphäre der Patienten wird dem Gesundheitswesen per Gesetz zuteil. Das Gesetz berechtigt Patienten zum Datenschutz und setzt voraus, dass ein IT-Administrator oder HIPAA-Controller leicht bestimmen kann, auf welche Krankenpflegerin, Ärztin oder Sozialarbeiter zugegriffen oder die Patientenakten geändert wurden. Eines der häufigsten Beispiele für eine Verletzung des PHI-Zugriffs ist der Zugriff auf VIP-Patienten. Die Überwachungsprotokollfunktionalität ist erforderlich, um Untersuchungen zu allen PHI-Zugriffsverletzungen durchzuführen und die HIPAA-Anforderungen zu erfüllen.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Aktivieren von Überwachungsprotokollen für die Patienten-App

Eine Überwachung ist von mehreren vorherigen Konfigurationen abhängig:

1. Der Administrator müsste mit seinem FHIR-Dienstanbieter zusammenarbeiten, um EMR in einem von der Patienten-App verwendeten Format zu verwenden. Weitere Informationen finden Sie unter [Integrieren von elektronischen Krankenakten in Microsoft Teams.](patients-app.md)
2. Ein Administrator eines Gesundheitswesens müsste die Patienten-App im Teams Admin Center aktivieren. Weitere Informationen finden Sie unter Verwalten von [Richtlinien für das Einrichten von Apps in Microsoft Teams](../../teams-app-setup-policies.md) und verwandten Artikeln.
3. Der Administrator müsste Aktivitätsaudits auf die gleiche Weise aktivieren wie [](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) jede Aktivitätsprotokoll-Überwachung, wie unter Vor dem Starten und Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche beschrieben.](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Wenn die Überwachungsprotokollierung bereits installiert ist, ist für die Patienten-App nichts Besonderes erforderlich. Jedes Mal, wenn ein Gesundheitswesen die App in einem Team installiert und betreibt, zeichnen die Überwachungsprotokolle ihre PHI-Aktivität auf.
4. Der Administrator müsste dann die Verfügbarkeit der Patienten-App ankündigen, und Mitarbeiter des Gesundheitswesens müssten damit beginnen, Aktivitäten zu generieren, um in eine Überwachung einbezogen zu werden.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Ausführen einer Überwachung

Anweisungen zum Ausführen einer Suche im Aktivitätsprotokoll finden Sie unter [Durchsuchen des Überwachungsprotokolls.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Protokollierte Aktivitäten für die Patienten-App

Die Patienten-App verfügt über eigene protokollierte Aktivitäten, die in der folgenden Tabelle aufgeführt sind:

|Anzeigename |Vorgang|Beschreibung|
|:---|:---|:---|
| Angezeigte Patientenliste | PatientListView | Ein Benutzer hat eine Patientenliste angezeigt.|
| Gelöschte Patientenliste | PatientListDelete | Ein Benutzer hat eine Patientenliste gelöscht.|
| Hinzugefügter Patient zur Liste | PatientListAddPatient | Ein Patient wurde einer Patientenliste hinzugefügt. |
| Hinzugefügte Notiz für Patienten | PatientNoteAdd | Einem Patientendatensatz wurde eine Notiz hinzugefügt. |
| Erstelltes Patientenschema | PatientSchemaCreate | Es wurde eine Gruppe von Spalten erstellt, die im Patientendatensatz verwendet werden. |
| Benutzer hat einen Export initiiert | ExportInitiation | Patientendaten wurden aus der Patienten-App in eine Excel-Datei exportiert. Die Datei wird auf der Team-Sharepoint-Website gespeichert. |
| Erstellte Patientenliste | PatientListCreate | Ein Benutzer hat eine Patientenliste erstellt.|
| Festlegen der Standardpatientenliste| PatientListDefaultSet| Ein Benutzer hat eine bestimmte Liste als Standardliste festgelegt.|
| Patient aus Liste entfernt| PatientListRemovePatient | Ein Patient wurde aus einer Patientenliste entfernt. |
| Gesuchter Patient | PatientSearch | Sie haben einen Patientendatensatz im EHR-Dienst durchsucht. |
| Aktualisiertes Patientenschema | PatientSchemaUpdate  | Eine vorhandene Gruppe von Spalten, die im Patientendatensatz verwendet werden, wurde aktualisiert. |<!-- | Patient in eine andere Liste verschoben| PatientMoved | Der Patientendatensatz wurde von einer Liste in eine andere verschoben. |-->
| Umbenannte Patientenliste | PatientListRename | Eine Liste der Patienten wurde umbenannt. |
| Bearbeitete Spalten in der Patientenliste | PatientListEditColumns | Eine Spalte in einer Patientenliste wurde bearbeitet (hinzugefügt oder entfernt). |
| Angezeigte Patientendetails | PatientView | Ein Benutzer hat einen Patientendatensatz angezeigt.|
| Bearbeitete Patientendetails | PatientDetailsEdit | Ein Detail zu einem Patientendatensatz wurde bearbeitet. |
| Festlegen der EHR-Verbindung | EHRConnectionSet | Legen Sie die URL für die Verbindung mit der EHR-FHIR-Dienstverbindung ein. Beispiel: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

Sie können Ihre Überwachung nach Bedarf anpassen, um nach diesen protokollierten Aktivitäten zu suchen oder nach diesen zu filtern.

Protokollierte Aktivitäten für Microsoft Teams im Allgemeinen werden in [Microsoft Teams-Aktivitäten beschrieben.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Verwandte Themen

[Durchsuchen des Überwachungsprotokolls](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)