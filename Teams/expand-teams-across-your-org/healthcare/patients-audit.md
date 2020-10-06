---
title: 'Auditing patients-App für Teams IT-und Compliance-Administratoren '
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
description: Patienten-App für Teams-Administratoren
ms.openlocfilehash: c35f9a42cd950676a449608f192ca4100d981c72
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361575"
---
# <a name="audit-logs-for-patients-app"></a>Überwachungsprotokolle für die Patienten-App

> [!IMPORTANT]
> **Die Patienten-APP ist ab dem 15. Oktober 2020 veraltet, und die Benutzer können Sie nicht mehr aus dem App Store von Teams installieren. Wir empfehlen Ihnen, die Listen- [App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams noch heute zu verwenden.**
>
>Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt. Wenn die patients-App eingestellt wird, werden alle damit verknüpften Daten in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden. Aktuelle Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.
>
>Die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) ist für alle Teams-Benutzer vorinstalliert und steht in allen Teams und Kanälen als Registerkarte zur Verfügung. Mit Listen können Betreuerteams mithilfe der integrierten Patienten Vorlage, von Grund auf neu oder durch Importieren von Daten nach Excel, patientenlisten erstellen. Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Ein Überwachungsprotokoll für die APP-Aktivität der Patienten ermöglicht es after-Incident-Reaktions Teams, Änderungen an den elektronischen medizinischen Datensätzen (EMR) eines Patienten oder an Patienten Gesundheitsinformationen (Phi) zu überprüfen und festzustellen, ob Änderungen oder Verbesserungen der Richtlinien oder Verfahren für den Phi-Zugriff in Produktivitätstools erforderlich sind. Die Überwachungsprotokollereignisse decken Aktionen ab, die über die Benutzeroberfläche der Patienten-app ausgeführt werden.

## <a name="meet-hipaa-requirements"></a>Erfüllen der HIPAA-Anforderungen

Gemäß den HIPAA-Richtlinien müssen Gesundheitsdienstleister Aufzeichnungen über den gesamten Zugriff auf Phi behalten, damit die Änderungen überprüft werden können. Microsoft setzt sich für seine Unternehmenskunden ein, die Microsoft Teams verwenden, und um Ihnen zu helfen, die HIPAA-Anforderungen und-Steuerelemente zu erfüllen. Der Zugriff auf Phi über die Patienten-APP wird vollständig nachverfolgt, und Protokolle werden im Microsoft 365 Compliance Center zur Verfügung gestellt, wie im Artikel [Audit Log Search Funktionalität](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) beschrieben.

> [!IMPORTANT]
> Die Belastung durch den Schutz der Privatsphäre des Patienten wird dem Leistungserbringer gesetzlich auferlegt. Das Gesetz berechtigt die Patienten zum Datenschutz und setzt voraus, dass ein IT-Administrator oder HIPAA-Controller einfach feststellen kann, welche Krankenpfleger, Kliniker oder Sozialarbeiter auf Patientendatensätze zugegriffen oder diese geändert haben. Eines der häufigsten Beispiele einer Phi-Zugriffsverletzung ist der Zugriff auf VIP-Patienten. Die Überwachungsprotokoll Funktion ist erforderlich, um Untersuchungen zu einer Phi-Zugriffsverletzung durchzuführen und die HIPAA-Anforderungen zu erfüllen.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Aktivieren von Überwachungsprotokollen für die Patienten-App

Eine Überwachung ist von mehreren vorherigen Konfigurationen abhängig:

1. Der Administrator müsste mit seinem FHIR-Dienstanbieter zusammenarbeiten, um EMR in einem von der Patienten-App verwendeten Format zu verwenden. Weitere Informationen finden Sie unter [integrieren elektronischer Gesundheitsdatensätze in Microsoft Teams](patients-app.md).
2. Ein Administrator des Gesundheits Anbieters müsste die Patienten-App im Team Admin Center aktivieren. Weitere Informationen finden Sie unter [Verwalten von App-Setup Richtlinien in Microsoft Teams und in](../../teams-app-setup-policies.md) verwandten Artikeln.
3. Der Administrator muss Aktivitäts Überwachungen aktivieren, wie dies bei der Überwachung von Aktivitätsprotokollen möglich ist, wie in beschrieben, [bevor Sie beginnen](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) , und aktivieren [oder Deaktivieren der Überwachungsprotokoll Suche](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search). Wenn die Überwachungsprotokollierung bereits aktiviert ist, wird für die Patienten-App nichts besonderes benötigt. Jedes Mal, wenn ein medizinischer Anbieter die app in einem Team installiert und ausführt, zeichnen die Überwachungsprotokolle ihre Phi-Aktivität auf.
4. Der Administrator müsste dann die Verfügbarkeit der Patienten-App ankündigen, und die Mitarbeiter des Gesundheitswesens müssten mit der Generierung von Aktivitäten beginnen, die in einer Überwachung enthalten sein sollen.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Ausführen einer Überwachung

Anweisungen zum Ausführen einer Suche im Aktivitätsprotokoll finden Sie unter [Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

## <a name="logged-activities-for-patients-app"></a>Protokollierte Aktivitäten für Patienten-App

Die app "Patienten" verfügt über eigene protokollierte Aktivitäten, die in der folgenden Tabelle aufgeführt sind:

|Anzeigename |Vorgang|Beschreibung|
|:---|:---|:---|
| Angezeigte Patientenliste | PatientListView | Ein Benutzer hat eine Patientenliste angezeigt.|
| Liste der gelöschten Patienten | PatientListDelete | Ein Benutzer hat eine Liste mit Patienten gelöscht.|
| Patient zur Liste hinzugefügt | PatientListAddPatient | Ein Patient wurde einer Patientenliste hinzugefügt. |
| Notiz für Patienten hinzugefügt | PatientNoteAdd | Eine Notiz wurde einem patientendatensatz hinzugefügt. |
| Erstelltes Patienten Schema | PatientSchemaCreate | Eine Gruppe von Spalten, die im patientendatensatz verwendet wurden, wurde erstellt. |
| Der Benutzer hat einen Export initiiert | ExportInitiation | Patientendaten wurden aus der Patienten-app in eine Excel-Datei exportiert. Die Datei wird auf der SharePoint-Team Website gespeichert. |
| Erstellte Patientenliste | PatientListCreate | Ein Benutzer hat eine Liste mit Patienten erstellt.|
| Festlegen der standardmäßigen Patientenliste| PatientListDefaultSet| Ein Benutzer hat eine bestimmte Liste als Standardliste eingestellt.|
| Patient aus Liste entfernt| PatientListRemovePatient | Ein Patient wurde aus einer Liste von Patienten entfernt. |
| Patient gesucht | PatientSearch | Hat einen Patienten Eintrag im EPA-Dienst durchsucht. |
| Aktualisiertes Patienten Schema | PatientSchemaUpdate  | Es wurde eine vorhandene Gruppe von Spalten aktualisiert, die im patientendatensatz verwendet wurden. |<!-- | Patient in eine andere Liste verschoben| PatientMoved | Der patientendatensatz wurde von einer Liste in eine andere verschoben. |-->
| Patientenliste umbenannt | PatientListRename | Eine Liste der Patienten wurde umbenannt. |
| Bearbeitete Spalten in der Patientenliste | PatientListEditColumns | Eine Spalte in einer Liste von Patienten wurde bearbeitet (hinzugefügt oder entfernt). |
| Patientendetails angezeigt | PatientView | Ein Benutzer hat einen patientendatensatz angezeigt.|
| Bearbeitete Patientendaten | PatientDetailsEdit | Ein Detail zu einem patientendatensatz wurde bearbeitet. |
| EPA-Verbindung einrichten | EHRConnectionSet | Stellen Sie die URL ein, die für die Verbindung mit der EPA-FHIR Dienstverbindung verwendet wird. Beispiel: https://<span>API-V8-dstu2.hspconsortium.org/ContosoHospital/Open</span>  |
||||

Sie können ihre Überwachung nach Bedarf anpassen, um nach diesen protokollierten Aktivitäten zu suchen oder diese zu filtern.

Protokollierte Aktivitäten für Microsoft Teams im Allgemeinen werden in [Microsoft Teams-Aktivitäten](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)beschrieben.

## <a name="related-topics"></a>Verwandte Themen

[Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)
