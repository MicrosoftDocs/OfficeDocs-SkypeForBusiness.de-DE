---
title: Patienten-APP und EPA-Integrations DSTU2-Schnittstelle
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft Teams patients App EPA-Integration
ms.openlocfilehash: 179cd031b6e32ee3ed32a6d3be1fa4afaae68cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570369"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="39847-103">Benutzeroberflächenspezifikation DSTU2</span><span class="sxs-lookup"><span data-stu-id="39847-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="39847-104">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="39847-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="39847-105">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="39847-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="39847-106">Patienten</span><span class="sxs-lookup"><span data-stu-id="39847-106">Patient</span></span>](#patient)
- [<span data-ttu-id="39847-107">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="39847-107">Observation</span></span>](#observation)
- [<span data-ttu-id="39847-108">Bedingung</span><span class="sxs-lookup"><span data-stu-id="39847-108">Condition</span></span>](#condition)
- [<span data-ttu-id="39847-109">Auftreten</span><span class="sxs-lookup"><span data-stu-id="39847-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="39847-110">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="39847-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="39847-111">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="39847-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="39847-112">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="39847-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="39847-113">Standort</span><span class="sxs-lookup"><span data-stu-id="39847-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="39847-114">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="39847-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="39847-115">Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39847-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="39847-116">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource Posten ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers.</span><span class="sxs-lookup"><span data-stu-id="39847-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="39847-117">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die mit den einzelnen Anforderungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="39847-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="39847-118">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="39847-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="39847-119">Auf alle folgenden FHIR-Ressourcen sollte über direkten Ressourcenverweis zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="39847-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="39847-120">Konformitäts mindestanforderungs Feld Satz</span><span class="sxs-lookup"><span data-stu-id="39847-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="39847-121">Der FHIR-Server muss die Konformitätserklärung für uns implementieren, um eine sachliche Zusammenfassung seiner Funktionen zu haben.</span><span class="sxs-lookup"><span data-stu-id="39847-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="39847-122">Wir erwarten die folgenden Parameter in einem DSTU2-FHIR-Server:</span><span class="sxs-lookup"><span data-stu-id="39847-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="39847-123">Rest</span><span class="sxs-lookup"><span data-stu-id="39847-123">REST</span></span>
   1. <span data-ttu-id="39847-124">Modus</span><span class="sxs-lookup"><span data-stu-id="39847-124">Mode</span></span>
   2. <span data-ttu-id="39847-125">Interaktion</span><span class="sxs-lookup"><span data-stu-id="39847-125">Interaction</span></span>
   3. <span data-ttu-id="39847-126">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="39847-126">Resource: Type</span></span>
   4. <span data-ttu-id="39847-127">Sicherheit: [Erweiterung für OAuth-URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="39847-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="39847-128">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten, da wir mehrere Versionen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="39847-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="39847-129">Weitere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="39847-130">Patienten</span><span class="sxs-lookup"><span data-stu-id="39847-130">Patient</span></span>

<span data-ttu-id="39847-131">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge der [Argonaut-Patientenprofil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder sind:</span><span class="sxs-lookup"><span data-stu-id="39847-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="39847-132">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="39847-132">Name.Family</span></span>
2. <span data-ttu-id="39847-133">Name. given</span><span class="sxs-lookup"><span data-stu-id="39847-133">Name.Given</span></span>
3. <span data-ttu-id="39847-134">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="39847-134">Gender</span></span>
4. <span data-ttu-id="39847-135">BirthDate</span><span class="sxs-lookup"><span data-stu-id="39847-135">BirthDate</span></span>
5. <span data-ttu-id="39847-136">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="39847-136">MRN (Identifier)</span></span>

<span data-ttu-id="39847-137">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="39847-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="39847-138">Name. use</span><span class="sxs-lookup"><span data-stu-id="39847-138">Name.Use</span></span>
2. <span data-ttu-id="39847-139">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="39847-139">Name.Prefix</span></span>
3. <span data-ttu-id="39847-140">CareProvider (dieser Verweis auf die Patienten Ressource sollte die Anzeigefelder umfassen, die im folgenden Beispiel gezeigt werden.)</span><span class="sxs-lookup"><span data-stu-id="39847-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="39847-141">Request: besorgen Sie sich <fhir-Server>/Patient/<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="39847-142">Response: {"Ressourcenname": "Patient", "ID": "<Patient-ID>";</span><span class="sxs-lookup"><span data-stu-id="39847-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="39847-143">.</span><span class="sxs-lookup"><span data-stu-id="39847-143"></span></span>
      <span data-ttu-id="39847-144">.</span><span class="sxs-lookup"><span data-stu-id="39847-144"></span></span>
      <span data-ttu-id="39847-145">"Name": [{"Use": "offiziell"; "prefix": ["Mr"], "Familie": ["Chau"], "given": ["Hugh"]}], "Identifier": [{"Use": "offiziell"; "Typ": {"Coding": [{"System": "http://hl7.org/fhir/v2/0203"; "Code": "Herr"}]}, "Wert": "1234567"}], "Geschlecht": "männlich"; "Geburtsdatum": "1957-06-05 "," careProvider ": [{" Display ":" Jane Doe "}],}</span><span class="sxs-lookup"><span data-stu-id="39847-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="39847-146">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="39847-147">ID</span><span class="sxs-lookup"><span data-stu-id="39847-147">id</span></span>
2. <span data-ttu-id="39847-148">Familie: Contains = (sucht nach allen Patienten, deren Familienname den Wert enthält.)</span><span class="sxs-lookup"><span data-stu-id="39847-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="39847-149">given =\<Teilzeichenfolge></span><span class="sxs-lookup"><span data-stu-id="39847-149">given=\<substring></span></span>
4. <span data-ttu-id="39847-150">Name =\<Teilzeichenfolge></span><span class="sxs-lookup"><span data-stu-id="39847-150">name=\<substring></span></span>
5. <span data-ttu-id="39847-151">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="39847-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="39847-152">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="39847-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="39847-153">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben \_wurden, und die Anzahl wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="39847-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="39847-154">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="39847-154">identifier=\<mrn></span></span>

<span data-ttu-id="39847-155">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="39847-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="39847-156">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="39847-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="39847-157">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="39847-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="39847-158">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="39847-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="39847-159">Name</span><span class="sxs-lookup"><span data-stu-id="39847-159">Name</span></span>
- <span data-ttu-id="39847-160">BirthDate</span><span class="sxs-lookup"><span data-stu-id="39847-160">Birthdate</span></span>

<span data-ttu-id="39847-161">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="39847-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="39847-162">Request: Post <fhir-Server>/Patient/_search Request Body: given = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="39847-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="39847-163">Response: {"Ressourcenname": "Bundle", "ID": "<Bundle-ID>";</span><span class="sxs-lookup"><span data-stu-id="39847-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="39847-164">.</span><span class="sxs-lookup"><span data-stu-id="39847-164"></span></span>
      <span data-ttu-id="39847-165">.</span><span class="sxs-lookup"><span data-stu-id="39847-165"></span></span>
      <span data-ttu-id="39847-166">"Eintrag": [{"Ressource": {"Ressourcen": "Patient"; "ID": "<Patient-ID>"; "Name": [{"Text": "Hugh Chau", "Familie": ["Chau"], "given": ["Hugh"]}], "Gender": "männlich"; "Geburtsdatum": "1957-06-05"}, "suchen": {"der Modus": "Vergleich"}}]</span><span class="sxs-lookup"><span data-stu-id="39847-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="39847-167">Weitere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="39847-168">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="39847-168">Observation</span></span>

<span data-ttu-id="39847-169">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut Vital Signs-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="39847-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="39847-170">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="39847-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="39847-171">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="39847-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="39847-172">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="39847-172">ValueQuantity.Value</span></span>

<span data-ttu-id="39847-173">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="39847-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="39847-174">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="39847-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="39847-175">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="39847-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="39847-176">Wenn Sie Komponenten Beobachtungen verwenden, gilt dieselbe Logik für jede Komponentenüberwachung.</span><span class="sxs-lookup"><span data-stu-id="39847-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="39847-177">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="39847-178">Patient =\<Patienten-ID\></span><span class="sxs-lookup"><span data-stu-id="39847-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="39847-179">Sort: DESC =\<Feld Ex.</span><span class="sxs-lookup"><span data-stu-id="39847-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="39847-180">Datum\></span><span class="sxs-lookup"><span data-stu-id="39847-180">date\></span></span>

<span data-ttu-id="39847-181">Das Ziel besteht darin, die neuesten vitalen Zeichen für einen Patienten abzurufen [VitalSigns. ДСТУ. SAZ] (Observation?).</span><span class="sxs-lookup"><span data-stu-id="39847-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="39847-182">Request: besorgen Sie sich <fhir-Server>/Observation? Patient =<Patient-ID>&_sort:d ESC = Datum&Kategorie = Vital-Zeichen</span><span class="sxs-lookup"><span data-stu-id="39847-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="39847-183">Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Type": "searchset", "Total": 20; "Eintrag": [{"Resource": {"Ressource": "Observation"; "ID": "<Resource-ID>"; "Category": {"Coding": [{Code ":" Vital-Signs "}]," Code ": {" Codierung ": [{" System ":"http://loinc.org";" Code ":" 39156-5 ";" Display ":" BMI "}],}," effectiveDateTime ":" 2009-12-01 ";" valueQuantity ": {" Wert ": 34,4," Einheit ":" kg/m2 ";" System ":"http://unitsofmeasure.org";" Code ":" kg/m2 "}},},.</span><span class="sxs-lookup"><span data-stu-id="39847-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="39847-184">.</span><span class="sxs-lookup"><span data-stu-id="39847-184"></span></span>
        <span data-ttu-id="39847-185">.</span><span class="sxs-lookup"><span data-stu-id="39847-185"></span></span>
      <span data-ttu-id="39847-186">] }</span><span class="sxs-lookup"><span data-stu-id="39847-186"></span></span>

* * *

<span data-ttu-id="39847-187">Weitere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="39847-188">Bedingung</span><span class="sxs-lookup"><span data-stu-id="39847-188">Condition</span></span>

<span data-ttu-id="39847-189">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind:</span><span class="sxs-lookup"><span data-stu-id="39847-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="39847-190">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="39847-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="39847-191">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="39847-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="39847-192">Aufnahmedatum</span><span class="sxs-lookup"><span data-stu-id="39847-192">Date Recorded</span></span>
2. <span data-ttu-id="39847-193">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="39847-193">Severity</span></span>

<span data-ttu-id="39847-194">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="39847-195">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-195">patient=\<patient id></span></span>
2. <span data-ttu-id="39847-196">_Count =\<maximale Ergebnisse></span><span class="sxs-lookup"><span data-stu-id="39847-196">_count=\<max results></span></span>

<span data-ttu-id="39847-197">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="39847-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="39847-198">Request: besorgen Sie sich <fhir-Server>/Condition? Patient =<Patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="39847-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="39847-199">Antwort: {"Ressourcen": "Bundle", "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressource": "Bedingung"; "ID": "<Resource-ID>"; "Code": {"Coding": [{               "System": "http://snomed.info/sct", "Code": "386033004", "Display": "Neuropathie (Nervenschaden)"}]}, "dateRecorded": "2018-09-17", "Schweregrad": {"Codierung": [{"Syst EM ":"http://snomed.info/sct"," Code ":" 24484000 ";" Anzeige ":" schwere "}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="39847-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="39847-200">Weitere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="39847-201">Auftreten</span><span class="sxs-lookup"><span data-stu-id="39847-201">Encounter</span></span>

<span data-ttu-id="39847-202">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder für das US-Core-Encounter-Profil "muss" handelt:</span><span class="sxs-lookup"><span data-stu-id="39847-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="39847-203">Status</span><span class="sxs-lookup"><span data-stu-id="39847-203">Status</span></span>
2. <span data-ttu-id="39847-204">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="39847-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="39847-205">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils</span><span class="sxs-lookup"><span data-stu-id="39847-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="39847-206">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="39847-206">Period.Start</span></span>
2. <span data-ttu-id="39847-207">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="39847-207">Location[0].Location.Display</span></span>

<span data-ttu-id="39847-208">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="39847-209">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-209">patient=\<patient id></span></span>
2. <span data-ttu-id="39847-210">_sort: DESC =\<Feld Ex.</span><span class="sxs-lookup"><span data-stu-id="39847-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="39847-211">Datum></span><span class="sxs-lookup"><span data-stu-id="39847-211">date></span></span>
3. <span data-ttu-id="39847-212">_Count =\<maximale Ergebnisse></span><span class="sxs-lookup"><span data-stu-id="39847-212">_count=\<max results></span></span>

<span data-ttu-id="39847-213">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="39847-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="39847-214">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="39847-214">Each encounter references a location resource.</span></span> <span data-ttu-id="39847-215">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="39847-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="39847-216">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="39847-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="39847-217">Request: besorgen Sie sich <fhir-Server>/Encounter? Patient =<Patient-ID>&_sort:d ESC = Datum&_count = 1</span><span class="sxs-lookup"><span data-stu-id="39847-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="39847-218">Antwort: {"Ressourcen": "Bundle", "Type": "searchset", "Total": 1; "Eintrag": [{"Resource": {"Ressource": "Encounter"; "ID": "<Resource-ID>"; "Bezeichner": [{"Use": "offizielle"; "" ""<id>"" "" "" "" "" "" " : "angekommen", "Typ": [{"Coding": [{"Display": "Termin"}],}], "Patient": {"Bezug": "Patient/<Patient-ID>"}, "Period": {"Start": "09/17/2018 1:00:00 pm"}, "Ort": [{              "Ort": {"Anzeige": "Clinic-HNO"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="39847-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="39847-219">Weitere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="39847-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="39847-220">AllergyIntolerance</span></span>

<span data-ttu-id="39847-221">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-AllergyIntolerance-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="39847-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="39847-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="39847-222">Code.Text</span></span>
2. <span data-ttu-id="39847-223">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="39847-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="39847-224">Status</span><span class="sxs-lookup"><span data-stu-id="39847-224">Status</span></span>

<span data-ttu-id="39847-225">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="39847-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="39847-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="39847-226">RecordedDate</span></span>
2. <span data-ttu-id="39847-227">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="39847-227">Note.Text</span></span>
3. <span data-ttu-id="39847-228">Reaktion [..]. Substanz. Text</span><span class="sxs-lookup"><span data-stu-id="39847-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="39847-229">Reaktion [..]. Manifestation [..]. Text</span><span class="sxs-lookup"><span data-stu-id="39847-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="39847-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="39847-230">Text.Div</span></span>

<span data-ttu-id="39847-231">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="39847-232">Patient = \<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-232">Patient =  \<patient id></span></span>

<span data-ttu-id="39847-233">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="39847-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="39847-234">Request: besorgen Sie sich <fhir-Server>/allergyintolerance? Patient =<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="39847-235">Antwort: {"Ressourcen": "Bundle", "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "AllergyIntolerance"; "ID": "<Resource-ID>"; "recordedDate": "2018-09-17T07:00:00.00 0Z ";" Substanz ": {" Text ":" Cashew-Nüsse "}," Status ":" bestätigt "," Reaktion ": [{" Substanz ": {" Text ":" Cashew-Nuss-Allergen-Extrakt-injizierbares Produkt "}," manifestati auf ": [{" Text ":" anaphylaktischer-Reaktion "}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="39847-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="39847-236">Weitere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="39847-237">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="39847-237">Medication Order</span></span>

<span data-ttu-id="39847-238">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-MedicationOrder-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="39847-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="39847-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="39847-239">DateWritten</span></span>
2. <span data-ttu-id="39847-240">Verschreiber. Display</span><span class="sxs-lookup"><span data-stu-id="39847-240">Prescriber.Display</span></span>
3. <span data-ttu-id="39847-241">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="39847-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="39847-242">Medikation. Text (wenn Konzept)</span><span class="sxs-lookup"><span data-stu-id="39847-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="39847-243">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="39847-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="39847-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="39847-244">DateEnded</span></span>
2. <span data-ttu-id="39847-245">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="39847-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="39847-246">Text. div</span><span class="sxs-lookup"><span data-stu-id="39847-246">Text.Div</span></span>

<span data-ttu-id="39847-247">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="39847-248">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-248">patient=\<patient id></span></span>
2. <span data-ttu-id="39847-249">_Count =\<maximale Ergebnisse></span><span class="sxs-lookup"><span data-stu-id="39847-249">_count=\<max results></span></span>

<span data-ttu-id="39847-250">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="39847-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="39847-251">Request: besorgen Sie sich <fhir-Server>/medicationorder? Patient =<Patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="39847-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="39847-252">Antwort: {"Ressource": "Bundle"; "ID": "<-Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcentyp": "MedicationOrder"; "ID": "<Resource-ID>"; "dateWritten": "2018-09-17"; "Medi cationCodeableConcept ": {" Text ":" Lisinopril 20 mg Oral Tablet "}," Verschreiber ": {" Anzeige ":" Jane Doe "}," dosageInstruction ": [{" Text ":" 1 Daily "}]}}]}</span><span class="sxs-lookup"><span data-stu-id="39847-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="39847-253">Weitere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="39847-254">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="39847-254">Coverage</span></span>

<span data-ttu-id="39847-255">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="39847-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="39847-256">Zahlenden</span><span class="sxs-lookup"><span data-stu-id="39847-256">Payor</span></span>

<span data-ttu-id="39847-257">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="39847-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="39847-258">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-258">patient=\<patient id></span></span>

<span data-ttu-id="39847-259">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="39847-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="39847-260">Request: besorgen Sie sich <fhir-Server>/Coverage? Patient =<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="39847-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="39847-261">Antwort: {"Ressource": "Bundle"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "Coverage"; "ID": "<Resource-ID>"; "Plan": "keine Erstversicherung"; "Teilnehmer": {"Bezug": "Patient/ <Patient-ID> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="39847-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="39847-262">Weitere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="39847-263">Ort</span><span class="sxs-lookup"><span data-stu-id="39847-263">Location</span></span>

<span data-ttu-id="39847-264">Diese Ressource wird nur als Referenz für die [Encounter](#encounter) -Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="39847-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="39847-265">Weitere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="39847-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
