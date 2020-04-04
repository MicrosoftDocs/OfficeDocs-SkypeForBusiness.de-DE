---
title: Patienten-APP und EPA-Integrations STU3-Schnittstelle
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
description: Erfahren Sie mehr über die STU3-Schnittstellenspezifikation in Teams, einschließlich der Einrichtung oder Neukonfiguration eines FHIR-Servers für die Zusammenarbeit mit der Microsoft Teams-Patienten-app.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 35d887575ffb894b7a47e50511e6bd6c3a9a75d1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141198"
---
# <a name="stu3-interface-specification"></a>Benutzeroberflächenspezifikation STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss. Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:

- [Patienten](#patient)
- [Beobachtung](#observation)
- [Bedingung](#condition)
- [Auftreten](#encounter)
- [Allergie-Intoleranz](#allergyintolerance)
- [Abdeckung](#coverage)
- [Medikations Anweisung](#medication-request) (ersetzt die MedicationOrder in der DSTU2-Version des PatientsApp)
- Ort (die Informationen, die aus dieser Ressource benötigt werden, können in der Begegnung enthalten sein)

> [!NOTE]
> Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen wird). Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.

Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource müssen ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers senden. Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die den jeweiligen Anforderungen entsprechen. Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).

## <a name="capability-statement"></a>Capability-Anweisung

Hierbei handelt es sich um die erforderlichen Mindestanforderungen:

1. Rest
   1. Modus
   2. Interaktion
   3. Ressource: Typ
   4. Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten.)

Weitere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="patient"></a>Patienten

Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge der Argonaut-Patientenprofil Felder sind:

1. Name. given
2. Name. Familie
3. Geschlecht
4. BirthDate
5. MRN (Bezeichner)

Zusätzlich zu den [Argonaut-Feldern](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:

1. Name. use
2. Name. Prefix
3. [GeneralPractitioner] – der GeneralPractitioner-Verweis sollte in die Patienten Ressource aufgenommen werden (nur Anzeigefeld)

Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:

1. ID
2. Familie = (sucht nach allen Patienten, deren Familienname den Wert enthält)
3. given =\<Teilzeichenfolge>
4. Geburtsdatum = (exakte Übereinstimmung)
5. Gender = (Werte, die einer der administrativen-Gender-Werte sind)
6. \_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen) <br> Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurück \_gegeben wurden, und die Anzahl wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.
7. Identifier =\<MRN>

Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:

- ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.
- MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde. Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.
- Name
- BirthDate

Sehen Sie sich das folgende Beispiel des Anrufs an:

* * *

    Request: Post <fhir-Server>/Patient/_search Request Body: given = Ruth&Family = Black
    
    Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "Typ": "searchset"; "Total": 1; "Link": [{"Relation": "selbst"; "URL": <fhir-Server>/Patient/_search "}]," Eintrag ": [{" fullUrl ": <fhir-Server>/Patient/<Patient-ID>"; "Ressource": {"Ressourcentyp": "Patient"; "ID": "<Patient-ID>"; "Meta": {"Version-Nr": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "Text": {"Status": "generated", "div": "<div>\n        <p>Ruth schwarz</p>\n      </div>"}," Bezeichner ": [{" Use ":" üblich ";" Typ ": {" Coding ": [{" System ":"https://hl7.org/fhir/v2/0203";" Code ":" Herr ";" Anzeige ":" medizinische Datensatznummer ";" userSelected ": false}]," Text ":" medizinische Datensatznummer "}," System "http://hospital.smarthealthit.org:" ";" Wert ":" 1234567 "}]," aktiv ": wahr," Name ": [{" Use ":" offiziell "," Familie ":" schwarz ";" angegeben ": [" Ruth ";" C. "
    ]}], "Telecom": [{"System": "Telefon"; "Wert": "800-599-2739"; "Use": "Home"}, {"System": "Telefon"; "Wert": "800-808-7785"; "verwenden": "Mobil"}, {"System": "e-Mail"; "Wert": "Ruth.Black@example.com"}], "Geschlecht": "weiblich", "Geburtsdatum": "1951-08-23", "Adresse": [{"Use": "Start", "Zeile": ["26 South RdApt 22"], "Ort": "Sapulpa", "Zustand": "OK"; "PLZ": "74066"; "Land": "USA"}]}, "suchen": {"Modus": "Übereinstimmung"}}]}

* * *

    Request: besorgen Sie sich <fhir-Server>/Patient/<Patienten-ID>
    
    Response: {"Ressourcentyp": "Patient"; "ID": "<Patient-ID>"; "Bezeichner": [{"Use": "üblich"; "Typ": {"Coding": [{"System":https://hl7.org/fhir/v2/0203""; "Code": "Herr",}], "Text": "medizinische Datensatznummer"}, "Wert": "1234567"}], "Name": [{"Use": "offiziell", "Familie": "Adams"; "given": ["Daniel"; "X." ]}], "Gender": "männlich"; "Geburtsdatum": "1925-12-23",}

* * *

Weitere [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="observation"></a>Beobachtung

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut Vital-Signs-Profils](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)sind.

1. Effektiv (Datum oder Zeitraum)
2. Code. Coding. Code
3. ValueQuantity. Value

Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:

1. Code. Coding. Display
2. ValueQuantity. Unit

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _sort =-Datum
3. Kategorie (wir werden nach "Category = Vital-Signs" suchen), um die Liste der Vitalzeichen abzurufen.

Beziehen Sie sich auf dieses Beispiel des Anrufs:

* * *

    Request: besorgen Sie sich <fhir-Server>/Observation? Patient =<Patient-ID>&Kategorie = Vital-Zeichen
    
    Response: {"Ressourcen": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset", "Total": 20; "Eintrag": [{"Resource": {"Ressource": "Observation"; "ID": "<Resource-ID>"; "Category": [{"Coding": [{"System": "https://hl7.org/fhir/observation-category"; "Code": "Vital-Signs"}]; "Code": {"Coding": [{"System": "http://loinc.org"; "Code": "8867-4"; "Display": "heart_rate"}]}, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": {"Wert": 72,0, "Unit": "{Beats}/min.", "System": "http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Weitere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="condition"></a>Bedingung

Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge des Argonaut- [Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind.

1. Code. Coding [0]. Anzeigen

Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:

1. AssertedDate
2. Schweregrad

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _Count =\<maximale Ergebnisse>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

* * *

    Request: besorgen Sie sich <fhir-Server>/Condition? Patient =<Patient-ID>&_count = 10
    
    Antwort: {"Ressourcen": "Bundle", "ID": "<-Bundle-ID>"; "Typ": "searchset"; "Total": 2; "Eintrag": [{"Resource": {"Ressourcentyp": "Bedingung"; "ID": "<Resource-ID>"; "Code": {"Coding": [{"Systemhttp://snomed.info/sct": ""; "Code": "185903001"; "Anzeige": "benötigt eine Influenza-Immunisierung",}]}, "Schweregrad": {"Coding":http://snomed.info/sct[{"System": "", "Code": "24484000"; "Anzeige": "schwere"}]}, "assertedDate": "2018-04-04"}},.
        .
        .
      ] }

* * *
Weitere [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="encounter"></a>Auftreten

Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [US-Core-Encounter-Profils](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have"-Felder handelt.

1. Status
2. Geben Sie [0] ein. Codierung [0]. Anzeigen

Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils:

1. Periode. Start
2. Ort [0]. Location. Display

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _sort: DESC =\<Feld Ex. Datum>
3. _Count =\<maximale Ergebnisse>

Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können. Jede Begegnung verweist auf eine Standortressource. Der Bezug umfasst auch das Anzeigefeld des Standorts.

Weitere [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="allergyintolerance"></a>AllergyIntolerance

Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) -Profils sind:

1. Code. Text
2. Code. Coding [0]. Anzeigen
3. ClinicalStatus/VerificationStatus (wir lesen beide)

Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch das folgende Feld lesen:

1. AssertedDate
2. Hinweis. Text
3. Reaktion
    1. Substanz (ein Codierungselement)
    2. Manifestation (ein Codierungselement)

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient = \<Patienten-ID>

Sehen Sie sich das folgende Beispiel des Anrufs an: 

* * *

    Request: besorgen Sie sich <fhir-Server>/allergyintolerance? Patient =<Patienten-ID>
    
    Response: {"Ressourcentyp": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressource": "AllergyIntolerance"; "ID": "<Resource-ID>"; "clinicalStatus": "aktiv"; "verificationStatus": "bestätigt"; "Code": {"Coding": [{"System":http://rxnav.nlm.nih.gov/REST/Ndfrt"", "Code": "N0000175503"; "Display": "Sulfonamid antibakterielle",}], "Text": "Sulfonamid antibakteriell"}, "assertedDate": "2018-01-01T00:00:00-07:00"; "Reaktion": [{"Manifest": [{"Coding": [{"System": "http://snomed.info/sct"; "Code": "271807003"; "Display": "Hautausschlag",}], "Text": "Hautausschlag"}],}]}}]}

* * *

Weitere [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="medication-request"></a>Medikations Anfrage

Hierbei handelt es sich um die Mindestanforderungen, die eine Teilmenge des [US-Core-Medikaments anfordern](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medikation. Display (wenn Bezug)
2. Medikation. Text (wenn CodableConcept)
3. AuthoredOn
4. Requestor. Agent. Display

Zusätzlich zu den US-Core-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:

1. DosageInstruction[..]. Text
2. Text

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient =\<Patienten-ID>
2. _Count =\<maximale Ergebnisse>

Weitere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.

## <a name="coverage"></a>Abdeckung

Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:

1. Gruppieren, mindestens ein Element mit
    1. GroupDisplay
    2. PlanDisplay
2. Zeitraum
3. SubscriberId

Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:

1. Patient = \<Patienten-ID>

Weitere [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.
