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
description: Erfahren Sie mehr über die Integration elektronischer Integritätsdaten Sätze in die Microsoft Teams patients-APP und die STU3-Schnittstellenspezifikation.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772266"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="299d9-103">Benutzeroberflächenspezifikation STU3</span><span class="sxs-lookup"><span data-stu-id="299d9-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="299d9-104">Die Patienten-App wurde im 30. Oktober, 2020, eingestellt und durch die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt.</span><span class="sxs-lookup"><span data-stu-id="299d9-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="299d9-105">Mit Listen können Betreuerteams in Ihrer Gesundheitsorganisation patientenlisten für Szenarien erstellen, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen.</span><span class="sxs-lookup"><span data-stu-id="299d9-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="299d9-106">Schauen Sie sich die Vorlage Patienten in Listen an, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="299d9-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="299d9-107">Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="299d9-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="299d9-108">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="299d9-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="299d9-109">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="299d9-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="299d9-110">Patienten</span><span class="sxs-lookup"><span data-stu-id="299d9-110">Patient</span></span>](#patient)
- [<span data-ttu-id="299d9-111">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="299d9-111">Observation</span></span>](#observation)
- [<span data-ttu-id="299d9-112">Bedingung</span><span class="sxs-lookup"><span data-stu-id="299d9-112">Condition</span></span>](#condition)
- [<span data-ttu-id="299d9-113">Auftreten</span><span class="sxs-lookup"><span data-stu-id="299d9-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="299d9-114">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="299d9-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="299d9-115">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="299d9-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="299d9-116">[Medikations Anweisung](#medication-request) (ersetzt die MedicationOrder in der DSTU2-Version des PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="299d9-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="299d9-117">Ort (die Informationen, die aus dieser Ressource benötigt werden, können in der Begegnung enthalten sein)</span><span class="sxs-lookup"><span data-stu-id="299d9-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="299d9-118">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen wird). Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="299d9-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="299d9-119">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource müssen ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers senden.</span><span class="sxs-lookup"><span data-stu-id="299d9-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="299d9-120">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die den jeweiligen Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="299d9-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="299d9-121">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="299d9-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="299d9-122">Capability-Anweisung</span><span class="sxs-lookup"><span data-stu-id="299d9-122">Capability Statement</span></span>

<span data-ttu-id="299d9-123">Hierbei handelt es sich um die erforderlichen Mindestanforderungen:</span><span class="sxs-lookup"><span data-stu-id="299d9-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="299d9-124">Rest</span><span class="sxs-lookup"><span data-stu-id="299d9-124">REST</span></span>

    - <span data-ttu-id="299d9-125">Modus</span><span class="sxs-lookup"><span data-stu-id="299d9-125">Mode</span></span>
    - <span data-ttu-id="299d9-126">Interaktion</span><span class="sxs-lookup"><span data-stu-id="299d9-126">Interaction</span></span>
    - <span data-ttu-id="299d9-127">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="299d9-127">Resource: Type</span></span>
    - <span data-ttu-id="299d9-128">Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="299d9-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="299d9-129">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten.)</span><span class="sxs-lookup"><span data-stu-id="299d9-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="299d9-130">Weitere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="299d9-131">Patienten</span><span class="sxs-lookup"><span data-stu-id="299d9-131">Patient</span></span>

<span data-ttu-id="299d9-132">Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge der Argonaut-Patientenprofil Felder sind:</span><span class="sxs-lookup"><span data-stu-id="299d9-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="299d9-133">Name. given</span><span class="sxs-lookup"><span data-stu-id="299d9-133">Name.Given</span></span>
 - <span data-ttu-id="299d9-134">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="299d9-134">Name.Family</span></span>
 - <span data-ttu-id="299d9-135">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="299d9-135">Gender</span></span>
 - <span data-ttu-id="299d9-136">BirthDate</span><span class="sxs-lookup"><span data-stu-id="299d9-136">BirthDate</span></span>
 - <span data-ttu-id="299d9-137">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="299d9-137">MRN (Identifier)</span></span>

<span data-ttu-id="299d9-138">Zusätzlich zu den [Argonaut-Feldern](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="299d9-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="299d9-139">Name. use</span><span class="sxs-lookup"><span data-stu-id="299d9-139">Name.Use</span></span>
 - <span data-ttu-id="299d9-140">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="299d9-140">Name.Prefix</span></span>
 - <span data-ttu-id="299d9-141">[GeneralPractitioner] – der GeneralPractitioner-Verweis sollte in die Patienten Ressource aufgenommen werden (nur Anzeigefeld)</span><span class="sxs-lookup"><span data-stu-id="299d9-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="299d9-142">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="299d9-143">ID</span><span class="sxs-lookup"><span data-stu-id="299d9-143">id</span></span>
 - <span data-ttu-id="299d9-144">Familie = (sucht nach allen Patienten, deren Familienname den Wert enthält)</span><span class="sxs-lookup"><span data-stu-id="299d9-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="299d9-145">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="299d9-145">given=\<substring></span></span>
 - <span data-ttu-id="299d9-146">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="299d9-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="299d9-147">Gender = (Werte, die einer der administrativen-Gender-Werte sind)</span><span class="sxs-lookup"><span data-stu-id="299d9-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="299d9-148">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="299d9-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="299d9-149">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl \_ wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="299d9-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="299d9-150">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="299d9-150">identifier=\<mrn></span></span>

<span data-ttu-id="299d9-151">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="299d9-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="299d9-152">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="299d9-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="299d9-153">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="299d9-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="299d9-154">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="299d9-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="299d9-155">Name</span><span class="sxs-lookup"><span data-stu-id="299d9-155">Name</span></span>
- <span data-ttu-id="299d9-156">BirthDate</span><span class="sxs-lookup"><span data-stu-id="299d9-156">Birthdate</span></span>

<span data-ttu-id="299d9-157">Sehen Sie sich das folgende Beispiel des Anrufs an:</span><span class="sxs-lookup"><span data-stu-id="299d9-157">See the following example of the call:</span></span>

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

<span data-ttu-id="299d9-158">Weitere [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="299d9-159">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="299d9-159">Observation</span></span>

<span data-ttu-id="299d9-160">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-Vital-Signs Profils](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)sind.</span><span class="sxs-lookup"><span data-stu-id="299d9-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="299d9-161">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="299d9-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="299d9-162">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="299d9-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="299d9-163">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="299d9-163">ValueQuantity.Value</span></span>

<span data-ttu-id="299d9-164">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="299d9-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="299d9-165">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="299d9-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="299d9-166">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="299d9-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="299d9-167">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="299d9-168">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="299d9-168">patient=\<patient id></span></span>
 - <span data-ttu-id="299d9-169">_sort =-Datum</span><span class="sxs-lookup"><span data-stu-id="299d9-169">_sort=-date</span></span>
 - <span data-ttu-id="299d9-170">Kategorie (wir werden nach "Category = Vital-Signs" suchen), um die Liste der Vitalzeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="299d9-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="299d9-171">Beziehen Sie sich auf dieses Beispiel des Anrufs:</span><span class="sxs-lookup"><span data-stu-id="299d9-171">Refer to this example of the call:</span></span>

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

<span data-ttu-id="299d9-172">Weitere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="299d9-173">Bedingung</span><span class="sxs-lookup"><span data-stu-id="299d9-173">Condition</span></span>

<span data-ttu-id="299d9-174">Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge des Argonaut- [Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind.</span><span class="sxs-lookup"><span data-stu-id="299d9-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="299d9-175">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="299d9-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="299d9-176">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="299d9-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="299d9-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="299d9-177">AssertedDate</span></span>
 - <span data-ttu-id="299d9-178">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="299d9-178">Severity</span></span>

<span data-ttu-id="299d9-179">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="299d9-180">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="299d9-180">patient=\<patient id></span></span>
 - <span data-ttu-id="299d9-181">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="299d9-181">_count=\<max results></span></span>

<span data-ttu-id="299d9-182">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="299d9-182">See the following example of this call:</span></span>

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

<span data-ttu-id="299d9-183">Weitere [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="299d9-184">Auftreten</span><span class="sxs-lookup"><span data-stu-id="299d9-184">Encounter</span></span>

<span data-ttu-id="299d9-185">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [US-Core-Encounter-Profils](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have"-Felder handelt.</span><span class="sxs-lookup"><span data-stu-id="299d9-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="299d9-186">Status</span><span class="sxs-lookup"><span data-stu-id="299d9-186">Status</span></span>
 - <span data-ttu-id="299d9-187">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="299d9-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="299d9-188">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils:</span><span class="sxs-lookup"><span data-stu-id="299d9-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="299d9-189">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="299d9-189">Period.Start</span></span>
 - <span data-ttu-id="299d9-190">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="299d9-190">Location[0].Location.Display</span></span>

<span data-ttu-id="299d9-191">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="299d9-192">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="299d9-192">patient=\<patient id></span></span>
 - <span data-ttu-id="299d9-193">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="299d9-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="299d9-194">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="299d9-194">_count=\<max results></span></span>

<span data-ttu-id="299d9-195">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="299d9-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="299d9-196">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="299d9-196">Each encounter references a location resource.</span></span> <span data-ttu-id="299d9-197">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="299d9-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="299d9-198">Weitere [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="299d9-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="299d9-199">AllergyIntolerance</span></span>

<span data-ttu-id="299d9-200">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) -Profils sind:</span><span class="sxs-lookup"><span data-stu-id="299d9-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="299d9-201">Code. Text</span><span class="sxs-lookup"><span data-stu-id="299d9-201">Code.Text</span></span>
 - <span data-ttu-id="299d9-202">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="299d9-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="299d9-203">ClinicalStatus/VerificationStatus (wir lesen beide)</span><span class="sxs-lookup"><span data-stu-id="299d9-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="299d9-204">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch das folgende Feld lesen:</span><span class="sxs-lookup"><span data-stu-id="299d9-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="299d9-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="299d9-205">AssertedDate</span></span>
 - <span data-ttu-id="299d9-206">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="299d9-206">Note.Text</span></span>
 - <span data-ttu-id="299d9-207">Reaktion</span><span class="sxs-lookup"><span data-stu-id="299d9-207">Reaction</span></span>
    - <span data-ttu-id="299d9-208">Substanz (ein Codierungselement)</span><span class="sxs-lookup"><span data-stu-id="299d9-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="299d9-209">Manifestation (ein Codierungselement)</span><span class="sxs-lookup"><span data-stu-id="299d9-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="299d9-210">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="299d9-211">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="299d9-211">Patient =  \<patient id></span></span>

<span data-ttu-id="299d9-212">Sehen Sie sich das folgende Beispiel des Anrufs an:</span><span class="sxs-lookup"><span data-stu-id="299d9-212">See the following example of the call:</span></span> 

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

<span data-ttu-id="299d9-213">Weitere [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="299d9-214">Medikations Anfrage</span><span class="sxs-lookup"><span data-stu-id="299d9-214">Medication Request</span></span>

<span data-ttu-id="299d9-215">Hierbei handelt es sich um die Mindestanforderungen, die eine Teilmenge des [US-Core-Medikaments anfordern](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="299d9-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="299d9-216">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="299d9-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="299d9-217">Medikation. Text (wenn CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="299d9-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="299d9-218">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="299d9-218">AuthoredOn</span></span>
 - <span data-ttu-id="299d9-219">Requestor. Agent. Display</span><span class="sxs-lookup"><span data-stu-id="299d9-219">Requester.Agent.Display</span></span>

<span data-ttu-id="299d9-220">Zusätzlich zu den US-Core-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="299d9-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="299d9-221">DosageInstruction[..]. Text</span><span class="sxs-lookup"><span data-stu-id="299d9-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="299d9-222">Text</span><span class="sxs-lookup"><span data-stu-id="299d9-222">Text</span></span>

<span data-ttu-id="299d9-223">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="299d9-224">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="299d9-224">patient=\<patient id></span></span>
 - <span data-ttu-id="299d9-225">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="299d9-225">_count=\<max results></span></span>

<span data-ttu-id="299d9-226">Weitere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="299d9-227">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="299d9-227">Coverage</span></span>

<span data-ttu-id="299d9-228">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="299d9-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="299d9-229">Gruppieren, mindestens ein Element mit</span><span class="sxs-lookup"><span data-stu-id="299d9-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="299d9-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="299d9-230">GroupDisplay</span></span>
    - <span data-ttu-id="299d9-231">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="299d9-231">PlanDisplay</span></span>
 - <span data-ttu-id="299d9-232">Zeitraum</span><span class="sxs-lookup"><span data-stu-id="299d9-232">Period</span></span>
 - <span data-ttu-id="299d9-233">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="299d9-233">SubscriberId</span></span>

<span data-ttu-id="299d9-234">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="299d9-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="299d9-235">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="299d9-235">Patient = \<patient id></span></span>

<span data-ttu-id="299d9-236">Weitere [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="299d9-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
