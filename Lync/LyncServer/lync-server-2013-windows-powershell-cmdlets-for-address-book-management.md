---
title: 'Lync Server 2013: Windows PowerShell-Cmdlets für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737496bbb6db1e003ec09a05980c3ef474c69924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="22efa-102">Windows PowerShell-Cmdlets für Adressbuchdienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22efa-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="22efa-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="22efa-104">Lync Server stellt eine Reihe von Windows PowerShell-Cmdlets für die Befehlszeilenschnittstelle bereit, um den Adressbuchdienst zu verwalten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="22efa-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="22efa-105">Bei einigen dieser Cmdlets handelt es sich um Ersetzungen für die Befehle "ABServer. exe", die in früheren Versionen von Office Communications Server verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="22efa-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="22efa-106">In den folgenden Themen finden Sie die Cmdlets, die zum Einrichten, erstellen und Abrufen von Informationen über den Adressbuchdienst, seine Konfiguration und Informationen zu den Webdiensten verwendet werden, die vom Adressbuchdienst verwendet werden, wenn Clients den Adressbuchdienst abrufen. Dateien und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="22efa-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="22efa-107">Alle diese Cmdlets werden über die lync Server-Verwaltungsshell ausgestellt, die sich in den lync Server-Tools auf einem Server oder auf einer Workstation befindet, auf der die Verwaltungstools installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="22efa-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="22efa-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="22efa-108">In This Section</span></span>

  - [<span data-ttu-id="22efa-109">New-CsAddressBookConfiguration für Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-110">Einrichten von CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-111">Get-CsAddressBookConfiguration für die Verwaltung von Adressbüchern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-112">Remove-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-113">Test-CsAddressBookService für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="22efa-114">Test-CsAddressBookWebQuery für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="22efa-115">Update-CsAddressBook für die Verwaltung von Adressbüchern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="22efa-116">New-CsClientPolicy für Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="22efa-117">Einrichten von CsClientPolicy für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="22efa-118">Get-CsService für die Verwaltung von Adressbüchern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="22efa-119">New-CsWebServiceConfiguration für Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-120">Get-CsWebServiceConfiguration für die Verwaltung von Adressbüchern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-121">Einrichten von CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="22efa-122">Remove-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22efa-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="22efa-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="22efa-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22efa-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22efa-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

