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
ms.openlocfilehash: bcae5b6fae3da469aaaa35b3a0494273fa8d29ba
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277215"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="4ef10-103">Benutzeroberflächenspezifikation STU3</span><span class="sxs-lookup"><span data-stu-id="4ef10-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ef10-104">**30. September, 2020, wird die APP für Patienten als veraltet markiert, und die Benutzer können Sie nicht mehr aus dem App Store von Teams installieren. Wir empfehlen Ihnen, die Listen- [App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams noch heute zu verwenden.**</span><span class="sxs-lookup"><span data-stu-id="4ef10-104">**Effective September 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="4ef10-105">Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4ef10-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4ef10-106">Wenn die patients-App eingestellt wird, werden alle damit verknüpften Daten in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4ef10-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4ef10-107">Aktuelle Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ef10-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4ef10-108">Die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) ist für alle Teams-Benutzer vorinstalliert und steht in allen Teams und Kanälen als Registerkarte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4ef10-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="4ef10-109">Mit Listen können Betreuerteams mithilfe der integrierten Patienten Vorlage, von Grund auf neu oder durch Importieren von Daten nach Excel, patientenlisten erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ef10-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="4ef10-110">Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="4ef10-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4ef10-111">Zum Einrichten oder Neukonfigurieren eines FHIR-Servers für die Arbeit mit der Microsoft Teams-Patienten-App müssen Sie verstehen, auf welche Daten die App zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="4ef10-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4ef10-112">Der FHIR-Server muss Post Anforderungen mithilfe von bündeln für die folgenden Ressourcen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4ef10-113">Patienten</span><span class="sxs-lookup"><span data-stu-id="4ef10-113">Patient</span></span>](#patient)
- [<span data-ttu-id="4ef10-114">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="4ef10-114">Observation</span></span>](#observation)
- [<span data-ttu-id="4ef10-115">Bedingung</span><span class="sxs-lookup"><span data-stu-id="4ef10-115">Condition</span></span>](#condition)
- [<span data-ttu-id="4ef10-116">Auftreten</span><span class="sxs-lookup"><span data-stu-id="4ef10-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4ef10-117">Allergie-Intoleranz</span><span class="sxs-lookup"><span data-stu-id="4ef10-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4ef10-118">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="4ef10-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="4ef10-119">[Medikations Anweisung](#medication-request) (ersetzt die MedicationOrder in der DSTU2-Version des PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="4ef10-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="4ef10-120">Ort (die Informationen, die aus dieser Ressource benötigt werden, können in der Begegnung enthalten sein)</span><span class="sxs-lookup"><span data-stu-id="4ef10-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="4ef10-121">Die Patienten Ressource ist die einzige obligatorische Ressource (ohne die die APP überhaupt nicht geladen wird). Es wird jedoch empfohlen, dass der Partner die Unterstützung für alle oben aufgeführten Ressourcen pro Spezifikationen implementiert, die nachfolgend aufgeführt sind, um die optimale Benutzererfahrung mit der Microsoft Teams-Patienten-APP zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4ef10-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4ef10-122">Abfragen der Microsoft Teams-Patienten-App für mehr als eine Ressource müssen ein Bündel (Batch) von Anforderungen an die URL des FHIR-Servers senden.</span><span class="sxs-lookup"><span data-stu-id="4ef10-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4ef10-123">Der Server verarbeitet jede Anforderung und gibt ein Bündel der Ressourcen zurück, die den jeweiligen Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4ef10-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4ef10-124">Weitere Informationen und Beispiele finden Sie unter [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="4ef10-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="4ef10-125">Capability-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4ef10-125">Capability Statement</span></span>

<span data-ttu-id="4ef10-126">Hierbei handelt es sich um die erforderlichen Mindestanforderungen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="4ef10-127">Rest</span><span class="sxs-lookup"><span data-stu-id="4ef10-127">REST</span></span>
   1. <span data-ttu-id="4ef10-128">Modus</span><span class="sxs-lookup"><span data-stu-id="4ef10-128">Mode</span></span>
   2. <span data-ttu-id="4ef10-129">Interaktion</span><span class="sxs-lookup"><span data-stu-id="4ef10-129">Interaction</span></span>
   3. <span data-ttu-id="4ef10-130">Ressource: Typ</span><span class="sxs-lookup"><span data-stu-id="4ef10-130">Resource: Type</span></span>
   4. <span data-ttu-id="4ef10-131">Sicherheit: [Erweiterung für OAuth-URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4ef10-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="4ef10-132">FhirVersion (für unseren Code ist dies erforderlich, um zu verstehen, auf welche Version wir pivotieren sollten.)</span><span class="sxs-lookup"><span data-stu-id="4ef10-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="4ef10-133">Weitere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4ef10-134">Patienten</span><span class="sxs-lookup"><span data-stu-id="4ef10-134">Patient</span></span>

<span data-ttu-id="4ef10-135">Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge der Argonaut-Patientenprofil Felder sind:</span><span class="sxs-lookup"><span data-stu-id="4ef10-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="4ef10-136">Name. given</span><span class="sxs-lookup"><span data-stu-id="4ef10-136">Name.Given</span></span>
2. <span data-ttu-id="4ef10-137">Name. Familie</span><span class="sxs-lookup"><span data-stu-id="4ef10-137">Name.Family</span></span>
3. <span data-ttu-id="4ef10-138">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="4ef10-138">Gender</span></span>
4. <span data-ttu-id="4ef10-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="4ef10-139">BirthDate</span></span>
5. <span data-ttu-id="4ef10-140">MRN (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="4ef10-140">MRN (Identifier)</span></span>

<span data-ttu-id="4ef10-141">Zusätzlich zu den [Argonaut-Feldern](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4ef10-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="4ef10-142">Name.Use</span></span>
2. <span data-ttu-id="4ef10-143">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="4ef10-143">Name.Prefix</span></span>
3. <span data-ttu-id="4ef10-144">[GeneralPractitioner] – der GeneralPractitioner-Verweis sollte in die Patienten Ressource aufgenommen werden (nur Anzeigefeld)</span><span class="sxs-lookup"><span data-stu-id="4ef10-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="4ef10-145">Bei einer Ressourcensuche wird die Post-Methode unter/Patient/_search und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-146">ID</span><span class="sxs-lookup"><span data-stu-id="4ef10-146">id</span></span>
2. <span data-ttu-id="4ef10-147">Familie = (sucht nach allen Patienten, deren Familienname den Wert enthält)</span><span class="sxs-lookup"><span data-stu-id="4ef10-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="4ef10-148">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="4ef10-148">given=\<substring></span></span>
4. <span data-ttu-id="4ef10-149">Geburtsdatum = (exakte Übereinstimmung)</span><span class="sxs-lookup"><span data-stu-id="4ef10-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="4ef10-150">Gender = (Werte, die einer der administrativen-Gender-Werte sind)</span><span class="sxs-lookup"><span data-stu-id="4ef10-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="4ef10-151">\_Anzahl (maximale Anzahl der Ergebnisse, die zurückgegeben werden sollen)</span><span class="sxs-lookup"><span data-stu-id="4ef10-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4ef10-152">Die Antwort sollte die Gesamtanzahl der Datensätze enthalten, die als Ergebnis der Suche zurückgegeben wurden, und die Anzahl \_ wird vom PatientsApp verwendet, um die Anzahl der zurückgegebenen Datensätze zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="4ef10-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="4ef10-153">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="4ef10-153">identifier=\<mrn></span></span>

<span data-ttu-id="4ef10-154">Das Ziel besteht darin, nach einem Patienten durchsuchen und Filtern zu können:</span><span class="sxs-lookup"><span data-stu-id="4ef10-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4ef10-155">ID: Dies ist die Ressourcen-ID, die jede Ressource in FHIR hat.</span><span class="sxs-lookup"><span data-stu-id="4ef10-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4ef10-156">MRN: Dies ist der tatsächliche Bezeichner für den Patienten, den das klinische Personal kennen würde.</span><span class="sxs-lookup"><span data-stu-id="4ef10-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4ef10-157">Wir verstehen, dass diese MRN auf dem Typ des Bezeichners in der Bezeichner Ressource in FHIR basiert.</span><span class="sxs-lookup"><span data-stu-id="4ef10-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="4ef10-158">Name</span><span class="sxs-lookup"><span data-stu-id="4ef10-158">Name</span></span>
- <span data-ttu-id="4ef10-159">BirthDate</span><span class="sxs-lookup"><span data-stu-id="4ef10-159">Birthdate</span></span>

<span data-ttu-id="4ef10-160">Sehen Sie sich das folgende Beispiel des Anrufs an:</span><span class="sxs-lookup"><span data-stu-id="4ef10-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="4ef10-161">Request: Post <fhir-Server>/Patient/_search Request Body: given = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="4ef10-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="4ef10-162">Response: {"Ressourcenname": "Bundle"; "ID": "<Bundle-ID>"; "Meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "Typ": "searchset"; "Total": 1; "Link": [{"Relation": "selbst"; "URL": <fhir-Server>/Patient/_search "}]," Eintrag ": [{" fullUrl ": <fhir-Server>/Patient/<Patient-ID>"; "Ressource": {"Ressourcentyp": "Patient"; "ID": "<Patient-ID>"; "Meta": {"Version-Nr": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "Text": {"Status": "generated", "div": "</span><span class="sxs-lookup"><span data-stu-id="4ef10-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="4ef10-163">\n</span><span class="sxs-lookup"><span data-stu-id="4ef10-163">\n</span></span>        <p><span data-ttu-id="4ef10-164">Ruth schwarz</span><span class="sxs-lookup"><span data-stu-id="4ef10-164">Ruth Black</span></span></p><span data-ttu-id="4ef10-165">\n</span><span class="sxs-lookup"><span data-stu-id="4ef10-165">\n</span></span>      </div><span data-ttu-id="4ef10-166">"}," Bezeichner ": [{" Use ":" üblich ";" Typ ": {" Coding ": [{" System ":" https://hl7.org/fhir/v2/0203 ";" Code ":" Herr ";" Anzeige ":" medizinische Datensatznummer ";" userSelected ": false}]," Text ":" medizinische Datensatznummer "}," System ":" http://hospital.smarthealthit.org ";" Wert ":" 1234567 "}]," aktiv ": wahr," Name ": [{" Use ":" offiziell "," Familie ":" schwarz ";" angegeben ": [" Ruth ";" C. "</span><span class="sxs-lookup"><span data-stu-id="4ef10-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="4ef10-167">]}], "Telecom": [{"System": "Telefon"; "Wert": "800-599-2739"; "Use": "Home"}, {"System": "Telefon"; "Wert": "800-808-7785"; "verwenden": "Mobil"}, {"System": "e-Mail"; "Wert": "Ruth.Black@example.com"}], "Geschlecht": "weiblich", "Geburtsdatum": "1951-08-23", "Adresse": [{"Use": "Start", "Zeile": ["26 South RdApt 22"], "Ort": "Sapulpa", "Zustand": "OK"; "PLZ": "74066"; "Land": "USA"}]}, "suchen": {"Modus": "Übereinstimmung"}}]}</span><span class="sxs-lookup"><span data-stu-id="4ef10-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="4ef10-168">Request: besorgen Sie sich <fhir-Server>/Patient/<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4ef10-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="4ef10-169">Response: {"Ressourcentyp": "Patient"; "ID": "<Patient-ID>"; "Bezeichner": [{"Use": "üblich"; "Typ": {"Coding": [{"System": " https://hl7.org/fhir/v2/0203 "; "Code": "Herr",}], "Text": "medizinische Datensatznummer"}, "Wert": "1234567"}], "Name": [{"Use": "offiziell", "Familie": "Adams"; "given": ["Daniel"; "X."</span><span class="sxs-lookup"><span data-stu-id="4ef10-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="4ef10-170">]}], "Gender": "männlich"; "Geburtsdatum": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="4ef10-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="4ef10-171">Weitere [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4ef10-172">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="4ef10-172">Observation</span></span>

<span data-ttu-id="4ef10-173">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut Vital-Signs-Profils](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)sind.</span><span class="sxs-lookup"><span data-stu-id="4ef10-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="4ef10-174">Effektiv (Datum oder Zeitraum)</span><span class="sxs-lookup"><span data-stu-id="4ef10-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="4ef10-175">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="4ef10-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="4ef10-176">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="4ef10-176">ValueQuantity.Value</span></span>

<span data-ttu-id="4ef10-177">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4ef10-178">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="4ef10-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="4ef10-179">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="4ef10-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="4ef10-180">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-181">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4ef10-181">patient=\<patient id></span></span>
2. <span data-ttu-id="4ef10-182">_sort =-Datum</span><span class="sxs-lookup"><span data-stu-id="4ef10-182">_sort=-date</span></span>
3. <span data-ttu-id="4ef10-183">Kategorie (wir werden nach "Category = Vital-Signs" suchen), um die Liste der Vitalzeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4ef10-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="4ef10-184">Beziehen Sie sich auf dieses Beispiel des Anrufs:</span><span class="sxs-lookup"><span data-stu-id="4ef10-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="4ef10-185">Request: besorgen Sie sich <fhir-Server>/Observation? Patient =<Patient-ID>&Kategorie = Vital-Zeichen</span><span class="sxs-lookup"><span data-stu-id="4ef10-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="4ef10-186">Response: {"Ressourcen": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset", "Total": 20; "Eintrag": [{"Resource": {"Ressource": "Observation"; "ID": "<Resource-ID>"; "Category": [{"Coding": [{"System": " https://hl7.org/fhir/observation-category "; "Code": "Vital-Signs"}]; "Code": {"Coding": [{"System": " http://loinc.org "; "Code": "8867-4"; "Display": "heart_rate"}]}, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": {"Wert": 72,0, "Unit": "{Beats}/min.", "System": " http://unitsofmeasure.org ",}}},.</span><span class="sxs-lookup"><span data-stu-id="4ef10-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="4ef10-187">.</span><span class="sxs-lookup"><span data-stu-id="4ef10-187">.</span></span>
        <span data-ttu-id="4ef10-188">.</span><span class="sxs-lookup"><span data-stu-id="4ef10-188">.</span></span>
      <span data-ttu-id="4ef10-189">] }</span><span class="sxs-lookup"><span data-stu-id="4ef10-189">] }</span></span>

* * *

<span data-ttu-id="4ef10-190">Weitere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4ef10-191">Bedingung</span><span class="sxs-lookup"><span data-stu-id="4ef10-191">Condition</span></span>

<span data-ttu-id="4ef10-192">Hier sind die erforderlichen Mindestanforderungen, die eine Teilmenge des Argonaut- [Bedingungs Profils](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)sind.</span><span class="sxs-lookup"><span data-stu-id="4ef10-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="4ef10-193">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="4ef10-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="4ef10-194">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4ef10-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4ef10-195">AssertedDate</span></span>
2. <span data-ttu-id="4ef10-196">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="4ef10-196">Severity</span></span>

<span data-ttu-id="4ef10-197">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-198">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4ef10-198">patient=\<patient id></span></span>
2. <span data-ttu-id="4ef10-199">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4ef10-199">_count=\<max results></span></span>

<span data-ttu-id="4ef10-200">Sehen Sie sich das folgende Beispiel für diesen Aufruf an:</span><span class="sxs-lookup"><span data-stu-id="4ef10-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4ef10-201">Request: besorgen Sie sich <fhir-Server>/Condition? Patient =<Patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4ef10-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4ef10-202">Antwort: {"Ressourcen": "Bundle", "ID": "<-Bundle-ID>"; "Typ": "searchset"; "Total": 2; "Eintrag": [{"Resource": {"Ressourcentyp": "Bedingung"; "ID": "<Resource-ID>"; "Code": {"Coding": [{"System": " http://snomed.info/sct "; "Code": "185903001"; "Anzeige": "benötigt eine Influenza-Immunisierung",}]}, "Schweregrad": {"Coding": [{"System": " http://snomed.info/sct ", "Code": "24484000"; "Anzeige": "schwere"}]}, "assertedDate": "2018-04-04"}},.</span><span class="sxs-lookup"><span data-stu-id="4ef10-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="4ef10-203">.</span><span class="sxs-lookup"><span data-stu-id="4ef10-203">.</span></span>
        <span data-ttu-id="4ef10-204">.</span><span class="sxs-lookup"><span data-stu-id="4ef10-204">.</span></span>
      <span data-ttu-id="4ef10-205">] }</span><span class="sxs-lookup"><span data-stu-id="4ef10-205">] }</span></span>

* * *
<span data-ttu-id="4ef10-206">Weitere [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4ef10-207">Auftreten</span><span class="sxs-lookup"><span data-stu-id="4ef10-207">Encounter</span></span>

<span data-ttu-id="4ef10-208">Hierbei handelt es sich um die mindestens erforderlichen Felder, bei denen es sich um eine Teilmenge des [US-Core-Encounter-Profils](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have"-Felder handelt.</span><span class="sxs-lookup"><span data-stu-id="4ef10-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="4ef10-209">Status</span><span class="sxs-lookup"><span data-stu-id="4ef10-209">Status</span></span>
2. <span data-ttu-id="4ef10-210">Geben Sie [0] ein. Codierung [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="4ef10-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4ef10-211">Darüber hinaus sind die folgenden Felder aus den Feldern "muss unterstützen" des US Core Encounter-Profils:</span><span class="sxs-lookup"><span data-stu-id="4ef10-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="4ef10-212">Periode. Start</span><span class="sxs-lookup"><span data-stu-id="4ef10-212">Period.Start</span></span>
2. <span data-ttu-id="4ef10-213">Ort [0]. Location. Display</span><span class="sxs-lookup"><span data-stu-id="4ef10-213">Location[0].Location.Display</span></span>

<span data-ttu-id="4ef10-214">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-215">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4ef10-215">patient=\<patient id></span></span>
2. <span data-ttu-id="4ef10-216">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="4ef10-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="4ef10-217">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4ef10-217">_count=\<max results></span></span>

<span data-ttu-id="4ef10-218">Das Ziel besteht darin, den letzten bekannten Standort des Patienten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="4ef10-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="4ef10-219">Jede Begegnung verweist auf eine Standortressource.</span><span class="sxs-lookup"><span data-stu-id="4ef10-219">Each encounter references a location resource.</span></span> <span data-ttu-id="4ef10-220">Der Bezug umfasst auch das Anzeigefeld des Standorts.</span><span class="sxs-lookup"><span data-stu-id="4ef10-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="4ef10-221">Weitere [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4ef10-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4ef10-222">AllergyIntolerance</span></span>

<span data-ttu-id="4ef10-223">Hierbei handelt es sich um die mindestanforderungs Felder, die eine Teilmenge des [Argonaut-AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) -Profils sind:</span><span class="sxs-lookup"><span data-stu-id="4ef10-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="4ef10-224">Code. Text</span><span class="sxs-lookup"><span data-stu-id="4ef10-224">Code.Text</span></span>
2. <span data-ttu-id="4ef10-225">Code. Coding [0]. Anzeigen</span><span class="sxs-lookup"><span data-stu-id="4ef10-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="4ef10-226">ClinicalStatus/VerificationStatus (wir lesen beide)</span><span class="sxs-lookup"><span data-stu-id="4ef10-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="4ef10-227">Zusätzlich zu den Argonaut-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch das folgende Feld lesen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="4ef10-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4ef10-228">AssertedDate</span></span>
2. <span data-ttu-id="4ef10-229">Hinweis. Text</span><span class="sxs-lookup"><span data-stu-id="4ef10-229">Note.Text</span></span>
3. <span data-ttu-id="4ef10-230">Reaktion</span><span class="sxs-lookup"><span data-stu-id="4ef10-230">Reaction</span></span>
    1. <span data-ttu-id="4ef10-231">Substanz (ein Codierungselement)</span><span class="sxs-lookup"><span data-stu-id="4ef10-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="4ef10-232">Manifestation (ein Codierungselement)</span><span class="sxs-lookup"><span data-stu-id="4ef10-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="4ef10-233">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-234">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="4ef10-234">Patient =  \<patient id></span></span>

<span data-ttu-id="4ef10-235">Sehen Sie sich das folgende Beispiel des Anrufs an:</span><span class="sxs-lookup"><span data-stu-id="4ef10-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="4ef10-236">Request: besorgen Sie sich <fhir-Server>/allergyintolerance? Patient =<Patienten-ID></span><span class="sxs-lookup"><span data-stu-id="4ef10-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="4ef10-237">Response: {"Ressourcentyp": "Bundle"; "ID": "<Bundle-ID>"; "Typ": "searchset"; "Total": 1; "Eintrag": [{"Resource": {"Ressource": "AllergyIntolerance"; "ID": "<Resource-ID>"; "clinicalStatus": "aktiv"; "verificationStatus": "bestätigt"; "Code": {"Coding": [{"System": " http://rxnav.nlm.nih.gov/REST/Ndfrt ", "Code": "N0000175503"; "Display": "Sulfonamid antibakterielle",}], "Text": "Sulfonamid antibakteriell"}, "assertedDate": "2018-01-01T00:00:00-07:00"; "Reaktion": [{"Manifest": [{"Coding": [{"System": " http://snomed.info/sct "; "Code": "271807003"; "Display": "Hautausschlag",}], "Text": "Hautausschlag"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4ef10-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4ef10-238">Weitere [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="4ef10-239">Medikations Anfrage</span><span class="sxs-lookup"><span data-stu-id="4ef10-239">Medication Request</span></span>

<span data-ttu-id="4ef10-240">Hierbei handelt es sich um die Mindestanforderungen, die eine Teilmenge des [US-Core-Medikaments anfordern](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="4ef10-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="4ef10-241">Medikation. Display (wenn Bezug)</span><span class="sxs-lookup"><span data-stu-id="4ef10-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="4ef10-242">Medikation. Text (wenn CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="4ef10-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="4ef10-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="4ef10-243">AuthoredOn</span></span>
4. <span data-ttu-id="4ef10-244">Requestor. Agent. Display</span><span class="sxs-lookup"><span data-stu-id="4ef10-244">Requester.Agent.Display</span></span>

<span data-ttu-id="4ef10-245">Zusätzlich zu den US-Core-Feldern kann die Patienten-App für eine hervorragende Benutzererfahrung auch die folgenden Felder lesen:</span><span class="sxs-lookup"><span data-stu-id="4ef10-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4ef10-246">DosageInstruction[..]. Text</span><span class="sxs-lookup"><span data-stu-id="4ef10-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="4ef10-247">Text</span><span class="sxs-lookup"><span data-stu-id="4ef10-247">Text</span></span>

<span data-ttu-id="4ef10-248">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-249">Patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4ef10-249">patient=\<patient id></span></span>
2. <span data-ttu-id="4ef10-250">_Count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4ef10-250">_count=\<max results></span></span>

<span data-ttu-id="4ef10-251">Weitere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4ef10-252">Abdeckung</span><span class="sxs-lookup"><span data-stu-id="4ef10-252">Coverage</span></span>

<span data-ttu-id="4ef10-253">Hierbei handelt es sich um die mindestens erforderlichen Felder, die nicht in den USA-Core-oder Argonaut-Profilen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="4ef10-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="4ef10-254">Gruppieren, mindestens ein Element mit</span><span class="sxs-lookup"><span data-stu-id="4ef10-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="4ef10-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="4ef10-255">GroupDisplay</span></span>
    2. <span data-ttu-id="4ef10-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="4ef10-256">PlanDisplay</span></span>
2. <span data-ttu-id="4ef10-257">Zeitraum</span><span class="sxs-lookup"><span data-stu-id="4ef10-257">Period</span></span>
3. <span data-ttu-id="4ef10-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="4ef10-258">SubscriberId</span></span>

<span data-ttu-id="4ef10-259">Bei einer Ressourcensuche werden die Get-Methode und die folgenden Parameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ef10-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4ef10-260">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="4ef10-260">Patient = \<patient id></span></span>

<span data-ttu-id="4ef10-261">Weitere [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) Informationen zu diesem Feld Satz finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4ef10-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
