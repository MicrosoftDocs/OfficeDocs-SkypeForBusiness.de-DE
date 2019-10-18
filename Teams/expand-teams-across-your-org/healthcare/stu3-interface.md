---
title: Patienten-APP und EPA-Integrations STU3-Schnittstelle
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
ms.openlocfilehash: 836c28f339a3936f03315b005c0eedfc49e0f2ba
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569243"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="4dec5-103">Benutzeroberflächenspezifikation STU3</span><span class="sxs-lookup"><span data-stu-id="4dec5-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4dec5-104">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="4dec5-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4dec5-105">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4dec5-106">Patienten</span><span class="sxs-lookup"><span data-stu-id="4dec5-106">Patient</span></span>](#patient)
- [<span data-ttu-id="4dec5-107">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="4dec5-107">Observation</span></span>](#observation)
- [<span data-ttu-id="4dec5-108">Bedingung</span><span class="sxs-lookup"><span data-stu-id="4dec5-108">Condition</span></span>](#condition)
- [<span data-ttu-id="4dec5-109">Auftreten</span><span class="sxs-lookup"><span data-stu-id="4dec5-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4dec5-110">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="4dec5-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4dec5-111">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="4dec5-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="4dec5-112">[Medikations Anweisung](#medication-request) (ersetzt die MedicationOrder in der DSTU2-Version des PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="4dec5-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="4dec5-113">Ort (die Informationen, die aus dieser Ressource benötigt werden, können in der Begegnung enthalten sein)</span><span class="sxs-lookup"><span data-stu-id="4dec5-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="4dec5-114">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen wird). Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4dec5-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4dec5-115">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource müssen ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers senden.</span><span class="sxs-lookup"><span data-stu-id="4dec5-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4dec5-116">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die den jeweiligen Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4dec5-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4dec5-117">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="4dec5-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="4dec5-118">Capability-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4dec5-118">Capability Statement</span></span>

<span data-ttu-id="4dec5-119">Hierbei handelt es sich um die erforderlichen Mindestanforderungen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="4dec5-120">Rest</span><span class="sxs-lookup"><span data-stu-id="4dec5-120">REST</span></span>
   1. <span data-ttu-id="4dec5-121">Modus</span><span class="sxs-lookup"><span data-stu-id="4dec5-121">Mode</span></span>
   2. <span data-ttu-id="4dec5-122">Interaktion</span><span class="sxs-lookup"><span data-stu-id="4dec5-122">Interaction</span></span>
   3. <span data-ttu-id="4dec5-123">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="4dec5-123">Resource: Type</span></span>
   4. <span data-ttu-id="4dec5-124">Sicherheit: [Erweiterung für OAuth-URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4dec5-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="4dec5-125">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten.)</span><span class="sxs-lookup"><span data-stu-id="4dec5-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="4dec5-126">Weitere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4dec5-127">Patienten</span><span class="sxs-lookup"><span data-stu-id="4dec5-127">Patient</span></span>

<span data-ttu-id="4dec5-128">Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge der Argonaut-Patientenprofil Felder sind:</span><span class="sxs-lookup"><span data-stu-id="4dec5-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="4dec5-129">Name. given</span><span class="sxs-lookup"><span data-stu-id="4dec5-129">Name.Given</span></span>
2. <span data-ttu-id="4dec5-130">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="4dec5-130">Name.Family</span></span>
3. <span data-ttu-id="4dec5-131">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="4dec5-131">Gender</span></span>
4. <span data-ttu-id="4dec5-132">BirthDate</span><span class="sxs-lookup"><span data-stu-id="4dec5-132">BirthDate</span></span>
5. <span data-ttu-id="4dec5-133">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="4dec5-133">MRN (Identifier)</span></span>

<span data-ttu-id="4dec5-134">Zusätzlich zu den [Argonaut-Feldern](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4dec5-135">Name. use</span><span class="sxs-lookup"><span data-stu-id="4dec5-135">Name.Use</span></span>
2. <span data-ttu-id="4dec5-136">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="4dec5-136">Name.Prefix</span></span>
3. <span data-ttu-id="4dec5-137">[GeneralPractitioner] – der GeneralPractitioner-Verweis sollte in die Patienten Ressource aufgenommen werden (nur Anzeigefeld)</span><span class="sxs-lookup"><span data-stu-id="4dec5-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="4dec5-138">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-139">ID</span><span class="sxs-lookup"><span data-stu-id="4dec5-139">id</span></span>
2. <span data-ttu-id="4dec5-140">Familie = (sucht nach allen Patienten, deren Familienname den Wert enthält)</span><span class="sxs-lookup"><span data-stu-id="4dec5-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="4dec5-141">given =\<Teilzeichenfolge></span><span class="sxs-lookup"><span data-stu-id="4dec5-141">given=\<substring></span></span>
4. <span data-ttu-id="4dec5-142">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="4dec5-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="4dec5-143">Gender = (Werte, die einer der administrativen-Gender-Werte sind)</span><span class="sxs-lookup"><span data-stu-id="4dec5-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="4dec5-144">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="4dec5-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4dec5-145">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurück \_gegeben wurden, und die Anzahl wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="4dec5-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="4dec5-146">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="4dec5-146">identifier=\<mrn></span></span>

<span data-ttu-id="4dec5-147">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="4dec5-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4dec5-148">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="4dec5-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4dec5-149">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="4dec5-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4dec5-150">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="4dec5-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="4dec5-151">Name</span><span class="sxs-lookup"><span data-stu-id="4dec5-151">Name</span></span>
- <span data-ttu-id="4dec5-152">BirthDate</span><span class="sxs-lookup"><span data-stu-id="4dec5-152">Birthdate</span></span>

<span data-ttu-id="4dec5-153">Sehen Sie sich das folgende Beispiel des Anrufs an:</span><span class="sxs-lookup"><span data-stu-id="4dec5-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="4dec5-154">Request: Post <fhir-Server>/Patient/_search Request Body: given = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="4dec5-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="4dec5-155">Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "Typ": "searchset"; "Total": 1; "Link": [{"Relation": "selbst"; "URL": <fhir-Server>/Patient/_search "}]," Eintrag ": [{" fullUrl ": <fhir-Server>/Patient/<Patient-ID>"; "Resource": {"Ressource": "Patient"; "ID": "<Patient-ID>"; "Meta": {"Version-ID": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "Text": {"Status": "generated"; "div": "</span><span class="sxs-lookup"><span data-stu-id="4dec5-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="4dec5-156">\n</span><span class="sxs-lookup"><span data-stu-id="4dec5-156">\n</span></span>        <p><span data-ttu-id="4dec5-157">Ruth schwarz</span><span class="sxs-lookup"><span data-stu-id="4dec5-157">Ruth Black</span></span></p><span data-ttu-id="4dec5-158">\n</span><span class="sxs-lookup"><span data-stu-id="4dec5-158">\n</span></span>      </div><span data-ttu-id="4dec5-159">"}," Bezeichner ": [{" Use ":" üblich ";" Typ ": {" Coding ": [{" System ":"http://hl7.org/fhir/v2/0203";" Code ":" Herr ";" Anzeige ":" medizinische Datensatznummer ";" userSelected ": falsch}]," Text ":" medizinische Datensatznummer "}," System "http://hospital.smarthealthit.org:" "," Wert ":" 1234567 "}]," aktiv ": wahr;" Name ": [{" Use ":" offiziell ";" Familie ":" schwarz ";" given ": [" Ruth ";" C. "</span><span class="sxs-lookup"><span data-stu-id="4dec5-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="4dec5-160">]}], "Telecom": [{"System": "Telefon"; "Wert": "800-599-2739", "Use": "Home"}, {"System": "Telefon"; "Wert": "800-808-7785"; "verwenden": "Mobil"}, {"System": "e-Mail"; "Wert": "Ruth.Black@example.com"}], "Geschlecht": "weiblich"; "Geburtsdatum": "1951-08-23"; " Address ": [{" Use ":" Home ";" Zeile ": [" 26 South RdApt 22 "]," Ort ":" Sapulpa "," State ":" OK "," PLZ ":" 74066 "," Land ":" USA "}]}," suchen ": {" Modus ":" Übereinstimmung "}}]}</span><span class="sxs-lookup"><span data-stu-id="4dec5-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="4dec5-161">Request: besorgen Sie sich <fhir-Server>/Patient/<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="4dec5-162">Response: {"Ressourcenname": "Patient"; "ID": "<Patient-ID>"; "Identifier": [{"Use": "üblich"; "Typ": {"Coding": [{"System":http://hl7.org/fhir/v2/0203""; "Code": "Herr",}], "Text": "medizinische Datensatznummer"}, "Wert": "1234567"}], "Name": [{"Use": "offizielle"; " Family ":" Adams ";" given ": [" Daniel ";" X. "</span><span class="sxs-lookup"><span data-stu-id="4dec5-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="4dec5-163">]}], "Gender": "männlich"; "Geburtsdatum": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="4dec5-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="4dec5-164">Weitere [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4dec5-165">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="4dec5-165">Observation</span></span>

<span data-ttu-id="4dec5-166">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut Vital-Signs-Profils](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)sind.</span><span class="sxs-lookup"><span data-stu-id="4dec5-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="4dec5-167">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="4dec5-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="4dec5-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="4dec5-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="4dec5-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="4dec5-169">ValueQuantity.Value</span></span>

<span data-ttu-id="4dec5-170">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4dec5-171">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="4dec5-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="4dec5-172">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="4dec5-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="4dec5-173">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-174">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-174">patient=\<patient id></span></span>
2. <span data-ttu-id="4dec5-175">_sort =-Datum</span><span class="sxs-lookup"><span data-stu-id="4dec5-175">_sort=-date</span></span>
3. <span data-ttu-id="4dec5-176">Kategorie (wir werden nach "Category = Vital-Signs" suchen), um die Liste der Vitalzeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4dec5-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="4dec5-177">Beziehen Sie sich auf dieses Beispiel des Anrufs:</span><span class="sxs-lookup"><span data-stu-id="4dec5-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="4dec5-178">Request: besorgen Sie sich <fhir-Server>/Observation? Patient =<Patient-ID>&Kategorie = Vital-Zeichen</span><span class="sxs-lookup"><span data-stu-id="4dec5-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="4dec5-179">Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>", "Type": "searchset", "Total": 20; "Eintrag": [{"Resource": {"Ressourcentyp": "Observation"; "ID": "<Resource-ID>"; "Kategorie": [{"Coding": [{"System"http://hl7.org/fhir/observation-category: "", "Code": " Vital-Signs "}],}]," Code ": {" Coding ": [{" System ":http://loinc.org" "," Code ":" 8867-4 "," Display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" Wert ": 72,0," Unit ":" {Beats}/min. "," System "http://unitsofmeasure.org:" ",}}},.</span><span class="sxs-lookup"><span data-stu-id="4dec5-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="4dec5-180">.</span><span class="sxs-lookup"><span data-stu-id="4dec5-180"></span></span>
        <span data-ttu-id="4dec5-181">.</span><span class="sxs-lookup"><span data-stu-id="4dec5-181"></span></span>
      <span data-ttu-id="4dec5-182">] }</span><span class="sxs-lookup"><span data-stu-id="4dec5-182"></span></span>

* * *

<span data-ttu-id="4dec5-183">Weitere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4dec5-184">Bedingung</span><span class="sxs-lookup"><span data-stu-id="4dec5-184">Condition</span></span>

<span data-ttu-id="4dec5-185">Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge des Argonaut- [Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind.</span><span class="sxs-lookup"><span data-stu-id="4dec5-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="4dec5-186">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="4dec5-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="4dec5-187">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4dec5-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4dec5-188">AssertedDate</span></span>
2. <span data-ttu-id="4dec5-189">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="4dec5-189">Severity</span></span>

<span data-ttu-id="4dec5-190">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-191">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-191">patient=\<patient id></span></span>
2. <span data-ttu-id="4dec5-192">_Count =\<maximale Ergebnisse></span><span class="sxs-lookup"><span data-stu-id="4dec5-192">_count=\<max results></span></span>

<span data-ttu-id="4dec5-193">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="4dec5-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4dec5-194">Request: besorgen Sie sich <fhir-Server>/Condition? Patient =<Patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4dec5-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4dec5-195">Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Type": "searchset", "Total": 2; "Eintrag": [{"Resource": {"Ressource": "Bedingung"; "ID": "<Resource-ID>"; "Code": {"Coding": [{"System":http://snomed.info/sct""; "Code": "185903001"; " Display ":" benötigt eine Influenza-Impfung ",}]}," Schweregrad ": {" Coding ": [{" Systemhttp://snomed.info/sct":" ";" Code ":" 24484000 ";" Display ":" schwere "}]}," assertedDate ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="4dec5-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="4dec5-196">.</span><span class="sxs-lookup"><span data-stu-id="4dec5-196"></span></span>
        <span data-ttu-id="4dec5-197">.</span><span class="sxs-lookup"><span data-stu-id="4dec5-197"></span></span>
      <span data-ttu-id="4dec5-198">] }</span><span class="sxs-lookup"><span data-stu-id="4dec5-198"></span></span>

* * *
<span data-ttu-id="4dec5-199">Weitere [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4dec5-200">Auftreten</span><span class="sxs-lookup"><span data-stu-id="4dec5-200">Encounter</span></span>

<span data-ttu-id="4dec5-201">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [US-Core-Encounter-Profils](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have"-Felder handelt.</span><span class="sxs-lookup"><span data-stu-id="4dec5-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="4dec5-202">Status</span><span class="sxs-lookup"><span data-stu-id="4dec5-202">Status</span></span>
2. <span data-ttu-id="4dec5-203">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="4dec5-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4dec5-204">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils:</span><span class="sxs-lookup"><span data-stu-id="4dec5-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="4dec5-205">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="4dec5-205">Period.Start</span></span>
2. <span data-ttu-id="4dec5-206">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="4dec5-206">Location[0].Location.Display</span></span>

<span data-ttu-id="4dec5-207">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-208">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-208">patient=\<patient id></span></span>
2. <span data-ttu-id="4dec5-209">_sort: DESC =\<Feld Ex.</span><span class="sxs-lookup"><span data-stu-id="4dec5-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="4dec5-210">Datum></span><span class="sxs-lookup"><span data-stu-id="4dec5-210">date></span></span>
3. <span data-ttu-id="4dec5-211">_Count =\<maximale Ergebnisse></span><span class="sxs-lookup"><span data-stu-id="4dec5-211">_count=\<max results></span></span>

<span data-ttu-id="4dec5-212">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="4dec5-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="4dec5-213">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="4dec5-213">Each encounter references a location resource.</span></span> <span data-ttu-id="4dec5-214">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="4dec5-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="4dec5-215">Weitere [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4dec5-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4dec5-216">AllergyIntolerance</span></span>

<span data-ttu-id="4dec5-217">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) -Profils sind:</span><span class="sxs-lookup"><span data-stu-id="4dec5-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="4dec5-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="4dec5-218">Code.Text</span></span>
2. <span data-ttu-id="4dec5-219">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="4dec5-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="4dec5-220">ClinicalStatus/VerificationStatus (wir lesen beide)</span><span class="sxs-lookup"><span data-stu-id="4dec5-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="4dec5-221">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch das folgende Feld lesen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="4dec5-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4dec5-222">AssertedDate</span></span>
2. <span data-ttu-id="4dec5-223">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="4dec5-223">Note.Text</span></span>
3. <span data-ttu-id="4dec5-224">Reaktion</span><span class="sxs-lookup"><span data-stu-id="4dec5-224">Reaction</span></span>
    1. <span data-ttu-id="4dec5-225">Substanz (ein Codierungselement)</span><span class="sxs-lookup"><span data-stu-id="4dec5-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="4dec5-226">Manifestation (ein Codierungselement)</span><span class="sxs-lookup"><span data-stu-id="4dec5-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="4dec5-227">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-228">Patient = \<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-228">Patient =  \<patient id></span></span>

<span data-ttu-id="4dec5-229">Sehen Sie sich das folgende Beispiel des Anrufs an:</span><span class="sxs-lookup"><span data-stu-id="4dec5-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="4dec5-230">Request: besorgen Sie sich <fhir-Server>/allergyintolerance? Patient =<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="4dec5-231">Antwort: {"Ressource": "Bundle"; "ID": "<-Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcentyp": "AllergyIntolerance"; "ID": "<Resource-ID>"; "clinicalStatus": "aktiv"; "ve rificationStatus ":" bestätigt ";" Code ": {" Coding ": [{" System ":"http://rxnav.nlm.nih.gov/REST/Ndfrt";" Code ":" N0000175503 ";" Display ":" Sulfonamid antibakteriell ",}]," Text ":" Sulfonamid Ant ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," Reaktion ": [{" Manifestation ": [{" Codierung ": [{" System ":"http://snomed.info/sct";" Code ":  "271807003", "Display": "Hautausschlag",}], "Text": "Hautausschlag"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4dec5-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4dec5-232">Weitere [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="4dec5-233">Medikations Anfrage</span><span class="sxs-lookup"><span data-stu-id="4dec5-233">Medication Request</span></span>

<span data-ttu-id="4dec5-234">Hierbei handelt es sich um die Mindestanforderungen, die eine Teilmenge des [US-Core-Medikaments anfordern](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="4dec5-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="4dec5-235">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="4dec5-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="4dec5-236">Medikation. Text (wenn CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="4dec5-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="4dec5-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="4dec5-237">AuthoredOn</span></span>
4. <span data-ttu-id="4dec5-238">Requestor. Agent. Display</span><span class="sxs-lookup"><span data-stu-id="4dec5-238">Requester.Agent.Display</span></span>

<span data-ttu-id="4dec5-239">Zusätzlich zu den US-Core-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4dec5-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4dec5-240">DosageInstruction[..]. Text</span><span class="sxs-lookup"><span data-stu-id="4dec5-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="4dec5-241">Text</span><span class="sxs-lookup"><span data-stu-id="4dec5-241">Text</span></span>

<span data-ttu-id="4dec5-242">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-243">Patient =\<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-243">patient=\<patient id></span></span>
2. <span data-ttu-id="4dec5-244">_Count =\<maximale Ergebnisse></span><span class="sxs-lookup"><span data-stu-id="4dec5-244">_count=\<max results></span></span>

<span data-ttu-id="4dec5-245">Weitere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4dec5-246">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="4dec5-246">Coverage</span></span>

<span data-ttu-id="4dec5-247">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="4dec5-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="4dec5-248">Gruppieren, mindestens ein Element mit</span><span class="sxs-lookup"><span data-stu-id="4dec5-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="4dec5-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="4dec5-249">GroupDisplay</span></span>
    2. <span data-ttu-id="4dec5-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="4dec5-250">PlanDisplay</span></span>
2. <span data-ttu-id="4dec5-251">Zeitraum</span><span class="sxs-lookup"><span data-stu-id="4dec5-251">Period</span></span>
3. <span data-ttu-id="4dec5-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="4dec5-252">SubscriberId</span></span>

<span data-ttu-id="4dec5-253">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4dec5-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4dec5-254">Patient = \<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4dec5-254">Patient = \<patient id></span></span>

<span data-ttu-id="4dec5-255">Weitere [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4dec5-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
