---
title: Patienten-APP und EPA-Integrations DSTU2-Schnittstelle
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
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Erfahren Sie mehr über die DSTU2-Schnittstellenspezifikation in Teams, einschließlich der Einrichtung oder Neukonfiguration eines FHIR-Servers für die Zusammenarbeit mit der Microsoft Teams-Patienten-app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f09f43af431b3f0cc6d9f984171206f2549a550a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136955"
---
# <a name="dstu2-interface-specification"></a>Benutzeroberflächenspezifikation DSTU2

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss. Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:

- [Patienten](#patient)
- [Beobachtung](#observation)
- [Bedingung](#condition)
- [Auftreten](#encounter)
- [Allergie-Intoleranz](#allergyintolerance)
- [Abdeckung](#coverage)
- [Medikations Bestellung](#medication-order)
- [Standort](#location)

> [!NOTE]
> Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen werden kann. Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.

Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource Posten ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers. Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die mit den einzelnen Anforderungen übereinstimmen. Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).

Auf alle folgenden FHIR-Ressourcen sollte über direkten Ressourcenverweis zugegriffen werden können.

## <a name="conformance-minimum-required-field-set"></a>Konformitäts mindestanforderungs Feld Satz

 Der FHIR-Server muss die Konformitätserklärung für uns implementieren, um eine sachliche Zusammenfassung seiner Funktionen zu haben. Wir erwarten die folgenden Parameter in einem DSTU2-FHIR-Server:

1. Rest
   1. Modus
   2. Interaktion
   3. Ressource: Typ
   4. Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten, da wir mehrere Versionen unterstützen.)

Weitere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="patient"></a>Patienten

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge der [Argonaut-Patientenprofil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder sind:

1. Name. Familie
2. Name. given
3. Geschlecht
4. BirthDate
5. MRN (Bezeichner)

Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:

1. Name. use
2. Name. Prefix
3. CareProvider (dieser Verweis auf die Patienten Ressource sollte die Anzeigefelder umfassen, die im folgenden Beispiel gezeigt werden.)

* * *

    Request: besorgen Sie sich <fhir-Server>/Patient/<Patienten-ID>
    
    Response: {"Ressourcenname": "Patient", "ID": "<Patient-ID>";
      .
      .
      "Name": [{"Use": "offiziell"; "prefix": ["Mr"], "Familie": ["Chau"], "given": ["Hugh"]}], "Identifier": [{"Use": "offiziell", "Typ": {"Codierung": [{"System": "https://hl7.org/fhir/v2/0203"; "Code": "Herr"}]}, "Wert": "1234567"}], "Geschlecht": "männlich", "Geburtstag": "1957-06-05", "careProvider": [{"Display": "Jane Doe"}],}

* * *

Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:

1. ID
2. Familie: Contains = (sucht nach allen Patienten, deren Familienname den Wert enthält.)
3. given =\<Teilzeichenfolge>
4. Name =\<Teilzeichenfolge>
5. Geburtsdatum = (exakte Übereinstimmung)
6. \_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen) <br> Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben \_wurden, und die Anzahl wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.
7. Identifier =\<MRN>

Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:

- ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.
- MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde. Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.
- Name
- BirthDate

Sehen Sie sich das folgende Beispiel für diesen Aufruf an.

* * *

    Request: Post <fhir-Server>/Patient/_search Request Body: given = Hugh&Family = Chau
    
    Response: {"Ressourcenname": "Bundle", "ID": "<Bundle-ID>";
      .
      .
      "Eintrag": [{"Ressource": {"Ressourcen": "Patient"; "ID": "<Patient-ID>"; "Name": [{"Text": "Hugh Chau", "Familie": ["Chau"], "given": ["Hugh"]}], "Gender": "männlich"; "Geburtsdatum": "1957-06-05"}, "suchen": {"der Modus": "Vergleich"}}]

* * *

Weitere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="observation"></a>Beobachtung

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut Vital Signs-Profils sind:

 1. Effektiv (Datum oder Zeitraum)
 2. Code. Coding. Code
 3. ValueQuantity. Value

Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:

 1. Code. Coding. Display
 2. ValueQuantity. Unit

Wenn Sie Komponenten Beobachtungen verwenden, gilt dieselbe Logik für jede Komponentenüberwachung.

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID\>
2. Sort: DESC =\<Feld Ex. Datum\>

Das Ziel besteht darin, die neuesten vitalen Zeichen für einen Patienten abzurufen [VitalSigns. ДСТУ. SAZ] (Observation?).

* * *

    Request: besorgen Sie sich <fhir-Server>/Observation? Patient =<Patient-ID>&_sort:d ESC = Datum&Kategorie = Vital-Zeichen
    
    Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Type": "searchset", "Total": 20; "Eintrag": [{"Resource": {"Ressource": "Observation"; "ID": "<Resource-ID>"; "Category": {"Coding": [{Code ":" Vital-Signs "}],}," Code ": {" Coding ": [{" System "http://loinc.org:" ";" Code ":" 39156-5 ";" Display ":" BMI "}],}," effectiveDateTime ":" 2009-12-01 ";" valueQuantity ": {" Wert ": 34,4;" Einheit ":" kg/m2 ";" System "http://unitsofmeasure.org:" "," Code ":" kg/m2 "}},},.
        .
        .
      ] }

* * *

Weitere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="condition"></a>Bedingung

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind:

1. Code. Coding [0]. Anzeigen

Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:

1. Aufnahmedatum
2. Schweregrad

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _Count =\<maximale Ergebnisse>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

* * *

    Request: besorgen Sie sich <fhir-Server>/Condition? Patient =<Patient-ID>&_count = 10
    
    Response: {"Ressource": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "Bedingung"; "ID": "<Resource-ID>"; "Code": {"Coding": [{"System": "http://snomed.info/sct"; "Code": "386033004", "Display": "Neuropathie (Nerve Damage)"}]}, "dateRecorded": "2018-09-17"; "Severity": {"Coding": [{"System"http://snomed.info/sct: ""; "Code": "24484000"; "Anzeige": "schwere"}]}},}]}

* * *

Weitere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="encounter"></a>Auftreten

Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder für das US-Core-Encounter-Profil "muss" handelt:

1. Status
2. Geben Sie [0] ein. Codierung [0]. Anzeigen

Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils

1. Periode. Start
2. Ort [0]. Location. Display

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _sort: DESC =\<Feld Ex. Datum>
3. _Count =\<maximale Ergebnisse>

Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können. Jede Begegnung verweist auf eine Standortressource. Der Bezug umfasst auch das Anzeigefeld des Standorts. Sehen Sie sich das folgende Beispiel für diesen Aufruf an.
* * *

    Request: besorgen Sie sich <fhir-Server>/Encounter? Patient =<Patient-ID>&_sort:d ESC = Datum&_count = 1
    
    Antwort: {"Ressourcen": "Bundle", "Type": "searchset", "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "Begegnung"; "ID": "<Resource-ID->"; "Bezeichner": [{"Use": "offiziell"; "" "<id>" "" ""; Status ":" angekommen ";" Typ ": [{" Coding ": [{" Display ":" Termin "}],}]," Patient ": {" Bezug ":" Patienten-<-ID> "}," Zeitraum ": {" Start ":" 09/17/2018 1:00:00 pm "}," Ort ": [{" Ort ": {" Anzeige ":" Clinic-HNO "},}]}}]}

* * *

Weitere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="allergyintolerance"></a>AllergyIntolerance

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-AllergyIntolerance-Profils sind:

1. Code. Text
2. Code. Coding [0]. Anzeigen
3. Status

Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:

1. RecordedDate
2. Hinweis. Text
3. Reaktion [..]. Substanz. Text
4. Reaktion [..]. Manifestation [..]. Text
5. Text. div

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient = \<Patienten-ID>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

* * *

    Request: besorgen Sie sich <fhir-Server>/allergyintolerance? Patient =<Patienten-ID>
    
    Response: {"Ressource": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "AllergyIntolerance"; "ID": "<Resource-ID>"; "recordedDate": "2018-09-17T07:00:00.000 z", "Substanz": {"Text": "Cashew-Nüsse"}, "Status": "bestätigt"; "Reaktion": [{"Substanz": {"Text": "Cashew-Nuss-Allergen Extrakt injizierbares Produkt"}, "Manifestation": [{"Text": "anaphylaktischer-Reaktion"}]}]}}]}

* * *

Weitere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="medication-order"></a>Medikations Bestellung

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-MedicationOrder-Profils sind:

1. DateWritten
2. Verschreiber. Display
3. Medikation. Display (wenn Bezug)
4. Medikation. Text (wenn Konzept)

Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:

1. DateEnded
2. DosageInstruction. Text
3. Text. div

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _Count =\<maximale Ergebnisse>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

* * *

    Request: besorgen Sie sich <fhir-Server>/medicationorder? Patient =<Patient-ID>&_count = 10
    
    Response: {"Ressource": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "MedicationOrder"; "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"Text": "Lisinopril 20 mg Oral Tablet"}, "Verschreiber": {"Anzeige": "Jane Doe"}, "dosageInstruction": [{"Text": "1 Daily"}]}}]}

* * *  

Weitere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="coverage"></a>Abdeckung

Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:

1. Zahlenden

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

* * *

    Request: besorgen Sie sich <fhir-Server>/Coverage? Patient =<Patienten-ID>
    
    Response: {"Ressourcen": "Bundle"; "Typ": "searchset", "Total": 1; "Eintrag": [{"Resource": {"Ressourcentyp": "Coverage"; "ID": "<Resource-ID>"; "Plan": "keine Erstversicherung"; "Teilnehmer": {"Bezug": "Patient/<Patient-ID>"}}}]}

* * *

Weitere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="location"></a>Ort

Diese Ressource wird nur als Referenz für die [Encounter](#encounter) -Ressource verwendet.

Weitere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) Informationen zu diesem Feld Satz finden Sie unter.
