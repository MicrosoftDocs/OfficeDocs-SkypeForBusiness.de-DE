---
title: 'Lync Server 2013: Löschen eines Kontaktobjekts für eine Telefonanlage für gemeinsame Bereiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98702f392020586b546d2db89fe6355923b47f67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="bfb96-102">Löschen eines Kontaktobjekts für einen öffentlichen Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb96-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfb96-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bfb96-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bfb96-104">Möglicherweise möchten Sie das Kontaktobjekt löschen, das einem Telefon im öffentlichen Bereich zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bfb96-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="bfb96-105">Wenn Sie beispielsweise das Telefon aus einer Mitarbeiter Lounge entfernen, muss diesem Telefon kein Kontaktobjekt zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="bfb96-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="bfb96-106">Das Cmdlet **Remove-CsCommonAreaPhone** bietet Ihnen die Möglichkeit, Telefonkonten für gemeinsame Bereiche zu löschen.</span><span class="sxs-lookup"><span data-stu-id="bfb96-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="bfb96-107">Wenn Sie dieses Cmdlet ausführen, wird das Telefon aus der Liste der Telefone in öffentlichen Bereichen gelöscht, die von **Get-CsCommonAreaPhone**zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bfb96-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="bfb96-108">Darüber hinaus wird das dem Telefon zugeordnete Kontaktobjekt aus Active Directory-Domänendienste gelöscht.</span><span class="sxs-lookup"><span data-stu-id="bfb96-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="bfb96-109">Verwenden **Sie Remove-CsCommonAreaPhone** , um ein Telefon für gemeinsame Bereiche oder alle Telefone für gemeinsame Bereiche mit einem gemeinsamen Element wie Anzeigename oder Land-und Ortsvorwahl zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bfb96-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="bfb96-110">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="bfb96-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bfb96-111">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="bfb96-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="bfb96-112">Entfernen eines angegebenen Telefons für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="bfb96-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="bfb96-113">Mit dem folgenden Befehl wird das Telefon für öffentliche Bereiche mit der SIP-Adresse SIP:mainlobby@litwareinc.com entfernt:</span><span class="sxs-lookup"><span data-stu-id="bfb96-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="bfb96-114">Entfernen von Telefonen in öffentlichen Bereichen basierend auf Ihrem Anzeigenamen</span><span class="sxs-lookup"><span data-stu-id="bfb96-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="bfb96-115">Mit diesem Befehl werden alle Telefone im öffentlichen Bereich entfernt, wobei der Anzeigename den Zeichenfolgenwert "Building 14" enthält:</span><span class="sxs-lookup"><span data-stu-id="bfb96-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="bfb96-116">Entfernen von Telefonen in öffentlichen Bereichen basierend auf ihren Landes-und Ortsvorwahl</span><span class="sxs-lookup"><span data-stu-id="bfb96-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="bfb96-117">Mit diesem Befehl werden alle Telefone für gemeinsame Bereiche für die Vereinigten Staaten (Ländercode 1) und die Vorwahl 425 entfernt:</span><span class="sxs-lookup"><span data-stu-id="bfb96-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="bfb96-118">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="bfb96-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfb96-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfb96-119">See Also</span></span>


[<span data-ttu-id="bfb96-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="bfb96-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

