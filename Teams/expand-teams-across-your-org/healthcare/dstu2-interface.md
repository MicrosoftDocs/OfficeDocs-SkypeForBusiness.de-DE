---
title: " Patienten App und EHR Integration DSTU2-Schnittstelle"
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integration von Microsoft-Teams Patienten app EHR
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643104"
---
# <a name="dstu2-interface-specification"></a>DSTU2 Interface-Spezifikation

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Einrichten oder Neukonfiguration einen FHIR Server die Microsoft-Teams Patienten app entwickelt ist erforderlich, welche die app muss für den Zugriff auf Daten zu verstehen. Der FHIR-Server muss POST-Anforderungen mithilfe der Pakete für die folgenden Ressourcen unterstützen:

- [Patienten](#patient)
- [Beobachtung](#observation)
- [Bedingung](#condition)
- [Auftreten](#encounter)
- [Allergie Intoleranz](#allergyintolerance)
- [Abdeckung](#coverage)
- [Medikament Reihenfolge](#medication-order)
- [Standort](#location)

> [!NOTE]
> Die Patient Ressource ist die einzigen obligatorischen Ressource (ohne den die app gar nicht geladen werden. Jedoch wird empfohlen, dass der Partner Unterstützung für die oben genannten Ressourcen pro Spezifikationen finden Sie weiter unten Endbenutzer am besten mit der Microsoft-Teams Patienten App implementieren.

Abfragen von der Microsoft-Teams Patienten-app für mehr als einer Ressource bereitstellen eine Bundle (BATCH) von Anforderungen in FHIR die URL des Servers. Der Server jeder Anforderung verarbeitet und gibt ein Bundle Ressourcen mit jeder Anforderung übereinstimmt. Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).

Die folgenden FHIR-Ressourcen sollten Verweis direkte Ressource verfügbar sein.

## <a name="conformance-minimum-required-field-set"></a>Legen Sie die Konformität minimale Pflichtfeld

 Die FHIR-Server muss die Konformität-Anweisung für uns eine konkrete Zusammenfassung der Funktionen haben implementieren. Wir erwarten, dass die folgenden Parameter in einem DSTU2 FHIR Server:

1. Ruhepause
   1. Modus
   2. Interaktion
   3. Ressource: Typ
   4. Sicherheit: [Erweiterung für OAuth-URIs](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (unsere Code erfordert dies zu verstehen, welche Version wir Pivotieren sollte wie wir mehrere Versionen unterstützen.)

Finden Sie unter [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) für andere Details für dieses Feld festzulegen.

## <a name="patient"></a>Patienten

Dies sind die minimale erforderliche Felder, die eine Teilmenge der [Patienten Profil Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder:

1. Name.Family
2. Name.Given
3. Geschlecht
4. Geburtsdatum
5. MRN (ID)

Zusätzlich zu den Feldern Argonaut liest für einen größeren Benutzerkomfort die Patienten app außerdem die folgenden Felder:

1. Name.Use
2. Name.Prefix
3. CareProvider (dieser Referenz für die Patienten Ressource sollte im folgenden Beispiel gezeigten die Anzeigen von Feldern enthalten.)

* * *

    Anforderung: GET <fhir-Server>/Patient/<patient-id>
    
    Antwort: {"ResourceType": "Patient", "Id": "<patient-Id>".
      .
      .
      "Name": [{"verwenden": "offizielle", "Präfix": ["Mr"], "Familie": ["Chau"], "angegebenen": ["Hugh"]}], "ID": [{"verwenden": "offizielle", "Typ": {"Codieren": [{"System": "http://hl7.org/fhir/v2/0203", "Code": "MR"}]}, "Wert": "1234567"}], "Geschlecht": "Männlich", "Geburtsdatum": "1957-06-05 ","CareProvider": [{"anzeigen":"Susanne"}];}

* * *

Eine Ressourcensuche verwendet die POST-Methode zur /Patient/_search und die folgenden Parameter:

1. ID
2. Familie: enthält = (sucht nach allen Patienten, deren Namen Produktfamilie enthält den Wert).
3. angegebenen =\<Substring>
4. Name =\<Substring>
5. Geburtsdatum =(exact match)
6. \_(maximale Anzahl der Ergebnisse an, die zurückgegeben werden sollen) <br> Die Antwort sollte die Gesamtzahl der als Ergebnis der Suche zurückgegebenen Datensätze enthalten und \_Anzahl wird durch die PatientsApp zur Begrenzung der Anzahl der zurückgegebenen Datensätze verwendet werden.
7. ID =\<Mrn>

Ziel ist es, suchen und Filtern zu einem Patienten ein durch Folgendes möglich:

- ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.
- MRN: Dies ist der tatsächlichen Bezeichner für den Patienten, den klinischer Mitarbeiter wissen müssen. Wir wissen, dass diese MRN Bezeichnertyp innerhalb der Bezeichner-Ressource im FHIR basiert
- Name
- Geburtsdatum

Finden Sie im folgenden Beispiel wird dieses Anrufs.

* * *

    : POST <fhir-Server>/Patient/_search anfordern Anforderungstext: angegebenen = Hugh&family = Chau
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle-Id>".
      .
      .
      "Entry": [{"Resource": {"ResourceType": "Patient", "Id": "<patient Id>", "Name": [{"Text": "Hugh Chau", "Familie": ["Chau"], "angegebenen": "" [Hugh]}], "Geschlecht": "Männlich", "Geburtsdatum": "1957-06-05"}, "Suche": {"Mode": "match"}}]}

* * *

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) für andere Details für dieses Feld festzulegen.

## <a name="observation"></a>Beobachtung

Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils auf Anzeichen für meine Argonaut:

 1. Die Übermittlung wirksamer (Datum Zeiten)
 2. Code.Coding.Code
 3. ValueQuantity.Value

Zusätzlich zu den Feldern Argonaut liest für einen größeren Benutzerkomfort die Patienten app außerdem die folgenden Felder:

 1. Code.Coding.Display
 2. ValueQuantity.Unit

Wenn Sie Komponente Beobachtungen verwenden, gilt die Logik für jede Komponente Beobachtung.

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten-Id\>
2. Sortieren: Desc =\<ex-Feld. Datum\>

Ziel ist es, die neuesten wesentlichen Anzeichen zu einem Patienten ein [VitalSigns.DSTU.saz] (Beobachtung?) abrufen können.

* * *

    Anforderung: <fhir-Server>/Beobachtung abrufen? Patient = <patient-Id>&_sort:desc Date&category = wichtiger Gleichheitszeichen (=)
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 20, "Entry": [{"Resource": {"ResourceType": "Beobachtung", "Id": "<resource Id>", "Kategorie": {"Codieren": [{Code":"wichtiger Anzeichen"}];},"Code": {" Codieren": [{"System":"http://loinc.org","Code":"39156-5","Anzeige":"Bmi"}];},"EffectiveDateTime":"2009-12-01","ValueQuantity": {"Wert": 34.4,"Einheit":" kg/m2","System":"http://unitsofmeasure.org","Code":" kg/m2"}},},.
        .
        .
      ] }

* * *

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) für andere Details für dieses Feld festzulegen.

## <a name="condition"></a>Bedingung

Dies sind die minimale erforderliche Felder, die eine Teilmenge des [Argonaut Bedingung Profil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code.Coding[0]. Anzeige

Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:

1. Datum erfasst
2. Schweregrad

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. _count =\<max Results>

Finden Sie im folgenden Beispiel wird dieses Anrufs:

* * *

    Anforderung: <fhir-Server>/Bedingung abrufen? Patient = <patient Id>&_count = 10
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "Bedingung", "Id": "<resource Id>", "Code": {"Codieren": [{               "System": "http://snomed.info/sct", "Code": "386033004", "anzeigen": "Neuropathy (Nerven Beschädigung)"}]}, "DateRecorded": "2018-09-17", "Severity": {"Codieren": [{"Syst Dieser Abschnitt":"http://snomed.info/sct","Code":"24484000","anzeigen":"Severe"}]}},}]}

* * *

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) für andere Details für dieses Feld festzulegen.

## <a name="encounter"></a>Auftreten

Dies sind die minimale erforderliche Felder, die eine Teilmenge der uns Core auftreten Profil "benötigen" Felder:

1. Status
2. Typ [0]. Codieren [0]. Anzeige

Darüber hinaus Felder die folgenden Felder aus uns Core auftreten Profil "unterstützen" müssen

1. Period.Start
2. Position [0]. Location.Display

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. _sort:desc =\<ex-Feld. date>
3. _count =\<max Results>

Ziel ist es, den Patienten letzten bekannten Speicherort abrufen können. Jede verweist auf eine Ressource Speicherort. Der Verweis umfassen ferner Anzeigefeld des Speicherorts. Finden Sie im folgenden Beispiel wird dieses Anrufs.
* * *

    Anforderung: Erste <fhir-Server>/treffen? Patient = <patient-Id>&_sort:desc = Date&_count = 1
    
    Antwort: {"ResourceType": "Bundle", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "Auftreten", "Id": "<resource Id>", "ID": [{"verwenden": "offizielle", "Wert": "<id>"}], "Status" : "angekommen", "Typ": [{"Codieren": [{"anzeigen": "Termin"}],}], "Patient": {"Referenz": "Patient/<patient-Id>"} "Punkt": {"start": "09/17/2018 1:00:00 PM"}, "Ort": [{              "Position": {"anzeigen": "Clinic – ENT"},}]}}]}

* * *

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) für andere Details für dieses Feld festzulegen.

## <a name="allergyintolerance"></a>AllergyIntolerance

Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils Argonaut AllergyIntolerance:

1. Code.Text
2. Code.Coding[0]. Anzeige
3. Status

Zusätzlich zu den Feldern Argonaut liest für einen größeren Benutzerkomfort die Patienten app außerdem die folgenden Felder:

1. RecordedDate
2. Note.Text
3. Reaktion [.]. Substance.Text
4. Reaktion [.]. Manifestation [.]. Text
5. Text.Div

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient = \<Patienten Id>

Finden Sie im folgenden Beispiel wird dieses Anrufs:

* * *

    Anforderung: <fhir-Server>/AllergyIntolerance abrufen? Patient = <patient Id>
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "AllergyIntolerance", "Id": "<resource Id>", "RecordedDate": "2018-09-17T07:00:00.00 0Z","Inhalt": {"Text":"Cashew Nuts"},"Status":"bestätigt","Reaktion": [{"Inhalt": {"Text":"Cashew Mutter allergener extrahieren um injizierbare Produkt"},"Manifestati auf": [{"Text":"Anaphylactic Reaktion"}]}]}}]}

* * *

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) für andere Details für dieses Feld festzulegen.

## <a name="medication-order"></a>Medikament Reihenfolge

Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils Argonaut MedicationOrder:

1. DateWritten
2. Prescriber.Display
3. Medication.Display (wenn Referenz)
4. Medication.Text (wenn Konzept)

Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:

1. DateEnded
2. DosageInstruction.Text
3. Text.Div

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. _count =\<max Results>

Finden Sie im folgenden Beispiel wird dieses Anrufs:

* * *

    Anforderung: <fhir-Server>/MedicationOrder abrufen? Patient = <patient Id>&_count = 10
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "MedicationOrder", "Id": "<resource Id>", "DateWritten": "2018-09-17", "Medi CationCodeableConcept": {"Text":"Lisinopril 20 MG mündliche Tablet"},"prescriber": {"anzeigen":"Susanne"},"DosageInstruction": [{"Text":"1 täglich"}]}}]}

* * *  

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) für andere Details für dieses Feld festzulegen.

## <a name="coverage"></a>Abdeckung

Dies sind die minimalen Pflichtfelder nicht fallen uns Core oder Argonaut Profile:

1. Erstattungsorganisationen sicherzustellen

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>

Finden Sie im folgenden Beispiel wird dieses Anrufs:

* * *

    Anforderung: <fhir-Server>/Abdeckung abrufen? Patient = <patient Id>
    
    Antwort: {"ResourceType": "Bundle", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "Abdeckung", "Id": "<resource Id>", "Plan": "No primären Versicherungsvertreter", "Abonnenten": {"Referenz": "Patient / <patient Id> "}}}]}

* * *

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) für andere Details für dieses Feld festzulegen.

## <a name="location"></a>Ort

Diese Ressource wird nur als Verweis auf die Ressource [auftreten](#encounter) verwendet.

Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) für andere Details für dieses Feld festzulegen.
