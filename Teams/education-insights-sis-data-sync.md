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
ms.openlocfilehash: 8f6d4a7dca340d297543abb3620a36cdd804ca9f
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196579"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>SIS-Daten (Schülerinformationssystem) mit Education Insights synchronisieren
Je mehr Daten in [Education Insights](class-insights.md) eingespeist werden, desto besser können Dozenten Ihre Schüler/Studenten sowie Schulleiter ihre Dozenten unterstützen.

Um Einblicke auf Organisationsebene bereitzustellen, müssen wir [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) verwenden, um eine Verbindung mit dem Schülerinformationssystem (SIS) herzustellen, damit Insights die hierarchische Struktur des Bildungssystems richtig zugeordnet ist. 

Dies ist *nicht* erforderlich für das Anzeigen von Insights auf Klassenebene als Dozent der Klasse, weil wir die Klassenstruktur und Berechtigungen von Teams verwenden.

## <a name="plan-your-sis-integration"></a>Planen Ihrer SIS-Integration
Die SIS-Daten bieten die hierarchische Struktur des Bildungssystems und bilden ab, welcher Benutzer wo zugeordnet ist.

Insights funktioniert am besten unter Verwendung des [SDS V2-Dateiformats](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format), unterstützt aber auch das [SDS V1-Dateiformat](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) mit *eingeschränkter* Funktionalität.

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Unterschiede zwischen den Dateiformaten SDS V1 und V2

| Datentyp |   V1 | V2 (empfohlen für neue Kunden) |
|:--- |:--- |:--- |
| **Benutzer** | Das V1-Format enthält **nur Dozenten**, sodass Sie zum Festlegen von Berechtigungen auf Organisationsebene für Ihre Schulleiter nach ihnen suchen und die Berechtigung für jeden einzelnen manuell festlegen müssen. | Das V2-Format enthält **alle Rollen**, sodass Sie rollenbasierte Berechtigungen zuweisen können. |
| **Organisationen** | Das V1-Format enthält **nur Schulen**, sodass nur eine Aggregationsebene (alle Ihre Schulen) angezeigt wird. Sie können in eine bestimmte Schule hineinzoomen, indem Sie eine flache Liste verwenden. Diese Liste kann jedoch eine große Anzahl von Schulen oder verschiedene Schultypen enthalten, die schwer zu vergleichen sind (z. B. Grundschule mit Sekundarschule oder naturwissenschaftliche mit künstlerischer Schule).<br/><br/> Wenn eine Hierarchie vorhanden ist, können Sie sinnvolle Ebenen erstellen, wie z. B. eine Naturwissenschafts- oder Kunstabteilung.| Das V2-Format enthält **die vollständige Hierarchie Ihres Schulbezirks oder Ihrer Bildungseinrichtung**, einschließlich Universitäten, Fachhochschulen, Fakultäten, Campus, Regionen, Programmen und so weiter.<br/><br/> Mit einer Hierarchie können Sie relevante Aggregationen nach jeder Ebene der Hierarchie sehen, schnell zwischen Organisationseinheiten auf jeder Ebene vergleichen, bestimmten Ebenen Berechtigungen zuweisen, Ziele nach Organsationsebene setzen usw.|

### <a name="type-of-data-required"></a>Benötigter Datentyp
Die folgende Tabelle zeigt die Art der Daten, die benötigt werden, um das Beste aus Insights herauszuholen.

| Datentyp | Beispiele dafür, was Sie bereitstellen müssen|Warum ist das wichtig?|
|:--- |:--- |:--- |
| **Benutzer** |   Rolle (z. B. Schüler/Student)<br/> [Klassen-/Jahrgangsstufe](#supported-grade-level-values) (z. B. 10)<br/> Organisation (Name) | Wenn wir jede Person korrekt ihrer Rolle, ihrer Klassen-/Jahrgangsstufe und ihrer Organisation zuordnen, können wir sicherstellen, dass die Zusammenfassungen und Aggregationen korrekt sind.|
| **Organisationen** | Organisationstyp (z. B. Fachhochschule) |   Die Hierarchie hier ist wichtig. So können Schulen beispielsweise zu einem Schulbezirk gehören, und dieser Schulbezirk kann zu einem Bundesland/-staat gehören.<br/> Wenn ein Leiter eines Schulbezirks berechtigt ist, Daten zu sehen, gilt dies nur für die Schulen in diesem Schulbezirk.|
| **Klassen** | Titel (z. B. Computerwissenschaft 101) | Diese Tabelle detailliert, welche Kurse in der Organisation abgehalten werden. Diese Tabelle muss richtig zugeordnet sein, damit der Schüler/Student dem richtigen Kurs zugeordnet werden kann. |
| **Registrierung** | Rolle (z. B. Schüler/Student) | Diese Tabelle ist für Schüler/Studenten und Dozenten und dadurch wissen wir, in welchem Kurs sie eingeschrieben sind. |

> [!NOTE]
> Während des Bereitstellungsprozesses können Sie entscheiden, ob Sie SDS für die Bereitstellung von Benutzern und Klassen in Teams oder nur zur Bereitstellung von Daten für Insights verwenden möchten.

## <a name="best-practices"></a>Bewährte Methoden
Die genaue Abbildung der Hierarchie und die Zuordnung der Personen innerhalb dieser Hierarchie ermöglicht es Insights, genaue Daten und präzisere und relevantere Einblicke für die verschiedenen Typen von Ausbildungsleitern zu liefern.

Je mehr Details Sie hier bereitstellen, desto besser und relevanter werden die Berichte und Spotlights sein.
Hier sind einige bewährte Methoden, die für eine reibungslose Bereitstellung von SDS sorgen, damit Ihre Benutzer Insights optimal nutzen können.

### <a name="users"></a>Benutzer
*   Vergewissern Sie sich, dass *alle Benutzer* in den von Ihnen angegebenen und synchronisierten Dateien aufgelistet sind. Dies schließt alle Schüler/Studenten und Mitarbeiter ein, die Daten zu den von ihnen abgedeckten Organisationseinheiten sehen müssen.

    Wenn im SIS derzeit nur Lehrkräfte aufgelistet sind, fügen Sie die anderen Benutzer manuell hinzu, bevor Sie die Dateien in SIS hochladen und die Daten synchronisieren.

    Wenn einige Schüler oder Studenten fehlen, werden die Statistiken von Insights nur von den registrierten Schülern/Studierenden gesammelt, was zu irreführenden Daten und Schlussfolgerungen führt.
    
*   Stellen Sie sicher, *Vor- und Nachnamen jedes Benutzers anzugeben*. Ist dies nicht der Fall, werden sie über ihre E-Mail-Adresse referenziert, was in den Berichten und Spotlights (Karten mit Einblicken in die Aktivitäten oder Leistungen der Schüler/Studenten) zu einer weniger positiven Erfahrung führt.

*   Die *Klassen-/Jahrgangsstufe muss als zweistellige Zahl eingegeben werden* (z. B. 07 für Jahrgang 7). Schauen Sie sich die [Zuordnungsliste an](#supported-grade-level-values). 

*   Es ist wichtig, *die Klassen-/Jahrgangsstufe bei allen Schülern/Studenten hinzuzufügen*, damit die Daten nach Klassen-/Jahrgangsstufe gefiltert werden können.    

*   Stellen Sie sicher, dass *jeder Benutzer der entsprechenden Organisationseinheit zugewiesen* wird. Auf diese Weise werden wir in unseren Spotlights keine irreführenden Daten anzeigen, die auf aggregierten Daten für jedes Gerät basieren.

    *   Ein Schüler oder Student kann mehr als einer Organisationseinheit zugeordnet werden, z. B. Studenten, die in einem speziellen Programm oder an zwei Fakultäten eingeschrieben sind. Geben Sie in einem solchen Fall zwei Zeilen in der Benutzerdatei für diesen Schüler/Student an – eine für jede Organisation.
    
    *   Basierend auf der Organisationseinheit für Mitarbeiter können Sie die relevanten Berechtigungen definieren. Stellen Sie sicher, dass sie mit der richtigen Organisationsebene verknüpft sind, damit sie die erforderlichen Berechtigungen erhalten. Zum Beispiel muss ein Beratungslehrer, der vier Schulen zugewiesen ist, alle Klassen in diesen Schulen sehen; ein Schulleiter muss alle Klassen in seiner Schule sehen. 
    
*   Die Rolle ist von zentraler Bedeutung. Obwohl diese Liste geschlossen ist, versuchen Sie, die Rolle aus [der Liste](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) mit der tatsächlichen Rolle jedes Benutzers abzustimmen, den Sie hochladen. Auf diese Weise können Sie rollenbasierte Berechtigungen entsprechend zuweisen. Geben Sie z. B. allen Schuldirektoren die Berechtigung, die Klassen in ihrer Schule zu sehen, oder allen Professoren, ihre Fakultät zu sehen. 

### <a name="organizations"></a>Organisationen

* Stellen Sie sicher, *die tatsächliche Hierarchie Ihrer Organisation abzubilden*. Dies ist durch manuelles Hinzufügen der Datei möglich. In einigen Fällen wird diese Hierarchie nicht im SIS abgebildet. Dennoch kann es hier notwendig sein, die relevante Aggregation nach den einzelnen Hierarchieebenen zu sehen, bestimmten Ebenen Berechtigungen zuzuweisen, Ziele nach Organisationsebene zu setzen und so weiter. 

* Stellen Sie sicher, dass *alle Organisationseinheiten entlang der Organisationsstruktur Schüler/Studenten oder Klassen enthalten*, um Schüler-/Studentendaten für diese zu aggregieren. Es wird empfohlen, dass Schüler/Studenten der untersten Organisationsebene zugewiesen werden.

> [!NOTE]
> Weitere Details zur SDS-Bereitstellung finden Sie unter [SDS planen](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-using-sds"></a>Integrieren Sie SIS mithilfe von SDS

School Data Sync (SDS) wird mit Office 365 Education bereitgestellt. SDS liest die Daten aus dem Schülerinformationssystem (SIS) einer Bildungseinrichtung ein und integriert sie in Teams, um die automatische Erstellung von Onlineklassenräumen und Benutzern zu ermöglichen.

Außerdem werden die SIS-Daten mit Insights synchronisiert.

### <a name="sync-with-insights"></a>Synchronisierung mit Insights

Zuerst müssen Sie die Insights-Umschalttaste aktivieren, um den Synchronisierungsvorgang zu starten.

* Gehen Sie im [**SDS-Portal**](https://sds.microsoft.com) zu **Einstellungen**, scrollen Sie nach unten zu **Daten für Insights sammeln** und überprüfen Sie, ob es aktiviert ist (es ist standardmäßig *aktiviert*).

* Scrollen Sie nach unten zum nächsten Schalter, **Organisationsdaten aus SDS synchronisieren (Vorschau)** und aktivieren sie diesen.

Wenn die Option *Organisationsdaten aus SDS synchronisieren (Vorschau)* auf der Einstellungsseite nicht sehen, gehen Sie zur [Anmeldeseite](https://aka.ms/insights/join), um Ihre Informationen einzugeben und ein Teammitglied wird sich mit Ihnen in Kontakt setzen.

:::image type="content" source="media/insights-sds-settings.png" alt-text="Synchronisierung mit Insights-Umschalttaste":::

### <a name="deploy-sds"></a>Bereitstellen von SDS
**Wenn Sie SDS bereits verwenden**, empfiehlt es sich, unsere [bewährten Methoden](#best-practices) zu berücksichtigen. 

Um Ihre aktuellen Profile mit Insights zu synchronisieren, gehen Sie zu Ihren **Synchronisierungsprofilen**, klicken Sie auf **Bearbeiten** und wählen Sie **Mit Insights synchronisieren** aus. Für die erste Synchronisierung empfehlen wir, 24 Stunden zu warten, bis die Berichte nach dem Aktualisieren der Daten aus Ihrem SIS verfügbar sind.  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="Umschalttaste "Profil mit Insights synchronisieren"":::

**Wenn Sie SDS noch nicht verwenden**, müssen Sie es jetzt [bereitstellen](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).

Während des Bereitstellungsprozesses können Sie entscheiden, ob Sie SDS für die Bereitstellung von Benutzern und Klassen in Teams oder nur zur Bereitstellung von Daten für Insights verwenden möchten.

> [!NOTE]
> Wenn es Mitte des Jahres ist und Sie Teams bereits manuell erstellt haben, verwenden Sie SDS nur, um die Daten für Insights bereitzustellen, und erwägen Sie im nächsten Jahr, SDS auch für die Bereitstellung von Benutzern und Klassen in Teams zu verwenden.

### <a name="verify-the-sync-process"></a>Überprüfen des Synchronisierungsvorgangs
Ein neuer Statusbereich wird neben "Organisationsdaten aus SDS synchronisieren (Vorschau)" auf der Einstellungsseite angezeigt.
 
*   Wenn der Status **In Bearbeitung** lautet, warten Sie bis zu 24 Stunden nach der Bereitstellung des SDS-Profils.

*   Wenn der Status **Abgeschlossen** lautet – Herzlichen Glückwunsch! Sie können Sie Insights auf Organisationsebene anzeigen und mit dem nächsten Schritt fortfahren.

*   Wenn der Status **Mit Fehlern abgeschlossen**, **Mit Warnungen abgeschlossen** oder **Abgebrochen** lautet, laden Sie die Protokolldatei herunter, die die Fehler und Warnungen für die letzte Synchronisierung enthält, und überprüfen Sie, ob Sie diese Fehler beheben können. 

> [!IMPORTANT]
> Wenn Probleme auftreten, hilft Ihnen der [Kundendienst](https://aka.ms/edusupport) gerne weiter.

## <a name="supported-grade-level-values"></a>Unterstützten Klassenebenen-Werte

In den SDB-Dateien wird die Klassen-/Jahrgangsstufe als Aufzählungswerte definiert. Dies bedeutet, dass Sie nur einen ausgewählten Satz von Werten in der CSV-Datei angeben können. Alles andere als die angegebenen Werte führt zu einem Fehler bei der Synchronisierungsverarbeitung.

> [!NOTE]
> Die *Klassen-/Jahrgangsstufe muss als zweistellige Zahl eingegeben werden* (z. B. 07 für Jahrgang 7).

Der folgende Abschnitt definiert die unterstützten Werte in der Datei des Benutzers.

### <a name="united-states--worldwide-grade-levels"></a>Vereinigte Staaten / weltweite Klassenstufen
|Wert in der Datei (Spalte Klasse) | Bezeichnung in Insights|
|:---|:---| 
|IT|Säugling|
|PR|Vorschule|
|PK|Vor-Kindergarten|
|TK|Übergangskindergarten|
|KG|Kindergarten|
|01|Erste Klasse|
|02|Zweite Klasse|
|03|Dritte Klasse|
|04|Vierte Klasse|
|05|Fünfte Klasse|
|06|Sechste Klasse|
|07|Siebte Klasse|
|08|Achte Klasse|
|09|Neunte Klasse|
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
|01|Jahr 1|
|02|Jahr 2|
|03|Jahr 3|
|04|Jahr 4|
|05|Jahr 5|
|06|Jahr 6|
|07|Jahr 7|
|08|Jahr 8|
|09|Jahr 9|
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
