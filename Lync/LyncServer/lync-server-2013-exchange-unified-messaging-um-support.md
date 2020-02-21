---
title: 'Lync Server 2013: Exchange Unified Messaging (um)-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c65581d76d1622da6b64e0ccaa4e028e276d5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="1e175-102">Exchange Unified Messaging (um)-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e175-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e175-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1e175-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1e175-104">Lync Server 2013 unterstützt die Integration in Exchange Unified Messaging (um) für die Kombination von Sprachnachrichten und e-Mail-Messaging in einer einzelnen Messaging Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="1e175-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="1e175-105">In Exchange 2013 besteht Exchange um aus dem Exchange um Dienst, der auf dem Postfachserver installiert und ausgeführt wird, und dem um-Anruf Router, der installiert ist und auf dem Client Zugriffsserver ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e175-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="1e175-106">Für lync Server 2013 Enterprise-VoIP-Bereitstellungen kombiniert Exchange um Sprachnachrichten und e-Mail-Nachrichten in einem einzelnen Speicher, auf den von einem Telefon (Outlook Voice Access) oder einem Computer aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e175-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="1e175-107">Exchange um und lync Server 2013 arbeiten zusammen, um Mailboxansage, Outlook Voice Access und automatische Telefonzentralen für Benutzer von Enterprise-VoIP bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1e175-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="1e175-108">Zusätzlich zur Unterstützung der Integration in lokale Bereitstellungen von Exchange um unterstützt lync Server 2013 die Integration in gehostete Exchange um.</span><span class="sxs-lookup"><span data-stu-id="1e175-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="1e175-109">Dies ermöglicht Ihnen die Bereitstellung von Voicemessaging für Ihre Benutzer, wenn Sie einige oder alle Benutzer zu einem gehosteten Exchange-Dienstanbieter wie beispielsweise Microsoft Exchange Online migrieren.</span><span class="sxs-lookup"><span data-stu-id="1e175-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="1e175-110">Lync Server 2013 unterstützt die folgenden Versionen:</span><span class="sxs-lookup"><span data-stu-id="1e175-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="1e175-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="1e175-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="1e175-112">Microsoft Exchange Server 2010 (erforderlich) oder mit dem neuesten Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="1e175-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="1e175-113">Microsoft Exchange Server 2007 mit Service Pack 1 (SP1) (erforderlich) oder mit dem neuesten Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="1e175-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="1e175-114">Sie können Exchange um nicht mit lync Server 2013 oder einer lync Server 2013 Datenbank collocate.</span><span class="sxs-lookup"><span data-stu-id="1e175-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="1e175-115">Sie können Exchange um und lync Server 2013 in getrennten Gesamtstrukturen installieren.</span><span class="sxs-lookup"><span data-stu-id="1e175-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e175-116">Für Enterprise-VoIP-Bereitstellungen, für die eine Nebenstellenanlage bereitgestellt wurde, ist Exchange um möglicherweise nicht erforderlich, da die Nebenstellenanlage weiterhin Voicemail und verwandte Dienste für alle Benutzer bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1e175-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="1e175-117">Wenn Sie die Nebenstellenanlage schließlich zurückziehen (beispielsweise, wenn Sie SIP-Trunking für PSTN-Konnektivität (Public Switched Telephone Network) bereitstellen), müssen Sie Exchange um neu konfigurieren, um Benutzern, die zuvor das Voicemailsystem der Nebenstellenanlage verwendet haben, Voicemail bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1e175-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e175-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1e175-118">In This Section</span></span>

  - [<span data-ttu-id="1e175-119">Komponenten und Topologien für lokale Unified Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e175-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="1e175-120">Unterstützung für gehostete Exchange um Integration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e175-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

