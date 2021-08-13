---
title: Benutzeroberfläche für Patienten-App und EHR-Integration STU3
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
description: Hier erfahren Sie, wie Sie elektronische Krankenakten in die App Microsoft Teams Patienten und die Benutzeroberflächenspezifikation STU3 integrieren.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e51372f2c44bdd5bdeea8e4a7699d3f46881564e0c98f3049b95dcbd21eb66c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344042"
---
# <a name="stu3-interface-specification"></a>Benutzeroberflächenspezifikation STU3

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
- [Medikamenteausweisung](#medication-request) (ersetzt die "MedicationOrder" in der DSTU2-Version der PatientenApp)
- Ort (die für diese Ressource erforderlichen Informationen können in "Encounter" enthalten sein)

> [!NOTE]
> Die Patient-Ressource ist die einzige obligatorische Ressource (ohne die die App überhaupt nicht geladen wird). Es wird jedoch empfohlen, vom Partner die Unterstützung für alle oben genannten Ressourcen pro unten angegebenen Spezifikationen zu implementieren, um die Benutzerfreundlichkeit der Patienten-App Microsoft Teams verbessern zu können.

Abfragen von der Microsoft Teams-Patienten-App für mehr als eine Ressource müssen ein Paket (BATCH) mit Anforderungen an die URL des FSOURCE-Servers posten. Der Server muss jede Anforderung verarbeiten und ein Bündel der Ressourcen zurückgeben, die den einzelnen Anfragen entsprechen. Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Capability-Anweisung

Dies sind die mindestens erforderlichen Felder:

 - REST

    - Modus
    - Interaktion
    - Ressource: Typ
    - Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - F zur Kehrversion (Unser Code erfordert, dass Sie verstehen, auf welche Version wir pivotieren sollten.)

Weitere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="patient"></a>Patient

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder für das Patientenprofil "Ortsnaut" handelt:

 - Name.Given
 - Name.Family
 - Geschlecht
 - Geburtsdatum
 - MRN (Identifier)

Für eine großartige Benutzererfahrung kann die Patienten-App nicht nur die [Felder des Orts,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)sondern auch die folgenden Felder lesen:

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] – Der Bezug auf GeneralPractitioner sollte in die Patient-Ressource aufgenommen werden (nur Anzeigefeld)

Eine Ressourcensuche verwendet die POST-Methode bei /Patient/_search und die folgenden Parameter:

 - id
 - family=(Sucht nach allen Patienten, deren Familienname den Wert enthält)
 - given=\<substring>
 - birthdate=(genaue Übereinstimmung)
 - gender=(Werte, die eines verwaltungsspezifischen Geschlechtes sind)
 - \_Anzahl (maximale Anzahl der zurückgegebenen Ergebnisse) <br> Die Antwort sollte die Gesamtzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl wird von der PatientenApp verwendet, um die Anzahl der zurückgegebenen \_ Datensätze zu begrenzen.
 - identifier=\<mrn>

Das Ziel besteht in der Möglichkeit, wie folgt nach einem Patienten zu suchen und zu filtern:

- Nr.: Dies ist die Ressourcen-ID, über die jede Ressource in FSCHI verfügt.
- MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den der klinische Mitarbeiter hätte. Uns ist klar, dass diese MRN auf dem Typ des Bezeichners innerhalb der Bezeichnerressource in FSCHI basiert.
- Name
- Geburtsdatum

Sehen Sie sich das folgende Beispiel für den -Aufruf an:

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

Weitere [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="observation"></a>Beobachtung

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [Profils "Ortsnaut" Vital-Signs handelt.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Effektiv (Datum, Uhrzeit oder Zeitraum)
 - Code.Coding.Code
 - ValueQuantity.Value

Für eine großartige Benutzererfahrung kann die Patienten-App nicht nur Felder des Orts, sondern auch die folgenden Felder lesen:

 - Code.Coding.Display
 - ValueQuantity.Unit

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>
 - _sort=-Datum
 - Kategorie (wir fragen nach "category=vital-signs"), um die Liste der wichtigen Schilder abzurufen.

Sehen Sie sich das folgende Beispiel für den -Aufruf an:

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

Weitere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="condition"></a>Bedingung

Hier sehen Sie die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [Profils zur Bedingung "Durchdingung" handelt.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Anzeige

Für eine großartige Benutzererfahrung kann die Patienten-App nicht nur Felder des Orts, sondern auch die folgenden Felder lesen:

 - AssertedDate
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

Weitere [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="encounter"></a>Encounter

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der ["must](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) have"-Felder des US Core Encounter-Profils handelt.

 - Status
 - Geben Sie [0] ein. Coding[0]. Anzeige

Darüber hinaus müssen die folgenden Felder aus den "must support"-Feldern des US Core Encounter-Profils:

 - Period.Start
 - Position[0]. Location.Display

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

Das Ziel ist es, den letzten bekannten Standort des Patienten abrufen zu können. Jede -Ressource verweist auf eine Standortressource. Der Bezug muss auch das Anzeigefeld des Standorts enthalten.

Weitere [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="allergyintolerance"></a>VererbungIntolerance

Dabei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [Profils "OrtsnautEnIntolerance"](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) handelt:

 - Code.Text
 - Code.Coding[0]. Anzeige
 - KlinischerStatus/Überprüfungsstatus (beides wird gelesen)

Für eine großartige Benutzererfahrung kann die Patienten-App neben den Feldern des Orts auch das folgende Feld lesen:

 - AssertedDate
 - Note.Text
 - Reaktion
    - Im Code (ein Codeelement)
    - Abt. (ein Codeelement)

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - Patient =  \<patient id>

Sehen Sie sich das folgende Beispiel für den -Aufruf an: 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

Weitere [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="medication-request"></a>Medikamenteanforderung

Dies sind die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [Profils für die US-Medikamenteanforderung handelt:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)

 - Medication.Display (wenn Bezug)
 - Medication.Text (wenn CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Für eine großartige Benutzererfahrung kann die Patienten-App nicht nur die Felder "US Core" sondern auch die folgenden Felder lesen:

 - 12212279. Text
 - Text

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - patient=\<patient id>
 - _count=\<max results>

Weitere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) Details zu diesem Feldsatz finden Sie unter .

## <a name="coverage"></a>Abdeckung

Dies sind die mindestens erforderlichen Felder, die nicht von Profilen des US-Kerns oder Dessnaut abgedeckt werden:

 - Gruppieren, mindestens ein Element mit
    - GroupDisplay
    - PlanDisplay
 - Zeitraum
 - SubscriberId

Eine Ressourcensuche verwendet die GET-Methode und die folgenden Parameter:

 - Patient = \<patient id>

Weitere [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) Details zu diesem Feldsatz finden Sie unter .
