---
title: " Patienten App und EHR Integration DSTU2-Schnittstelle"
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
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643104"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="04f8f-103">DSTU2 Interface-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="04f8f-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="04f8f-104">Einrichten oder Neukonfiguration einen FHIR Server die Microsoft-Teams Patienten app entwickelt ist erforderlich, welche die app muss für den Zugriff auf Daten zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="04f8f-105">Der FHIR-Server muss POST-Anforderungen mithilfe der Pakete für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="04f8f-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="04f8f-106">Patienten</span><span class="sxs-lookup"><span data-stu-id="04f8f-106">Patient</span></span>](#patient)
- [<span data-ttu-id="04f8f-107">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="04f8f-107">Observation</span></span>](#observation)
- [<span data-ttu-id="04f8f-108">Bedingung</span><span class="sxs-lookup"><span data-stu-id="04f8f-108">Condition</span></span>](#condition)
- [<span data-ttu-id="04f8f-109">Auftreten</span><span class="sxs-lookup"><span data-stu-id="04f8f-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="04f8f-110">Allergie Intoleranz</span><span class="sxs-lookup"><span data-stu-id="04f8f-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="04f8f-111">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="04f8f-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="04f8f-112">Medikament Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="04f8f-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="04f8f-113">Standort</span><span class="sxs-lookup"><span data-stu-id="04f8f-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="04f8f-114">Die Patient Ressource ist die einzigen obligatorischen Ressource (ohne den die app gar nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="04f8f-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="04f8f-115">Jedoch wird empfohlen, dass der Partner Unterstützung für die oben genannten Ressourcen pro Spezifikationen finden Sie weiter unten Endbenutzer am besten mit der Microsoft-Teams Patienten App implementieren.</span><span class="sxs-lookup"><span data-stu-id="04f8f-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="04f8f-116">Abfragen von der Microsoft-Teams Patienten-app für mehr als einer Ressource bereitstellen eine Bundle (BATCH) von Anforderungen in FHIR die URL des Servers.</span><span class="sxs-lookup"><span data-stu-id="04f8f-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="04f8f-117">Der Server jeder Anforderung verarbeitet und gibt ein Bundle Ressourcen mit jeder Anforderung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="04f8f-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="04f8f-118">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="04f8f-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="04f8f-119">Die folgenden FHIR-Ressourcen sollten Verweis direkte Ressource verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="04f8f-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="04f8f-120">Legen Sie die Konformität minimale Pflichtfeld</span><span class="sxs-lookup"><span data-stu-id="04f8f-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="04f8f-121">Die FHIR-Server muss die Konformität-Anweisung für uns eine konkrete Zusammenfassung der Funktionen haben implementieren.</span><span class="sxs-lookup"><span data-stu-id="04f8f-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="04f8f-122">Wir erwarten, dass die folgenden Parameter in einem DSTU2 FHIR Server:</span><span class="sxs-lookup"><span data-stu-id="04f8f-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="04f8f-123">Ruhepause</span><span class="sxs-lookup"><span data-stu-id="04f8f-123">REST</span></span>
   1. <span data-ttu-id="04f8f-124">Modus</span><span class="sxs-lookup"><span data-stu-id="04f8f-124">Mode</span></span>
   2. <span data-ttu-id="04f8f-125">Interaktion</span><span class="sxs-lookup"><span data-stu-id="04f8f-125">Interaction</span></span>
   3. <span data-ttu-id="04f8f-126">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="04f8f-126">Resource: Type</span></span>
   4. <span data-ttu-id="04f8f-127">Sicherheit: [Erweiterung für OAuth-URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="04f8f-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="04f8f-128">FhirVersion (unsere Code erfordert dies zu verstehen, welche Version wir Pivotieren sollte wie wir mehrere Versionen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="04f8f-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="04f8f-129">Finden Sie unter [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="04f8f-130">Patienten</span><span class="sxs-lookup"><span data-stu-id="04f8f-130">Patient</span></span>

<span data-ttu-id="04f8f-131">Dies sind die minimale erforderliche Felder, die eine Teilmenge der [Patienten Profil Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder:</span><span class="sxs-lookup"><span data-stu-id="04f8f-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="04f8f-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="04f8f-132">Name.Family</span></span>
2. <span data-ttu-id="04f8f-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="04f8f-133">Name.Given</span></span>
3. <span data-ttu-id="04f8f-134">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="04f8f-134">Gender</span></span>
4. <span data-ttu-id="04f8f-135">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="04f8f-135">BirthDate</span></span>
5. <span data-ttu-id="04f8f-136">MRN (ID)</span><span class="sxs-lookup"><span data-stu-id="04f8f-136">MRN (Identifier)</span></span>

<span data-ttu-id="04f8f-137">Zusätzlich zu den Feldern Argonaut liest für einen größeren Benutzerkomfort die Patienten app außerdem die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="04f8f-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="04f8f-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="04f8f-138">Name.Use</span></span>
2. <span data-ttu-id="04f8f-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="04f8f-139">Name.Prefix</span></span>
3. <span data-ttu-id="04f8f-140">CareProvider (dieser Referenz für die Patienten Ressource sollte im folgenden Beispiel gezeigten die Anzeigen von Feldern enthalten.)</span><span class="sxs-lookup"><span data-stu-id="04f8f-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="04f8f-141">Anforderung: GET <fhir-Server>/Patient/<patient-id></span><span class="sxs-lookup"><span data-stu-id="04f8f-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="04f8f-142">Antwort: {"ResourceType": "Patient", "Id": "<patient-Id>".</span><span class="sxs-lookup"><span data-stu-id="04f8f-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="04f8f-143">.</span><span class="sxs-lookup"><span data-stu-id="04f8f-143"></span></span>
      <span data-ttu-id="04f8f-144">.</span><span class="sxs-lookup"><span data-stu-id="04f8f-144"></span></span>
      <span data-ttu-id="04f8f-145">"Name": [{"verwenden": "offizielle", "Präfix": ["Mr"], "Familie": ["Chau"], "angegebenen": ["Hugh"]}], "ID": [{"verwenden": "offizielle", "Typ": {"Codieren": [{"System": "http://hl7.org/fhir/v2/0203", "Code": "MR"}]}, "Wert": "1234567"}], "Geschlecht": "Männlich", "Geburtsdatum": "1957-06-05 ","CareProvider": [{"anzeigen":"Susanne"}];}</span><span class="sxs-lookup"><span data-stu-id="04f8f-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="04f8f-146">Eine Ressourcensuche verwendet die POST-Methode zur /Patient/_search und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-147">ID</span><span class="sxs-lookup"><span data-stu-id="04f8f-147">id</span></span>
2. <span data-ttu-id="04f8f-148">Familie: enthält = (sucht nach allen Patienten, deren Namen Produktfamilie enthält den Wert).</span><span class="sxs-lookup"><span data-stu-id="04f8f-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="04f8f-149">angegebenen =\<Substring></span><span class="sxs-lookup"><span data-stu-id="04f8f-149">given=\<substring></span></span>
4. <span data-ttu-id="04f8f-150">Name =\<Substring></span><span class="sxs-lookup"><span data-stu-id="04f8f-150">name=\<substring></span></span>
5. <span data-ttu-id="04f8f-151">Geburtsdatum =(exact match)</span><span class="sxs-lookup"><span data-stu-id="04f8f-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="04f8f-152">\_(maximale Anzahl der Ergebnisse an, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="04f8f-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="04f8f-153">Die Antwort sollte die Gesamtzahl der als Ergebnis der Suche zurückgegebenen Datensätze enthalten und \_Anzahl wird durch die PatientsApp zur Begrenzung der Anzahl der zurückgegebenen Datensätze verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04f8f-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="04f8f-154">ID =\<Mrn></span><span class="sxs-lookup"><span data-stu-id="04f8f-154">identifier=\<mrn></span></span>

<span data-ttu-id="04f8f-155">Ziel ist es, suchen und Filtern zu einem Patienten ein durch Folgendes möglich:</span><span class="sxs-lookup"><span data-stu-id="04f8f-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="04f8f-156">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="04f8f-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="04f8f-157">MRN: Dies ist der tatsächlichen Bezeichner für den Patienten, den klinischer Mitarbeiter wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="04f8f-158">Wir wissen, dass diese MRN Bezeichnertyp innerhalb der Bezeichner-Ressource im FHIR basiert</span><span class="sxs-lookup"><span data-stu-id="04f8f-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="04f8f-159">Name</span><span class="sxs-lookup"><span data-stu-id="04f8f-159">Name</span></span>
- <span data-ttu-id="04f8f-160">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="04f8f-160">Birthdate</span></span>

<span data-ttu-id="04f8f-161">Finden Sie im folgenden Beispiel wird dieses Anrufs.</span><span class="sxs-lookup"><span data-stu-id="04f8f-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="04f8f-162">: POST <fhir-Server>/Patient/_search anfordern Anforderungstext: angegebenen = Hugh&family = Chau</span><span class="sxs-lookup"><span data-stu-id="04f8f-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="04f8f-163">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle-Id>".</span><span class="sxs-lookup"><span data-stu-id="04f8f-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="04f8f-164">.</span><span class="sxs-lookup"><span data-stu-id="04f8f-164"></span></span>
      <span data-ttu-id="04f8f-165">.</span><span class="sxs-lookup"><span data-stu-id="04f8f-165"></span></span>
      <span data-ttu-id="04f8f-166">"Entry": [{"Resource": {"ResourceType": "Patient", "Id": "<patient Id>", "Name": [{"Text": "Hugh Chau", "Familie": ["Chau"], "angegebenen": "" [Hugh]}], "Geschlecht": "Männlich", "Geburtsdatum": "1957-06-05"}, "Suche": {"Mode": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="04f8f-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="04f8f-167">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="04f8f-168">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="04f8f-168">Observation</span></span>

<span data-ttu-id="04f8f-169">Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils auf Anzeichen für meine Argonaut:</span><span class="sxs-lookup"><span data-stu-id="04f8f-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="04f8f-170">Die Übermittlung wirksamer (Datum Zeiten)</span><span class="sxs-lookup"><span data-stu-id="04f8f-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="04f8f-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="04f8f-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="04f8f-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="04f8f-172">ValueQuantity.Value</span></span>

<span data-ttu-id="04f8f-173">Zusätzlich zu den Feldern Argonaut liest für einen größeren Benutzerkomfort die Patienten app außerdem die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="04f8f-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="04f8f-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="04f8f-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="04f8f-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="04f8f-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="04f8f-176">Wenn Sie Komponente Beobachtungen verwenden, gilt die Logik für jede Komponente Beobachtung.</span><span class="sxs-lookup"><span data-stu-id="04f8f-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="04f8f-177">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-178">Patient =\<Patienten-Id\></span><span class="sxs-lookup"><span data-stu-id="04f8f-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="04f8f-179">Sortieren: Desc =\<ex-Feld.</span><span class="sxs-lookup"><span data-stu-id="04f8f-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="04f8f-180">Datum\></span><span class="sxs-lookup"><span data-stu-id="04f8f-180">date\></span></span>

<span data-ttu-id="04f8f-181">Ziel ist es, die neuesten wesentlichen Anzeichen zu einem Patienten ein [VitalSigns.DSTU.saz] (Beobachtung?) abrufen können.</span><span class="sxs-lookup"><span data-stu-id="04f8f-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="04f8f-182">Anforderung: <fhir-Server>/Beobachtung abrufen? Patient = <patient-Id>&_sort:desc Date&category = wichtiger Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="04f8f-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="04f8f-183">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 20, "Entry": [{"Resource": {"ResourceType": "Beobachtung", "Id": "<resource Id>", "Kategorie": {"Codieren": [{Code":"wichtiger Anzeichen"}];},"Code": {" Codieren": [{"System":"http://loinc.org","Code":"39156-5","Anzeige":"Bmi"}];},"EffectiveDateTime":"2009-12-01","ValueQuantity": {"Wert": 34.4,"Einheit":" kg/m2","System":"http://unitsofmeasure.org","Code":" kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="04f8f-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="04f8f-184">.</span><span class="sxs-lookup"><span data-stu-id="04f8f-184"></span></span>
        <span data-ttu-id="04f8f-185">.</span><span class="sxs-lookup"><span data-stu-id="04f8f-185"></span></span>
      <span data-ttu-id="04f8f-186">] }</span><span class="sxs-lookup"><span data-stu-id="04f8f-186"></span></span>

* * *

<span data-ttu-id="04f8f-187">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="04f8f-188">Bedingung</span><span class="sxs-lookup"><span data-stu-id="04f8f-188">Condition</span></span>

<span data-ttu-id="04f8f-189">Dies sind die minimale erforderliche Felder, die eine Teilmenge des [Argonaut Bedingung Profil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="04f8f-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="04f8f-190">Code.Coding[0]. Anzeige</span><span class="sxs-lookup"><span data-stu-id="04f8f-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="04f8f-191">Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="04f8f-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="04f8f-192">Datum erfasst</span><span class="sxs-lookup"><span data-stu-id="04f8f-192">Date Recorded</span></span>
2. <span data-ttu-id="04f8f-193">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="04f8f-193">Severity</span></span>

<span data-ttu-id="04f8f-194">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-195">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-195">patient=\<patient id></span></span>
2. <span data-ttu-id="04f8f-196">_count =\<max Results></span><span class="sxs-lookup"><span data-stu-id="04f8f-196">_count=\<max results></span></span>

<span data-ttu-id="04f8f-197">Finden Sie im folgenden Beispiel wird dieses Anrufs:</span><span class="sxs-lookup"><span data-stu-id="04f8f-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="04f8f-198">Anforderung: <fhir-Server>/Bedingung abrufen? Patient = <patient Id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="04f8f-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="04f8f-199">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "Bedingung", "Id": "<resource Id>", "Code": {"Codieren": [{               "System": "http://snomed.info/sct", "Code": "386033004", "anzeigen": "Neuropathy (Nerven Beschädigung)"}]}, "DateRecorded": "2018-09-17", "Severity": {"Codieren": [{"Syst Dieser Abschnitt":"http://snomed.info/sct","Code":"24484000","anzeigen":"Severe"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="04f8f-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="04f8f-200">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="04f8f-201">Auftreten</span><span class="sxs-lookup"><span data-stu-id="04f8f-201">Encounter</span></span>

<span data-ttu-id="04f8f-202">Dies sind die minimale erforderliche Felder, die eine Teilmenge der uns Core auftreten Profil "benötigen" Felder:</span><span class="sxs-lookup"><span data-stu-id="04f8f-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="04f8f-203">Status</span><span class="sxs-lookup"><span data-stu-id="04f8f-203">Status</span></span>
2. <span data-ttu-id="04f8f-204">Typ [0]. Codieren [0]. Anzeige</span><span class="sxs-lookup"><span data-stu-id="04f8f-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="04f8f-205">Darüber hinaus Felder die folgenden Felder aus uns Core auftreten Profil "unterstützen" müssen</span><span class="sxs-lookup"><span data-stu-id="04f8f-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="04f8f-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="04f8f-206">Period.Start</span></span>
2. <span data-ttu-id="04f8f-207">Position [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="04f8f-207">Location[0].Location.Display</span></span>

<span data-ttu-id="04f8f-208">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-209">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-209">patient=\<patient id></span></span>
2. <span data-ttu-id="04f8f-210">_sort:desc =\<ex-Feld.</span><span class="sxs-lookup"><span data-stu-id="04f8f-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="04f8f-211">date></span><span class="sxs-lookup"><span data-stu-id="04f8f-211">date></span></span>
3. <span data-ttu-id="04f8f-212">_count =\<max Results></span><span class="sxs-lookup"><span data-stu-id="04f8f-212">_count=\<max results></span></span>

<span data-ttu-id="04f8f-213">Ziel ist es, den Patienten letzten bekannten Speicherort abrufen können.</span><span class="sxs-lookup"><span data-stu-id="04f8f-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="04f8f-214">Jede verweist auf eine Ressource Speicherort.</span><span class="sxs-lookup"><span data-stu-id="04f8f-214">Each encounter references a location resource.</span></span> <span data-ttu-id="04f8f-215">Der Verweis umfassen ferner Anzeigefeld des Speicherorts.</span><span class="sxs-lookup"><span data-stu-id="04f8f-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="04f8f-216">Finden Sie im folgenden Beispiel wird dieses Anrufs.</span><span class="sxs-lookup"><span data-stu-id="04f8f-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="04f8f-217">Anforderung: Erste <fhir-Server>/treffen? Patient = <patient-Id>&_sort:desc = Date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="04f8f-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="04f8f-218">Antwort: {"ResourceType": "Bundle", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "Auftreten", "Id": "<resource Id>", "ID": [{"verwenden": "offizielle", "Wert": "<id>"}], "Status" : "angekommen", "Typ": [{"Codieren": [{"anzeigen": "Termin"}],}], "Patient": {"Referenz": "Patient/<patient-Id>"} "Punkt": {"start": "09/17/2018 1:00:00 PM"}, "Ort": [{              "Position": {"anzeigen": "Clinic – ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="04f8f-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="04f8f-219">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="04f8f-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="04f8f-220">AllergyIntolerance</span></span>

<span data-ttu-id="04f8f-221">Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="04f8f-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="04f8f-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="04f8f-222">Code.Text</span></span>
2. <span data-ttu-id="04f8f-223">Code.Coding[0]. Anzeige</span><span class="sxs-lookup"><span data-stu-id="04f8f-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="04f8f-224">Status</span><span class="sxs-lookup"><span data-stu-id="04f8f-224">Status</span></span>

<span data-ttu-id="04f8f-225">Zusätzlich zu den Feldern Argonaut liest für einen größeren Benutzerkomfort die Patienten app außerdem die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="04f8f-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="04f8f-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="04f8f-226">RecordedDate</span></span>
2. <span data-ttu-id="04f8f-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="04f8f-227">Note.Text</span></span>
3. <span data-ttu-id="04f8f-228">Reaktion [.]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="04f8f-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="04f8f-229">Reaktion [.]. Manifestation [.]. Text</span><span class="sxs-lookup"><span data-stu-id="04f8f-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="04f8f-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="04f8f-230">Text.Div</span></span>

<span data-ttu-id="04f8f-231">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-232">Patient = \<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-232">Patient =  \<patient id></span></span>

<span data-ttu-id="04f8f-233">Finden Sie im folgenden Beispiel wird dieses Anrufs:</span><span class="sxs-lookup"><span data-stu-id="04f8f-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="04f8f-234">Anforderung: <fhir-Server>/AllergyIntolerance abrufen? Patient = <patient Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="04f8f-235">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "AllergyIntolerance", "Id": "<resource Id>", "RecordedDate": "2018-09-17T07:00:00.00 0Z","Inhalt": {"Text":"Cashew Nuts"},"Status":"bestätigt","Reaktion": [{"Inhalt": {"Text":"Cashew Mutter allergener extrahieren um injizierbare Produkt"},"Manifestati auf": [{"Text":"Anaphylactic Reaktion"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="04f8f-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="04f8f-236">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="04f8f-237">Medikament Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="04f8f-237">Medication Order</span></span>

<span data-ttu-id="04f8f-238">Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="04f8f-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="04f8f-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="04f8f-239">DateWritten</span></span>
2. <span data-ttu-id="04f8f-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="04f8f-240">Prescriber.Display</span></span>
3. <span data-ttu-id="04f8f-241">Medication.Display (wenn Referenz)</span><span class="sxs-lookup"><span data-stu-id="04f8f-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="04f8f-242">Medication.Text (wenn Konzept)</span><span class="sxs-lookup"><span data-stu-id="04f8f-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="04f8f-243">Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="04f8f-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="04f8f-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="04f8f-244">DateEnded</span></span>
2. <span data-ttu-id="04f8f-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="04f8f-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="04f8f-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="04f8f-246">Text.Div</span></span>

<span data-ttu-id="04f8f-247">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-248">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-248">patient=\<patient id></span></span>
2. <span data-ttu-id="04f8f-249">_count =\<max Results></span><span class="sxs-lookup"><span data-stu-id="04f8f-249">_count=\<max results></span></span>

<span data-ttu-id="04f8f-250">Finden Sie im folgenden Beispiel wird dieses Anrufs:</span><span class="sxs-lookup"><span data-stu-id="04f8f-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="04f8f-251">Anforderung: <fhir-Server>/MedicationOrder abrufen? Patient = <patient Id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="04f8f-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="04f8f-252">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "MedicationOrder", "Id": "<resource Id>", "DateWritten": "2018-09-17", "Medi CationCodeableConcept": {"Text":"Lisinopril 20 MG mündliche Tablet"},"prescriber": {"anzeigen":"Susanne"},"DosageInstruction": [{"Text":"1 täglich"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="04f8f-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="04f8f-253">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="04f8f-254">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="04f8f-254">Coverage</span></span>

<span data-ttu-id="04f8f-255">Dies sind die minimalen Pflichtfelder nicht fallen uns Core oder Argonaut Profile:</span><span class="sxs-lookup"><span data-stu-id="04f8f-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="04f8f-256">Erstattungsorganisationen sicherzustellen</span><span class="sxs-lookup"><span data-stu-id="04f8f-256">Payor</span></span>

<span data-ttu-id="04f8f-257">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="04f8f-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04f8f-258">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-258">patient=\<patient id></span></span>

<span data-ttu-id="04f8f-259">Finden Sie im folgenden Beispiel wird dieses Anrufs:</span><span class="sxs-lookup"><span data-stu-id="04f8f-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="04f8f-260">Anforderung: <fhir-Server>/Abdeckung abrufen? Patient = <patient Id></span><span class="sxs-lookup"><span data-stu-id="04f8f-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="04f8f-261">Antwort: {"ResourceType": "Bundle", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "Abdeckung", "Id": "<resource Id>", "Plan": "No primären Versicherungsvertreter", "Abonnenten": {"Referenz": "Patient / <patient Id> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="04f8f-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="04f8f-262">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="04f8f-263">Ort</span><span class="sxs-lookup"><span data-stu-id="04f8f-263">Location</span></span>

<span data-ttu-id="04f8f-264">Diese Ressource wird nur als Verweis auf die Ressource [auftreten](#encounter) verwendet.</span><span class="sxs-lookup"><span data-stu-id="04f8f-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="04f8f-265">Finden Sie unter [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04f8f-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
