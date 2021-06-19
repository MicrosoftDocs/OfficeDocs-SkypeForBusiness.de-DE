---
title: SIS-Daten (Schülerinformationssystem) mit Education Insights synchronisieren
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: SIS-Daten (Schülerinformationssystem) mit Education Insights in Microsoft Teams synchronisieren.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997734"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>SIS-Daten (Schülerinformationssystem) mit Education Insights synchronisieren
Je mehr Daten in [Education Insights](class-insights.md) eingespeist werden, desto besser können Dozenten Ihre Schüler/Studenten sowie Schulleiter ihre Dozenten unterstützen.

Um Einblicke auf Organisationsebene bereitzustellen, müssen wir [School Data Sync (SDS)](/SchoolDataSync) verwenden, um eine Verbindung mit dem Schülerinformationssystem (SIS) herzustellen, damit Insights die hierarchische Struktur des Bildungssystems richtig zugeordnet ist. 

Dies ist *nicht* erforderlich für das Anzeigen von Insights auf Klassenebene als Dozent der Klasse, weil wir die Klassenstruktur und Berechtigungen von Teams verwenden.

## <a name="plan-your-school-data-sync-integration"></a>Planen der School Data Sync (SDS) Integration
Die Microsoft School Data Sync (SDS) stellt die Schüler-/Studenteninformationssystems (SIS)-Daten bereit und bildet die hierarchische Struktur des Bildungssystems und ordnet zu, welcher Benutzer wo zugewiesen ist, sowie zusätzliche Daten zur Hierarchie von Schülern und Organisationen.

Insights funktioniert am besten bei Verwendung des [SDS V2-Dateiformats](/schooldatasync/sds-v2-csv-file-format) und höher, unterstützt aber auch [SDS V1-Dateiformat](/schooldatasync/school-data-sync-format-csv-files-for-sds) *mit eingeschränkter Funktionalität*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Unterschiede zwischen den Dateiformaten SDS V1 und V2

Um Insights optimal nutzen zu können, empfiehlt es sich, das Dateiformat V2 oder V2.1 (bald verfügbar) zu verwenden.

| Datentyp | V1 | V2 |
|:--- |:--- |:--- |
| **Benutzer** | Das V1-Format enthält **nur Lehrkräfte**, sodass Sie zum Festlegen von Berechtigungen auf Organisationsebene für Ihre Bildungsleiter die jeweilige Berechtigung manuell definieren müssen. | Das V2-Format enthält **alle Rollen**, sodass Sie rollenbasierte Berechtigungen zuweisen können. |
| **Organisationen** | Das V1-Format enthält **nur Schulen**, sodass nur eine Aggregationsebene (alle Ihre Schulen) angezeigt wird. Sie können in eine bestimmte Schule hineinzoomen, indem Sie eine flache Liste verwenden. Diese Liste kann jedoch eine große Anzahl von Schulen oder verschiedene Schultypen enthalten, die schwer zu vergleichen sind (z. B. Grundschule mit Sekundarschule oder naturwissenschaftliche mit künstlerischer Schule).<br/><br/> Wenn eine Hierarchie vorhanden ist, können Sie sinnvolle Ebenen erstellen, wie z. B. eine Naturwissenschafts- oder Kunstabteilung.| Das V2-Format enthält **die vollständige Hierarchie Ihres Schulbezirks oder Ihrer Bildungseinrichtung**, einschließlich Universitäten, Fachhochschulen, Fakultäten, Campus, Regionen, Programmen und so weiter.<br/><br/> Mit einer Hierarchie können Sie relevante Aggregationen nach jeder Ebene der Hierarchie sehen, schnell zwischen Organisationseinheiten auf jeder Ebene vergleichen, bestimmten Ebenen Berechtigungen zuweisen, Ziele nach Organsationsebene setzen usw.|

> [!NOTE]
> Kunden können ab dem 15. Juli 2021 kein Onboarding des Dateiformats V2 durchführen und müssen stattdessen das V2.1-Format verwenden. Alle zukünftigen Upgrades und neuen Funktionen werden im V2.1-Format durchgeführt und sind vollständig abwärtskompatibel mit dem Dateiformat V1.

## <a name="best-practices"></a>Bewährte Methoden
Die genaue Abbildung der Hierarchie und die Zuordnung der Personen innerhalb dieser Hierarchie ermöglicht es Insights, genaue Daten und präzisere und relevantere Einblicke für die verschiedenen Typen von Ausbildungsleitern zu liefern.

Je mehr Details Sie hier bereitstellen, desto besser und relevanter werden die Berichte und Spotlights sein.

Hier sind einige bewährte Methoden, die für eine reibungslose Bereitstellung von SDS sorgen, damit Ihre Benutzer Insights optimal nutzen können.

### <a name="file-format-version-to-ue"></a>Zu verwendende Dateiformatversion
*   Verwenden Sie das Dateiformat V2.1 (in Kürze verfügbar), und synchronisieren Sie die optionalen Daten, die von Education Insights verwendet werden.

### <a name="users-and-roles"></a>Benutzer und Rollen
*   Vergewissern Sie sich, dass **alle Benutzer in den Dateien aufgeführt sind**, die Sie bereitstellen und synchronisieren. Dies schließt alle Schüler/Studenten und Mitarbeiter ein, die Daten aus den für sie relevanten Organisationseinheiten sehen müssen.
    Wenn im SIS derzeit nur Lehrkräfte aufgelistet sind, fügen Sie die anderen Benutzer manuell hinzu, bevor Sie die Dateien in SIS hochladen und die Daten synchronisieren.
    Die von Insights gesammelten Statistiken stammen nur von den registrierten Kursteilnehmern. Wenn einige Kursteilnehmer fehlen, führt dies zu irreführenden Daten und Schlussfolgerungen.
    
*   Stellen Sie sicher, dass Sie **Vor- und Nachnamen jedes Benutzers angeben**. Ist dies nicht der Fall, werden sie über ihre E-Mail-Adresse referenziert, was in den Berichten und Spotlights (Karten mit Einblicken in die Aktivitäten oder Leistungen der Schüler/Studenten) zu einer weniger optimalen Erfahrung führt.

*   Die Benotungs-/Jahresstufe muss auf dieser [Zuordnungsliste](#supported-grade-level-values)basieren. 

*   Es ist wichtig, **allen Kursteilnehmern die Stufe "Jahr/Klasse"** hinzuzufügen, damit die Aktivitätsdaten danach aggregiert und gefiltert werden können.    

*   Stellen Sie sicher, dass **jeder Benutzer der entsprechenden Organisationseinheit zugewiesen** wird. Auf diese Weise zeigt Education Insights keine irreführenden Daten in den Education Inisghts-Spotlights an.

    *   Ein Schüler/Student kann mehr als einer Organisationseinheit zugeordnet werden, z. B. Schüler/Studenten, die in einem speziellen Programm oder an zwei Fakultäten eingeschrieben sind. Falls der Kursteilnehmer mehr als einer Organisationseinheit zugefügt ist, geben Sie für jede eine Zeile in der Benutzerdatei für diesen Kursteilnehmer an.
    
    *   Der IT-Administrator kann basierend auf der Organisationseinheit Berechtigungen für Mitarbeiter erteilen. **Stellen Sie sicher, dass die Mitarbeiter der richtigen Einheitenebene** zugeordnet sind, damit sie die erforderlichen Berechtigungen erhalten. Zum Beispiel muss ein Beratungslehrer, der vier Schulen zugewiesen ist, alle Noten in diesen Schulen sehen; ein Schulleiter muss alle Klassen in seiner Schule sehen. 
    
*   **Die Rolle ist wichtig**. Obwohl diese Liste geschlossen ist, versuchen Sie, die Rolle aus [der Liste](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) mit der tatsächlichen Rolle jedes Benutzers abzustimmen, den Sie hochladen. Auf diese Weise können Sie rollenbasierte Berechtigungen entsprechend zuweisen. Geben Sie z. B. allen Schuldirektoren die Berechtigung, die Klassen in ihrer Schule zu sehen, oder allen Professoren, ihre Fakultät zu sehen. 

### <a name="organizations"></a>Organisationen

* Stellen Sie sicher, dass **die tatsächliche und vollständige Hierarchie Ihrer Organisation** widergespiegelt wird. Dies ist durch manuelles Hinzufügen der Datei möglich. In einigen Fällen wird diese Hierarchie nicht im SIS abgebildet. Dennoch kann es hier notwendig sein, die relevante Aggregation nach den einzelnen Hierarchieebenen zu sehen, bestimmten Ebenen Berechtigungen zuzuweisen, Ziele nach Organisationsebene zu setzen und so weiter. 

* Stellen Sie sicher, dass **alle Organisationseinheiten entlang der Organisationsstruktur Schüler/Studenten oder Klassen enthalten**, um Schüler-/Studentendaten für diese zu aggregieren. Es wird empfohlen, dass Schüler/Studenten der untersten Organisationsebene zugewiesen werden.

> [!NOTE]
> Weitere Details zur SDS-Bereitstellung finden Sie unter [SDS planen](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Integrieren von SIS-Daten mit SDS

School Data Sync (SDS) wird mit Office 365 Education bereitgestellt. SDS liest die Daten aus dem Schülerinformationssystem (SIS) einer Bildungseinrichtung und integriert sie in Microsoft-Anwendungen wie Teams, um die automatische Erstellung von Onlineklassen und Benutzern zu ermöglichen.

Außerdem werden die SIS-Daten mit Insights synchronisiert.

Als IT-Administrator können wählen, ob Sie SDS nur für die Bereitstellung, nur Insights oder für beides verwenden.

Um Ihre SIS-Informationen mit Educations Insights zu synchronisieren, befolgen Sie die Anweisungen in [Bereitstellen von SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).

### <a name="deploy-sds"></a>Bereitstellen von SDS
**Wenn Sie SDS bereits verwenden**, empfiehlt es sich, unsere [bewährten Methoden](#best-practices) zu berücksichtigen. 

**Wenn Sie SDS noch nicht verwenden**, müssen Sie es jetzt [bereitstellen](/schooldatasync/deploying-school-data-sync).

Während des Bereitstellungsprozesses können Sie entscheiden, ob Sie SDS für die Bereitstellung von Benutzern und Klassen in Teams oder nur zur Bereitstellung der Benutzer- und Organisationshierarchie für Insights verwenden möchten.

> [!NOTE]
> Wenn es Mitte des Jahres ist und Sie Teams bereits manuell erstellt haben, verwenden Sie SDS nur, um die Benutzer- und Organisationshierarchiedaten für Insights bereitzustellen, und erwägen Sie im nächsten Jahr, SDS auch für die Bereitstellung von Benutzern und Klassen in Teams zu verwenden.

### <a name="verify-the-sync-process"></a>Überprüfen des Synchronisierungsprozesses
Um den Fortschritt des Synchronisierungsstatus zu überprüfen, befolgen Sie die Anweisungen in [SDS for Insights Datenintegrität und -Überwachung](/schooldatasync/sds-for-insights-data-health-and-monitoring).

> [!IMPORTANT]
> Wenn Probleme auftreten, hilft Ihnen der [Kundendienst](https://aka.ms/edusupport) gerne weiter.

## <a name="supported-grade-level-values"></a>Unterstützten Klassenebenen-Werte

In den SDB-Dateien wird die Klassen-/Jahrgangsstufe als Aufzählungswerte definiert. Dies bedeutet, dass Sie nur einen ausgewählten Satz von Werten in der CSV-Datei angeben können. Alles andere als die angegebenen Werte führt zu einem Fehler bei der Synchronisierungsverarbeitung.

Der folgende Abschnitt definiert die unterstützten Werte in der Datei des Benutzers.

### <a name="united-states--worldwide-grade-levels"></a>Vereinigte Staaten / weltweite Klassenstufen
|Wert in der Datei (Spalte Klasse) | Bezeichnung in Insights|
|:---|:---| 
|IT|Säugling|
|PR|Vorschule|
|PK|Vor-Kindergarten|
|TK|Übergangskindergarten|
|KG|Kindergarten|
|01 oder 1|Erste Klasse|
|02 oder 2|Zweite Klasse|
|03 oder 3|Dritte Klasse|
|04 oder 4|Vierte Klasse|
|05 oder 5|Fünfte Klasse|
|06 oder 6|Sechste Klasse|
|07 oder 7|Siebte Klasse|
|08 oder 8|Achte Klasse|
|09 oder 9|Neunte Klasse|
|10|Zehnte Klasse|
|11|Elfte Klasse|
|12|Zwölfte Klasse|
|PS|Post-Sekundär|
|PS1|Studienanfänger|
|PS2|Stundent/Studentin im zweiten Studienjahr|
|PS3|Post-Sekundärer im dritten Studienjahr|
|PS4|Post-Sekundärer im vierten Studienjahr|
|Bachelor-Student|Bachelor-Student|
|Master-Student|Master-Student|
|Doktorand|Doktorand (Absolvent mit Schwerpunkt Forschung)|
|Ehemaliger|Ehemaliger|
|Erwachsenenbildung|Erwachsenenbildung|
|UG|Nicht bewertet|
|Andere|Andere|

### <a name="united-kingdom-year-groups"></a>Vereinigtes Königreich Jahrgangsgruppen
|Wert in der Datei (Spalte Klasse) | Bezeichnung in Insights|
|:---|:---| 
|IT|Kindergarten|
|PR|Vorschule|
|PK|Empfang|
|01 oder 1|Jahr 1|
|02 oder 2|Jahr 2|
|03 oder 3|Jahr 3|
|04 oder 4|Jahr 4|
|05 oder 5|Jahr 5|
|06 oder 6|Jahr 6|
|07 oder 7|Jahr 7|
|08 oder 8|Jahr 8|
|09 oder 9|Jahr 9|
|10|Jahr 10|
|11|Jahr 11|
|12|Jahr 12|
|13|Jahr 13|
|PS|Post-Sekundär|
|PS1|Post-Sekundär Jahr 1|
|PS2|Post-Sekundär Jahr 2|
|PS3|Post-Sekundär Jahr 3|
|PS4|Post-Sekundär Jahr 4|
|Bachelor-Student|Bachelor-Student|
|Master-Student|Master-Student|
|Doktorand|Doktorand (Absolvent mit Schwerpunkt Forschung)|
|Ehemaliger|Ehemaliger|
|Erwachsenenbildung|Erwachsenenbildung|
|UG|Nicht bewertet|
|Andere|Andere|

