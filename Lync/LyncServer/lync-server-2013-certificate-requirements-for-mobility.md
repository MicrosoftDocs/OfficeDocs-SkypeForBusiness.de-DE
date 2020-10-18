---
title: 'Lync Server 2013: Zertifikatanforderungen für die Mobilität'
description: 'Lync Server 2013: Zertifikatanforderungen für die Mobilität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575201"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="2fdfc-103">Zertifikatanforderungen für die Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fdfc-103">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fdfc-104">_**Letztes Änderungsstand des Themas:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="2fdfc-104">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="2fdfc-105">Wenn Sie das Mobilitätsfeature bereitstellen und die automatische Ermittlung für mobile Clients unterstützten, müssen Sie für Zertifikate bestimmte Einträge für alternative Antragstellernamen einfügen, um sichere Verbindungen von den mobilen Clients aus zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-105">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="2fdfc-106">Zur Unterstützung der automatischen Ermittlung müssen Sie für folgende Zertifikate Einträge für alternative Antragstellernamen einfügen:</span><span class="sxs-lookup"><span data-stu-id="2fdfc-106">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="2fdfc-107">Directorpool</span><span class="sxs-lookup"><span data-stu-id="2fdfc-107">Director pool</span></span>

  - <span data-ttu-id="2fdfc-108">Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="2fdfc-108">Front End pool</span></span>

  - <span data-ttu-id="2fdfc-109">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="2fdfc-109">Reverse proxy</span></span>

<span data-ttu-id="2fdfc-110">In diesem Abschnitt werden die Einträge für alternative Antragstellernamen beschrieben, die zur Unterstützung der automatischen Ermittlung für Zertifikate erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-110">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fdfc-111">Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist normalerweise ein einfacher Vorgang, aber das Hinzufügen von Einträgen für mehrere alternative Antragstellernamen zu öffentlichen Zertifikaten, die vom Reverseproxy verwendet werden, kann kostspielig sein.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-111">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="2fdfc-112">Wenn Sie über zahlreiche SIP-Domänen verfügen und das Hinzufügen von alternativen Antragstellernamen sehr kostspielig ist, können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Standardkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="2fdfc-112">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="2fdfc-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-113">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="2fdfc-114">Directorpool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="2fdfc-114">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fdfc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fdfc-115">Description</span></span></th>
<th><span data-ttu-id="2fdfc-116">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="2fdfc-116">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fdfc-117">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="2fdfc-117">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2fdfc-118">San = "lyncdiscoverinternal". &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-118">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fdfc-119">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="2fdfc-119">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2fdfc-120">San = lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-120">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2fdfc-121">Alternativ können Sie San = \* verwenden. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-121">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="2fdfc-122">Front-End-Pool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="2fdfc-122">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fdfc-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fdfc-123">Description</span></span></th>
<th><span data-ttu-id="2fdfc-124">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="2fdfc-124">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fdfc-125">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="2fdfc-125">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2fdfc-126">San = "lyncdiscoverinternal". &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-126">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fdfc-127">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="2fdfc-127">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2fdfc-128">San = lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-128">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2fdfc-129">Alternativ können Sie San = \* verwenden. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-129">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="2fdfc-130">Reverseproxy-Zertifikatanforderungen (öffentliche ZS)</span><span class="sxs-lookup"><span data-stu-id="2fdfc-130">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fdfc-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fdfc-131">Description</span></span></th>
<th><span data-ttu-id="2fdfc-132">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="2fdfc-132">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fdfc-133">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="2fdfc-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="2fdfc-134">San = lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2fdfc-134">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2fdfc-135">Sie weisen dieses SAN dem Zertifikat zu, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2fdfc-135">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2fdfc-136">Ihr Reverse Proxy Listener weist alternative Antragstellernamen für Ihre externen Webdienste-URLs auf (beispielsweise "San = lyncwebextpool01. contoso. com" und "dirwebexternal.contoso.com", wenn Sie den optionalen Director bereitgestellt haben).</span><span class="sxs-lookup"><span data-stu-id="2fdfc-136">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

