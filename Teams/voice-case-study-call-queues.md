---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786022"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="2215f-103">Contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="2215f-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="2215f-104">Contoso war mit automatischen Telefonzentralen und Anrufwarteschlangen aus der lokalen Skype for Business-Bereitstellung vertraut.</span><span class="sxs-lookup"><span data-stu-id="2215f-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="2215f-105">Wenn Sie wissen möchten, wie die automatischen Cloud-Telefonzentralen eingerichtet [werden](what-are-phone-system-auto-attendants.md) , haben Sie die automatische automatische Telefonzentrale in der Cloud überprüft. Beispiel für ein [kleines Unternehmen – Einrichten einer automatischen Telefon](tutorial-org-aa.yml)zentrale.</span><span class="sxs-lookup"><span data-stu-id="2215f-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="2215f-106">Wenn Sie mehr über die verfügbaren Optionen zum Einrichten von Anrufwarteschlangen erfahren möchten, hat Contoso [eine Cloud-Anrufwarteschlange erstellt](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="2215f-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="2215f-107">Anforderungen je nach Art der Website</span><span class="sxs-lookup"><span data-stu-id="2215f-107">Requirements depending on site type</span></span>

<span data-ttu-id="2215f-108">Je nach Typ der Website hatte Contoso die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="2215f-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="2215f-109">Websitetyp A: herkömmliche Legacy-Telefoniesysteme</span><span class="sxs-lookup"><span data-stu-id="2215f-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="2215f-110">Websitetyp A erforderlich, um die gleiche Telefonnummer, die der Rezeption zugeordnet ist, als Nummer für Ihre automatischen Telefonzentralen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="2215f-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="2215f-111">Die wichtigsten Abteilungen für jede dieser Websites hätten eigene Anrufwarteschlangen, die an Teammitglieder weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2215f-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="2215f-112">Es gab eine Mischung von Websites, die das Telefonsystem mit direktem Routing und Telefonsystem mit Anrufplänen verwendeten.</span><span class="sxs-lookup"><span data-stu-id="2215f-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="2215f-113">Website Typ B: Skype for Business Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="2215f-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="2215f-114">Der Websitetyp B hatte vorhandene automatische Telefonzentralen und Anrufwarteschlangen, die für die Migration zu Teams benötigt wurden.</span><span class="sxs-lookup"><span data-stu-id="2215f-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="2215f-115">Contoso musste die Telefonnummern beibehalten, die den automatischen Telefonzentralen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2215f-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="2215f-116">Contoso hat die Mehrheit dieser Websites mit Anrufplänen in das Telefon System verschoben.</span><span class="sxs-lookup"><span data-stu-id="2215f-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="2215f-117">In den wenigen Speicherorten, an denen keine Anrufpläne verfügbar waren, hat Contoso diese Websites jedoch in eine direkte Routing Konfiguration verschoben.</span><span class="sxs-lookup"><span data-stu-id="2215f-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="2215f-118">Websitetyp C: Skype for Business Enterprise Voice & herkömmliches Legacy-Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="2215f-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="2215f-119">Der Websitetyp C hatte vorhandene automatische Telefonzentralen, die sich im traditionellen Legacy-Telefoniesystem befanden.</span><span class="sxs-lookup"><span data-stu-id="2215f-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="2215f-120">Die Entscheidungen und Konfigurationen für diese Website waren mit dem Websitetyp A identisch.</span><span class="sxs-lookup"><span data-stu-id="2215f-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="2215f-121">Für alle Websitetypen stellte Contoso die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="2215f-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="2215f-122">F: werden neue oder bestehende Nummern verwendet?</span><span class="sxs-lookup"><span data-stu-id="2215f-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="2215f-123">A: contoso hat entschieden, vorhandene Telefonnummern für die Zuweisung zum Dienstkonto für die automatische Telefonzentrale zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2215f-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="2215f-124">F: Wann wird die automatische Telefonzentrale für eingehende Anrufe zur Verfügung stehen?</span><span class="sxs-lookup"><span data-stu-id="2215f-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="2215f-125">A: contoso hat entschieden, Geschäftszeiten festzulegen und Anrufe, die nach Geschäftszeiten empfangen werden, an die automatische Telefonzentrale "After Hours" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="2215f-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="2215f-126">F: wie werden die Anrufe an Mitglieder in einer Anrufwarteschlange weitergeleitet: Attendant, seriell oder Round Robin-Routing?</span><span class="sxs-lookup"><span data-stu-id="2215f-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="2215f-127">A: contoso hat beschlossen, Attendant-Routing zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2215f-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="2215f-128">Frage: wie können wir feststellen, wann ein Nutzer einen Anruf entgegenbringen sollte oder nicht?</span><span class="sxs-lookup"><span data-stu-id="2215f-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="2215f-129">A: contoso hat entschieden, die Anruf Behandlungsoptionen zu verwenden, um festzustellen, ob der Agent verfügbar ist: Anwesenheits basiertes Routing.</span><span class="sxs-lookup"><span data-stu-id="2215f-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="2215f-130">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2215f-130">Configuration</span></span>

<span data-ttu-id="2215f-131">Die Schritte zum Einrichten einer automatischen Telefonzentrale und einer Anrufwarteschlange beinhalten die folgenden Gliederungen unter [Verwalten von Ressourcenkonten](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="2215f-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="2215f-132">Rufen sie eine Dienstnummer ab.</span><span class="sxs-lookup"><span data-stu-id="2215f-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="2215f-133">Besorgen Sie sich ein kostenloses Telefonsystem – eine virtuelle Benutzerlizenz oder eine gebührenpflichtige Telefonsystem Lizenz, die Sie mit dem Ressourcenkonto oder einer Telefonsystem Lizenz verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2215f-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="2215f-134">Erstellen Sie das Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="2215f-134">Create the resource account.</span></span> <span data-ttu-id="2215f-135">Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen.</span><span class="sxs-lookup"><span data-stu-id="2215f-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="2215f-136">Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu.</span><span class="sxs-lookup"><span data-stu-id="2215f-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="2215f-137">Weitere Informationen finden Sie unter [Microsoft 365 Phone System – Virtual User License](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="2215f-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="2215f-138">Weisen Sie dem Ressourcenkonto, dem Sie Lizenzen zugewiesen haben, eine Dienst Telefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="2215f-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="2215f-139">Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="2215f-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="2215f-140">Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="2215f-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="2215f-141">Websites mit Telefon System mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="2215f-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="2215f-142">Contoso musste die Telefonnummer, die vom lokalen Netzbetreiber bereitgestellt wurde, als Dienstnummer in Office 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="2215f-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="2215f-143">Um eine Telefonnummer einzurichten, die über Direct Routing zur Verfügung steht, folgte Contoso den Anweisungen unter [Verwalten von Ressourcenkonten](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="2215f-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="2215f-144">Da Office 365 die lokalen Telefonnummern nicht kennt, hat Contoso PowerShell verwendet, um das Setup abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2215f-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="2215f-145">Zum Konfigurieren der automatischen Cloud-Telefonzentrale befolgte Contoso die in [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)erläuterten Schritte.</span><span class="sxs-lookup"><span data-stu-id="2215f-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="2215f-146">Zum Einrichten einer Cloud-Anrufwarteschlange folgte Contoso den Schritten unter [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="2215f-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="2215f-147">Websites mit Telefon System mit Anrufplan</span><span class="sxs-lookup"><span data-stu-id="2215f-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="2215f-148">Contoso musste die Telefonnummer, die für Skype for Business Enterprise-VoIP-Telefonzentralen verwendet wurde, an das Office 365 Phone-System portieren.</span><span class="sxs-lookup"><span data-stu-id="2215f-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="2215f-149">Dadurch konnte dieselbe Nummer als Dienstnummer für die Verwendung als automatische Telefonzentrale zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2215f-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="2215f-150">Um die Telefonnummer zu portieren, folgte Contoso den Anweisungen unter [übertragen von Telefonnummern in Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) und erhielt zusätzliche Anleitungen unter [Verwalten von Telefonnummern für Ihre Organisation](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="2215f-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="2215f-151">Zum Konfigurieren einer automatischen Cloud-Telefonzentrale befolgte Contoso die in [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)erläuterten Schritte.</span><span class="sxs-lookup"><span data-stu-id="2215f-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="2215f-152">Zum Einrichten einer Cloud-Anrufwarteschlange folgte Contoso den Schritten unter [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="2215f-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 