---
title: 'Lync Server 2013: Zertifikatanforderungen für die Mobilität'
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
ms.openlocfilehash: 5c3bf95f87fa663331f05861f91cd7f7f19a2728
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="f1e07-102">Zertifikatanforderungen für die Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e07-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1e07-103">_**Letztes Änderungsstand des Themas:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="f1e07-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="f1e07-104">Wenn Sie das Mobilitätsfeature bereitstellen und die automatische Ermittlung für mobile Clients unterstützten, müssen Sie für Zertifikate bestimmte Einträge für alternative Antragstellernamen einfügen, um sichere Verbindungen von den mobilen Clients aus zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f1e07-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="f1e07-105">Zur Unterstützung der automatischen Ermittlung müssen Sie für folgende Zertifikate Einträge für alternative Antragstellernamen einfügen:</span><span class="sxs-lookup"><span data-stu-id="f1e07-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="f1e07-106">Directorpool</span><span class="sxs-lookup"><span data-stu-id="f1e07-106">Director pool</span></span>

  - <span data-ttu-id="f1e07-107">Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="f1e07-107">Front End pool</span></span>

  - <span data-ttu-id="f1e07-108">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="f1e07-108">Reverse proxy</span></span>

<span data-ttu-id="f1e07-109">In diesem Abschnitt werden die Einträge für alternative Antragstellernamen beschrieben, die zur Unterstützung der automatischen Ermittlung für Zertifikate erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f1e07-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1e07-110">Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist normalerweise ein einfacher Vorgang, aber das Hinzufügen von Einträgen für mehrere alternative Antragstellernamen zu öffentlichen Zertifikaten, die vom Reverseproxy verwendet werden, kann kostspielig sein.</span><span class="sxs-lookup"><span data-stu-id="f1e07-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="f1e07-111">Wenn Sie über zahlreiche SIP-Domänen verfügen und das Hinzufügen von alternativen Antragstellernamen sehr kostspielig ist, können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Standardkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="f1e07-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="f1e07-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1e07-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="f1e07-113">Directorpool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="f1e07-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1e07-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1e07-114">Description</span></span></th>
<th><span data-ttu-id="f1e07-115">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="f1e07-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e07-116">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="f1e07-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="f1e07-117">San = "lyncdiscoverinternal". &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e07-118">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="f1e07-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="f1e07-119">San = lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f1e07-120">Alternativ können Sie San = \* verwenden. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="f1e07-121">Front-End-Pool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="f1e07-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1e07-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1e07-122">Description</span></span></th>
<th><span data-ttu-id="f1e07-123">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="f1e07-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e07-124">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="f1e07-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="f1e07-125">San = "lyncdiscoverinternal". &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e07-126">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="f1e07-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="f1e07-127">San = lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f1e07-128">Alternativ können Sie San = \* verwenden. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="f1e07-129">Reverseproxy-Zertifikatanforderungen (öffentliche ZS)</span><span class="sxs-lookup"><span data-stu-id="f1e07-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1e07-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1e07-130">Description</span></span></th>
<th><span data-ttu-id="f1e07-131">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="f1e07-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e07-132">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="f1e07-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="f1e07-133">San = lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="f1e07-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f1e07-134">Sie weisen dieses SAN dem Zertifikat zu, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f1e07-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f1e07-135">Ihr Reverse Proxy Listener weist alternative Antragstellernamen für Ihre externen Webdienste-URLs auf (beispielsweise "San = lyncwebextpool01. contoso. com" und "dirwebexternal.contoso.com", wenn Sie den optionalen Director bereitgestellt haben).</span><span class="sxs-lookup"><span data-stu-id="f1e07-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

