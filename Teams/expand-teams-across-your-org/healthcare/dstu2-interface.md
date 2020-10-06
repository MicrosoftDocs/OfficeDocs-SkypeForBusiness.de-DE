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
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361455"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="58c37-103">Benutzeroberflächenspezifikation DSTU2</span><span class="sxs-lookup"><span data-stu-id="58c37-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58c37-104">**Die Patienten-APP ist ab dem 15. Oktober 2020 veraltet, und die Benutzer können Sie nicht mehr aus dem App Store von Teams installieren. Wir empfehlen Ihnen, die Listen- [App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams noch heute zu verwenden.**</span><span class="sxs-lookup"><span data-stu-id="58c37-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="58c37-105">Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="58c37-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="58c37-106">Wenn die patients-App eingestellt wird, werden alle damit verknüpften Daten in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="58c37-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="58c37-107">Aktuelle Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="58c37-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="58c37-108">Die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) ist für alle Teams-Benutzer vorinstalliert und steht in allen Teams und Kanälen als Registerkarte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="58c37-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="58c37-109">Mit Listen können Betreuerteams mithilfe der integrierten Patienten Vorlage, von Grund auf neu oder durch Importieren von Daten nach Excel, patientenlisten erstellen.</span><span class="sxs-lookup"><span data-stu-id="58c37-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="58c37-110">Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="58c37-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="58c37-111">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="58c37-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="58c37-112">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="58c37-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="58c37-113">Patienten</span><span class="sxs-lookup"><span data-stu-id="58c37-113">Patient</span></span>](#patient)
- [<span data-ttu-id="58c37-114">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="58c37-114">Observation</span></span>](#observation)
- [<span data-ttu-id="58c37-115">Bedingung</span><span class="sxs-lookup"><span data-stu-id="58c37-115">Condition</span></span>](#condition)
- [<span data-ttu-id="58c37-116">Auftreten</span><span class="sxs-lookup"><span data-stu-id="58c37-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="58c37-117">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="58c37-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="58c37-118">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="58c37-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="58c37-119">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="58c37-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="58c37-120">Standort</span><span class="sxs-lookup"><span data-stu-id="58c37-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="58c37-121">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="58c37-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="58c37-122">Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58c37-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="58c37-123">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource Posten ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers.</span><span class="sxs-lookup"><span data-stu-id="58c37-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="58c37-124">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die mit den einzelnen Anforderungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="58c37-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="58c37-125">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="58c37-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="58c37-126">Auf alle folgenden FHIR-Ressourcen sollte über direkten Ressourcenverweis zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="58c37-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="58c37-127">Konformitäts mindestanforderungs Feld Satz</span><span class="sxs-lookup"><span data-stu-id="58c37-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="58c37-128">Der FHIR-Server muss die Konformitätserklärung für uns implementieren, um eine sachliche Zusammenfassung seiner Funktionen zu haben.</span><span class="sxs-lookup"><span data-stu-id="58c37-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="58c37-129">Wir erwarten die folgenden Parameter in einem DSTU2-FHIR-Server:</span><span class="sxs-lookup"><span data-stu-id="58c37-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="58c37-130">Rest</span><span class="sxs-lookup"><span data-stu-id="58c37-130">REST</span></span>
   1. <span data-ttu-id="58c37-131">Modus</span><span class="sxs-lookup"><span data-stu-id="58c37-131">Mode</span></span>
   2. <span data-ttu-id="58c37-132">Interaktion</span><span class="sxs-lookup"><span data-stu-id="58c37-132">Interaction</span></span>
   3. <span data-ttu-id="58c37-133">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="58c37-133">Resource: Type</span></span>
   4. <span data-ttu-id="58c37-134">Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="58c37-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="58c37-135">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten, da wir mehrere Versionen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="58c37-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="58c37-136">Weitere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="58c37-137">Patienten</span><span class="sxs-lookup"><span data-stu-id="58c37-137">Patient</span></span>

<span data-ttu-id="58c37-138">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge der [Argonaut-Patientenprofil](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) Felder sind:</span><span class="sxs-lookup"><span data-stu-id="58c37-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="58c37-139">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="58c37-139">Name.Family</span></span>
2. <span data-ttu-id="58c37-140">Name. given</span><span class="sxs-lookup"><span data-stu-id="58c37-140">Name.Given</span></span>
3. <span data-ttu-id="58c37-141">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="58c37-141">Gender</span></span>
4. <span data-ttu-id="58c37-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="58c37-142">BirthDate</span></span>
5. <span data-ttu-id="58c37-143">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="58c37-143">MRN (Identifier)</span></span>

<span data-ttu-id="58c37-144">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="58c37-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="58c37-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="58c37-145">Name.Use</span></span>
2. <span data-ttu-id="58c37-146">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="58c37-146">Name.Prefix</span></span>
3. <span data-ttu-id="58c37-147">CareProvider (dieser Verweis auf die Patienten Ressource sollte die Anzeigefelder umfassen, die im folgenden Beispiel gezeigt werden.)</span><span class="sxs-lookup"><span data-stu-id="58c37-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="58c37-148">Request: besorgen Sie sich <fhir-Server>/Patient/<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="58c37-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="58c37-149">Response: {"Ressourcenname": "Patient", "ID": "<Patient-ID>";</span><span class="sxs-lookup"><span data-stu-id="58c37-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="58c37-150">.</span><span class="sxs-lookup"><span data-stu-id="58c37-150">.</span></span>
      <span data-ttu-id="58c37-151">.</span><span class="sxs-lookup"><span data-stu-id="58c37-151">.</span></span>
      <span data-ttu-id="58c37-152">"Name": [{"Use": "offiziell"; "prefix": ["Mr"], "Familie": ["Chau"], "given": ["Hugh"]}], "Identifier": [{"Use": "offiziell", "Typ": {"Codierung": [{"System": " https://hl7.org/fhir/v2/0203 "; "Code": "Herr"}]}, "Wert": "1234567"}], "Geschlecht": "männlich", "Geburtstag": "1957-06-05", "careProvider": [{"Display": "Jane Doe"}],}</span><span class="sxs-lookup"><span data-stu-id="58c37-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="58c37-153">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="58c37-154">ID</span><span class="sxs-lookup"><span data-stu-id="58c37-154">id</span></span>
2. <span data-ttu-id="58c37-155">Familie: Contains = (sucht nach allen Patienten, deren Familienname den Wert enthält.)</span><span class="sxs-lookup"><span data-stu-id="58c37-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="58c37-156">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="58c37-156">given=\<substring></span></span>
4. <span data-ttu-id="58c37-157">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="58c37-157">name=\<substring></span></span>
5. <span data-ttu-id="58c37-158">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="58c37-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="58c37-159">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="58c37-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="58c37-160">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl \_ wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="58c37-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="58c37-161">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="58c37-161">identifier=\<mrn></span></span>

<span data-ttu-id="58c37-162">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="58c37-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="58c37-163">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="58c37-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="58c37-164">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="58c37-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="58c37-165">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="58c37-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="58c37-166">Name</span><span class="sxs-lookup"><span data-stu-id="58c37-166">Name</span></span>
- <span data-ttu-id="58c37-167">BirthDate</span><span class="sxs-lookup"><span data-stu-id="58c37-167">Birthdate</span></span>

<span data-ttu-id="58c37-168">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="58c37-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="58c37-169">Request: Post <fhir-Server>/Patient/_search Request Body: given = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="58c37-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="58c37-170">Response: {"Ressourcenname": "Bundle", "ID": "<Bundle-ID>";</span><span class="sxs-lookup"><span data-stu-id="58c37-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="58c37-171">.</span><span class="sxs-lookup"><span data-stu-id="58c37-171">.</span></span>
      <span data-ttu-id="58c37-172">.</span><span class="sxs-lookup"><span data-stu-id="58c37-172">.</span></span>
      <span data-ttu-id="58c37-173">"Eintrag": [{"Ressource": {"Ressourcen": "Patient"; "ID": "<Patient-ID>"; "Name": [{"Text": "Hugh Chau", "Familie": ["Chau"], "given": ["Hugh"]}], "Gender": "männlich"; "Geburtsdatum": "1957-06-05"}, "suchen": {"der Modus": "Vergleich"}}]</span><span class="sxs-lookup"><span data-stu-id="58c37-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="58c37-174">Weitere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="58c37-175">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="58c37-175">Observation</span></span>

<span data-ttu-id="58c37-176">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut Vital Signs-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="58c37-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="58c37-177">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="58c37-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="58c37-178">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="58c37-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="58c37-179">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="58c37-179">ValueQuantity.Value</span></span>

<span data-ttu-id="58c37-180">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="58c37-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="58c37-181">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="58c37-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="58c37-182">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="58c37-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="58c37-183">Wenn Sie Komponenten Beobachtungen verwenden, gilt dieselbe Logik für jede Komponentenüberwachung.</span><span class="sxs-lookup"><span data-stu-id="58c37-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="58c37-184">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="58c37-185">Patient =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="58c37-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="58c37-186">Sort: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="58c37-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="58c37-187">Das Ziel besteht darin, die neuesten vitalen Zeichen für einen Patienten abzurufen [VitalSigns. ДСТУ. SAZ] (Observation?).</span><span class="sxs-lookup"><span data-stu-id="58c37-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="58c37-188">Request: besorgen Sie sich <fhir-Server>/Observation? Patient =<Patient-ID>&_sort:d ESC = Datum&Kategorie = Vital-Zeichen</span><span class="sxs-lookup"><span data-stu-id="58c37-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="58c37-189">Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Type": "searchset", "Total": 20; "Eintrag": [{"Resource": {"Ressource": "Observation"; "ID": "<Resource-ID>"; "Category": {"Coding": [{Code ":" Vital-Signs "}],}," Code ": {" Coding ": [{" System ":" http://loinc.org ";" Code ":" 39156-5 ";" Display ":" BMI "}],}," effectiveDateTime ":" 2009-12-01 ";" valueQuantity ": {" Wert ": 34,4;" Einheit ":" kg/m2 ";" System ":" http://unitsofmeasure.org "," Code ":" kg/m2 "}},},.</span><span class="sxs-lookup"><span data-stu-id="58c37-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="58c37-190">.</span><span class="sxs-lookup"><span data-stu-id="58c37-190">.</span></span>
        <span data-ttu-id="58c37-191">.</span><span class="sxs-lookup"><span data-stu-id="58c37-191">.</span></span>
      <span data-ttu-id="58c37-192">] }</span><span class="sxs-lookup"><span data-stu-id="58c37-192">] }</span></span>

* * *

<span data-ttu-id="58c37-193">Weitere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="58c37-194">Bedingung</span><span class="sxs-lookup"><span data-stu-id="58c37-194">Condition</span></span>

<span data-ttu-id="58c37-195">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind:</span><span class="sxs-lookup"><span data-stu-id="58c37-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="58c37-196">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="58c37-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="58c37-197">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="58c37-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="58c37-198">Aufnahmedatum</span><span class="sxs-lookup"><span data-stu-id="58c37-198">Date Recorded</span></span>
2. <span data-ttu-id="58c37-199">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="58c37-199">Severity</span></span>

<span data-ttu-id="58c37-200">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="58c37-201">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="58c37-201">patient=\<patient id></span></span>
2. <span data-ttu-id="58c37-202">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="58c37-202">_count=\<max results></span></span>

<span data-ttu-id="58c37-203">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="58c37-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="58c37-204">Request: besorgen Sie sich <fhir-Server>/Condition? Patient =<Patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="58c37-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="58c37-205">Response: {"Ressource": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "Bedingung"; "ID": "<Resource-ID>"; "Code": {"Coding": [{"System": " http://snomed.info/sct "; "Code": "386033004", "Display": "Neuropathie (Nerve Damage)"}]}, "dateRecorded": "2018-09-17"; "Severity": {"Coding": [{"System": " http://snomed.info/sct "; "Code": "24484000"; "Anzeige": "schwere"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="58c37-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="58c37-206">Weitere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="58c37-207">Auftreten</span><span class="sxs-lookup"><span data-stu-id="58c37-207">Encounter</span></span>

<span data-ttu-id="58c37-208">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge der Felder für das US-Core-Encounter-Profil "muss" handelt:</span><span class="sxs-lookup"><span data-stu-id="58c37-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="58c37-209">Status</span><span class="sxs-lookup"><span data-stu-id="58c37-209">Status</span></span>
2. <span data-ttu-id="58c37-210">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="58c37-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="58c37-211">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils</span><span class="sxs-lookup"><span data-stu-id="58c37-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="58c37-212">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="58c37-212">Period.Start</span></span>
2. <span data-ttu-id="58c37-213">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="58c37-213">Location[0].Location.Display</span></span>

<span data-ttu-id="58c37-214">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="58c37-215">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="58c37-215">patient=\<patient id></span></span>
2. <span data-ttu-id="58c37-216">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="58c37-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="58c37-217">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="58c37-217">_count=\<max results></span></span>

<span data-ttu-id="58c37-218">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="58c37-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="58c37-219">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="58c37-219">Each encounter references a location resource.</span></span> <span data-ttu-id="58c37-220">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="58c37-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="58c37-221">Sehen Sie sich das folgende Beispiel für diesen Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="58c37-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="58c37-222">Request: besorgen Sie sich <fhir-Server>/Encounter? Patient =<Patient-ID>&_sort:d ESC = Datum&_count = 1</span><span class="sxs-lookup"><span data-stu-id="58c37-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="58c37-223">Antwort: {"Ressourcen": "Bundle", "Type": "searchset", "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "Begegnung"; "ID": "<Resource-ID->"; "Bezeichner": [{"Use": "offiziell"; "" "" <id> "" ""; Status ":" angekommen ";" Typ ": [{" Coding ": [{" Display ":" Termin "}],}]," Patient ": {" Bezug ":" Patienten-<-ID> "}," Zeitraum ": {" Start ":" 09/17/2018 1:00:00 pm "}," Ort ": [{" Ort ": {" Anzeige ":" Clinic-HNO "},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="58c37-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="58c37-224">Weitere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="58c37-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="58c37-225">AllergyIntolerance</span></span>

<span data-ttu-id="58c37-226">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-AllergyIntolerance-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="58c37-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="58c37-227">Code. Text</span><span class="sxs-lookup"><span data-stu-id="58c37-227">Code.Text</span></span>
2. <span data-ttu-id="58c37-228">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="58c37-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="58c37-229">Status</span><span class="sxs-lookup"><span data-stu-id="58c37-229">Status</span></span>

<span data-ttu-id="58c37-230">Zusätzlich zu den Argonaut-Feldern liest die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="58c37-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="58c37-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="58c37-231">RecordedDate</span></span>
2. <span data-ttu-id="58c37-232">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="58c37-232">Note.Text</span></span>
3. <span data-ttu-id="58c37-233">Reaktion [..]. Substanz. Text</span><span class="sxs-lookup"><span data-stu-id="58c37-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="58c37-234">Reaktion [..]. Manifestation [..]. Text</span><span class="sxs-lookup"><span data-stu-id="58c37-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="58c37-235">Text. div</span><span class="sxs-lookup"><span data-stu-id="58c37-235">Text.Div</span></span>

<span data-ttu-id="58c37-236">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="58c37-237">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="58c37-237">Patient =  \<patient id></span></span>

<span data-ttu-id="58c37-238">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="58c37-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="58c37-239">Request: besorgen Sie sich <fhir-Server>/AllergyIntolerance? Patient =<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="58c37-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="58c37-240">Response: {"Ressource": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "AllergyIntolerance"; "ID": "<Resource-ID>"; "recordedDate": "2018-09-17T07:00:00.000 z", "Substanz": {"Text": "Cashew-Nüsse"}, "Status": "bestätigt"; "Reaktion": [{"Substanz": {"Text": "Cashew-Nuss-Allergen Extrakt injizierbares Produkt"}, "Manifestation": [{"Text": "anaphylaktischer-Reaktion"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="58c37-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="58c37-241">Weitere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="58c37-242">Medikations Bestellung</span><span class="sxs-lookup"><span data-stu-id="58c37-242">Medication Order</span></span>

<span data-ttu-id="58c37-243">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des Argonaut-MedicationOrder-Profils sind:</span><span class="sxs-lookup"><span data-stu-id="58c37-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="58c37-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="58c37-244">DateWritten</span></span>
2. <span data-ttu-id="58c37-245">Verschreiber. Display</span><span class="sxs-lookup"><span data-stu-id="58c37-245">Prescriber.Display</span></span>
3. <span data-ttu-id="58c37-246">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="58c37-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="58c37-247">Medikation. Text (wenn Konzept)</span><span class="sxs-lookup"><span data-stu-id="58c37-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="58c37-248">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="58c37-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="58c37-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="58c37-249">DateEnded</span></span>
2. <span data-ttu-id="58c37-250">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="58c37-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="58c37-251">Text. div</span><span class="sxs-lookup"><span data-stu-id="58c37-251">Text.Div</span></span>

<span data-ttu-id="58c37-252">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="58c37-253">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="58c37-253">patient=\<patient id></span></span>
2. <span data-ttu-id="58c37-254">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="58c37-254">_count=\<max results></span></span>

<span data-ttu-id="58c37-255">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="58c37-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="58c37-256">Request: besorgen Sie sich <fhir-Server>/MedicationOrder? Patient =<Patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="58c37-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="58c37-257">Response: {"Ressource": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressourcen": "MedicationOrder"; "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"Text": "Lisinopril 20 mg Oral Tablet"}, "Verschreiber": {"Anzeige": "Jane Doe"}, "dosageInstruction": [{"Text": "1 Daily"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="58c37-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="58c37-258">Weitere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="58c37-259">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="58c37-259">Coverage</span></span>

<span data-ttu-id="58c37-260">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="58c37-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="58c37-261">Zahlenden</span><span class="sxs-lookup"><span data-stu-id="58c37-261">Payor</span></span>

<span data-ttu-id="58c37-262">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="58c37-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="58c37-263">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="58c37-263">patient=\<patient id></span></span>

<span data-ttu-id="58c37-264">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="58c37-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="58c37-265">Request: besorgen Sie sich <fhir-Server>/Coverage? Patient =<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="58c37-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="58c37-266">Response: {"Ressourcen": "Bundle"; "Typ": "searchset", "Total": 1; "Eintrag": [{"Resource": {"Ressourcentyp": "Coverage"; "ID": "<Resource-ID>"; "Plan": "keine Erstversicherung"; "Teilnehmer": {"Bezug": "Patient/<Patient-ID>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="58c37-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="58c37-267">Weitere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="58c37-268">Ort</span><span class="sxs-lookup"><span data-stu-id="58c37-268">Location</span></span>

<span data-ttu-id="58c37-269">Diese Ressource wird nur als Referenz für die [Encounter](#encounter) -Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="58c37-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="58c37-270">Weitere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58c37-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
