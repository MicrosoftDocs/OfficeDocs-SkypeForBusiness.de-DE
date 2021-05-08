---
title: DSTU2-Schnittstelle für Patienten-App und EHR-Integration
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
description: Erfahren Sie mehr über die DSTU2-Schnittstellenspezifikation in Teams, einschließlich Einrichten oder Neukonfigurieren eines FTRI-Servers für die Zusammenarbeit mit der Microsoft Teams-Patienten-App.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803483"
---
# <a name="dstu2-interface-specification"></a>Benutzeroberflächenspezifikation DSTU2

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Microsoft Teams ersetzt. Die Daten der Patienten-App werden in dem Gruppenpostfach der Office 365-Gruppe gespeichert, das zum Team gehört. Alle der Patienten-App zugeordneten Daten bleiben in dieser Gruppe erhalten, auf sie kann aber nicht mehr über die Benutzeroberfläche zugegriffen werden. Benutzer können ihre Listen mithilfe der App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) neu erstellen.
>
>Mit der Listen-App können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen. Sehen Sie sich die Vorlage "Patienten" in der Listen-App an, um die ersten Schritte zu unternehmen. Weitere Informationen zum Verwalten der Listen-App in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Das Einrichten oder Neukonfigurieren eines FSCHI-Servers für die Zusammenarbeit mit der Microsoft Teams-Patienten-App erfordert ein Verständnis der Daten, auf die die App zugreifen muss. Der F IMMER-Server muss POST-Anforderungen mithilfe von Bündeln für die folgenden Ressourcen unterstützen:

- [Patient](#patient)
- [Beobachtung](#observation)
- [Bedingung](#condition)
- [Encounter](#encounter)
- [Ungermieren](#allergyintolerance)
- [Abdeckung](#coverage)
- [Medikamentereihenfolge](#medication-order)
- [Standort](#location)

> [!NOTE]
> Die Patient-Ressource ist die einzige obligatorische Ressource (ohne die die App überhaupt nicht geladen wird). Es wird jedoch empfohlen, vom Partner die Unterstützung für alle oben genannten Ressourcen pro unten angegebenen Spezifikationen zu implementieren, um die Benutzerfreundlichkeit der Patienten-App Microsoft Teams verbessern zu können.

Abfragen von der Microsoft Teams-Patienten-App für mehr als eine Ressource posten ein Paket (BATCH) mit Anforderungen an die URL des FSOURCE-Servers. Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die den einzelnen Anfragen entsprechen. Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Der Zugriff auf alle folgenden FSOURCE-Ressourcen sollte über direkte Ressourcenverweise möglich sein.

## <a name="conformance-minimum-required-field-set"></a>Mindestens erforderliche Feldanzahl für Konformität

 Der FSCHI-Server muss die Konformitätsbestimmungen implementieren, damit wir eine auf Fakten bezogene Zusammenfassung seiner Funktionen erhalten können. In einem DSTU2-FTRI-Server werden die folgenden Parameter erwartet:

 - REST

    - Modus
    - Interaktion
    - Ressource: Typ
    - Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - Fversion (Unser Code erfordert, dass wir verstehen, auf welche Version wir pivotieren sollten, wenn wir mehrere Versionen unterstützen.)

Weitere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="patient"></a>Patient

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder des [Patientenprofils "Durchdingen"](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) handelt:

 - Name.Family
 - Name.Given
 - Geschlecht
 - Geburtsdatum
 - MRN (Identifier)

Für eine großartige Benutzererfahrung liest die Patienten-App nicht nur die Felder des Orts, sondern auch die folgenden Felder:

 - Name.Use
 - Name.Prefix
 - CareProvider (Dieser Verweis auf die Ressource Patient sollte die Anzeigefelder enthalten, die im folgenden Beispiel gezeigt werden.)

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

Eine Ressourcensuche verwendet die POST-Methode bei /Patient/_search und die folgenden Parameter:

 - id
 - family:contains=(Sucht nach allen Patienten, deren Familienname den Wert enthält.)
 - given=\<substring>
 - name=\<substring>
 - birthdate=(genaue Übereinstimmung)
 - \_Anzahl (maximale Anzahl der zurückgegebenen Ergebnisse) <br> Die Antwort sollte die Gesamtzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl wird von der PatientenApp verwendet, um die Anzahl der zurückgegebenen Datensätze \_ zu begrenzen.
 - identifier=\<mrn>

Das Ziel besteht in der Möglichkeit, wie folgt nach einem Patienten zu suchen und zu filtern:

- Nr.: Dies ist die Ressourcen-ID, über die jede Ressource in FSCHI verfügt.
- MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den der klinische Mitarbeiter hätte. Uns ist klar, dass die MRN auf dem Typ des Bezeichners innerhalb der Bezeichnerressource in F IMMER basiert.
- Name
- Geburtsdatum

Sehen Sie sich das folgende Beispiel für diesen Aufruf an.

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

Weitere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="observation"></a>Beobachtung

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des Profils für wichtige Schilder von Durchdingen handelt:

 - Effektiv (Datum, Uhrzeit oder Zeitraum)
 - Code.Coding.Code
 - ValueQuantity.Value

Für eine großartige Benutzererfahrung liest die Patienten-App nicht nur die Felder des Orts, sondern auch die folgenden Felder:

 - Code.Coding.Display
 - ValueQuantity.Unit

Bei Verwendung von Komponentenbeobachtungen gilt die gleiche Logik für jede Komponentenbeobachtung.

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

Das Ziel besteht in der Möglichkeit, die neuesten wichtigen Zeichen für einen Patienten wie [VitalSigns.DSTU.saz] (Beobachtung?) abzurufen.

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

Weitere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="condition"></a>Bedingung

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [Profils für die Zustandsbeschriftung Von Ihnen handelt:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Anzeige

Für eine großartige Benutzererfahrung kann die Patienten-App nicht nur Felder des Orts, sondern auch die folgenden Felder lesen:

 - Aufgezeichnetes Datum
 - Schweregrad

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>
 - _count=\<max results>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

Weitere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="encounter"></a>Encounter

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der "muss"-Felder des US Core Encounter-Profils handelt:

 - Status
 - Geben Sie [0] ein. Coding[0]. Anzeige

Darüber hinaus müssen die folgenden Felder aus den "must support"-Feldern des US-Core Encounter-Profils

 - Period.Start
 - Position[0]. Location.Display

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

Das Ziel ist es, den letzten bekannten Standort des Patienten abrufen zu können. Jede -Ressource verweist auf eine Standortressource. Der Bezug muss auch das Anzeigefeld des Standorts enthalten. Sehen Sie sich das folgende Beispiel für diesen Aufruf an.

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

Weitere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) Details zu diesem Feldsatz finden Sie unter .

## <a name="allergyintolerance"></a>VererbungIntolerance

Dabei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des Profils "OrtsnautEnIntolerance" handelt:

 - Code.Text
 - Code.Coding[0]. Anzeige
 - Status

Für eine großartige Benutzererfahrung liest die Patienten-App nicht nur die Felder des Orts, sondern auch die folgenden Felder:

 - RecordedDate
 - Note.Text
 - Reaktion[..]. Vorn.Text
 - Reaktion[..]. Oder[..]. Text
 - Text.Div

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - Patient =  \<patient id>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

Weitere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="medication-order"></a>Medikamentereihenfolge

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des Profils "Durchstellen von Medikamentebestellungen" handelt:

 - DateWritten
 - Vorsingen.Anzeige
 - Medication.Display (wenn Bezug)
 - Medication.Text (wenn Konzept)

Für eine großartige Benutzererfahrung kann die Patienten-App nicht nur Felder des Orts, sondern auch die folgenden Felder lesen:

 - DateEnded
 - 1222222.Text
 - Text.Div

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>
 - _count=\<max results>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

Weitere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="coverage"></a>Abdeckung

Dies sind die mindestens erforderlichen Felder, die nicht von Profilen des US-Kerns oder Dessnaut abgedeckt werden:

 - Payor

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>

Sehen Sie sich das folgende Beispiel für diesen Aufruf an:

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
Weitere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="location"></a>Ort

Diese Ressource wird nur als Verweis auf die Ressource ["Encounter"](#encounter) verwendet.

Weitere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) Details zu diesem Feldsatz finden Sie unter .
