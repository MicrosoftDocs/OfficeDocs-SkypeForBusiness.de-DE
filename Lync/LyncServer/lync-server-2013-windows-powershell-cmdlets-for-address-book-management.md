---
title: 'Lync Server 2013: Windows PowerShell-Cmdlets für die Adressbuchverwaltung'
description: 'Lync Server 2013: Windows PowerShell-Cmdlets für die Adressbuchverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b598d91a4d1a29a67d8f8ceb2477f2d9b96f1319
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546021"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="f83ed-103">Windows PowerShell-Cmdlets für Adressbuchdienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-103">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f83ed-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f83ed-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f83ed-105">Lync Server enthält eine Reihe von Windows PowerShell Cmdlets für Befehlszeilenschnittstelle, um den Adressbuchdienst zu verwalten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f83ed-105">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="f83ed-106">Einige dieser Cmdlets sind Ersatz für die ABServer.exe Befehle, die in früheren Versionen von Office Communications Server verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f83ed-106">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="f83ed-107">In den folgenden Themen finden Sie die Cmdlets zum Festlegen, Erstellen und Abrufen von Informationen über den Adressbuchdienst und seine Konfiguration sowie von Informationen über den Webdienst, den der Adressbuchdienst verwendet, wenn Clients Dateien und Einstellungen des Adressbuchdiensts abrufen.</span><span class="sxs-lookup"><span data-stu-id="f83ed-107">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="f83ed-108">Alle diese Cmdlets werden über die lync Server-Verwaltungsshell herausgegeben, die im lync Server Tools auf einem Server oder einer Arbeitsstation gefunden wurden, auf dem die Verwaltungstools installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f83ed-108">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f83ed-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f83ed-109">In This Section</span></span>

  - [<span data-ttu-id="f83ed-110">New-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-110">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-111">Festlegen von CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-111">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-112">Get-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-112">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-113">Remove-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-113">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-114">Test-CsAddressBookService für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-114">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-115">Test-CsAddressBookWebQuery für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-115">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-116">Update-CsAddressBook für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-116">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-117">New-CsClientPolicy für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-117">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-118">Festlegen von CsClientPolicy für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-118">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-119">Get-CsService für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-119">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-120">New-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-120">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-121">Get-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-121">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-122">Festlegen von CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-122">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="f83ed-123">Remove-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83ed-123">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f83ed-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f83ed-124">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f83ed-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f83ed-125">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

