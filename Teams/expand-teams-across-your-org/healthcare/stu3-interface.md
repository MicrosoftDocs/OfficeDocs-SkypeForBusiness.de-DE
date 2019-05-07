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
# <a name="stu3-interface-specification"></a><span data-ttu-id="fdfd7-103">STU3 Interface-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="fdfd7-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="fdfd7-104">Einrichten oder Neukonfiguration einen FHIR Server die Microsoft-Teams Patienten app entwickelt ist erforderlich, welche die app muss für den Zugriff auf Daten zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="fdfd7-105">Der FHIR-Server muss POST-Anforderungen mithilfe der Pakete für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="fdfd7-106">Patienten</span><span class="sxs-lookup"><span data-stu-id="fdfd7-106">Patient</span></span>](#patient)
- [<span data-ttu-id="fdfd7-107">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-107">Observation</span></span>](#observation)
- [<span data-ttu-id="fdfd7-108">Bedingung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-108">Condition</span></span>](#condition)
- [<span data-ttu-id="fdfd7-109">Auftreten</span><span class="sxs-lookup"><span data-stu-id="fdfd7-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="fdfd7-110">Allergie Intoleranz</span><span class="sxs-lookup"><span data-stu-id="fdfd7-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="fdfd7-111">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="fdfd7-112">[Medikament-Anweisung](#medication-request) (ersetzt die MedicationOrder in der DSTU2 Version von der PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="fdfd7-113">Speicherort (die Informationen benötigt dieser Ressource in Kontakt aufgenommen werden können)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="fdfd7-114">Die Patient Ressource ist die einzigen obligatorischen Ressource (ohne den die app gar nicht geladen werden); Jedoch wird empfohlen, dass der Partner Unterstützung für die oben genannten Ressourcen pro Spezifikationen finden Sie weiter unten Endbenutzer am besten mit der Microsoft-Teams Patienten App implementieren.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="fdfd7-115">Abfragen von der Microsoft-Teams Patienten-app für mehr als eine Ressource ist eine Bundle (BATCH) von Anforderungen in FHIR die URL des Servers bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="fdfd7-116">Der Server muss jeder Anforderung verarbeiten und Zurückgeben einer Bundle Ressourcen mit jeder Anforderung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="fdfd7-117">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="fdfd7-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="fdfd7-118">Capability-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-118">Capability Statement</span></span>

<span data-ttu-id="fdfd7-119">Dies sind die mindestens erforderlichen Felder aus:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="fdfd7-120">Ruhepause</span><span class="sxs-lookup"><span data-stu-id="fdfd7-120">REST</span></span>
   1. <span data-ttu-id="fdfd7-121">Modus</span><span class="sxs-lookup"><span data-stu-id="fdfd7-121">Mode</span></span>
   2. <span data-ttu-id="fdfd7-122">Interaktion</span><span class="sxs-lookup"><span data-stu-id="fdfd7-122">Interaction</span></span>
   3. <span data-ttu-id="fdfd7-123">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="fdfd7-123">Resource: Type</span></span>
   4. <span data-ttu-id="fdfd7-124">Sicherheit: [Erweiterung für OAuth-URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="fdfd7-125">FhirVersion (unsere Code ist dies zu verstehen, welche Version wir zum Pivotieren sollte erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="fdfd7-126">Finden Sie unter [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="fdfd7-127">Patienten</span><span class="sxs-lookup"><span data-stu-id="fdfd7-127">Patient</span></span>

<span data-ttu-id="fdfd7-128">Es folgen die minimale erforderliche Felder, die eine Teilmenge der Felder Patient Profil Argonaut:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="fdfd7-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="fdfd7-129">Name.Given</span></span>
2. <span data-ttu-id="fdfd7-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="fdfd7-130">Name.Family</span></span>
3. <span data-ttu-id="fdfd7-131">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="fdfd7-131">Gender</span></span>
4. <span data-ttu-id="fdfd7-132">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="fdfd7-132">BirthDate</span></span>
5. <span data-ttu-id="fdfd7-133">MRN (ID)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-133">MRN (Identifier)</span></span>

<span data-ttu-id="fdfd7-134">Zusätzlich zu den [Argonaut Felder](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fdfd7-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="fdfd7-135">Name.Use</span></span>
2. <span data-ttu-id="fdfd7-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="fdfd7-136">Name.Prefix</span></span>
3. <span data-ttu-id="fdfd7-137">[GeneralPractitioner] - die GeneralPractitioner Verweis in der Patienten Ressource (nur Anzeigefeld) einbezogen werden soll</span><span class="sxs-lookup"><span data-stu-id="fdfd7-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="fdfd7-138">Eine Ressourcensuche verwendet die POST-Methode zur /Patient/_search und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-139">ID</span><span class="sxs-lookup"><span data-stu-id="fdfd7-139">id</span></span>
2. <span data-ttu-id="fdfd7-140">Produktfamilie = (sucht alle Patienten, deren Namen Produktfamilie enthält den Wert)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="fdfd7-141">angegebenen =\<Substring></span><span class="sxs-lookup"><span data-stu-id="fdfd7-141">given=\<substring></span></span>
4. <span data-ttu-id="fdfd7-142">Geburtsdatum =(exact match)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="fdfd7-143">Geschlecht = (Werte zu einem von der administrativen Geschlecht)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="fdfd7-144">\_(maximale Anzahl der Ergebnisse an, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="fdfd7-145">Die Antwort sollte die Gesamtzahl der als Ergebnis der Suche zurückgegebenen Datensätze enthalten und \_Anzahl wird durch die PatientsApp zur Begrenzung der Anzahl der zurückgegebenen Datensätze verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="fdfd7-146">ID =\<Mrn></span><span class="sxs-lookup"><span data-stu-id="fdfd7-146">identifier=\<mrn></span></span>

<span data-ttu-id="fdfd7-147">Ziel ist es, suchen und Filtern zu einem Patienten ein durch Folgendes möglich:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="fdfd7-148">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="fdfd7-149">MRN: Dies ist der tatsächlichen Bezeichner für den Patienten, den klinischer Mitarbeiter wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="fdfd7-150">Wir wissen, dass diese MRN Bezeichnertyp innerhalb der Bezeichner-Ressource im FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="fdfd7-151">Name</span><span class="sxs-lookup"><span data-stu-id="fdfd7-151">Name</span></span>
- <span data-ttu-id="fdfd7-152">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="fdfd7-152">Birthdate</span></span>

<span data-ttu-id="fdfd7-153">Finden Sie im folgenden Beispiel wird für den Aufruf aus:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="fdfd7-154">: POST <fhir-Server>/Patient/_search anfordern Anforderungstext: angegebenen = Ruth&family = Schwarz</span><span class="sxs-lookup"><span data-stu-id="fdfd7-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="fdfd7-155">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Meta": {"LastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "Typ": "Searchset", "total": 1, "Link": [{"Beziehung": "self", "Url": <fhir-Server>/Patient/_search "}],"Entry": [{ "FullUrl": <fhir-Server>/Patient/<patient-Id> ","Resource": {"ResourceType":"Patient","Id":"<patient Id>","Meta": {"VersionId":"1","LastUpdated":" 2017-10-18T18:32:37.000 + 00:00 "},"Text": {"Status":"generiert","Div ": "</span><span class="sxs-lookup"><span data-stu-id="fdfd7-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="fdfd7-156">\n</span><span class="sxs-lookup"><span data-stu-id="fdfd7-156">\n</span></span>        <p><span data-ttu-id="fdfd7-157">Ruth Schwarz</span><span class="sxs-lookup"><span data-stu-id="fdfd7-157">Ruth Black</span></span></p><span data-ttu-id="fdfd7-158">\n</span><span class="sxs-lookup"><span data-stu-id="fdfd7-158">\n</span></span>      </div><span data-ttu-id="fdfd7-159">"},"ID": [{"verwenden":"Normal""Typ": {"Codieren": [{"System":"http://hl7.org/fhir/v2/0203","Code":"MR","anzeigen":"medizinische Datensatznummer","UserSelected": false}],"Text":"medizinische Datensatznummer"},"System":"http://hospital.smarthealthit.org","Wert":"1234567"}],"aktiv":" true "," Name": [{"verwenden":"offizielle","Familie":"Schwarz","angegebenen": ["Ruth","c ".</span><span class="sxs-lookup"><span data-stu-id="fdfd7-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="fdfd7-160">]}], "Telekommunikation": [{"System": "Telefon", "Wert": "800-599-2739", "Verwendung": "Privat"}, {"System": "Telefon", "Wert": "800-808-7785", "Verwendung": "Mobil"}, {"System": "e-Mail", "Wert": "ruth.black@example.com"}], "Geschlecht": "weiblich", "Geburtsdatum": "1951-08-23", " Adresse": [{"verwenden":"Start","Zeile": ["26 South RdApt 22"],"Ort":"Sapulpa","Bundesland":"OK","PLZ":"74066","Country":"USA"}]},"Suche": {"Mode":"match"}}]}</span><span class="sxs-lookup"><span data-stu-id="fdfd7-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="fdfd7-161">Anforderung: GET <fhir-Server>/Patient/<patient-id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="fdfd7-162">Antwort: {"ResourceType": "Patient", "Id": "<patient Id>", "ID": [{"verwenden": "Normal" "Typ": {"Codieren": [{"System": "http://hl7.org/fhir/v2/0203", "Code": "MR,"}], "Text": "medizinische Datensatznummer"}, "Wert": "1234567"}], "Name": [{"verwenden": "offizielle", " Familie":"Adams","angegebenen": ["Daniel","X".</span><span class="sxs-lookup"><span data-stu-id="fdfd7-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="fdfd7-163">{]}], "Geschlecht": "Männlich", "Geburtsdatum": "1925-12-23"}</span><span class="sxs-lookup"><span data-stu-id="fdfd7-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="fdfd7-164">Finden Sie unter [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="fdfd7-165">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-165">Observation</span></span>

<span data-ttu-id="fdfd7-166">Dies sind die minimale erforderliche Felder, die eine Teilmenge des [Argonaut Grunddaten - Profil](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="fdfd7-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="fdfd7-167">Die Übermittlung wirksamer (Datum Zeiten)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="fdfd7-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="fdfd7-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="fdfd7-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="fdfd7-169">ValueQuantity.Value</span></span>

<span data-ttu-id="fdfd7-170">Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fdfd7-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="fdfd7-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="fdfd7-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="fdfd7-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="fdfd7-173">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-174">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-174">patient=\<patient id></span></span>
2. <span data-ttu-id="fdfd7-175">= _sort-Datum</span><span class="sxs-lookup"><span data-stu-id="fdfd7-175">_sort=-date</span></span>
3. <span data-ttu-id="fdfd7-176">Kategorie (es wird eine Abfrage für "Kategorie wichtiger Gleichheitszeichen (=)") zum Abrufen der Liste der wesentlichen auf Anzeichen für.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="fdfd7-177">Finden Sie in diesem Beispiel für den Anruf:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="fdfd7-178">Anforderung: <fhir-Server>/Beobachtung abrufen? Patient = <patient Id>&category wichtiger Gleichheitszeichen (=)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="fdfd7-179">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 20, "Entry": [{"Resource": {"ResourceType": "Beobachtung", "Id": "<resource Id>", "Kategorie": [{"Codieren": [{"System": "http://hl7.org/fhir/observation-category", "Code": " wichtige signiert"}];}],"code": {"Codieren": [{"System":"http://loinc.org","Code":"8867 4","Anzeige":"Heart_rate"}]},"EffectiveDateTime":" 2009-04-08T00:00:00-06:00 ","ValueQuantity": {"Wert": 72.0,"Einheit":" {schlägt} / min ","System":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="fdfd7-180">.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-180"></span></span>
        <span data-ttu-id="fdfd7-181">.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-181"></span></span>
      <span data-ttu-id="fdfd7-182">] }</span><span class="sxs-lookup"><span data-stu-id="fdfd7-182"></span></span>

* * *

<span data-ttu-id="fdfd7-183">Finden Sie unter [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="fdfd7-184">Bedingung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-184">Condition</span></span>

<span data-ttu-id="fdfd7-185">Hier wird die minimale erforderliche Felder, die eine Teilmenge des [Argonaut Bedingung Profil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="fdfd7-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="fdfd7-186">Code.Coding[0]. Anzeige</span><span class="sxs-lookup"><span data-stu-id="fdfd7-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="fdfd7-187">Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fdfd7-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="fdfd7-188">AssertedDate</span></span>
2. <span data-ttu-id="fdfd7-189">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="fdfd7-189">Severity</span></span>

<span data-ttu-id="fdfd7-190">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-191">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-191">patient=\<patient id></span></span>
2. <span data-ttu-id="fdfd7-192">_count =\<max Results></span><span class="sxs-lookup"><span data-stu-id="fdfd7-192">_count=\<max results></span></span>

<span data-ttu-id="fdfd7-193">Finden Sie im folgenden Beispiel wird dieses Anrufs:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="fdfd7-194">Anforderung: <fhir-Server>/Bedingung abrufen? Patient = <patient Id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="fdfd7-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="fdfd7-195">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 2, "Entry": [{"Resource": {"ResourceType": "Bedingung", "Id": "<resource Id>", "Code": {"Codieren": [{"System": "http://snomed.info/sct", "Code": "185903001", " Anzeigen von":"Anforderungen Influenza Impfung"}]},"Severity": {"Codieren": [{"System":"http://snomed.info/sct","Code":"24484000","anzeigen":"Severe"}]},"AssertedDate":"2018-04-04"}},.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="fdfd7-196">.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-196"></span></span>
        <span data-ttu-id="fdfd7-197">.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-197"></span></span>
      <span data-ttu-id="fdfd7-198">] }</span><span class="sxs-lookup"><span data-stu-id="fdfd7-198"></span></span>

* * *
<span data-ttu-id="fdfd7-199">Finden Sie unter [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="fdfd7-200">Auftreten</span><span class="sxs-lookup"><span data-stu-id="fdfd7-200">Encounter</span></span>

<span data-ttu-id="fdfd7-201">Dies sind die minimale erforderliche Felder, die eine Teilmenge der [USA Core auftreten Profil](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "benötigen" Felder).</span><span class="sxs-lookup"><span data-stu-id="fdfd7-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="fdfd7-202">Status</span><span class="sxs-lookup"><span data-stu-id="fdfd7-202">Status</span></span>
2. <span data-ttu-id="fdfd7-203">Typ [0]. Codieren [0]. Anzeige</span><span class="sxs-lookup"><span data-stu-id="fdfd7-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="fdfd7-204">Darüber hinaus Felder die folgenden Felder aus uns Core auftreten Profil "unterstützen" müssen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="fdfd7-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="fdfd7-205">Period.Start</span></span>
2. <span data-ttu-id="fdfd7-206">Position [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="fdfd7-206">Location[0].Location.Display</span></span>

<span data-ttu-id="fdfd7-207">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-208">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-208">patient=\<patient id></span></span>
2. <span data-ttu-id="fdfd7-209">_sort:desc =\<ex-Feld.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="fdfd7-210">date></span><span class="sxs-lookup"><span data-stu-id="fdfd7-210">date></span></span>
3. <span data-ttu-id="fdfd7-211">_count =\<max Results></span><span class="sxs-lookup"><span data-stu-id="fdfd7-211">_count=\<max results></span></span>

<span data-ttu-id="fdfd7-212">Ziel ist es, den Patienten letzten bekannten Speicherort abrufen können.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="fdfd7-213">Jede verweist auf eine Ressource Speicherort.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-213">Each encounter references a location resource.</span></span> <span data-ttu-id="fdfd7-214">Der Verweis umfassen ferner Anzeigefeld des Speicherorts.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="fdfd7-215">Finden Sie unter [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="fdfd7-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="fdfd7-216">AllergyIntolerance</span></span>

<span data-ttu-id="fdfd7-217">Dies sind die minimale erforderliche Felder, die eine Teilmenge des Profils [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="fdfd7-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="fdfd7-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="fdfd7-218">Code.Text</span></span>
2. <span data-ttu-id="fdfd7-219">Code.Coding[0]. Anzeige</span><span class="sxs-lookup"><span data-stu-id="fdfd7-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="fdfd7-220">ClinicalStatus/VerificationStatus (wir lesen beide)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="fdfd7-221">Zusätzlich zu den Feldern Argonaut kann für einen größeren Benutzerkomfort die Patienten app auch das folgende Feld lesen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="fdfd7-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="fdfd7-222">AssertedDate</span></span>
2. <span data-ttu-id="fdfd7-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="fdfd7-223">Note.Text</span></span>
3. <span data-ttu-id="fdfd7-224">Reaktion</span><span class="sxs-lookup"><span data-stu-id="fdfd7-224">Reaction</span></span>
    1. <span data-ttu-id="fdfd7-225">Inhalt (eine Codierung-Element)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="fdfd7-226">Manifestation (ein Beispiel für Element)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="fdfd7-227">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-228">Patient = \<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-228">Patient =  \<patient id></span></span>

<span data-ttu-id="fdfd7-229">Finden Sie im folgenden Beispiel wird für den Aufruf aus:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="fdfd7-230">Anforderung: <fhir-Server>/AllergyIntolerance abrufen? Patient = <patient Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="fdfd7-231">Antwort: {"ResourceType": "Verpacken", "Id": "<bundle Id>", "Typ": "Searchset", "total": 1, "Entry": [{"Resource": {"ResourceType": "AllergyIntolerance", "Id": "<resource Id>", "ClinicalStatus": "aktiv", "Ve RificationStatus":"bestätigt","Code": {"Codieren": [{"System":"http://rxnav.nlm.nih.gov/REST/Ndfrt","Code":"N0000175503","anzeigen":"Sulfonamid antibakterieller"}],"Text":"Sulfonamid Ant Ibacterial"},"AssertedDate":" 2018-01-01T00:00:00-07:00 ","Reaktion": [{"Manifestation": [{"Codieren": [{"System":"http://snomed.info/sct","Code":  "271807003", "anzeigen": "Hautausschlag"}], "Text": "Hautausschlag"}];}]}}]}</span><span class="sxs-lookup"><span data-stu-id="fdfd7-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="fdfd7-232">Finden Sie unter [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="fdfd7-233">Medikament-Anforderung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-233">Medication Request</span></span>

<span data-ttu-id="fdfd7-234">Dies sind die minimale erforderliche Felder, die eine Teilmenge des [Profils US Core Medikament anfordern](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="fdfd7-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="fdfd7-235">Medication.Display (wenn Referenz)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="fdfd7-236">Medication.Text (wenn CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="fdfd7-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="fdfd7-237">AuthoredOn</span></span>
4. <span data-ttu-id="fdfd7-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="fdfd7-238">Requester.Agent.Display</span></span>

<span data-ttu-id="fdfd7-239">Zusätzlich zu den Feldern uns Core kann für einen größeren Benutzerkomfort die Patienten app auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fdfd7-240">DosageInstruction [.]. Text</span><span class="sxs-lookup"><span data-stu-id="fdfd7-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="fdfd7-241">Text</span><span class="sxs-lookup"><span data-stu-id="fdfd7-241">Text</span></span>

<span data-ttu-id="fdfd7-242">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-243">Patient =\<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-243">patient=\<patient id></span></span>
2. <span data-ttu-id="fdfd7-244">_count =\<max Results></span><span class="sxs-lookup"><span data-stu-id="fdfd7-244">_count=\<max results></span></span>

<span data-ttu-id="fdfd7-245">Finden Sie unter [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="fdfd7-246">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="fdfd7-246">Coverage</span></span>

<span data-ttu-id="fdfd7-247">Dies sind die minimalen Pflichtfelder nicht fallen uns Core oder Argonaut Profile:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="fdfd7-248">Gruppierung, mindestens ein Element mit</span><span class="sxs-lookup"><span data-stu-id="fdfd7-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="fdfd7-249">Gruppe anzeigenZeigen</span><span class="sxs-lookup"><span data-stu-id="fdfd7-249">GroupDisplay</span></span>
    2. <span data-ttu-id="fdfd7-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="fdfd7-250">PlanDisplay</span></span>
2. <span data-ttu-id="fdfd7-251">Zeitraum</span><span class="sxs-lookup"><span data-stu-id="fdfd7-251">Period</span></span>
3. <span data-ttu-id="fdfd7-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="fdfd7-252">SubscriberId</span></span>

<span data-ttu-id="fdfd7-253">Eine Ressourcensuche verwendet der GET-Methode und die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fdfd7-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fdfd7-254">Patient = \<Patienten Id></span><span class="sxs-lookup"><span data-stu-id="fdfd7-254">Patient = \<patient id></span></span>

<span data-ttu-id="fdfd7-255">Finden Sie unter [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) für andere Details für dieses Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fdfd7-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
