---
title: 'Lync Server 2013: Zertifikatanforderungen für die Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="8fbf7-102">Zertifikatanforderungen für die Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fbf7-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fbf7-103">_**Letztes Änderungsdatum des Themas:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="8fbf7-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="8fbf7-104">Wenn Sie das Mobilitätsfeature bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie bestimmte Einträge für alternative Namen in Zertifikate einbeziehen, um sichere Verbindungen von den mobilen Clients zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8fbf7-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="8fbf7-105">Sie müssen die Einträge für den alternativen Antragstellernamen für die automatische Ermittlung für die folgenden Zertifikate einbeziehen:</span><span class="sxs-lookup"><span data-stu-id="8fbf7-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="8fbf7-106">Directorpool</span><span class="sxs-lookup"><span data-stu-id="8fbf7-106">Director pool</span></span>

  - <span data-ttu-id="8fbf7-107">Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="8fbf7-107">Front End pool</span></span>

  - <span data-ttu-id="8fbf7-108">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="8fbf7-108">Reverse proxy</span></span>

<span data-ttu-id="8fbf7-109">In diesem Abschnitt werden die Einträge für Alternativen Betreff-Namen beschrieben, die für Ihre Zertifikate für die automatische Erkennung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8fbf7-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fbf7-110">Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Vorgang, aber das Hinzufügen von mehreren alternativen Subjektnamen Einträgen zu öffentlichen Zertifikaten, die vom Reverse-Proxy verwendet werden, kann kostspielig sein.</span><span class="sxs-lookup"><span data-stu-id="8fbf7-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="8fbf7-111">Wenn Sie über zahlreiche SIP-Domänen verfügen, die das Hinzufügen von alternativen Subjektnamen sehr teuer machen, können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS (die Standardkonfiguration) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fbf7-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="8fbf7-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-technical-requirements-for-mobility.md">Technische Voraussetzungen für Mobilität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8fbf7-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="8fbf7-113">Anforderungen des Director-Pool Zertifikats</span><span class="sxs-lookup"><span data-stu-id="8fbf7-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fbf7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbf7-114">Description</span></span></th>
<th><span data-ttu-id="8fbf7-115">Eintrag für den alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="8fbf7-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fbf7-116">URL des internen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="8fbf7-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8fbf7-117">San = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fbf7-118">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="8fbf7-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8fbf7-119">San = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8fbf7-120">Sie können auch San = \* verwenden. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="8fbf7-121">Anforderungen für das Front-End-Pool Zertifikat</span><span class="sxs-lookup"><span data-stu-id="8fbf7-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fbf7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbf7-122">Description</span></span></th>
<th><span data-ttu-id="8fbf7-123">Eintrag für den alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="8fbf7-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fbf7-124">URL des internen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="8fbf7-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8fbf7-125">San = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fbf7-126">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="8fbf7-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8fbf7-127">San = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8fbf7-128">Sie können auch San = \* verwenden. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="8fbf7-129">Zertifikatanforderungen für Reverse Proxy (öffentliche Zertifizierungsstelle)</span><span class="sxs-lookup"><span data-stu-id="8fbf7-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fbf7-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbf7-130">Description</span></span></th>
<th><span data-ttu-id="8fbf7-131">Eintrag für den alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="8fbf7-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fbf7-132">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="8fbf7-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8fbf7-133">San = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8fbf7-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8fbf7-134">Sie weisen dieses San dem Zertifikat zu, das dem SSL-Listener auf dem Reverse-Proxy zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8fbf7-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8fbf7-135">Ihr Reverse Proxy-Listener weist Alternative Namen für die externen Webdienste-URLs auf (Beispiel: San = lyncwebextpool01. contoso. com und dirwebexternal.contoso.com, wenn Sie den optionalen Director bereitgestellt haben).</span><span class="sxs-lookup"><span data-stu-id="8fbf7-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

