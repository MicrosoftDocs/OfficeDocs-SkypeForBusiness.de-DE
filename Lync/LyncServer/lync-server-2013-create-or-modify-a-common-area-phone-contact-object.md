---
title: 'Lync Server 2013: Erstellen oder Ändern eines Telefon Kontaktobjekts in einem gemeinsamen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1345477178d7991083332e809de3f764be4c3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="ffd3e-102">Erstellen oder Ändern eines Telefon Kontaktobjekts in einem gemeinsamen Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffd3e-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffd3e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ffd3e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ffd3e-104">Verwenden Sie das Cmdlet **New-CsCommonAreaPhone** , um Kontaktobjekte für Active Directory-Domänendienste für alle Ihre Telefone im allgemeinen Bereich zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ffd3e-105">Dieses Cmdlet kann entweder neue Kontaktobjekte für die Verwendung mit öffentlichen Telefonen erstellen, oder es kann vorhandene Kontaktobjekte mit einem neuen Telefon im öffentlichen Bereich verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="ffd3e-106">Wenn Sie die Eigenschaften der Kontaktobjekte ändern möchten, die für Telefone im allgemeinen Bereich zugeordnet sind, verwenden Sie das Cmdlet " **Satz-CsCommonAreaPhone** ".</span><span class="sxs-lookup"><span data-stu-id="ffd3e-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ffd3e-107">Optionale Parameter für "CsCommonAreaPhone" ermöglichen Ihnen, Elemente wie den Active Directory **-** Anzeigenamen des Kontakts oder den dem Telefon zugeordneten Uniform Resource Identifier (URI) zu ändern und das Konto für die Verwendung mit lync zu aktivieren und zu deaktivieren. Server.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="ffd3e-108">Ausführliche Informationen zu allen verfügbaren Änderungen finden Sie im Abschnitt Parameter unter [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="ffd3e-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="ffd3e-109">Ausführliche Informationen zu Parametern für **neue CsCommonAreaPhone** finden Sie unter [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="ffd3e-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="ffd3e-110">Sie können diese beiden Cmdlets entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ffd3e-111">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="ffd3e-112">Erstellen eines Telefon Kontaktobjekts für einen öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="ffd3e-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="ffd3e-113">Verwenden Sie das Cmdlet **New-CsCommonAreaPhone** , um ein neues Telefon Kontaktobjekt für einen öffentlichen Bereich zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ffd3e-114">Sie müssen mindestens die folgenden Informationen angeben, wenn Sie ein Kontaktobjekt erstellen:</span><span class="sxs-lookup"><span data-stu-id="ffd3e-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="ffd3e-115">**LineUri**: die Telefonnummer, die dem Telefon im öffentlichen Bereich zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="ffd3e-116">Beachten Sie, dass Sie das E. 164-Format verwenden müssen, wenn Sie die Telefonnummer angeben.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="ffd3e-117">**RegistrarPool**: der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des registrierungspools, in dem das Kontaktobjekt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="ffd3e-118">**OU**: Distinguished Name des Active Directory-Containers, in dem das Kontaktobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="ffd3e-119">Wir empfehlen außerdem, einen Anzeigenamen für Active Directory-Domänendienste bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="ffd3e-120">Andernfalls müssen Sie die Telefon Identität mithilfe einer GUID angeben.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="ffd3e-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ffd3e-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="ffd3e-122">Ändern eines Telefon Kontaktobjekts für einen öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="ffd3e-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="ffd3e-123">Wenn Sie die Eigenschaften eines vorhandenen öffentlichen Bereichs Telefons ändern möchten, verwenden Sie das Cmdlet " **Satz-CsCommonAreaPhone** ".</span><span class="sxs-lookup"><span data-stu-id="ffd3e-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ffd3e-124">Mit diesem Befehl wird beispielsweise die SIP-Adresse für das Telefon im öffentlichen Bereich mit der DisplayName-Lobby konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="ffd3e-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="ffd3e-125">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) und dem Cmdlet " [Satz-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) ".</span><span class="sxs-lookup"><span data-stu-id="ffd3e-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

