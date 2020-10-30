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
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803483"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="a3845-103">Benutzeroberflächenspezifikation DSTU2</span><span class="sxs-lookup"><span data-stu-id="a3845-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="a3845-104">Die Patienten-App wurde im 30. Oktober, 2020, eingestellt und durch die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a3845-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="a3845-105">Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a3845-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="a3845-106">Alle Daten, die mit der Patienten-App verknüpft sind, werden in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a3845-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="a3845-107">Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3845-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="a3845-108">Mit Listen können Betreuerteams in Ihrer Gesundheitsorganisation patientenlisten für Szenarien erstellen, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen.</span><span class="sxs-lookup"><span data-stu-id="a3845-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="a3845-109">Schauen Sie sich die Vorlage Patienten in Listen an, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a3845-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="a3845-110">Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="a3845-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="a3845-111">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="a3845-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="a3845-112">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="a3845-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="a3845-113">Patienten</span><span class="sxs-lookup"><span data-stu-id="a3845-113">Patient</span></span>](#patient)
- [<span data-ttu-id="a3845-114">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="a3845-114">Observation</span></span>](#observation)
- [<span data-ttu-id="a3845-115">Bedingung</span><span class="sxs-lookup"><span data-stu-id="a3845-115">Condition</span></span>](#condition)
- [<span data-ttu-id="a3845-116">Auftreten</span><span class="sxs-lookup"><span data-stu-id="a3845-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="a3845-117">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="a3845-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="a3845-118">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="a3845-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="a3845-119">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="a3845-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="a3845-120">Standort</span><span class="sxs-lookup"><span data-stu-id="a3845-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="a3845-121">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a3845-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="a3845-122">Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3845-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="a3845-123">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource Posten ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers.</span><span class="sxs-lookup"><span data-stu-id="a3845-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="a3845-124">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die mit den einzelnen Anforderungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a3845-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="a3845-125">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="a3845-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="a3845-126">Auf alle folgenden FHIR-Ressourcen sollte über direkten Ressourcenverweis zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="a3845-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="a3845-127">Konformitäts mindestanforderungs Feld Satz</span><span class="sxs-lookup"><span data-stu-id="a3845-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="a3845-128">Der FHIR-Server muss die Konformitätserklärung für uns implementieren, um eine sachliche Zusammenfassung seiner Funktionen zu haben.</span><span class="sxs-lookup"><span data-stu-id="a3845-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="a3845-129">Wir erwarten die folgenden Parameter in einem DSTU2-FHIR-Server:</span><span class="sxs-lookup"><span data-stu-id="a3845-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="a3845-130">Rest</span><span class="sxs-lookup"><span data-stu-id="a3845-130">REST</span></span>

    - <span data-ttu-id="a3845-131">Modus</span><span class="sxs-lookup"><span data-stu-id="a3845-131">Mode</span></span>
    - <span data-ttu-id="a3845-132">Interaktion</span><span class="sxs-lookup"><span data-stu-id="a3845-132">Interaction</span></span>
    - <span data-ttu-id="a3845-133">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="a3845-133">Resource: Type</span></span>
    - <span data-ttu-id="a3845-134">Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="a3845-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="a3845-135">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten, da wir mehrere Versionen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="a3845-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="a3845-136">Weitere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="a3845-137">Patienten</span><span class="sxs-lookup"><span data-stu-id="a3845-137">Patient</span></span>

<span data-ttu-id="a3845-138">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge der [Argonaut-Patientenprofil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder sind:</span><span class="sxs-lookup"><span data-stu-id="a3845-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="a3845-139">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="a3845-139">Name.Family</span></span>
 - <span data-ttu-id="a3845-140">Name. given</span><span class="sxs-lookup"><span data-stu-id="a3845-140">Name.Given</span></span>
 - <span data-ttu-id="a3845-141">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="a3845-141">Gender</span></span>
 - <span data-ttu-id="a3845-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="a3845-142">BirthDate</span></span>
 - <span data-ttu-id="a3845-143">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="a3845-143">MRN (Identifier)</span></span>

<span data-ttu-id="a3845-144">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="a3845-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="a3845-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="a3845-145">Name.Use</span></span>
 - <span data-ttu-id="a3845-146">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="a3845-146">Name.Prefix</span></span>
 - <span data-ttu-id="a3845-147">CareProvider (dieser Verweis auf die Patienten Ressource sollte die Anzeigefelder umfassen, die im folgenden Beispiel gezeigt werden.)</span><span class="sxs-lookup"><span data-stu-id="a3845-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="a3845-148">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="a3845-149">ID</span><span class="sxs-lookup"><span data-stu-id="a3845-149">id</span></span>
 - <span data-ttu-id="a3845-150">Familie: Contains = (sucht nach allen Patienten, deren Familienname den Wert enthält.)</span><span class="sxs-lookup"><span data-stu-id="a3845-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="a3845-151">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="a3845-151">given=\<substring></span></span>
 - <span data-ttu-id="a3845-152">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="a3845-152">name=\<substring></span></span>
 - <span data-ttu-id="a3845-153">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="a3845-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="a3845-154">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="a3845-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="a3845-155">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl \_ wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="a3845-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="a3845-156">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="a3845-156">identifier=\<mrn></span></span>

<span data-ttu-id="a3845-157">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="a3845-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="a3845-158">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="a3845-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="a3845-159">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="a3845-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="a3845-160">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="a3845-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="a3845-161">Name</span><span class="sxs-lookup"><span data-stu-id="a3845-161">Name</span></span>
- <span data-ttu-id="a3845-162">BirthDate</span><span class="sxs-lookup"><span data-stu-id="a3845-162">Birthdate</span></span>

<span data-ttu-id="a3845-163">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="a3845-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="a3845-164">Weitere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="a3845-165">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="a3845-165">Observation</span></span>

<span data-ttu-id="a3845-166">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut Vital Signs-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="a3845-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="a3845-167">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="a3845-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="a3845-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="a3845-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="a3845-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="a3845-169">ValueQuantity.Value</span></span>

<span data-ttu-id="a3845-170">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="a3845-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="a3845-171">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="a3845-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="a3845-172">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="a3845-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="a3845-173">Wenn Sie Komponenten Beobachtungen verwenden, gilt dieselbe Logik für jede Komponentenüberwachung.</span><span class="sxs-lookup"><span data-stu-id="a3845-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="a3845-174">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a3845-175">Patient =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="a3845-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="a3845-176">Sort: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="a3845-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="a3845-177">Das Ziel besteht darin, die neuesten vitalen Zeichen für einen Patienten abzurufen [VitalSigns. ДСТУ. SAZ] (Observation?).</span><span class="sxs-lookup"><span data-stu-id="a3845-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="a3845-178">Weitere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="a3845-179">Bedingung</span><span class="sxs-lookup"><span data-stu-id="a3845-179">Condition</span></span>

<span data-ttu-id="a3845-180">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind:</span><span class="sxs-lookup"><span data-stu-id="a3845-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="a3845-181">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="a3845-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="a3845-182">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="a3845-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="a3845-183">Aufnahmedatum</span><span class="sxs-lookup"><span data-stu-id="a3845-183">Date Recorded</span></span>
 - <span data-ttu-id="a3845-184">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="a3845-184">Severity</span></span>

<span data-ttu-id="a3845-185">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a3845-186">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a3845-186">patient=\<patient id></span></span>
 - <span data-ttu-id="a3845-187">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="a3845-187">_count=\<max results></span></span>

<span data-ttu-id="a3845-188">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="a3845-188">See the following example of this call:</span></span>

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

<span data-ttu-id="a3845-189">Weitere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="a3845-190">Auftreten</span><span class="sxs-lookup"><span data-stu-id="a3845-190">Encounter</span></span>

<span data-ttu-id="a3845-191">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder für das US-Core-Encounter-Profil "muss" handelt:</span><span class="sxs-lookup"><span data-stu-id="a3845-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="a3845-192">Status</span><span class="sxs-lookup"><span data-stu-id="a3845-192">Status</span></span>
 - <span data-ttu-id="a3845-193">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="a3845-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="a3845-194">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils</span><span class="sxs-lookup"><span data-stu-id="a3845-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="a3845-195">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="a3845-195">Period.Start</span></span>
 - <span data-ttu-id="a3845-196">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="a3845-196">Location[0].Location.Display</span></span>

<span data-ttu-id="a3845-197">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a3845-198">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a3845-198">patient=\<patient id></span></span>
 - <span data-ttu-id="a3845-199">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="a3845-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="a3845-200">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="a3845-200">_count=\<max results></span></span>

<span data-ttu-id="a3845-201">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="a3845-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="a3845-202">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="a3845-202">Each encounter references a location resource.</span></span> <span data-ttu-id="a3845-203">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="a3845-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="a3845-204">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="a3845-204">See the following example of this call.</span></span>

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

<span data-ttu-id="a3845-205">Weitere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="a3845-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="a3845-206">AllergyIntolerance</span></span>

<span data-ttu-id="a3845-207">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-AllergyIntolerance-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="a3845-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="a3845-208">Code. Text</span><span class="sxs-lookup"><span data-stu-id="a3845-208">Code.Text</span></span>
 - <span data-ttu-id="a3845-209">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="a3845-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="a3845-210">Status</span><span class="sxs-lookup"><span data-stu-id="a3845-210">Status</span></span>

<span data-ttu-id="a3845-211">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="a3845-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="a3845-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="a3845-212">RecordedDate</span></span>
 - <span data-ttu-id="a3845-213">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="a3845-213">Note.Text</span></span>
 - <span data-ttu-id="a3845-214">Reaktion [..]. Substanz. Text</span><span class="sxs-lookup"><span data-stu-id="a3845-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="a3845-215">Reaktion [..]. Manifestation [..]. Text</span><span class="sxs-lookup"><span data-stu-id="a3845-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="a3845-216">Text. div</span><span class="sxs-lookup"><span data-stu-id="a3845-216">Text.Div</span></span>

<span data-ttu-id="a3845-217">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a3845-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="a3845-218">Patient =  \<patient id></span></span>

<span data-ttu-id="a3845-219">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="a3845-219">See the following example of this call:</span></span>

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

<span data-ttu-id="a3845-220">Weitere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="a3845-221">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="a3845-221">Medication Order</span></span>

<span data-ttu-id="a3845-222">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-MedicationOrder-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="a3845-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="a3845-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="a3845-223">DateWritten</span></span>
 - <span data-ttu-id="a3845-224">Verschreiber. Display</span><span class="sxs-lookup"><span data-stu-id="a3845-224">Prescriber.Display</span></span>
 - <span data-ttu-id="a3845-225">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="a3845-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="a3845-226">Medikation. Text (wenn Konzept)</span><span class="sxs-lookup"><span data-stu-id="a3845-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="a3845-227">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="a3845-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="a3845-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="a3845-228">DateEnded</span></span>
 - <span data-ttu-id="a3845-229">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="a3845-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="a3845-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="a3845-230">Text.Div</span></span>

<span data-ttu-id="a3845-231">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a3845-232">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a3845-232">patient=\<patient id></span></span>
 - <span data-ttu-id="a3845-233">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="a3845-233">_count=\<max results></span></span>

<span data-ttu-id="a3845-234">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="a3845-234">See the following example of this call:</span></span>

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

<span data-ttu-id="a3845-235">Weitere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="a3845-236">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="a3845-236">Coverage</span></span>

<span data-ttu-id="a3845-237">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="a3845-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="a3845-238">Zahlenden</span><span class="sxs-lookup"><span data-stu-id="a3845-238">Payor</span></span>

<span data-ttu-id="a3845-239">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3845-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="a3845-240">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="a3845-240">patient=\<patient id></span></span>

<span data-ttu-id="a3845-241">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="a3845-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="a3845-242">Weitere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="a3845-243">Ort</span><span class="sxs-lookup"><span data-stu-id="a3845-243">Location</span></span>

<span data-ttu-id="a3845-244">Diese Ressource wird nur als Referenz für die [Encounter](#encounter) -Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3845-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="a3845-245">Weitere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a3845-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
