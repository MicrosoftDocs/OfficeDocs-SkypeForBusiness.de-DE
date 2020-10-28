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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772206"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="c867c-103">Benutzeroberflächenspezifikation DSTU2</span><span class="sxs-lookup"><span data-stu-id="c867c-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="c867c-104">Die Patienten-App wurde im 30. Oktober, 2020, eingestellt und durch die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c867c-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="c867c-105">Mit Listen können Betreuerteams in Ihrer Gesundheitsorganisation patientenlisten für Szenarien erstellen, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen.</span><span class="sxs-lookup"><span data-stu-id="c867c-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="c867c-106">Schauen Sie sich die Vorlage Patienten in Listen an, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c867c-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="c867c-107">Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md) .</span><span class="sxs-lookup"><span data-stu-id="c867c-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="c867c-108">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="c867c-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="c867c-109">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="c867c-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="c867c-110">Patienten</span><span class="sxs-lookup"><span data-stu-id="c867c-110">Patient</span></span>](#patient)
- [<span data-ttu-id="c867c-111">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="c867c-111">Observation</span></span>](#observation)
- [<span data-ttu-id="c867c-112">Bedingung</span><span class="sxs-lookup"><span data-stu-id="c867c-112">Condition</span></span>](#condition)
- [<span data-ttu-id="c867c-113">Auftreten</span><span class="sxs-lookup"><span data-stu-id="c867c-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="c867c-114">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="c867c-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="c867c-115">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="c867c-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="c867c-116">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="c867c-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="c867c-117">Standort</span><span class="sxs-lookup"><span data-stu-id="c867c-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="c867c-118">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c867c-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="c867c-119">Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c867c-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="c867c-120">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource Posten ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers.</span><span class="sxs-lookup"><span data-stu-id="c867c-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="c867c-121">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die mit den einzelnen Anforderungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c867c-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="c867c-122">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="c867c-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="c867c-123">Auf alle folgenden FHIR-Ressourcen sollte über direkten Ressourcenverweis zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="c867c-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="c867c-124">Konformitäts mindestanforderungs Feld Satz</span><span class="sxs-lookup"><span data-stu-id="c867c-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="c867c-125">Der FHIR-Server muss die Konformitätserklärung für uns implementieren, um eine sachliche Zusammenfassung seiner Funktionen zu haben.</span><span class="sxs-lookup"><span data-stu-id="c867c-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="c867c-126">Wir erwarten die folgenden Parameter in einem DSTU2-FHIR-Server:</span><span class="sxs-lookup"><span data-stu-id="c867c-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="c867c-127">Rest</span><span class="sxs-lookup"><span data-stu-id="c867c-127">REST</span></span>

    - <span data-ttu-id="c867c-128">Modus</span><span class="sxs-lookup"><span data-stu-id="c867c-128">Mode</span></span>
    - <span data-ttu-id="c867c-129">Interaktion</span><span class="sxs-lookup"><span data-stu-id="c867c-129">Interaction</span></span>
    - <span data-ttu-id="c867c-130">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="c867c-130">Resource: Type</span></span>
    - <span data-ttu-id="c867c-131">Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="c867c-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="c867c-132">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten, da wir mehrere Versionen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="c867c-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="c867c-133">Weitere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="c867c-134">Patienten</span><span class="sxs-lookup"><span data-stu-id="c867c-134">Patient</span></span>

<span data-ttu-id="c867c-135">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge der [Argonaut-Patientenprofil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder sind:</span><span class="sxs-lookup"><span data-stu-id="c867c-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="c867c-136">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="c867c-136">Name.Family</span></span>
 - <span data-ttu-id="c867c-137">Name. given</span><span class="sxs-lookup"><span data-stu-id="c867c-137">Name.Given</span></span>
 - <span data-ttu-id="c867c-138">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="c867c-138">Gender</span></span>
 - <span data-ttu-id="c867c-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="c867c-139">BirthDate</span></span>
 - <span data-ttu-id="c867c-140">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="c867c-140">MRN (Identifier)</span></span>

<span data-ttu-id="c867c-141">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="c867c-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="c867c-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="c867c-142">Name.Use</span></span>
 - <span data-ttu-id="c867c-143">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="c867c-143">Name.Prefix</span></span>
 - <span data-ttu-id="c867c-144">CareProvider (dieser Verweis auf die Patienten Ressource sollte die Anzeigefelder umfassen, die im folgenden Beispiel gezeigt werden.)</span><span class="sxs-lookup"><span data-stu-id="c867c-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="c867c-145">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="c867c-146">ID</span><span class="sxs-lookup"><span data-stu-id="c867c-146">id</span></span>
 - <span data-ttu-id="c867c-147">Familie: Contains = (sucht nach allen Patienten, deren Familienname den Wert enthält.)</span><span class="sxs-lookup"><span data-stu-id="c867c-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="c867c-148">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="c867c-148">given=\<substring></span></span>
 - <span data-ttu-id="c867c-149">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="c867c-149">name=\<substring></span></span>
 - <span data-ttu-id="c867c-150">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="c867c-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="c867c-151">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="c867c-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="c867c-152">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl \_ wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="c867c-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="c867c-153">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="c867c-153">identifier=\<mrn></span></span>

<span data-ttu-id="c867c-154">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="c867c-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="c867c-155">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="c867c-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="c867c-156">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="c867c-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="c867c-157">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="c867c-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="c867c-158">Name</span><span class="sxs-lookup"><span data-stu-id="c867c-158">Name</span></span>
- <span data-ttu-id="c867c-159">BirthDate</span><span class="sxs-lookup"><span data-stu-id="c867c-159">Birthdate</span></span>

<span data-ttu-id="c867c-160">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="c867c-160">See the following example  of this call.</span></span>

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

<span data-ttu-id="c867c-161">Weitere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="c867c-162">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="c867c-162">Observation</span></span>

<span data-ttu-id="c867c-163">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut Vital Signs-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="c867c-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="c867c-164">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="c867c-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="c867c-165">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="c867c-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="c867c-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="c867c-166">ValueQuantity.Value</span></span>

<span data-ttu-id="c867c-167">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="c867c-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="c867c-168">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="c867c-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="c867c-169">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="c867c-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="c867c-170">Wenn Sie Komponenten Beobachtungen verwenden, gilt dieselbe Logik für jede Komponentenüberwachung.</span><span class="sxs-lookup"><span data-stu-id="c867c-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="c867c-171">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c867c-172">Patient =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="c867c-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="c867c-173">Sort: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="c867c-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="c867c-174">Das Ziel besteht darin, die neuesten vitalen Zeichen für einen Patienten abzurufen [VitalSigns. ДСТУ. SAZ] (Observation?).</span><span class="sxs-lookup"><span data-stu-id="c867c-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="c867c-175">Weitere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="c867c-176">Bedingung</span><span class="sxs-lookup"><span data-stu-id="c867c-176">Condition</span></span>

<span data-ttu-id="c867c-177">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind:</span><span class="sxs-lookup"><span data-stu-id="c867c-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="c867c-178">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="c867c-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="c867c-179">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="c867c-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="c867c-180">Aufnahmedatum</span><span class="sxs-lookup"><span data-stu-id="c867c-180">Date Recorded</span></span>
 - <span data-ttu-id="c867c-181">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="c867c-181">Severity</span></span>

<span data-ttu-id="c867c-182">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c867c-183">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c867c-183">patient=\<patient id></span></span>
 - <span data-ttu-id="c867c-184">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c867c-184">_count=\<max results></span></span>

<span data-ttu-id="c867c-185">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="c867c-185">See the following example of this call:</span></span>

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

<span data-ttu-id="c867c-186">Weitere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="c867c-187">Auftreten</span><span class="sxs-lookup"><span data-stu-id="c867c-187">Encounter</span></span>

<span data-ttu-id="c867c-188">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder für das US-Core-Encounter-Profil "muss" handelt:</span><span class="sxs-lookup"><span data-stu-id="c867c-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="c867c-189">Status</span><span class="sxs-lookup"><span data-stu-id="c867c-189">Status</span></span>
 - <span data-ttu-id="c867c-190">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="c867c-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="c867c-191">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils</span><span class="sxs-lookup"><span data-stu-id="c867c-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="c867c-192">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="c867c-192">Period.Start</span></span>
 - <span data-ttu-id="c867c-193">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="c867c-193">Location[0].Location.Display</span></span>

<span data-ttu-id="c867c-194">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c867c-195">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c867c-195">patient=\<patient id></span></span>
 - <span data-ttu-id="c867c-196">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="c867c-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="c867c-197">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c867c-197">_count=\<max results></span></span>

<span data-ttu-id="c867c-198">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="c867c-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="c867c-199">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="c867c-199">Each encounter references a location resource.</span></span> <span data-ttu-id="c867c-200">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="c867c-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="c867c-201">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="c867c-201">See the following example of this call.</span></span>

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

<span data-ttu-id="c867c-202">Weitere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="c867c-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="c867c-203">AllergyIntolerance</span></span>

<span data-ttu-id="c867c-204">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-AllergyIntolerance-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="c867c-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="c867c-205">Code. Text</span><span class="sxs-lookup"><span data-stu-id="c867c-205">Code.Text</span></span>
 - <span data-ttu-id="c867c-206">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="c867c-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="c867c-207">Status</span><span class="sxs-lookup"><span data-stu-id="c867c-207">Status</span></span>

<span data-ttu-id="c867c-208">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="c867c-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="c867c-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="c867c-209">RecordedDate</span></span>
 - <span data-ttu-id="c867c-210">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="c867c-210">Note.Text</span></span>
 - <span data-ttu-id="c867c-211">Reaktion [..]. Substanz. Text</span><span class="sxs-lookup"><span data-stu-id="c867c-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="c867c-212">Reaktion [..]. Manifestation [..]. Text</span><span class="sxs-lookup"><span data-stu-id="c867c-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="c867c-213">Text. div</span><span class="sxs-lookup"><span data-stu-id="c867c-213">Text.Div</span></span>

<span data-ttu-id="c867c-214">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c867c-215">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="c867c-215">Patient =  \<patient id></span></span>

<span data-ttu-id="c867c-216">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="c867c-216">See the following example of this call:</span></span>

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

<span data-ttu-id="c867c-217">Weitere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="c867c-218">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="c867c-218">Medication Order</span></span>

<span data-ttu-id="c867c-219">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-MedicationOrder-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="c867c-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="c867c-220">DateWritten</span><span class="sxs-lookup"><span data-stu-id="c867c-220">DateWritten</span></span>
 - <span data-ttu-id="c867c-221">Verschreiber. Display</span><span class="sxs-lookup"><span data-stu-id="c867c-221">Prescriber.Display</span></span>
 - <span data-ttu-id="c867c-222">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="c867c-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="c867c-223">Medikation. Text (wenn Konzept)</span><span class="sxs-lookup"><span data-stu-id="c867c-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="c867c-224">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="c867c-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="c867c-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="c867c-225">DateEnded</span></span>
 - <span data-ttu-id="c867c-226">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="c867c-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="c867c-227">Text. div</span><span class="sxs-lookup"><span data-stu-id="c867c-227">Text.Div</span></span>

<span data-ttu-id="c867c-228">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c867c-229">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c867c-229">patient=\<patient id></span></span>
 - <span data-ttu-id="c867c-230">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c867c-230">_count=\<max results></span></span>

<span data-ttu-id="c867c-231">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="c867c-231">See the following example of this call:</span></span>

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

<span data-ttu-id="c867c-232">Weitere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="c867c-233">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="c867c-233">Coverage</span></span>

<span data-ttu-id="c867c-234">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="c867c-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="c867c-235">Zahlenden</span><span class="sxs-lookup"><span data-stu-id="c867c-235">Payor</span></span>

<span data-ttu-id="c867c-236">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="c867c-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c867c-237">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c867c-237">patient=\<patient id></span></span>

<span data-ttu-id="c867c-238">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="c867c-238">See the following example of this call:</span></span>

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
    
<span data-ttu-id="c867c-239">Weitere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="c867c-240">Ort</span><span class="sxs-lookup"><span data-stu-id="c867c-240">Location</span></span>

<span data-ttu-id="c867c-241">Diese Ressource wird nur als Referenz für die [Encounter](#encounter) -Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="c867c-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="c867c-242">Weitere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c867c-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
