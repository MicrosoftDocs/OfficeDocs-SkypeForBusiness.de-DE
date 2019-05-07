---
title: Patienten App und EHR Integration STU3-Schnittstelle
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
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643106"
---
# <a name="stu3-interface-specification"></a>STU3 Interface-Spezifikation

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Einrichten oder Neukonfiguration einen FHIR Server die Microsoft-Teams Patienten app entwickelt ist erforderlich, welche die app muss für den Zugriff auf Daten zu verstehen. Der FHIR-Server muss POST-Anforderungen mithilfe der Pakete für die folgenden Ressourcen unterstützen:

- [Patienten](#patient)
- [Beobachtung](#observation)
- [Bedingung](#condition)
- [Auftreten](#encounter)
- [Allergie Intoleranz](#allergyintolerance)
- [Abdeckung](#coverage)
- [Medikament-Anweisung](#medication-request) (ersetzt die MedicationOrder in der DSTU2 Version von der PatientsApp)
- Speicherort (die Informationen benötigt dieser Ressource in Kontakt aufgenommen werden können)

> [!NOTE]
> Die Patient Ressource ist die einzigen obligatorischen Ressource (ohne den die app gar nicht geladen werden); Jedoch wird empfohlen, dass der Partner Unterstützung für die oben genannten Ressourcen pro Spezifikationen finden Sie weiter unten Endbenutzer am besten mit der Microsoft-Teams Patienten App implementieren.

Abfragen von der Microsoft-Teams Patienten-app für mehr als eine Ressource ist eine Bundle (BATCH) von Anforderungen in FHIR die URL des Servers bereitstellen. Der Server muss jeder Anforderung verarbeiten und Zurückgeben einer Bundle Ressourcen mit jeder Anforderung übereinstimmt. Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).

## <a name="capability-statement"></a>Capability-Anweisung

Dies sind die mindestens erforderlichen Felder aus:

1. Ruhepause
   1. Modus
   2. Interaktion
   3. Ressource: Typ
   4. Sicherheit: [Erweiterung für OAuth-URIs](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (unsere Code ist dies zu verstehen, welche Version wir zum Pivotieren sollte erforderlich.)

Finden Sie unter [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) für andere Details für dieses Feld festzulegen.

## <a name="patient"></a>Patienten

Es folgen die minimale erforderliche Felder, die eine Teilmenge der Felder Patient Profil Argonaut:

1. Name.Given
2. Name.Family
3. Geschlecht
4. Geburtsdatum
5. MRN (ID)

Zusätzlich zu den [Argonaut Felder](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:

1. Name.Use
2. Name.Prefix
3. [GeneralPractitioner] - die GeneralPractitioner Verweis in der Patienten Ressource (nur Anzeigefeld) einbezogen werden soll

Eine Ressourcensuche verwendet die POST-Methode zur /Patient/_search und die folgenden Parameter:

1. ID
2. Produktfamilie = (sucht alle Patienten, deren Namen Produktfamilie enthält den Wert)
3. angegebenen =\<Substring>
4. Geburtsdatum =(exact match)
5. Geschlecht = (Werte zu einem von der administrativen Geschlecht)
6. \_(maximale Anzahl der Ergebnisse an, die zurückgegeben werden sollen) <br> Die Antwort sollte die Gesamtzahl der als Ergebnis der Suche zurückgegebenen Datensätze enthalten und \_Anzahl wird durch die PatientsApp zur Begrenzung der Anzahl der zurückgegebenen Datensätze verwendet werden.
7. ID =\<Mrn>

Ziel ist es, suchen und Filtern zu einem Patienten ein durch Folgendes möglich:

- ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.
- MRN: Dies ist der tatsächlichen Bezeichner für den Patienten, den klinischer Mitarbeiter wissen müssen. Wir wissen, dass diese MRN Bezeichnertyp innerhalb der Bezeichner-Ressource im FHIR basiert.
- Name
- Geburtsdatum

Finden Sie im folgenden Beispiel wird für den Aufruf aus:

* * *

    : POST <fhir-Server>/Patient/_search anfordern Anforderungstext: angegebenen = Ruth&family = Schwarz
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Meta": {"LastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "Typ": "Searchset", "total": 1, "Link": [{"Beziehung": "self", "Url": <fhir-Server>/Patient/_search "}],"Entry": [{ "FullUrl": <fhir-Server>/Patient/<patient-Id> ","Resource": {"ResourceType":"Patient","Id":"<patient Id>","Meta": {"VersionId":"1","LastUpdated":" 2017-10-18T18:32:37.000 + 00:00 "},"Text": {"Status":"generiert","Div ": "<div>\n        <p>Ruth Schwarz</p>\n      </div>"},"ID": [{"verwenden":"Normal""Typ": {"Codieren": [{"System":"http://hl7.org/fhir/v2/0203","Code":"MR","anzeigen":"medizinische Datensatznummer","UserSelected": false}],"Text":"medizinische Datensatznummer"},"System":"http://hospital.smarthealthit.org","Wert":"1234567"}],"aktiv":" true "," Name": [{"verwenden":"offizielle","Familie":"Schwarz","angegebenen": ["Ruth","c ".
    ]}], "Telekommunikation": [{"System": "Telefon", "Wert": "800-599-2739", "Verwendung": "Privat"}, {"System": "Telefon", "Wert": "800-808-7785", "Verwendung": "Mobil"}, {"System": "e-Mail", "Wert": "ruth.black@example.com"}], "Geschlecht": "weiblich", "Geburtsdatum": "1951-08-23", " Adresse": [{"verwenden":"Start","Zeile": ["26 South RdApt 22"],"Ort":"Sapulpa","Bundesland":"OK","PLZ":"74066","Country":"USA"}]},"Suche": {"Mode":"match"}}]}

* * *

    Anforderung: GET <fhir-Server>/Patient/<patient-id>
    
    Antwort: {"ResourceType": "Patient", "Id": "<patient Id>", "ID": [{"verwenden": "Normal" "Typ": {"Codieren": [{"System": "http://hl7.org/fhir/v2/0203", "Code": "MR,"}], "Text": "medizinische Datensatznummer"}, "Wert": "1234567"}], "Name": [{"verwenden": "offizielle", " Familie":"Adams","angegebenen": ["Daniel","X". {]}], "Geschlecht": "Männlich", "Geburtsdatum": "1925-12-23"}

* * *

Finden Sie unter [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) für andere Details für dieses Feld festzulegen.

## <a name="observation"></a>Beobachtung

Dies sind die minimale erforderliche Felder, die eine Teilmenge des [Argonaut Grunddaten - Profil](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Die Übermittlung wirksamer (Datum Zeiten)
2. Code.Coding.Code
3. ValueQuantity.Value

Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:

1. Code.Coding.Display
2. ValueQuantity.Unit

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. = _sort-Datum
3. Kategorie (es wird eine Abfrage für "Kategorie wichtiger Gleichheitszeichen (=)") zum Abrufen der Liste der wesentlichen auf Anzeichen für.

Finden Sie in diesem Beispiel für den Anruf:

* * *

    Anforderung: <fhir-Server>/Beobachtung abrufen? Patient = <patient Id>&category wichtiger Gleichheitszeichen (=)
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 20, "Entry": [{"Resource": {"ResourceType": "Beobachtung", "Id": "<resource Id>", "Kategorie": [{"Codieren": [{"System": "http://hl7.org/fhir/observation-category", "Code": " wichtige signiert"}];}],"code": {"Codieren": [{"System":"http://loinc.org","Code":"8867 4","Anzeige":"Heart_rate"}]},"EffectiveDateTime":" 2009-04-08T00:00:00-06:00 ","ValueQuantity": {"Wert": 72.0,"Einheit":" {schlägt} / min ","System":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Finden Sie unter [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) für andere Details für dieses Feld festzulegen.

## <a name="condition"></a>Bedingung

Hier wird die minimale erforderliche Felder, die eine Teilmenge des [Argonaut Bedingung Profil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code.Coding[0]. Anzeige

Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:

1. AssertedDate
2. Schweregrad

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. _count =\<max Results>

Finden Sie im folgenden Beispiel wird dieses Anrufs:

* * *

    Anforderung: <fhir-Server>/Bedingung abrufen? Patient = <patient Id>&_count = 10
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 2, "Entry": [{"Resource": {"ResourceType": "Bedingung", "Id": "<resource Id>", "Code": {"Codieren": [{"System": "http://snomed.info/sct", "Code": "185903001", " Anzeigen von":"Anforderungen Influenza Impfung"}]},"Severity": {"Codieren": [{"System":"http://snomed.info/sct","Code":"24484000","anzeigen":"Severe"}]},"AssertedDate":"2018-04-04"}},.
        .
        .
      ] }

* * *
Finden Sie unter [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) für andere Details für dieses Feld festzulegen.

## <a name="encounter"></a>Auftreten

Dies sind die minimale erforderliche Felder, die eine Teilmenge der [USA Core auftreten Profil](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "benötigen" Felder).

1. Status
2. Typ [0]. Codieren [0]. Anzeige

Darüber hinaus Felder die folgenden Felder aus uns Core auftreten Profil "unterstützen" müssen:

1. Period.Start
2. Position [0]. Location.Display

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. _sort:desc =\<ex-Feld. date>
3. _count =\<max Results>

Ziel ist es, den Patienten letzten bekannten Speicherort abrufen können. Jede verweist auf eine Ressource Speicherort. Der Verweis umfassen ferner Anzeigefeld des Speicherorts.

Finden Sie unter [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) für andere Details für dieses Feld festzulegen.

## <a name="allergyintolerance"></a>AllergyIntolerance

Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code.Text
2. Code.Coding[0]. Anzeige
3. ClinicalStatus/VerificationStatus (wir lesen beide)

Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch das folgende Feld lesen:

1. AssertedDate
2. Note.Text
3. Reaktion
    1. Inhalt (eine Codierung-Element)
    2. Manifestation (ein Beispiel für Element)

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient = \<Patienten Id>

Finden Sie im folgenden Beispiel wird für den Aufruf aus: 

* * *

    Anforderung: <fhir-Server>/AllergyIntolerance abrufen? Patient = <patient Id>
    
    Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "AllergyIntolerance", "Id": "<resource Id>", "ClinicalStatus": "aktiv", "Ve RificationStatus":"bestätigt","Code": {"Codieren": [{"System":"http://rxnav.nlm.nih.gov/REST/Ndfrt","Code":"N0000175503","anzeigen":"Sulfonamid antibakterieller"}],"Text":"Sulfonamid Ant Ibacterial"},"AssertedDate":" 2018-01-01T00:00:00-07:00 ","Reaktion": [{"Manifestation": [{"Codieren": [{"System":"http://snomed.info/sct","Code":  "271807003", "anzeigen": "Hautausschlag"}], "Text": "Hautausschlag"}];}]}}]}

* * *

Finden Sie unter [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) für andere Details für dieses Feld festzulegen.

## <a name="medication-request"></a>Medikament-Anforderung

Dies sind die minimale erforderliche Felder, die eine Teilmenge des [Profils US Core Medikament anfordern](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medication.Display (wenn Referenz)
2. Medication.Text (wenn CodableConcept)
3. AuthoredOn
4. Requester.Agent.Display

Zusätzlich zu den Feldern uns Core kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:

1. DosageInstruction [.]. Text
2. Text

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient =\<Patienten Id>
2. _count =\<max Results>

Finden Sie unter [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) für andere Details für dieses Feld festzulegen.

## <a name="coverage"></a>Abdeckung

Dies sind die minimalen Pflichtfelder nicht fallen uns Core oder Argonaut Profile:

1. Gruppierung, mindestens ein Element mit
    1. Gruppe anzeigenZeigen
    2. PlanDisplay
2. Zeitraum
3. SubscriberId

Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:

1. Patient = \<Patienten Id>

Finden Sie unter [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) für andere Details für dieses Feld festzulegen.
