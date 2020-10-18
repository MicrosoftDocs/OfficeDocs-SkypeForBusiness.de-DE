---
title: 'Lync Server 2013: Erstellen oder Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen'
description: 'Lync Server 2013: Erstellen oder Ändern eines Kontaktobjekts für einen Telefonapparat für gemeinsame Bereiche.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5ede23f495a63b2d556b556817d4171a08723
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578231"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="ea20d-103">Erstellen oder Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea20d-103">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea20d-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ea20d-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ea20d-105">Verwenden Sie das **New-CsCommonAreaPhone-** Cmdlet, um Active Directory-Domänendienste Kontaktobjekte für alle Telefone im öffentlichen Bereich zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea20d-105">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ea20d-106">Mit diesem Cmdlet können Sie entweder neue Kontaktobjekte für Telefone in öffentlichen Bereichen erstellen oder vorhandene Kontaktobjekte einem neuen Telefon im öffentlichen Bereich zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ea20d-106">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="ea20d-107">Verwenden Sie das Cmdlet "CsCommonAreaPhone", um die Eigenschaften der Contact **-** Objekte zu ändern, die mit Telefonen in öffentlichen Bereichen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ea20d-107">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ea20d-108">Mit den optionalen Parametern für " **CsCommonAreaPhone** " können Sie Elemente ändern, beispielsweise den Anzeigenamen des Active Directory Kontakts oder den dem Telefon zugeordneten-URI (Uniform Resource Identifier) und das Konto für die Verwendung mit lync Server aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ea20d-108">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="ea20d-109">Ausführliche Informationen zu allen verfügbaren Änderungen finden Sie im Abschnitt Parameters unter [Festlegen von CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="ea20d-109">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="ea20d-110">Ausführliche Informationen zu **New-CsCommonAreaPhone** -Parametern finden Sie unter [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="ea20d-110">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="ea20d-111">Sie können diese beiden Cmdlets sowohl in der lync Server 2013-Verwaltungsshell als auch in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea20d-111">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ea20d-112">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ea20d-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="ea20d-113">Erstellen eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="ea20d-113">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="ea20d-114">Verwenden Sie das **New-CsCommonAreaPhone-** Cmdlet, um ein neues Kontaktobjekt für eine öffentliche Telefonanlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea20d-114">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ea20d-115">Sie müssen mindestens die folgenden Informationen angeben, wenn Sie ein Contact-Objekt erstellen:</span><span class="sxs-lookup"><span data-stu-id="ea20d-115">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="ea20d-116">**LineUri**: die Telefonnummer, die dem Telefon im öffentlichen Bereich zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ea20d-116">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="ea20d-117">Beachten Sie, dass Sie beim Angeben der Telefonnummer das E. 164-Format verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="ea20d-117">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="ea20d-118">**RegistrarPool**: der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Registrierungsstellen Pools, der als Host für das Contact-Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea20d-118">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="ea20d-119">**OU**: DN (Distinguished Name) des Active Directory Containers, in dem das Contact-Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ea20d-119">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="ea20d-120">Außerdem wird empfohlen, einen Active Directory-Domänendienste Anzeigenamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea20d-120">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="ea20d-121">Andernfalls müssen Sie eine GUID verwenden, um die Telefon Identität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea20d-121">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="ea20d-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea20d-122">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="ea20d-123">Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="ea20d-123">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="ea20d-124">Um die Eigenschaften eines vorhandenen Telefons für gemeinsame Bereiche zu ändern, verwenden Sie das Cmdlet " **Sets-CsCommonAreaPhone** ".</span><span class="sxs-lookup"><span data-stu-id="ea20d-124">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ea20d-125">Mit dem folgenden Befehl wird beispielsweise die SIP-Adresse für das Telefon für öffentliche Bereiche mit der DisplayName-Lobby konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="ea20d-125">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="ea20d-126">Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsCommonAreaPhone-](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet und das Cmdlet "Set [-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) ".</span><span class="sxs-lookup"><span data-stu-id="ea20d-126">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

