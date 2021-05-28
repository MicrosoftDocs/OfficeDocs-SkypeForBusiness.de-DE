---
title: 'App für Überwachung von Patienten für Teams IT- und Compliance-Administratoren '
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
description: Informationen zur Überwachung der Patienten-App für Teams Administratoren
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a2c5b006384d113dde82f702dee68a82b99685f6
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697832"
---
# <a name="audit-logs-for-patients-app"></a>Überwachungsprotokolle für die Patienten-App

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Microsoft Teams ersetzt. Die Daten der Patienten-App werden in dem Gruppenpostfach der Office 365-Gruppe gespeichert, das zum Team gehört. Alle der Patienten-App zugeordneten Daten bleiben in dieser Gruppe erhalten, auf sie kann aber nicht mehr über die Benutzeroberfläche zugegriffen werden. Benutzer können ihre Listen mithilfe der App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) neu erstellen.
>
>Mit der Listen-App können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen. Sehen Sie sich die Vorlage "Patienten" in der Listen-App an, um die ersten Schritte zu unternehmen. Weitere Informationen zum Verwalten der Listen-App in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Mit einem Überwachungsprotokoll für Patienten-App-Aktivitäten können Teams für die Reaktion auf Vorfälle Änderungen an den elektronischen Krankenakten (Electronic Medical Records, EMR) oder PHI (Patient Healthcare Information) eines Patienten überprüfen und feststellen, ob Änderungen oder Verbesserungen der Richtlinien oder Verfahren für den PHI-Zugriff in Produktivitätstools erforderlich sind. Die Überwachungsprotokollereignisse behandeln Aktionen, die über die Benutzeroberfläche der Patienten-App ausgeführt werden.

## <a name="meet-hipaa-requirements"></a>Erfüllen der HIPAA-Anforderungen

Gemäß den HIPAA-Richtlinien müssen Anbieter im Gesundheitswesen Aufzeichnungen über alle Zugriffe auf PHI speichern, damit die Änderungen überwacht werden können. Microsoft verpflichtet sich für unternehmensweite Kunden, die Microsoft Teams verwenden und ihnen dabei helfen, HIPAA-Anforderungen und -Steuerelemente zu erfüllen. Der Zugriff auf PHI über die Patienten-App wird vollständig nachverfolgt, und Protokolle werden im Microsoft 365 Compliance Center verfügbar gemacht, wie im Artikel zur Überwachungsprotokollsuche [beschrieben.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

> [!IMPORTANT]
> Die Pflege der Patientendaten wird vom Gesetz dem Gesundheitswesen unter die Last gestellt. Das Gesetz berechtigt Patienten zum Datenschutz und erfordert, dass ein IT-Administrator oder HIPAA-Controller problemlos bestimmen kann, welche Krankenschwester, Klinikangestellte oder Sozialarbeiter auf Patientenakten zugegriffen oder diese geändert haben. Eines der häufigsten Beispiele für eine Verletzung des PHI-Zugriffs ist der Zugriff auf VIP-Patienten. Die Überwachungsprotokollfunktion ist erforderlich, um Untersuchungen bei Verletzungen des PHI-Zugriffs durchzuführen und die HIPAA-Anforderungen zu erfüllen.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Aktivieren von Überwachungsprotokollen für die Patienten-App

Eine Überwachung hängt von mehreren vorherigen Konfigurationen ab:

1. Der Administrator muss mit seinem FFORMAT-Dienstanbieter zusammenarbeiten, um EMR in einem von der Patienten-App verwendeten Format zu verwenden. 
2. Ein Administrator eines Gesundheitswesens muss die Patienten-App in Teams Admin Center aktivieren. Weitere [Informationen finden Sie](../../teams-app-setup-policies.md) unter Verwalten Microsoft Teams Richtlinien für die App-Einrichtung in den zugehörigen Artikeln.
3. Der Administrator muss Aktivitätsprüfungen auf die gleiche Weise aktivieren wie jede Aktivitätsprotokollprüfung, wie [unter](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) Bevor Sie beginnen und Überwachungsprotokollsuche aktivieren oder [deaktivieren beschrieben.](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Wenn die Überwachungsprotokollierung bereits on ist, ist für die Patienten-App nichts Besonderes erforderlich. Jedes Mal, wenn ein Gesundheitswesensanbieter die App in einem Team installiert und führt, zeichnen die Überwachungsprotokolle ihre PHI-Aktivität auf.
4. Der Administrator müsste dann die Verfügbarkeit der Patienten-App ankündigen, und Mitarbeiter im Gesundheitswesen mussten mit der Generierung von Aktivitäten beginnen, um in ein Audit eingeschlossen zu werden.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Ausführen einer Überwachung

Anweisungen zum Ausführen einer Suche im Aktivitätsprotokoll finden Sie unter [Durchsuchen des Überwachungsprotokolls.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Protokollierte Aktivitäten für die Patienten-App

Die Patienten-App verfügt über eigene protokollierte Aktivitäten, die in der folgenden Tabelle aufgeführt sind:

|Anzeigename | Vorgang | Beschreibung|
|:---|:---|:---|
| Angezeigte Patientenliste | PatientListView | Ein Benutzer hat eine Patientenliste angezeigt.|
| Liste der gelöschten Patienten | PatientListDelete | Ein Benutzer hat eine Liste von Patienten gelöscht.|
| Patient zur Liste hinzugefügt | PatientListAdd Patient | Ein Patient wurde zu einer Liste der Patienten hinzugefügt. |
| Notiz für Patienten hinzugefügt | PatientNoteAdd | Eine Notiz wurde zu einem Patientenakte hinzugefügt. |
| Patientenschema erstellt | PatientSchemaCreate | Es wurde eine Reihe von Spalten erstellt, die in der Krankenakte verwendet werden. |
| Ein Benutzer hat einen Export initiiert | ExportInitiation | Patientendaten wurden aus der Patienten-App in eine Patientendatei Excel exportiert. Die Datei wird auf der SharePoint-Website des Teams gespeichert. |
| Patientenliste erstellt | PatientListCreate | Ein Benutzer hat eine Liste der Patienten erstellt.|
| Standard-Patientenliste festlegen| PatientListDefaultSet| Ein Benutzer hat eine bestimmte Liste als Standardliste festgelegt.|
| Patient aus Liste entfernt| PatientListRemove Patient | Ein Patient wurde aus einer Liste von Patienten entfernt. |
| Gesuchter Patient | PatientSearch | Es wurde ein Patientendatensatz im EHR-Dienst durchsucht. |
| Aktualisiertes Patientenschema | PatientSchemaUpdate  | Es wurde ein vorhandener Satz von Spalten aktualisiert, die in der Krankenakte verwendet wurden. |<!-- | Patient in andere Liste verschoben| PatientMoved | Die Krankenakte wurde aus einer Liste in eine andere verschoben. |-->
| Umbenannte Patientenliste | PatientListRename | Eine Liste der Patienten wurde umbenannt. |
| Bearbeitete Spalten in der Patientenliste | PatientListEditColumns | Eine Spalte in einer Liste von Patienten wurde bearbeitet (hinzugefügt oder entfernt). |
| Patientendetails anzeigen | PatientView | Ein Benutzer hat eine Krankenakte angezeigt.|
| Bearbeitete Patientendetails | PatientDetailsEdit | Es wurde ein Detail zu einer Krankenakte bearbeitet. |
| Festlegen der EHR-Verbindung | EHRConnectionSet | Legen Sie die URL für die Verbindung mit der EHR FEHR-Dienstverbindung festgelegt. Beispiel: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

Sie können Ihr Audit nach Bedarf anpassen, um nach diesen protokollierten Aktivitäten zu suchen oder nach diesen zu filtern.

Protokollierte Aktivitäten für Microsoft Teams im Allgemeinen werden in den Microsoft Teams [beschrieben.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Verwandte Themen

[Durchsuchen des Überwachungsprotokolls](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
